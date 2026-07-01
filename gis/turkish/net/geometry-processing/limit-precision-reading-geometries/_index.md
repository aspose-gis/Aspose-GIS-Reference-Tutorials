---
date: 2026-04-03
description: Aspose.GIS for .NET kullanarak vektör katmanı oluşturmayı ve geometrileri
  okurken hassasiyeti sınırlamayı öğrenin. Optimum coğrafi veri işleme için adım adım
  rehber.
keywords:
- create vector layer
- reduce shapefile size
- set precision model
linktitle: Geometrileri Okurken Hassasiyeti Sınırla
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile Vektör Katmanı Oluşturun, Hassasiyeti Sınırlayın
url: /tr/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektör Katmanı Oluşturma, Aspose.GIS for .NET ile Hassasiyeti Sınırlama

## Giriş
Coğrafi veriyle çalışırken, genellikle **create vector layer** nesneleri oluşturmanız ve koordinat detayının kaç ondalık basamağa ihtiyaç duyduğunuza karar vermeniz gerekir. Hassasiyeti sınırlamak yalnızca işleme hızını artırmakla kalmaz, aynı zamanda **reduce shapefile size** da sağlayarak depolama ve aktarımı daha verimli hâle getirir. Bu öğreticide bir vektör katmanı oluşturmayı, basit bir nokta geometrisi yazmayı ve ardından hem tam hem de yuvarlatılmış hassasiyet modellerini kullanarak geri okumayı adım adım göstereceğiz. Sonunda, uygulamanızın doğruluk gereksinimlerine uygun **set precision model** seçeneklerini anlayacaksınız.

## Hızlı Yanıtlar
- **“limit precision” ne anlama gelir?** Koordinat değerlerini tanımlı bir ondalık basamak sayısına yuvarlar.  
- **Neden önce bir vektör katmanı oluşturmalıyım?** Vektör katmanı, noktalar, çizgiler ve çokgenler gibi geometrileri depolayan kapsayıcıdır.  
- **Hangi hassasiyet modelleri mevcuttur?** `PrecisionModel.Exact` (yuvarlama yok) ve `PrecisionModel.Rounding(n)` (*n* ondalık basamağa yuvarlar).  
- **Bunu denemek için bir lisansa ihtiyacım var mı?** Yayınlar sayfasından ücretsiz bir deneme sürümü mevcuttur.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core ve .NET 5/6+.

## Neden hassasiyeti sınırlamalı ve bu nasıl yardımcı olur?
- **Performans artışı** – Daha az basamak, ayrıştırılacak ve serileştirilecek daha az veri demektir.  
- **Daha küçük dosyalar** – Koordinatları yuvarlamak, özellikle büyük veri setlerinde shapefile’ı belirgin şekilde küçültebilir.  
- **Yeterli doğruluk** – Birçok GIS analizi sub‑milimetre hassasiyet gerektirmez, bu yüzden 2‑3 ondalığa yuvarlamak genellikle yeterlidir.

## Önkoşullar
Bu yolculuğa başlamadan önce, aşağıdaki önkoşulların yerine getirildiğinden emin olun:

1. **Kurulum** – Aspose.GIS for .NET kütüphanesinin geliştirme ortamınıza kurulmuş olması gerekir. Eğer kurulu değilse, [sürüm sayfası](https://releases.aspose.com/gis/net/) adresinden indirebilirsiniz.
2. **.NET'e aşinalık** – Sağlanan kod örneklerini anlamak ve uygulamak için C# ve .NET çerçevesi hakkında temel bilgi gereklidir.
3. **Geliştirme Ortamı** – Visual Studio gibi çalışan bir .NET geliştirme ortamı gereklidir.
4. **Belge Dizini** – İşlem sırasında oluşturulan shapefile’ı depolayıp erişebileceğiniz bir dizin oluşturun.

## Ad Alanlarını İçe Aktarma
Geometrileri okurken hassasiyeti sınırlama işlevini uygulamaya başlamadan önce, gerekli ad alanlarını içe aktardığımızdan emin olalım:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Vektör Katmanı Nasıl Oluşturulur
İlk adım, geometrimizi tutacak **create vector layer** oluşturmaktır. Bu katman, daha sonra farklı hassasiyet ayarlarıyla yeniden açabilmemiz için bir Shapefile olarak kaydedilecektir.
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Hassasiyet Seçeneklerini Ayarlama
Sonraki adımda, geometrileri okuma seçeneklerini tanımlamamız, istenen hassasiyet modelini belirtmemiz gerekir. Tam hassasiyetle başlayabiliriz:
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Tam Hassasiyetle Geometrileri Okuma
Şimdi, belirtilen seçeneklerle vektör katmanını açarak geometrileri tam hassasiyetle okuyalım:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Hassasiyeti Kesme
Belirli bir ondalık basamak sayısına hassasiyeti kesmek istiyorsak, hassasiyet modelini buna göre ayarlayabiliriz:
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Farklı Senaryolar İçin Hassasiyet Modeli Nasıl Ayarlanır
`Exact` ile `Rounding` ne zaman kullanılmalı merak edebilirsiniz. İşte iki yaygın senaryo:

| Senaryo | Önerilen Model | Sebep |
|----------|-------------------|--------|
| Yüksek hassasiyetli bilimsel analiz | `PrecisionModel.Exact` | Koordinat detayının kaybı yok |
| Web haritalama döşemeleri veya mobil uygulamalar | `PrecisionModel.Rounding(2)` | Dosya boyutunu azaltır ve render süresini hızlandırır |

Doğru modeli seçmek, doğruluğu performansla dengeleyen **set precision model** karar verme sürecinin bir parçasıdır.

## Yaygın Sorunlar ve Çözümler
- **Beklenmeyen koordinat değerleri** – Katmanı açmadan önce `options.XYPrecisionModel`'i *ayarlandığından* emin olun. Açtıktan sonra değiştirmek etkisizdir.  
- **Dosya bulunamadı** – `path` değişkeninin geçerli bir dizine işaret ettiğini ve Shapefile'ın önceki adımda başarıyla oluşturulduğunu doğrulayın.  
- **Yanlış geometri tipi** – Örnek bir `Point` kullanıyor. Diğer geometri tipleri (ör. `LineString`) için dönüşüm gerçek tipe uygun olmalıdır.  

## Shapefile Boyutunu Küçültmek İçin İpuçları
- İhtiyacınız olan doğruluğu karşılayan en az ondalık sayısı ile `PrecisionModel.Rounding` kullanın.  
- Katmanı yazmadan önce gereksiz öznitelik alanlarını kaldırın.  
- Eğer aktarmanız gerekiyorsa, oluşan `.shp`, `.shx` ve `.dbf` dosyalarını standart ZIP araçlarıyla sıkıştırın.

## Sonuç
Sonuç olarak, geometrileri okurken hassasiyeti yönetmek, coğrafi veri işleme açısından kritik bir unsurdur. Aspose.GIS for .NET, bunu verimli bir şekilde gerçekleştirmek için güçlü işlevler sunar. Yukarıdaki adımları izleyerek **create vector layer** nesnelerini sorunsuz bir şekilde oluşturabilir, **set precision model** ayarlayabilir ve gerektiğinde **reduce shapefile size** yaparak uygulamalarınızda optimal veri işleme sağlayabilirsiniz.

## SSS
### Aspose.GIS for .NET'i .NET Core veya .NET Standard gibi diğer .NET çerçeveleriyle kullanabilir miyim?
Evet, Aspose.GIS for .NET, .NET Core ve .NET Standard dahil olmak üzere çeşitli .NET çerçeveleriyle uyumludur.

### Aspose.GIS for .NET için deneme sürümü mevcut mu?
Evet, ücretsiz bir deneme sürümünü [sürüm sayfası](https://releases.aspose.com/) üzerinden edinebilirsiniz.

### Aspose.GIS for .NET için kapsamlı belgeleri nereden bulabilirim?
Detaylı bilgi ve örnekler için [belgeler](https://reference.aspose.com/gis/net/) sayfasına bakabilirsiniz.

### Aspose.GIS for .NET için geçici lisansları nasıl alabilirim?
Geçici lisanslar, Aspose.GIS için [satın alma sayfası](https://purchase.aspose.com/temporary-license/) üzerinden temin edilebilir.

### Aspose.GIS for .NET için yardım veya destek nereden alabilirim?
Herhangi bir soru, tartışma veya destek ihtiyacı için Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) sayfasını ziyaret edebilirsiniz.

## Sıkça Sorulan Sorular
**S: Hassasiyeti sınırlamak orijinal shapefile'ı etkiler mi?**  
**C:** Hayır. Hassasiyet yalnızca geometri okunurken uygulanır; kaynak dosya değişmeden kalır.

**S: X ve Y koordinatları için farklı bir hassasiyet modeli kullanabilir miyim?**  
**C:** Aspose.GIS şu anda her iki eksene aynı `XYPrecisionModel`'i uygular.

**S: Özel bir yuvarlama işlevi ayarlamak mümkün mü?**  
**C:** API yalnızca yerleşik `PrecisionModel.Rounding(int)` metodunu destekler. Özel mantık için, okuduktan sonra koordinatları işlemek gerekir.

---

**Son Güncelleme:** 2026-04-03  
**Test Edilen:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
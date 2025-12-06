---
date: 2025-12-06
description: Aspose.GIS for .NET kullanarak C#'de LineString nasıl oluşturulur, LineString'e
  nokta eklenir ve bir geometrinin diğerini kapsayıp kapsamadığı nasıl kontrol edilir,
  öğrenin.
language: tr
linktitle: Create LineString C# – Check Geometry Covers Another
second_title: Aspose.GIS .NET API
title: LineString Oluşturma C# – Geometrinin Başkasını Kapsadığını Kontrol Et
url: /net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Geometri Başkasını Kapsıyor Kontrol Et

## Giriş
Aspose.GIS for .NET, geliştiricilere .NET uygulamaları içinde coğrafi verilerle verimli bir şekilde çalışmak için araçlar sunan güçlü bir kütüphanedir. İster bir haritalama uygulaması oluşturuyor, ister mekânsal verileri analiz ediyor ya da coğrafi özellikleri yazılımınıza entegre ediyor olun, Aspose.GIS geliştirme sürecinizi kolaylaştırmak için kapsamlı bir işlevsellik seti sunar. Bu öğreticide **C# içinde LineString nasıl oluşturulur**, çizgiye nokta ekleme ve `Covers` ile `CoveredBy` metodlarını kullanarak **noktanın çizgi üzerindeki kontrolü** nasıl yapılır öğreneceksiniz.

## Hızlı Yanıtlar
- **“C# içinde LineString oluşturmak” ne anlama geliyor?** `LineString` geometri nesnesini örnekleyip koordinat noktalarıyla doldurmak anlamına gelir.  
- **Bir noktanın çizgi üzerinde olup olmadığını kontrol eden yöntem hangisidir?** `LineString` üzerinde `Covers` metodunu ya da `Point` üzerinde `CoveredBy` metodunu kullanın.  
- **Örneği çalıştırmak için lisansa ihtiyacım var mı?** Değerlendirme için geçici bir lisans yeterlidir; üretim için tam lisans gereklidir.  
- **Bu .NET Core ile kullanılabilir mi?** Evet, Aspose.GIS .NET Framework ve .NET Core’u destekler.  
- **Bir LineString’e kaç nokta ekleyebilirim?** Katı bir limit yoktur; mekânsal analiziniz için ihtiyacınız kadar nokta ekleyebilirsiniz.

## **create LineString C#** Nedir?
`LineString`, düz çizgi segmentleriyle birbirine bağlanan sıralı bir nokta listesi içeren geometrik bir şekildir. C# içinde, `Aspose.Gis.Geometries` ad alanındaki `LineString` sınıfını örnekleyerek ve ardından `AddPoint` metodunu kullanarak **LineString’e nokta ekleyerek** oluşturursunuz.

## Neden Aspose.GIS'i bir noktanın çizgi üzerindeki kontrolü için kullanmalısınız?
- **Hassasiyet** – Kayan nokta hesaplamalarını ve mekânsal öngörüleri doğru bir şekilde işler.  
- **Çapraz platform** – .NET Framework, .NET Core ve .NET 5/6+ ile çalışır.  
- **Zengin API** – `Covers`, `CoveredBy`, `Intersects` vb. mekânsal ilişki metodlarını içeren tam bir paket sunar.  

## Önkoşullar
Aspose.GIS for .NET’i kullanmaya başlamadan önce aşağıdaki önkoşulları yerine getirdiğinizden emin olun:

### 1. Visual Studio'yu Kurun
Sisteminizde Visual Studio yüklü olduğundan emin olun. Aspose.GIS for .NET, Visual Studio ile sorunsuz bir şekilde bütünleşir ve sorunsuz bir geliştirme deneyimi sağlar.

### 2. Aspose.GIS for .NET'i Edinin
Aspose.GIS for .NET kütüphanesini [website](https://releases.aspose.com/gis/net/) adresinden indirin. Kütüphaneyi doğrudan indirebilir ya da NuGet gibi bir paket yöneticisi kullanarak projenize ekleyebilirsiniz.

### 3. .NET Framework'e Hakim Olma
Aspose.GIS for .NET’i etkili bir şekilde kullanabilmek için .NET framework ve C# programlama diline temel bir hakimiyet gereklidir.

### 4. Dokümantasyon ve Destek Erişimi
Aspose.GIS API’leri ve işlevleri hakkında ayrıntılı bilgi için [documentation](https://reference.aspose.com/gis/net/) adresine bakın. Herhangi bir sorunla karşılaşırsanız ya da sorularınız olursa, [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) üzerinden destek alabilirsiniz.

### 5. İsteğe Bağlı: Geçici Lisans
Aspose.GIS for .NET’i keşfediyorsanız, kütüphanenin özelliklerini değerlendirmek için [here](https://purchase.aspose.com/temporary-license/) adresinden geçici bir lisans alabilirsiniz.

## Ad Alanlarını İçe Aktarın
Aspose.GIS for .NET’i projenizde kullanmadan önce gerekli ad alanlarını içe aktarmanız gerekir:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Şimdi, Aspose.GIS for .NET kullanarak **bir geometrinin diğerini kapsayıp kapsamadığını kontrol etme** konusunu anlamak için örneği birma ayıralım.

## **create LineString C#** Nasıl Oluşturulur – Adım Adım Kılavuz

### Adım 1: LineString Nesnesi Oluşturun
```csharp
var line = new LineString();
```
Burada, iki‑boyutlu bir alanda birbirine bağlı çizgi segmentlerinden oluşan bir `LineString` nesnesi örnekliyoruz.

### Adım 2: **LineString'e Noktalar Ekle**
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
`AddPoint` metodunu kullanarak **LineString’e nokta ekliyoruz**. Bu örnekte iki nokta ekliyoruz: (0, 0) ve (1, 1), basit bir diyagonal çizgi segmenti oluşturuyor.

### Adım 3: Point Nesnesi Oluşturun
```csharp
var point = new Point(0, 0);
```
İki‑boyutlu bir alanda tek bir noktayı temsil eden bir `Point` nesnesi örnekliyoruz. Burada, (0, 0) koordinatlarında bir nokta oluşturuyoruz.

### Adım 4: **Noktanın Çizgi Üzerinde Kontrolü** – Çizgi noktayı kapsıyor mu?
```csharp
Console.WriteLine(line.Covers(point));    // True
```
`Covers` metodunu kullanarak çizginin noktayı kapsayıp kapsamadığını kontrol edin. Bu durumda, nokta (0, 0) tam olarak çizgi üzerinde bulunduğu için `True` döner.

### Adım 5: Ters İlişkiyi Doğrulayın – Nokta çizgi tarafından kapsanıyor mu?
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
Benzer şekilde, `CoveredBy` metodunu kullanarak noktanın çizgi tarafından kapsanıp kapsanmadığını kontrol edin. Nokta (0, 0) çizgi üzerinde olduğu için yine `True` döner.

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden Oluşur | Çözüm |
|-------|--------------|-------|
| `line.Covers(point)` returns `False` even though the point looks on the line | Nokta koordinatları, kayan‑nokta hassasiyeti nedeniyle tam olarak aynı değildir. | Koordinatlarda `Math.Round` kullanın veya `line.Distance(point) < epsilon` gibi tolerans‑bazlı bir kontrol uygulayın. |
| Missing `using Aspose.Gis.Geometries;` | Ad alanı içe aktarılmadığı için derleme hataları oluşur. | **Ad Alanlarını İçe Aktarın** bölümündeki import ifadesinin mevcut olduğundan emin olun. |
| License exception at runtime | Üretim ortamında geçerli bir lisans yüklenmemiştir. | `License license = new License(); license.SetLicense("Aspose.GIS.lic");` kodu ile geçici ya da tam lisans yükleyin. |

## Sıkça Sorulan Sorular

**Q: Aspose.GIS for .NET'i ticari projelerimde kullanabilir miyim?**  
A: Evet, uygun lisansı aldıktan sonra Aspose.GIS for .NET'i hem ticari hem de ticari olmayan projelerde kullanabilirsiniz.

**Q: Aspose.GIS for .NET .NET Core ile uyumlu mu?**  
A: Evet, Aspose.GIS for .NET hem .NET Framework hem de .NET Core ortamlarıyla uyumludur.

**Q: Aspose.GIS for .NET çeşitli GIS formatlarını destekliyor mu?**  
A: Evet, Aspose.GIS for .NET Shapefile, GeoJSON, KML ve daha birçok GIS formatını destekler.

**Q: Aspose.GIS for .NET'in geliştirilmesine katkıda bulunabilir miyim?**  
A: Aspose.GIS for .NET, Aspose tarafından geliştirilen tescilli bir kütüphanedir; dış katkılar kabul edilmez. Ancak, kütüphaneyi iyileştirmek için geri bildirim ve öneri sunabilirsiniz.

**Q: Aspose.GIS for .NET için güncellemeler ne sıklıkla yayınlanıyor?**  
A: Aspose.GIS for .NET için yeni özellikler, iyileştirmeler ve hata düzeltmeleri içeren güncellemeler düzenli olarak yayınlanır. En son sürümler için [website](https://releases.aspose.com/gis/net/) adresini kontrol edin.

## Sonuç
Sonuç olarak, Aspose.GIS for .NET .NET uygulamalarında coğrafi verilerle çalışmak için güçlü araçlar sunar. Yukarıda belirtilen adımları izleyerek **C# içinde LineString oluşturabilir**, **LineString’e nokta ekleyebilir** ve **noktanın çizgi üzerindeki kontrolünü** gerçekleştirerek bir geometrinin diğerini kapsayıp kapsamadığını belirleyebilirsiniz. Bu yetenek, yazılımınızın mekânsal analiz özelliklerini geliştirir ve daha ileri GIS işlemlerine kapı açar.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2025-12-06  
**Test Edilen:** Aspose.GIS for .NET (en son sürüm)  
**Yazar:** Aspose
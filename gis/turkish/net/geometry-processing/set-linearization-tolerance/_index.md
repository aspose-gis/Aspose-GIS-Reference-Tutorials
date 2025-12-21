---
date: 2025-12-21
description: Aspose.GIS for .NET kullanarak vektör katmanı oluşturmayı, lineerleştirme
  toleransını ayarlamayı ve katmana özellik eklemeyi öğrenin. GeoJSON dosyalarını
  dışa aktarmak için bu adım adım kılavuzu izleyin.
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET kullanarak Vektör Katmanı Oluşturma ve Lineerleştirme Toleransını
  Ayarlama
url: /tr/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET kullanarak Vektör Katmanı Oluşturma ve Lineerleştirme Toleransını Ayarlama

## Giriş
Eğer **create vector layer** dosyaları oluşturmanız, eğri hassasiyetini kontrol etmeniz ve sonucu bir GeoJSON belgesi olarak dışa aktarmanız gerekiyorsa, Aspose.GIS for .NET bunu oldukça basit hale getirir. Bu öğreticide GeoJSON seçeneklerini nasıl yapılandıracağınızı, lineerleştirme toleransını nasıl ayarlayacağınızı ve **add feature to layer** nesnelerini nasıl ekleyeceğinizi öğreneceksiniz — tüm bunları kodu temiz ve üretim‑hazır tutarak.

## Hızlı Yanıtlar
- **What does “create vector layer” mean?** Yeni bir GIS vektör veri kümesi (ör. bir GeoJSON dosyası) oluşturur ve bu küme geometrileri ve öznitelikleri depolayabilir.  
- **How to set tolerance?** `GeoJsonOptions` sınıfının `LinearizationTolerance` özelliğini kullanın.  
- **Can I export a GeoJSON file?** Evet—`Drivers.GeoJson` sürücüsüyle bir `VectorLayer` oluşturmanız yeterlidir.  
- **Do I need a license?** Geçerli bir Aspose.GIS lisansı tüm özelliklerin kilidini açar; geçici bir lisans değerlendirme için çalışır.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “create vector layer” nedir?
Bir vektör katmanı oluşturmak, nokta, çizgi ve çokgen gibi geometrik özellikleri tutabilen yeni bir GIS konteyneri (ör. bir GeoJSON dosyası) başlatmak anlamına gelir. Bu katman, oluşturduğunuz tüm geometrilerin ve eklediğiniz tüm özniteliklerin hedefi olur.

## GeoJSON seçeneklerini neden yapılandırmalıyız?
GeoJSON seçeneklerini yapılandırmak — özellikle **linearization tolerance** — eğri geometrilerin (ör. `CircularString`) uygulamanızın doğruluk gereksinimlerini karşılayacak bir hassasiyetle yaklaştırılmasını sağlar. Bu adım, daha sonra **export GeoJSON file** işlemiyle web haritalarında veya mekansal analizlerde kullanmak için kritik öneme sahiptir.

## Önkoşullar
1. **Visual Studio** yüklü (herhangi bir güncel sürüm).  
2. **Aspose.GIS license** (veya geçici bir değerlendirme anahtarı).  
3. **Aspose.GIS for .NET** kütüphanesi indirilmiş ve projenize referans verilmiş.  
4. **C#** hakkında temel bilgi.

## Ad Alanlarını İçe Aktarma
First, import the required namespaces so the compiler knows where to find the GIS classes:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım‑Adım Kılavuz

### Adım 1: GeoJSON Seçeneklerini Yapılandırma (tolerans nasıl ayarlanır)
`GeoJsonOptions` nesnesi oluşturacağız ve Aspose.GIS'e lineerleştirilmiş geometrinin orijinal eğriye ne kadar yakın olması gerektiğini söyleyeceğiz.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Adım 2: Çıktı Yolunu Tanımlama (GeoJSON nasıl dışa aktarılır)
Oluşturulan dosyanın nereye kaydedileceğini belirtin. Yer tutucuyu gerçek klasör yolunuzla değiştirin.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Adım 3: **Create Vector Layer** yapılandırılmış seçeneklerle
Şimdi `VectorLayer.Create` metodunu kullanarak gerçekten **create vector layer** yapıyoruz. `using` bloğu kaynakların doğru şekilde serbest bırakılmasını garanti eder.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Adım 4: Geometri Oluşturma (ör. bir circular string)
Burada örnek bir geometri oluşturuyoruz — bir `CircularString`. Bunu geçerli herhangi bir WKT ile değiştirebilirsiniz.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Adım 5: **Add Feature to Layer** ve kaydet
Son olarak bir özellik (feature) oluşturuyor, geometrisini atıyor ve katmana ekliyoruz. Bu, **add feature to layer** işleminin çekirdeğidir.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

`using` bloğu sona erdiğinde, katman `path` içinde tanımlanan dosyaya otomatik olarak yazılır ve size kullanıma hazır bir GeoJSON dosyası sağlar.

## Yaygın Sorunlar ve İpuçları
- **Incorrect path** – Dizinin var olduğundan ve yazma izinlerine sahip olduğunuzdan emin olun.  
- **Tolerance too low** – `LinearizationTolerance` değerini çok düşük bir değere ayarlamak dosya boyutunu dramatik şekilde artırabilir. Doğruluk ihtiyaçlarınıza göre ayarlayın.  
- **License errors** – Lisans uyarıları görürseniz, herhangi bir Aspose.GIS çağrısından önce lisans dosyasının doğru yüklendiğini doğrulayın.

## Sıkça Sorulan Sorular

**S: Aspose.GIS for .NET diğer .NET framework'leriyle uyumlu mu?**  
C: Evet, .NET Framework, .NET Core ve .NET 5/6/7 ile çalışır.

**S: Aspose.GIS'i ticari projelerde kullanabilir miyim?**  
C: Kesinlikle. Ticari bir lisans tüm değerlendirme kısıtlamalarını kaldırır.

**S: Aspose.GIS GeoJSON dışındaki diğer GIS formatlarını destekliyor mu?**  
C: Evet, Shapefile, KML, GML ve daha birçok formatı destekler.

**S: Deneme sürümü mevcut mu?**  
C: Aspose web sitesinden ücretsiz bir deneme sürümü indirebilirsiniz.

**S: Destek nereden alınabilir?**  
C: Aspose forumlarını veya kaynaklar bölümündeki destek bağlantısını kullanın.

## Sonuç
Bu adımları izleyerek artık **create vector layer** nasıl yapılacağını, lineerleştirme toleransını nasıl yapılandıracağınızı ve sorunsuz bir **export GeoJSON file** oluşturmak için **add feature to layer** işlemini nasıl gerçekleştireceğinizi biliyorsunuz. Ek geometri tiplerini ve öznitelik yönetimini keşfederek Aspose.GIS'i .NET GIS projelerinizde tam anlamıyla kullanın.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2025-12-21  
**Test Edilen Versiyon:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose
---
date: 2026-01-15
description: Aspose.GIS for .NET'i keşfedin ve mekânsal referans sistemiyle vektör
  katmanı oluşturun. SRS'yi nasıl ayarlayacağınızı, katman oluşturmayı ve GIS verilerini
  yönetmeyi öğrenin. Şimdi indirin!
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: SRS ile Vektör Katmanı Oluştur
url: /tr/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektör Katmanı Oluşturma ve SRS

## Giriş
Aspose.GIS for .NET, geliştiricilerin **create vector layer** nesnelerini oluşturmasını ve coğrafi bilgi sistemi (GIS) verileriyle .NET uygulamalarında sorunsuz çalışmasını sağlayan güçlü bir kütüphanedir. Bu öğreticide, bir mekânsal referans sistemi (SRS) ile vektör katmanı nasıl oluşturulur, mekânsal referans ayarlamanın nedenleri ve bunun gerçek‑dünya projelerine getirdiği faydalar ele alınacaktır. Bu rehberin sonunda, .NET çözümlerinizde GIS yeteneklerini güvenle entegre edebileceksiniz.

## Hızlı Yanıtlar
- **Bu öğreticinin temel amacı nedir?** Aspose.GIS for .NET kullanarak belirli bir SRS ile vektör katmanı oluşturmayı göstermek.  
- **Örnekte hangi projeksiyon kullanılıyor?** World Mercator (EPSG:3395).  
- **Kodu çalıştırmak için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme yeterlidir; üretim için ticari lisans gereklidir.  
- **Aynı yaklaşımı diğer GIS formatlarıyla kullanabilir miyim?** Evet, aynı SRS işleme Shapefile, GeoJSON, KML vb. formatlar için geçerlidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Vektör katmanı nedir ve neden mekânsal referansı ayarlamalısınız?
**Vector layer** geometrik özellikleri (nokta, çizgi, çokgen) ve bunlara ait öznitelik verilerini birlikte depolar. **Spatial reference** (SRS) atamak, GIS yazılımının bu koordinatları Dünya yüzeyinde nasıl yorumlayacağını belirtir. Doğru SRS ayarı, ölçümlerin doğruluğunu, diğer katmanlarla doğru örtüşmeyi ve güvenilir harita görselleştirmelerini sağlar.

## Önkoşullar
Başlamadan önce şunlara sahip olun:

- C# ve .NET geliştirme temelleri.  
- Aspose.GIS for .NET kütüphanesi yüklü. **[burada](https://releases.aspose.com/gis/net/)** indirebilirsiniz.  
- Bir geliştirme ortamı (Visual Studio, VS Code veya herhangi bir C# IDE).  

## Namespace'leri İçe Aktarma
C# dosyanızın en üst kısmında gerekli ad alanlarını içe aktardığınızdan emin olun:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Mekânsal Referansı (SRS) Ayarlama – Adım 1
World Mercator projeksiyonunu örnek alarak **projected spatial reference system** oluşturalım. Bu, bir katman için **how to set srs** nasıl yapılır gösterir.

```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```

## Katman Oluşturma – Adım 2
Şimdi **create a vector layer** (bir Shapefile) oluşturup, az önce tanımladığımız SRS'yi kullanan özellikler ekleyeceğiz. Bu bölüm, Aspose.GIS ile **how to create layer** sorusuna yanıt verir.

```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // This will throw an exception as the geometry has a different SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```

> **Pro ipucu:** Geometrinin `SpatialReferenceSystem` değerinin, katmanın SRS'siyle eşleştiğinden emin olun. Eşleşmezse `GisException` hatası alınır, yukarıda gösterildiği gibi.

## Mekânsal Referans Sistemini Doğrulama – Adım 3
Son olarak katmanı açın ve SRS'nin doğru uygulanıp uygulanmadığını doğrulayın.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

`IsEquivalent` çağrısı `true` dönerse, istediğiniz mekânsal referansla **create vector layer** işlemini başarıyla tamamlamış olursunuz.

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden Oluşur | Çözüm |
|-------|----------------|-----|
| `GisException` özelliği eklerken | Geometri katmandan farklı bir SRS kullanıyor | `feature.Geometry.SpatialReferenceSystem`'ı eklemeden önce katmanın SRS'sine ayarlayın |
| Katman GIS yazılımında boş görünüyor | Shapefile uygun bir `.prj` dosyası olmadan oluşturulmuş | Katman oluşturulurken `projectedSrs` nesnesinin geçirildiğinden emin olun |
| Beklenmeyen koordinat değerleri | Yanlış projeksiyon parametreleri (ör. merkez meridyen) | `AddProjectionParameter`'a geçirilen parametreleri tekrar kontrol edin |

## SSS
### Aspose.GIS tüm GIS dosya formatlarıyla uyumlu mu?
Aspose.GIS Shapefile, GeoJSON, KML ve daha fazlası dahil olmak üzere çeşitli GIS formatlarını destekler. Tam liste için **[belgelendirme](https://reference.aspose.com/gis/net/)** sayfasına bakın.

### Aspose.GIS'i bir web uygulamasında kullanabilir miyim?
Kesinlikle! Aspose.GIS for .NET, web uygulamaları, masaüstü uygulamaları ve hatta mobil uygulamalarda kullanılabilecek kadar esnektir.

### Aspose.GIS için desteği nereden alabilirim?
Herhangi bir sorunuz veya karşılaştığınız bir sorun için **[Aspose.GIS forumu](https://forum.aspose.com/c/gis/33)**'nda yardımcı bir topluluk bulabilirsiniz.

### Ücretsiz deneme mevcut mu?
Evet, Aspose.GIS özelliklerini **[burada](https://releases.aspose.com/)** ücretsiz deneme sürümüyle keşfedebilirsiniz.

### Aspose.GIS için lisans nasıl satın alınır?
Lisans satın almak için **[satın alma sayfası](https://purchase.aspose.com/buy)**'ı ziyaret edin.

## Sıkça Sorulan Sorular (Ek)

**S: Farklı bir SRS ile bir geometri eklemeye çalışırsam ne olur?**  
C: Aspose.GIS bir `GisException` fırlatır. Ya geometrinin yeniden projeksiyonunu yapmalı ya da katmanın SRS'siyle aynı olduğundan emin olmalısınız.

**S: Mevcut bir katmanın SRS'sini değiştirebilir miyim?**  
C: Evet, istediğiniz SRS ile yeni bir katman oluşturup, özellikleri gerektiğinde yeniden projekte ederek kopyalayabilirsiniz.

**S: 3D koordinatlarla çalışmak mümkün mü?**  
C: Aspose.GIS Z‑koordinatlarını destekler; sadece Z değeri kabul eden geometri yapıcılarını kullanmanız yeterlidir.

**S: Kütüphane datum dönüşümlerini otomatik olarak yönetiyor mu?**  
C: Geometrileri `Geometry.Transform` ile yeniden projekte ettiğinizde, Aspose.GIS gerekli datum kaymasını otomatik olarak gerçekleştirir.

**S: .NET sürümleri resmi olarak hangi sürümler test edilmiştir?**  
C: Kütüphane .NET Framework 4.5+, .NET Core 3.1+, ve .NET 5/6/7 ile test edilmiştir.

## Sonuç
Artık Aspose.GIS for .NET kullanarak özel bir mekânsal referans sistemiyle **create vector layer** oluşturmayı öğrendiniz. Doğru SRS'yi ayarlayarak, geometrileri tutarlı bir şekilde işleyerek ve katmanın meta verilerini doğrulayarak, herhangi bir standart GIS yazılımıyla sorunsuz bir şekilde çalışabilen sağlam GIS‑entegre uygulamalar geliştirebilirsiniz.

---

**Son Güncelleme:** 2026-01-15  
**Test Edilen:** Aspose.GIS 24.11 for .NET (yazım anındaki en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
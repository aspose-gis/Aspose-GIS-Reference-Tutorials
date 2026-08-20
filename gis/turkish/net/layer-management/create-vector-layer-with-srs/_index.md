---
date: 2026-06-30
description: Aspose.GIS for .NET kullanarak bir spatial reference system ile vector
  layer oluşturmayı öğrenin. Step‑by‑step kılavuz, code‑free açıklamalar ve FAQs.
keywords:
- how to create vector layer
- Aspose.GIS spatial reference
- .NET GIS tutorial
linktitle: Aspose.GIS for .NET kullanarak SRS ile Vector Layer Oluşturma
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer with a spatial reference system using
    Aspose.GIS for .NET. Step‑by‑step guide, code‑free explanations, and FAQs.
  headline: How to Create Vector Layer with SRS using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS throws a `GisException`. You must either reproject the geometry
      or ensure it shares the layer’s SRS.
    question: What happens if I try to add a geometry with a different SRS?
  - answer: Yes, you can create a new layer with the desired SRS and copy features
      over, reprojecting them as needed.
    question: Can I change the SRS of an existing layer?
  - answer: Aspose.GIS supports Z‑coordinates; just use geometry constructors that
      accept a Z value.
    question: Is it possible to work with 3D coordinates?
  - answer: When you reproject geometries using `Geometry.Transform`, Aspose.GIS performs
      the necessary datum shift.
    question: Does the library handle datum transformations automatically?
  - answer: The library is tested with .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7.
    question: Which .NET versions are officially tested?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET kullanarak SRS ile Vector Layer Oluşturma
url: /tr/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET kullanarak SRS ile Vektör Katman Oluşturma

## Giriş
Bu öğreticide, Aspose.GIS for .NET ile mekansal referans sistemi (SRS) içeren **vektör katman** nesnelerinin nasıl oluşturulacağını keşfedeceksiniz. Bir SRS atamanın ardındaki mantığı adım adım gösterecek, bunu ayarlamak için kesin adımları sunacak ve doğru ölçümler, diğer GIS verileriyle sorunsuz örtüşme gibi gerçek dünya avantajlarını açıklayacağız. Sonunda, herhangi bir .NET uygulamasına sağlam GIS işlevselliği eklemeye hazır olacaksınız.

## Hızlı Yanıtlar
- **Bu öğreticinin temel amacı nedir?** Aspose.GIS for .NET kullanarak belirli bir SRS ile vektör katman oluşturmayı göstermek.  
- **Örnekte hangi projeksiyon kullanılıyor?** Dünya Mercator (EPSG:3395).  
- **Kodu çalıştırmak için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Diğer GIS formatlarıyla aynı yaklaşımı kullanabilir miyim?** Evet, aynı SRS işleme Shapefile, GeoJSON, KML vb. için geçerlidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Vektör katman nedir ve neden mekansal referans ayarlanmalı?
**Vektör katman**, geometrik özellikleri (nokta, çizgi, çokgen) ve bunlara ait öznitelik verilerini bir arada saklar. **Mekansal referans sistemi** atamak, GIS yazılımının bu koordinatları Dünya yüzeyine nasıl haritalayacağını belirler; bu da doğru mesafe hesaplamaları, katman hizalaması ve güvenilir harita render'ı sağlar.

## Neden bir mekansal referans sistemi ayarlamalıyız?
Tanımlı bir SRS kullanmak, farklı kaynaklardan gelen katmanları birleştirirken koordinat dönüşüm hatalarını %95'e kadar azaltır. Aspose.GIS, Shapefile, GeoJSON, KML ve GML dahil **20+** giriş ve çıkış formatını destekler; çok sayfalı veri setlerini tüm dosyayı belleğe yüklemeden işler.

## Önkoşullar
- C# ve .NET geliştirme hakkında temel bilgi.  
- Aspose.GIS for .NET kütüphanesi yüklü. **[buradan](https://releases.aspose.com/gis/net/)** indirebilirsiniz.  
- Bir geliştirme ortamı (Visual Studio, VS Code veya herhangi bir C# IDE).  

## Ad Alanlarını İçe Aktarın
Gerekli ad alanlarının C# dosyanızın en üstünde içe aktarıldığından emin olun:

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

## Mekansal referans (SRS) nasıl ayarlanır – Adım 1
Projeksiyonlu SRS'nizi iki satırda yükleyin: bir `ProjectedSpatialReferenceSystem` örneği oluşturun, Mercator projeksiyon parametrelerini yapılandırın ve katmana eklemeye hazır olun.

`ProjectedSpatialReferenceSystem` bir projeksiyonlu koordinat referans sistemini tanımlayan bir sınıftır.  
`ProjectedSpatialReferenceSystemParameters` merkezi meridyen ve ölçek faktörü gibi projeksiyon SRS'sini yapılandırmak için gereken parametreleri tutar.

Dünya Mercator projeksiyonunu örnek olarak kullanarak bir **projeksiyonlu mekansal referans sistemi** oluşturalım. Bu, bir katman için **srs nasıl ayarlanır** gösterir.

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

## Katman nasıl oluşturulur – Adım 2
Bir Shapefile katmanı örnekleyin, önceden tanımlanan `projectedSrs`'i geçirin ve ardından `SpatialReferenceSystem`'i katmanın SRS'siyle eşleşen geometrileri ekleyin.

`Layer` (ör. bir Shapefile), tek bir GIS dosyasında saklanan özellik koleksiyonunu temsil eder.  
Şimdi **vektör katman** (bir Shapefile) oluşturup, az önce tanımladığımız SRS'yi kullanan özellikleri ekleyeceğiz. Bu bölüm, Aspose.GIS ile **katman nasıl oluşturulur** sorusuna yanıt verir.

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

## Mekansal Referans Sistemini Doğrulama – Adım 3
Yeni oluşturulan katmanı açın, `SpatialReferenceSystem`'ini alın ve `IsEquivalent` ile orijinal `projectedSrs` ile karşılaştırın. `true` sonucu, SRS'nin doğru şekilde uygulandığını onaylar.

`IsEquivalent` iki mekansal referans sisteminin aynı koordinat sistemini temsil edip etmediğini kontrol eder.  
Son olarak, katmanı açın ve SRS'nin doğru şekilde uygulandığını doğrulayın.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

`IsEquivalent` çağrısı `true` dönerse, istediğiniz mekansal referansla **vektör katman oluşturma** işlemini başarıyla tamamlamış olursunuz.

## Yaygın Sorunlar ve Çözümler
`GisException`, Aspose.GIS'in eşleşmeyen SRS gibi hatalar için attığı istisna türüdür.  

| Sorun | Neden Oluşur | Çözüm |
|-------|--------------|------|
| `GisException` özellik eklerken | Geometri, katmandan farklı bir SRS kullanıyor | `feature.Geometry.SpatialReferenceSystem`'ı eklemeden önce katmanın SRS'sine ayarlayın |
| Katman GIS yazılımında boş görünüyor | Shapefile, uygun bir `.prj` dosyası olmadan oluşturuldu | Katman oluşturulurken `projectedSrs` nesnesinin geçirildiğinden emin olun |
| Beklenmeyen koordinat değerleri | Yanlış projeksiyon parametreleri (ör. merkez meridyen) | `AddProjectionParameter`'a geçirilen parametreleri tekrar kontrol edin |

## SSS
### Aspose.GIS tüm GIS dosya formatlarıyla uyumlu mu?
Aspose.GIS **20+** GIS formatını destekler; Shapefile, GeoJSON, KML, GML ve daha fazlası dahildir. Tam liste için **[belgelere](https://reference.aspose.com/gis/net/)** bakın.

### Aspose.GIS'i bir web uygulamasında kullanabilir miyim?
Kesinlikle! Aspose.GIS for .NET, ASP.NET, ASP.NET Core ve herhangi bir sunucu‑tarafı .NET ortamında çalışır.

### Aspose.GIS için destek nereden alınabilir?
Herhangi bir sorunuz veya karşılaştığınız bir sorun için **[Aspose.GIS forumu](https://forum.aspose.com/c/gis/33)**'nda yardımcı bir topluluk bulabilirsiniz.

### Ücretsiz deneme mevcut mu?
Evet, Aspose.GIS özelliklerini **[buradan](https://releases.aspose.com/)** ücretsiz deneme sürümüyle keşfedebilirsiniz.

### Aspose.GIS için lisans nasıl satın alınır?
Lisans satın almak için **[satın alma sayfasını](https://purchase.aspose.com/buy)** ziyaret edin.

## Sıkça Sorulan Sorular (Ek)

**Q: Farklı bir SRS ile geometri eklemeye çalışırsam ne olur?**  
A: Aspose.GIS bir `GisException` fırlatır. Geometriyi yeniden projekte etmeniz ya da katmanın SRS'siyle aynı olmasını sağlamanız gerekir.

**Q: Mevcut bir katmanın SRS'sini değiştirebilir miyim?**  
A: Evet, istenen SRS ile yeni bir katman oluşturup, özellikleri gerektiğinde yeniden projekte ederek kopyalayabilirsiniz.

**Q: 3D koordinatlarla çalışmak mümkün mü?**  
A: Aspose.GIS Z‑koordinatlarını destekler; Z değeri kabul eden geometri yapıcılarını kullanmanız yeterlidir.

**Q: Kütüphane datum dönüşümlerini otomatik olarak yönetiyor mu?**  
A: Geometrileri `Geometry.Transform` ile yeniden projekte ettiğinizde, Aspose.GIS gerekli datum kaymasını otomatik olarak gerçekleştirir.

**Q: Hangi .NET sürümleri resmi olarak test edilmiştir?**  
A: Kütüphane .NET Framework 4.5+, .NET Core 3.1+, ve .NET 5/6/7 ile test edilmiştir.

## Sonuç
Artık Aspose.GIS for .NET kullanarak özel bir mekansal referans sistemiyle **vektör katman oluşturma** konusunda bilgi sahibisiniz. Doğru SRS'yi ayarlayarak, geometrileri tutarlı bir şekilde işleyerek ve katmanın meta verilerini doğrulayarak, herhangi bir standart GIS yazılımıyla sorunsuz çalışan sağlam GIS‑entegre uygulamalar geliştirebilirsiniz.

---

**Last Updated:** 2026-06-30  
**Tested With:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Author:** Aspose

## İlgili Öğreticiler

- [Vektör Katman Oluştur ve Katman Mekansal Referans Sistemini Ayarla](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [File GDB'de Vektör Katman Oluştur – Aspose.GIS .NET Öğreticisi](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Katmanı Nasıl Değiştirilir – Aspose.GIS .NET Katman Etkileşimi](/gis/net/layer-interaction-and-data-access/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
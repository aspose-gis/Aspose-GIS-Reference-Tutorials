---
title: SRS ile Vektör Katmanı Oluşturun
linktitle: SRS ile Vektör Katmanı Oluşturun
second_title: Aspose.GIS .NET API'si
description: Kusursuz GIS entegrasyonunun anahtarı olan Aspose.GIS for .NET'i keşfedin. Belirtilen uzamsal referans sistemleriyle vektör katmanlarını zahmetsizce oluşturun. Şimdi İndirin!
type: docs
weight: 13
url: /tr/net/layer-management/create-vector-layer-with-srs/
---
## giriiş
Aspose.GIS for .NET, geliştiricilerin .NET uygulamalarında coğrafi bilgi sistemi (GIS) verileriyle sorunsuz bir şekilde çalışmasına olanak tanıyan güçlü bir kütüphanedir. Bu derste, uzaysal referans sistemi (SRS) ile bir vektör katmanı oluşturmaya odaklanacağız. Bu kılavuzun sonunda, GIS yeteneklerini .NET projelerinize zahmetsizce entegre edebileceksiniz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- C# ve .NET geliştirme konusunda temel bilgiler.
-  Aspose.GIS for .NET kütüphanesi kuruldu. İndirebilirsin[Burada](https://releases.aspose.com/gis/net/).
- Bir geliştirme ortamı kuruldu ve hazır.
## Ad Alanlarını İçe Aktar
C# dosyanızın başında gerekli ad alanlarının içe aktarıldığından emin olun:
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
## Adım 1: Öngörülen Uzamsal Referans Sistemini Kurun
Örnek olarak Dünya Mercator projeksiyonunu kullanarak projeksiyonlu bir mekansal referans sistemi (SRS) oluşturalım. Bu adımları takip et:
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
## Adım 2: Vektör Katmanı Oluşturun ve Özellikler Ekleyin
Şimdi bir şekil dosyası oluşturalım ve belirtilen SRS ile özellikler ekleyelim:
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
        layer.Add(feature); // Geometrinin farklı bir SRS'si olduğundan bu bir istisna oluşturacaktır
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## Adım 3: Uzamsal Referans Sistemini Doğrulayın
Son olarak katmanı açalım ve mekansal referans sistemini doğrulayalım:
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / Dünya Mercatörü"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Doğruya dönmeli
}
```
Bu adımları izleyerek Aspose.GIS for .NET'i kullanarak belirli bir uzamsal referans sistemine sahip bir vektör katmanını başarıyla oluşturdunuz.
## Çözüm
Aspose.GIS sayesinde GIS işlevselliğini .NET uygulamalarınıza entegre etmek hiç bu kadar kolay olmamıştı. Vektör katmanlarını zahmetsizce oluşturma ve mekansal referans sistemlerini yönetme becerisi sayesinde projelerinizi güçlü coğrafi özelliklerle geliştirebilirsiniz.
## SSS
### Aspose.GIS tüm GIS dosya formatlarıyla uyumlu mu?
 Aspose.GIS, Shapefile, GeoJSON, KML ve daha fazlası dahil olmak üzere çeşitli GIS formatlarını destekler. Kontrol edin[dokümantasyon](https://reference.aspose.com/gis/net/) tam liste için.
### Aspose.GIS'i bir web uygulamasında kullanabilir miyim?
Kesinlikle! Aspose.GIS for .NET çok yönlüdür ve web uygulamalarında, masaüstü uygulamalarında ve hatta mobil uygulamalarda kullanılabilir.
### Aspose.GIS için nereden destek alabilirim?
 Şu adreste yararlı bir topluluk bulabilirsiniz:[Aspose.GIS forumu](https://forum.aspose.com/c/gis/33) Karşılaşabileceğiniz her türlü soru veya sorun için.
### Ücretsiz deneme mevcut mu?
 Evet, ücretsiz deneme sürümünü edinerek Aspose.GIS'in özelliklerini keşfedebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.GIS lisansını nasıl satın alabilirim?
 Lisans satın almak için şu adresi ziyaret edin:[satın alma sayfası](https://purchase.aspose.com/buy).
---
date: 2026-06-15
description: Aspose.GIS for .NET ile vector layer oluşturmayı ve katman spatial reference
  system ayarlamayı öğrenin. Spatial reference tanımlamayı, point feature eklemeyi
  ve EPSG kodunu almayı ustalaşın.
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: Katman Spatial Reference System Ayarla
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Vector Layer Oluşturma ve Katman Spatial Reference System Ayarlama
url: /tr/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektör Katmanı Oluşturma ve Katman Uzamsal Referans Sistemini Ayarlama

## Giriş
Geniş Coğrafi Bilgi Sistemleri (GIS) dünyasında **Aspose.GIS for .NET**, **70+** vektör ve raster formatını destekleyen, tüm veri kümesini belleğe yüklemeden **10 GB**'den büyük dosyaları işleyebilen sağlam, yüksek performanslı bir kütüphane olarak öne çıkar. Bu öğreticide **vektör katmanı oluşturacak**, uzamsal referansını tanımlayacak, **nokta özelliği ekleyecek** ve EPSG kodunu alacaksınız — adım adım net bir rehberle. İster bir haritalama servisi, veri dönüşüm hattı, ister uzamsal analiz motoru geliştirin, bu temelleri öğrenmek shapefile koordinat sisteminizi doğru tutar ve GIS iş akışınızı güvenilir kılar.

## Hızlı Yanıtlar
- **“create vector layer” ne anlama gelir?** Yeni bir GIS katmanı (ör. bir Shapefile) oluşturur; bu katman nokta, çizgi veya çokgen gibi geometrileri depolayabilir.  
- **Örnekte hangi EPSG kodu kullanılıyor?** EPSG 26918 (NAD83 / UTM zone 18N).  
- **Katmanı oluşturduktan sonra bir nokta özelliği ekleyebilir miyim?** Evet—`ConstructFeature()` kullanın ve bir `Point` geometrisi atayın.  
- **Katmanın CRS'sini nasıl alırım?** `layer.SpatialReferenceSystem.EpsgCode` veya `.Name` okuyun.  
- **Aspose.GIS için lisans gerekir mi?** Ücretsiz deneme mevcuttur; üretim kullanımı için lisans gereklidir.

## Vektör katmanı oluşturma nedir?
**Vektör katmanı oluşturma** işlemi, geometrik özellikler ve öznitelik verileri tutabilen yeni bir vektör veri kümesi (ör. bir Shapefile) yaratır. Aspose.GIS'te bu, bir sürücü ve uzamsal referans sistemi ile bir `VectorLayer` nesnesi örnekleyerek yapılır.

## Katman koordinat sistemini (CRS) doğru şekilde ayarlamak neden önemlidir?
Doğru koordinat referans sistemini (CRS) ayarlamak, depoladığınız her geometrinin diğer uzamsal veri setleriyle hizalanmasını sağlar. Aspose.GIS ile standart bir EPSG kodu kullanarak CRS tanımlayabilirsiniz; bu, dünya çapındaki GIS yazılımlarıyla birlikte çalışabilirliği garanti eder. Örneğin, EPSG 26918 NAD83 / UTM zone 18N'i tanımlar ve doğu ABD'deki veriler için yaygın bir projeksiyondur.

## Önkoşullar
- .NET geliştirme deneyimi (C# veya VB.NET).  
- Visual Studio 2022 veya daha yeni bir sürüm.  
- Aspose.GIS for .NET kütüphanesi – **[buradan](https://releases.aspose.com/gis/net/)** indirin.  
- Uzamsal referans sistemleri (CRS/EPSG) hakkında temel bilgi.

## Ad Alanlarını İçe Aktar
`Aspose.Gis` ad alanı temel GIS sınıflarını, `Aspose.Gis.Geometries` ise `Point` gibi geometri tiplerini sağlar.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Aspose.GIS for .NET'te bir vektör katmanı nasıl oluşturulur?
`VectorLayer`, bir Shapefile gibi bir vektör veri kümesini temsil eder ve özellik oluşturma, okuma ve düzenleme yöntemleri sunar.  
`SpatialReferenceSystem`, EPSG kodu kullanarak koordinat referans sistemini tanımlar.  

Hedef klasörü yükleyin, EPSG kodlu bir `SpatialReferenceSystem` tanımlayın ve Shapefile sürücüsüyle `VectorLayer.Create` çağrısını yapın. Bu tek çağrı yeni bir `.shp` dosyası oluşturur, eşlik eden `.shx` ve `.dbf` dosyalarını yazar ve CRS meta verisini gömerek özellik eklemeye hazır hâle getirir.

### Adım 1: Belge Dizinini Belirtin
Belge dizininizin yolunu belirterek uzamsal veri dosyalarınızın saklanacağı konumu tanımlayın.

```csharp
string dataDir = "Your Document Directory";
```

### Adım 2: Uzamsal Referansı Tanımlayın ve Shapefile Koordinat Sistemini Ayarlayın
`SpatialReferenceSystem`, bir katmanın CRS'sini EPSG kodu ile temsil eder.  

Shapefile yolu tanımlayın ve EPSG kodu (bu örnekte 26918) kullanarak **uzamsal referansı tanımlayın**. Bu adım **shapefile koordinat sistemini katman için ayarlar**.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Bir vektör katmanına nokta özelliği nasıl eklenir?
`Point`, tek bir X/Y koordinat çifti temsil eden bir geometri tipidir.  

Yeni bir özellik oluşturun, istediğiniz X/Y koordinatlarıyla bir `Point` geometrisi atayın ve açık `VectorLayer`a ekleyin. İşlem, geometriyi `.shp` dosyasına ve öznitelik kaydını `.dbf` dosyasına tek bir işlemde yazar.

### Adım 3: Vektör Katmanı Oluşturun
`ConstructFeature` yeni bir özellik nesnesi oluşturur; bu nesne geometri ve öznitelik verisi tutabilir.  

Şimdi **belirtilen Shapefile yolu, sürücü türü (Shapefile) ve az önce tanımladığınız uzamsal referans sistemi** ile vektör katmanı oluşturun.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### Adım 4: Katmana Nokta Özelliği Ekleyin
Yeni bir özellik oluşturun ve **nokta özelliği** eklemek için geometrisini (koordinatları 60, 24 olan bir `Point`) ayarlayın. Ardından özelliği vektör katmanına ekleyin.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### Adım 5: Uzamsal Referans Sistem Bilgilerini Al (EPSG Kodunu Al)
Vector Layer'ı açın ve uzamsal referans sistemi hakkında EPSG kodu ve insan tarafından okunabilir adı gibi bilgileri alın. Bu, **EPSG kodunu alma** ve **katman CRS'sini ayarlama** gösterir.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden Oluşur | Çözüm |
|-------|----------------|-----|
| **Katman açılamıyor** | Yanlış sürücü veya bozuk dosya yolu | `Drivers.Shapefile`'ı doğrulayın ve `path`'in mevcut bir `.shp` dosyasına işaret ettiğinden emin olun. |
| **Yanlış CRS görüntüleniyor** | Yanlış EPSG kodu kullanılması | EPSG kodunu güvenilir bir kaynaktan (ör. EPSG.io) tekrar kontrol edin. |
| **Özellik kaydedilmedi** | `using` bloğu içinde `layer.Add(feature)` çağrılmadı | Katman serbest bırakılmadan önce `Add` metodunun çalıştığından emin olun. |

## Sıkça Sorulan Sorular
**Q:** Mevcut bir Shapefile'ın CRS'ini nasıl değiştiririm?  
A: Katmanı açın, istenen EPSG koduyla yeni bir `SpatialReferenceSystem` oluşturun, bunu `layer.SpatialReferenceSystem`'a atayın, ardından katmanı kaydedin.

**Q:** Aynı yaklaşımı kullanarak diğer geometri tiplerini (ör. çokgenler) ekleyebilir miyim?  
A: Evet—`new Point(x, y)` yerine `new Polygon(...)` veya `new LineString(...)` kullanabilirsiniz.

**Q:** Büyük veri setleriyle verimli çalışmak mümkün mü?  
A: Akış API'lerini (`VectorLayer.Create` ile `FeatureCollection`) kullanın ve kaynakları hızlıca serbest bırakmak için katmanları zamanında dispose edin.

**Q:** Aspose.GIS koordinat dönüşümünü destekliyor mu?  
A: Evet—`Geometry.Transform(targetSrs)` ile geometrileri farklı uzamsal referanslar arasında yeniden projekte edebilirsiniz.

**Q:** Hangi .NET sürümleri destekleniyor?  
A: Aspose.GIS .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7 ile çalışır.

---

**Son Güncelleme:** 2026-06-15  
**Test Edilen:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Eğitimler

- [Aspose.GIS for .NET kullanarak Vektör Katmanı Oluşturma ve Lineerleştirme Toleransını Ayarlama](/gis/net/geometry-processing/set-linearization-tolerance/)
- [File GDB'de Vektör Katmanı Oluşturma – Aspose.GIS .NET Eğitimi](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [spatial reference wgs84 – Aspose.GIS kullanarak GDB'ye Katman Ekleme](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
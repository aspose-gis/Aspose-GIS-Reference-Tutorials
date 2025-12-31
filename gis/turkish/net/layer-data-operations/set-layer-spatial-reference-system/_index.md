---
date: 2025-12-31
description: Aspose.GIS for .NET ile vektör katman oluşturmayı ve katman uzamsal referans
  sistemini ayarlamayı öğrenin. Uzamsal referansı tanımlamayı, nokta özelliği eklemeyi
  ve EPSG kodunu almayı ustalaşın.
linktitle: Set Layer Spatial Reference System
second_title: Aspose.GIS .NET API
title: Vektör Katmanı Oluştur ve Katman Uzamsal Referans Sistemini Ayarla
url: /tr/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektör Katmanı Oluşturma ve Katman Uzamsal Referans Sistemini Ayarlama

## Introduction
Coğrafi Bilgi Sistemleri (GIS) dünyasında **Aspose.GIS for .NET**, geliştiriciler için sağlam ve çok yönlü bir araç olarak öne çıkar. Bu öğreticide **vektör katmanı oluşturacak**, uzamsal referansını tanımlayacak, bir nokta özelliği ekleyecek ve EPSG kodunu alacaksınız—hepsi net, adım‑adım yönergelerle. İster deneyimli bir GIS mühendisi olun, ister yeni başlıyor olun, bu teknikler shapefile koordinat sistemini doğru şekilde ayarlamanıza ve mekansal veri iş akışlarınızın güvenilirliğini artırmanıza yardımcı olacaktır.

## Quick Answers
- **“Vektör katmanı oluşturma” ne anlama gelir?** Yeni bir GIS katmanı (ör. bir Shapefile) oluşturur ve nokta, çizgi veya çokgen gibi geometrileri depolayabilir.  
- **Örnekte hangi EPSG kodu kullanılıyor?** EPSG 26918 (NAD83 / UTM zone 18N).  
- **Katmanı oluşturduktan sonra bir nokta özelliği ekleyebilir miyim?** Evet—`ConstructFeature()` kullanın ve bir `Point` geometrisi atayın.  
- **Katmanın CRS'sini nasıl alırım?** `layer.SpatialReferenceSystem.EpsgCode` veya `.Name` değerini okuyun.  
- **Aspose.GIS için lisansa ihtiyacım var mı?** Ücretsiz deneme sürümü mevcuttur; üretim kullanımı için lisans gereklidir.

## Prerequisites
Öğreticiye başlamadan önce aşağıdaki ön koşulların sağlandığından emin olun:
- .NET programlamada temel bilgi.  
- Sisteminizde Visual Studio yüklü.  
- Aspose.GIS for .NET kütüphanesi, [buradan](https://releases.aspose.com/gis/net/) indirebilirsiniz.  
- GIS'te uzamsal referans sistemleri hakkında temel anlayış.

## Import Namespaces
.NET projenizde, Aspose.GIS tarafından sağlanan işlevlere erişmek için gerekli ad alanlarını içe aktararak başlayın. Aşağıdaki kod parçacığını kullanın:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Step 1: Specify the Document Directory
Belge dizininizin yolunu belirtin. Bu, mekansal veri dosyalarınızın saklanacağı konum olacaktır.

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Define Spatial Reference and Set Shapefile Coordinate System
Shapefile yolunu tanımlayın ve **uzamsal referansı** EPSG kodu (bu örnekte 26918) kullanarak **tanımlayın**. Bu adım, katman için **shapefile koordinat sistemini ayarlar**.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Step 3: Create Vector Layer
Şimdi **vektör katmanı oluşturun**; belirtilen Shapefile yolu, sürücü türü (Shapefile) ve az önce tanımladığınız uzamsal referans sistemi ile.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

## Step 4: Add Point Feature to the Layer
Yeni bir özellik oluşturun ve **nokta özelliği ekleyin**; geometrisini (koordinatları 60, 24 olan bir `Point`) ayarlayın. Ardından özelliği vektör katmanına ekleyin.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

## Step 5: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
Vector Layer'ı açın ve uzamsal referans sistemi hakkında bilgi alın; örneğin EPSG kodu ve insan tarafından okunabilir adı. Bu, **EPSG kodunu almayı** ve **katman CRS'sini ayarlamayı** gösterir.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

Bu adımları kendi kullanım senaryonuza göre tekrarlayın; böylece **vektör katmanı oluşturma** sanatını ve Aspose.GIS for .NET ile uzamsal referansları yönetmeyi ustalıkla yapabilirsiniz.

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **Katman açılamıyor** | Yanlış sürücü veya bozuk dosya yolu | `Drivers.Shapefile` doğruluğunu kontrol edin ve `path` değişkeninin mevcut bir `.shp` dosyasına işaret ettiğinden emin olun. |
| **Yanlış CRS gösteriliyor** | Hatalı EPSG kodu kullanılması | EPSG kodunu güvenilir bir kaynaktan (ör. EPSG.io) tekrar kontrol edin. |
| **Özellik kaydedilmiyor** | `using` bloğu içinde `layer.Add(feature)` çağrılmaması | Katman serbest bırakılmadan önce `Add` metodunun çalıştırıldığından emin olun. |

## Frequently Asked Questions
### Aspose.GIS diğer GIS kütüphaneleriyle uyumlu mu?
Evet, Aspose.GIS diğer GIS kütüphaneleriyle iyi entegrasyon sağlar ve birlikte kullanılabilir.

### Aspose.GIS'i hem masaüstü hem de web uygulamalarında kullanabilir miyim?
Kesinlikle! Aspose.GIS çok yönlüdür ve hem masaüstü hem de web‑tabanlı uygulamalarda kullanılabilir.

### Aspose.GIS için lisans seçenekleri mevcut mu?
Evet, lisans seçeneklerini inceleyebilir ve satın alabilirsiniz: [buradan](https://purchase.aspose.com/buy).

### Aspose.GIS için ücretsiz deneme sürümü var mı?
Elbette! Ücretsiz deneme sürümünü şu adresten indirebilirsiniz: [buradan](https://releases.aspose.com/).

### Aspose.GIS ile ilgili sorular için nereden destek alabilirim?
Her türlü destek ve soru için [Aspose.GIS forumunu](https://forum.aspose.com/c/gis/33) ziyaret edin.

## Additional Frequently Asked Questions
**S: Mevcut bir Shapefile'ın CRS'sini nasıl değiştiririm?**  
C: Katmanı açın, istediğiniz EPSG koduyla yeni bir `SpatialReferenceSystem` oluşturun ve kaydetmeden önce `layer.SpatialReferenceSystem` özelliğine atayın.

**S: Aynı yöntemle başka geometri tipleri (ör. çokgenler) ekleyebilir miyim?**  
C: Evet—`new Point(x, y)` ifadesini ihtiyacınıza göre `new Polygon(...)` veya `new LineString(...)` ile değiştirin.

**S: Büyük veri setleriyle verimli çalışmak mümkün mü?**  
C: Akış (streaming) API'lerini kullanın (`VectorLayer.Create` ile `FeatureCollection`) ve kaynakları serbest bırakmak için katmanları zamanında dispose edin.

**S: Aspose.GIS koordinat dönüşümünü destekliyor mu?**  
C: Evet—`Geometry.Transform(targetSrs)` ile geometrileri farklı uzamsal referanslar arasında yeniden projekte edebilirsiniz.

**S: Hangi .NET sürümleri destekleniyor?**  
C: Aspose.GIS .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7 ile çalışır.

## Conclusion
Bu öğreticide **vektör katmanı oluşturma**, uzamsal referansını tanımlama, **nokta özelliği ekleme** ve **EPSG kodunu alma** konularını Aspose.GIS for .NET kullanarak inceledik. Bu adımları ustalaştırarak shapefile koordinat sistemini güvenle ayarlayabilir, katman CRS'sini yönetebilir ve güvenilir GIS uygulamaları geliştirebilirsiniz.

---

**Last Updated:** 2025-12-31  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
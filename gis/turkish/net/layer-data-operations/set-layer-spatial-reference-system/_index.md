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

## Giriiş
Coğrafi Bilgi Sistemleri (GIS) dünyasında **Aspose.GIS for .NET**, geliştiriciler için sağlam ve çok yönlü bir araç olarak öne çıkar. Bu öğreticide **vektör planı oluşturacak**, uzamsal referansını tanımlayacak, bir nokta özelliği ekleyecek ve EPSG verilerini sunacak—hepsi net, adım‑adım talimatlarla. İster havade bir GIS mühendisi olun, ister yeni başlayın, bu teknikler şekil dosyası koordinat sistemini doğru şekilde ayarlamanıza ve mekansal veri akışlarının verimliliğini artırmanıza yardımcı olacaktır.

## Hızlı Yanıtlar
- **“Vektör katmanı oluşturma” ne anlama gelir?**Yeni bir GIS haritası (ör. bir Shapefile) oluşturur ve nokta, çizgi veya çokgen gibi geometrileri depolayabilir.
- **Örnekte hangi EPSG kodu kullanılıyor?**EPSG26918 (NAD83 / UTM Zone18N).
- **Katmanı oluşturduktan sonra bir nokta özelliği olabilir mi?**Evet—`ConstructFeature()` kullanın ve bir `Point` geometrisi atayın.
- **Katmanın CRS'sini nasıl alırım?**`layer.SpatialReferenceSystem.EpsgCode` veya `.Name` değerini okuyun.
- **Aspose.GIS için lisansa ihtiyacınız var mı?**Ücretsiz deneme sürümü mevcuttur; üretim kullanımı için lisans gereklidir.

## Önkoşullar
Öğreticiye başlamadan önce aşağıdaki ön koşulların sağlandığından emin olun:
- .NET programlamada temel bilgiler.
- Sisteminizde Visual Studio Yüklü.
- Aspose.GIS for .NET kütüphanesi, [buradan](https://releases.aspose.com/gis/net/) indirmeler.
- GIS'te uzamsal referans sistemleri hakkında temel anlayış.

## Ad Alanlarını İçe Aktar
.NET projenizde, Aspose.GIS tarafından sağlanan kapasiteler için uygun reklam alanlarını aktarmaya başlayın. kod Aşağıdaki parçacığını kullanın:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Adım 1: Belge Dizinini Belirleyin
Belge dizininizin yolu belirlenir. Bu, mekansal veri dosyalarının saklanacağı yerde olacaktır.

```csharp
string dataDir = "Your Document Directory";
```

## Adım 2: Mekansal Referansı Tanımlayın ve Shapefile Koordinat Sistemini Ayarlayın
Shapefile yolunu tanımlayın ve **uzamsal referansı** EPSG kodu (bu örnekte 26918) kullanarak **tanımlayın**. Bu adım, katman için **shapefile koordinat sistemini ayarlar**.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Adım 3: Vektör Katmanı Oluşturun
Şimdi **vektör katmanı oluşturun**; belirtilen Shapefile yolu, sürücü türü (Shapefile) ve az önce tanımladığınız uzamsal referans sistemi ile.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

## Adım 4: Katmana Nokta Özelliği Ekleme
Yeni bir özellik oluşturun ve **nokta özelliği ekleyin**; geometrisini (koordinatları 60, 24 olan bir `Point`) ayarlayın. Ardından özelliği vektör katmanına ekleyin.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

## Adım 5: Mekansal Referans Sistemi Bilgilerini Alma (EPSG Kodunu Alma)
Vector Layer'ı açın ve uzamsal referans sistemi hakkında bilgi alın; örneğin EPSG kodu ve insan tarafından okunabilir adı. Bu, **EPSG kodunu almayı** ve **katman CRS'sini ayarlamayı** gösterir.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

Bu adımları kendi kullanım senaryonuza göre tekrarlayın; böylece **vektör katmanı oluşturma** sanatını ve Aspose.GIS for .NET ile uzamsal referansları yönetmeyi ustalıkla yapabilirsiniz.

## Yaygın Sorunlar ve Çözümler
| Sayı | Neden Olur | Düzelt |
|----------|-----|-----|
| **Katman açmıyor** | Yanlış sürücü veya bozuk dosya yolu | `Drivers.Shapefile` doğruluk kontrolünü edin ve `path` değişkeninin mevcut bir `.shp` dosyasına işaretlendiğinde emin olun. |
| **Yanlış CRS gösteriliyor** | Hatalı EPSG kodunun kullanılması | EPSG kodu güvenilir bir kaynaktan (ör. EPSG.io) tekrar kontrol edin. |
| **Özellik kaydedilmiyor** | ``kullanma` tükenmesi içinde `layer.Add(feature)` çağrılmaması | Katman serbest bırakılmadan önce `Add` yönteminin çalıştırıldığından emin olun. |

## Ek Sıkça Sorulan Sorular
**S: Mevcut bir Shapefile'ın CRS'sini nasıl değiştiririm?**
C: Katmanı açmak, istediğiniz EPSG koduyla yeni bir `SpatialReferenceSystem` oluşturup kaydetmeden önce `layer.SpatialReferenceSystem` özelliğini atayın.

**S: Aynı işlemin başka geometri türleri (ör. çokgenler) seçenekleri var mı?**
C: Evet—`new Point(x, y)` şartına göre `new Polygon(...)` veya `new LineString(...)` ile onaylandı.

**S: Büyük veri setleriyle verimli çalışmak mümkün mü?**
C: Akış (streaming) API'lerini kullanın (`VectorLayer.Create` ile `FeatureCollection`) ve kaynakları serbest bırakmak için katmanları zamanında imha edin.

**S: Aspose.GIS koordinat hızının büyüklüğü mü?**
C: Evet—`Geometry.Transform(targetSrs)` ile geometrileri farklı uzamsal referanslar arasında yeniden projekte edebilirsiniz.

**S: Hangi .NET uzantısı destekleniyor?**
C: Aspose.GIS .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7 ile çalışır.

## Çözüm
Bu öğreticide **vektör planı oluşturma**, uzamsal referansını tanımlama, **nokta özelliği ekleme** ve **EPSG kodlama alma** konularını Aspose.GIS for .NET kullanarak inceledik. Bu hızları ustalaştırarak şekil dosyası koordinatlarını ölçebilir, katman CRS'sini yönetebilir ve güvenilir GIS uygulamalarını geliştirebilirsiniz.

---

**Son Güncelleme:** 2025-12-31
**Test Edilen Sürüm:** Aspose.GIS 24.11 for .NET
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
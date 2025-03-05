---
title: Çözgü Raster Formatları
linktitle: Çözgü Raster Formatları
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS for .NET ile coğrafi programlama dünyasını keşfedin. Gelişmiş mekansal veri görselleştirmesi için raster formatlarını adım adım çarpıtmayı öğrenin.
type: docs
weight: 23
url: /tr/net/layer-data-operations/warp-raster-formats/
---
## giriiş
Aspose.GIS for .NET ile coğrafi programlamanın heyecan verici dünyasına hoş geldiniz! Bu eğitimde, Aspose.GIS'i kullanarak raster formatlarını çarpıtma sürecinde size rehberlik edeceğiz. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, geotiff manipülasyonunun inceliklerini araştırırken, konumsal verilerinize tamamen yeni bir bakış açısı kazandırırken kemerlerinizi bağlayın.
## Önkoşullar
Bu yolculuğa çıkmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
-  Aspose.GIS for .NET: Henüz yapmadıysanız Aspose.GIS kütüphanesini indirip yükleyin. En son sürümü bulabilirsiniz[Burada](https://releases.aspose.com/gis/net/).
- Belge Dizininiz: Belgelerinizi saklamak için bir dizin oluşturun. Bu, raster çarpıtma işlemi sırasında dosya yönetimi için çok önemli olacaktır.
Artık donanıma sahip olduğumuza göre koda geçelim.
## Ad Alanlarını İçe Aktar
Öncelikle doğru araçların elimizde olduğundan emin olalım. Jeo-uzaysal maceranızı başlatmak için gerekli ad alanlarını içe aktarın:
```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Raster;
using Aspose.Gis.SpatialReferencing;
```
## 1. Adım: Yolu Başlatın
Belge dizininizin yolunu ayarlayarak başlayın. İşte tüm sihrin gerçekleşeceği yer:
```csharp
string dataDir = "Your Document Directory";
```
## Adım 2: Raster Katmanını Açın
GeoTiff raster katmanını açın ve onu dönüşüme hazırlayın. Bu adım sonraki çözgü operasyonu için aşamayı belirler:
```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(dataDir, "raster_float32.tif")))
```
## Adım 3: Raster'ı Çözün
Şimdi warp işlemini gerçekleştirelim. Raster verilerinize yeni bir soluk getirmek için hedef boyutları ve mekansal referans sistemini belirtin:
```csharp
using (var warped = layer.Warp(new WarpOptions(){Height = 40, Width = 40, TargetSpatialReferenceSystem = SpatialReferenceSystem.Wgs84}))
```
## Adım 4: Raster Bilgilerini Çıkarın
Dönüştürülen rasterın sırlarını açığa çıkarmanın zamanı geldi. Hücre boyutu, uzaysal referans sistemi, sınırlar ve bant sayısı gibi temel bilgileri çıkarın:
```csharp
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
var bandCount = warped.BandCount;
```
## Adım 5: Raster Ayrıntılarını Yazdırın
Ortaya çıkardığımız ilgi çekici ayrıntıların çıktısını alarak çarpık raster hakkında fikir verelim:
```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
Console.WriteLine($"bandCount: {bandCount}");
```
## Adım 6: Raster Bantlarını Keşfedin
Veri türlerini, istatistiklerini ve nodata değerlerinin varlığını çözerek taramanın ayrı ayrı bantlarını inceleyin:
```csharp
for (int i = 0; i < warped.BandCount; i++)
{
    var dataType = warped.GetBand(i).DataType;
    var hasNoData = !warped.NoDataValues.IsNull();
    var statistics = warped.GetStatistics(i);
    Console.WriteLine();
    Console.WriteLine($"Band: {i}");
    Console.WriteLine($"dataType: {dataType}");
    Console.WriteLine($"statistics: {statistics}");
    Console.WriteLine($"hasNoData: {hasNoData}");
    if (hasNoData)
        Console.WriteLine($"noData: {warped.NoDataValues[i]}");
}
```
## Çözüm
Tebrikler! Aspose.GIS for .NET'i kullanarak jeouzaysal programlamanın çarpıtma bölgesinde başarılı bir şekilde gezindiniz. Bu adımları izleyerek, raster manipülasyonuna ilişkin değerli bilgiler elde ederek konumsal verileriniz için yeni olasılıkların kilidini açtınız.
## SSS
### Aspose.GIS tüm tarama formatlarıyla uyumlu mu?
Evet, Aspose.GIS çok çeşitli raster formatlarını destekleyerek çeşitli mekansal veri kümelerinin işlenmesinde esneklik sağlar.
### Coğrafi referansı olmayan görüntülerde tarama çarpıtması yapabilir miyim?
Aspose.GIS, coğrafi referanslı verileri işleyerek doğru dönüşümler sağlamak üzere tasarlanmıştır. Raster görsellerinizin uygun mekansal referans bilgilerine sahip olduğundan emin olun.
### Aspose.GIS topluluğuna nasıl katkıda bulunabilirim?
 Konuyla ilgili tartışmaya katılın[Aspose.GIS forumu](https://forum.aspose.com/c/gis/33) deneyimlerinizi paylaşmak, sorular sormak ve diğer geliştiricilerle işbirliği yapmak için.
### Aspose.GIS'in ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü indirerek Aspose.GIS'in yeteneklerini keşfedebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.GIS için geçici lisanslar mevcut mu?
 Evet, geçici lisansa ihtiyacınız varsa alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
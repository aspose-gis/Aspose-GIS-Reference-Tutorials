---
title: Özellikleri GeoJSON'a Çıkarın
linktitle: Özellikleri GeoJSON'a Çıkarın
second_title: Aspose.GIS .NET API'si
description: Özellikleri GeoJSON'a çıkarmak için Aspose.GIS for .NET kullanımına ilişkin adım adım kılavuzu keşfedin. CBS'nin gücünden kolaylıkla yararlanın! #Aspose #GIS
type: docs
weight: 23
url: /tr/net/layer-management/extract-features-to-geojson/
---
## giriiş
Aspose.GIS for .NET kullanarak özelliklerin GeoJSON'a çıkarılmasıyla ilgili adım adım eğitimimize hoş geldiniz! İster deneyimli bir geliştirici olun ister GIS programlama yolculuğunuza yeni başlıyor olun, bu kılavuz süreç boyunca size yol göstererek Aspose.GIS for .NET'in tüm gücünden faydalanmanızı sağlayacaktır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
-  Aspose.GIS for .NET: Kütüphanenin kurulu olduğundan emin olun. Değilse, adresinden indirebilirsiniz.[Aspose.GIS for .NET sayfası](https://releases.aspose.com/gis/net/).
-  Şekil Dosyası Verileri: Giriş için bir Şekil Dosyasını hazır bulundurun. Örnek verilere ihtiyacınız varsa bunu şurada bulabilirsiniz:[Aspose.GIS belgeleri](https://reference.aspose.com/gis/net/).
- .NET Ortamı: Sağlanan kodu çalıştırmak için bir .NET ortamı kurun.
- Belge Dizini: Kod parçacığında belge dizininizin yolunu tanımlayın.
Artık her şey hazır olduğuna göre, GeoJSON'a özellikler çıkarmaya başlayalım!
## Ad Alanlarını İçe Aktar
Öncelikle kodunuza gerekli ad alanlarını ekleyin:
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Bu ad alanları Aspose.GIS işlevleriyle çalışmak için gereklidir.
## Adım 1: Giriş Şekil Dosyasını Açın
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Giriş şekil dosyasını işlemeye yönelik kodunuz buraya gelir
}
```
 Giriş Shapefile'ı kullanarak açın.`VectorLayer.Open` yöntem.
## Adım 2: GeoJSON Çıktısını Oluşturun
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // GeoJSON çıktısını oluşturmaya yönelik kodunuz buraya gelecek
}
```
 GeoJSON çıktısını kullanarak şunu oluşturun:`VectorLayer.Create` yöntem.
## 3. Adım: Nitelikleri Kopyalayın
```csharp
outputLayer.CopyAttributes(inputLayer);
```
 Nitelikleri girdi katmanından çıktı katmanına kopyalayın.`CopyAttributes` yöntem.
## Adım 4: Süreç Özellikleri
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Her giriş özelliğini işlemeye yönelik kodunuz buraya gelir
}
```
Giriş katmanındaki her özelliği yineleyin ve bunları ayrı ayrı işleyin.
## Adım 5: Özellikleri Tarihe Göre Filtreleyin
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
Özellikleri tarih koşuluna göre filtreleyin. Bu örnekte, doğum tarihi 1982'den önce olan özellikler atlanıyor.
## Adım 6: Yeni Bir Özellik Oluşturun
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Giriş özelliğinden geometriyi ve değerleri kopyalayarak çıktı katmanı için yeni bir özellik oluşturun.
Tebrikler! Aspose.GIS for .NET'i kullanarak özellikleri başarıyla GeoJSON'a çıkardınız.
## Çözüm
Bu eğitimde Aspose.GIS for .NET kullanarak GeoJSON'a özellik çıkarma sürecini araştırdık. Bu güçlü kütüphane, CBS geliştirme için bir olasılıklar dünyasının kapılarını açıyor. Aspose.GIS'in tüm potansiyelini ortaya çıkarmak için farklı veri kümeleri ve işlevlerle denemeler yapın.
## SSS
### S: Daha fazla belgeyi nerede bulabilirim?
 Ziyaret edin[Aspose.GIS belgeleri](https://reference.aspose.com/gis/net/) derinlemesine bilgi için.
### S: Geçici lisansı nasıl alabilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### S: Nereden destek alabilirim?
 Katılmak[Aspose.GIS forumu](https://forum.aspose.com/c/gis/33) topluluk desteği ve tartışmalar için.
### S: Ücretsiz deneme mevcut mu?
 Evet, ücretsiz deneme sürümünü bulabilirsiniz[Burada](https://releases.aspose.com/).
### S: Aspose.GIS for .NET'i nereden satın alabilirim?
 Ürünü satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).
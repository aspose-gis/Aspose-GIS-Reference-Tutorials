---
title: Akışa GeoJSON Yaz
linktitle: Akışa GeoJSON Yaz
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS for .NET'in gücünü keşfedin! Zahmetsizce yayın yapmak için GeoJSON yazın. Kusursuz coğrafi entegrasyon için hemen indirin.
type: docs
weight: 25
url: /tr/net/layer-data-operations/write-geojson-to-stream/
---
## giriiş
Aspose.GIS'i kullanarak .NET uygulamanızda GeoJSON'un gücünden yararlanmak mı istiyorsunuz? Peki, doğru yerdesiniz! Bu adım adım kılavuz, Aspose.GIS for .NET'in güçlü özelliklerinden yararlanarak GeoJSON'u bir akışa yazma sürecinde size yol gösterecektir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1. Aspose.GIS for .NET Library: Aspose.GIS for .NET kütüphanesinin kurulu olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/gis/net/).
2. Belge Dizini: Projenizde bir belge dizini kurun ve yolunu not edin.
Şimdi öğreticiye başlayalım!
## Ad Alanlarını İçe Aktar
İlk olarak Aspose.GIS işlevlerine erişmek için kodunuza gerekli ad alanlarını eklediğinizden emin olun:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```
## 1. Adım: Belge Dizinini Ayarlayın
```csharp
string dataDir = "Your Document Directory";
```
"Belge Dizininiz"i belge dizininizin gerçek yolu ile değiştirin.
## 2. Adım: Bellek Akışı Oluşturun
```csharp
using (var memoryStream = new MemoryStream())
{
    // Sonraki adımların kodu buraya gelecek
}
```
## Adım 3: GeoJSON Sürücüsüyle Vektör Katmanı Oluşturun
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Sonraki adımların kodu buraya gelecek
}
```
## Adım 4: Özellik Niteliklerini Tanımlayın
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```
## Adım 5: Özellik Oluşturun ve Ekleyin
```csharp
// İlk Özellik
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// İkinci Özellik
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```
## Adım 6: GeoJSON Çıktısını Görüntüleyin
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```
Tebrikler! Aspose.GIS for .NET'i kullanarak GeoJSON'u bir akışa başarıyla yazdınız.
## Çözüm
Bu eğitimde Aspose.GIS for .NET'i projenize entegre etmek için temel adımları ele aldık ve özellikle GeoJSON'u bir akışa yazmaya odaklandık. Bu basit ama güçlü adımlarla uygulamanızın coğrafi yeteneklerini geliştirebilirsiniz.
## Sıkça Sorulan Sorular
### Aspose.GIS for .NET'i hem Windows hem de Linux ortamlarında kullanabilir miyim?
Evet, Aspose.GIS for .NET hem Windows hem de Linux sistemleriyle uyumludur.
### Ücretsiz deneme mevcut mu?
 Kesinlikle! Ücretsiz denemeyi keşfedebilirsiniz[Burada](https://releases.aspose.com/).
### Ayrıntılı belgeleri nerede bulabilirim?
 Belgelere göz atın[Burada](https://reference.aspose.com/gis/net/).
### Geçici lisansı nasıl alabilirim?
 Geçici lisanslar mevcut[Burada](https://purchase.aspose.com/temporary-license/).
### Yardıma mı ihtiyacınız var veya daha fazla sorunuz mu var?
 Destek forumumuzu ziyaret edin[Burada](https://forum.aspose.com/c/gis/33).
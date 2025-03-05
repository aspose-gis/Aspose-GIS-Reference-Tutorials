---
title: Jeo-uzaysal Veri Etkileşiminde Uzmanlaşmak
linktitle: KML Katmanı ile etkileşime gir
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS ile .NET'te coğrafi veri manipülasyonunun gücünü keşfedin. KML katmanlarıyla etkileşime geçmek için adım adım kılavuz. Şimdi ücretsiz deneme sürümünü indirin!
type: docs
weight: 17
url: /tr/net/layer-interaction-and-data-access/interact-with-kml-layer/
---
## giriiş
Sürekli gelişen yazılım geliştirme ortamında, coğrafi verilerin potansiyelinden yararlanmak giderek daha önemli hale geliyor. Aspose.GIS for .NET, .NET ortamındaki coğrafi verilerle sorunsuz bir şekilde etkileşime geçmek için güçlü bir araç ve işlevsellik seti sunan, zorlu bir müttefik olarak ortaya çıkıyor. Bu derste, Aspose.GIS'i KML katmanlarıyla etkileşimde bulunmak için kullanmanın inceliklerini inceleyerek jeouzamsal veri manipülasyonunun olanaklarını ortaya çıkaracağız.
## Önkoşullar
Bu yolculuğa çıkmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
-  Aspose.GIS for .NET: Kitaplığı şuradan indirip yükleyin:[Aspose.GIS for .NET indirme sayfası](https://releases.aspose.com/gis/net/).
- Geliştirme Ortamı: Aspose.GIS'i .NET projelerinize sorunsuz bir şekilde entegre etmek için Visual Studio gibi uygun bir geliştirme ortamı kurun.
Şimdi öğreticiye geçelim.
## Ad Alanlarını İçe Aktar
KML katmanlarıyla etkileşime geçmeden önce projenize gerekli ad alanlarını eklediğinizden emin olun. Bu adım, coğrafi veri işleme için gereken sınıflara ve yöntemlere erişiminizin olmasını sağlar.
```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Drawing;
using System.Threading;
using Aspose.Gis.Formats.Kml;
using Aspose.Gis.Formats.Kml.Styles;
using Aspose.Gis.Geometries;
using Point = Aspose.Gis.Geometries.Point;
```
## 1. Adım: Belge Dizinini Ayarlayın
KML dosyalarının saklanacağı belge dizininizin yolunu tanımlayın.
```csharp
string dataDir = "Your Document Directory";
```
## 2. Adım: KML Katmanı Oluşturun
Aspose.GIS'i kullanarak KML dosyasının yolunu belirterek bir KML katmanını başlatın.
```csharp
using (var layer = Drivers.Kml.CreateLayer(dataDir + "Kml_File_out.kml"))
{
```
## 3. Adım: Nitelikleri Tanımlayın
Dize, tamsayı, boolean ve double gibi farklı veri türlerini temsil etmek için KML katmanına nitelikler ekleyin.
```csharp
layer.Attributes.Add(new FeatureAttribute("string_data", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("int_data", AttributeDataType.Integer));
layer.Attributes.Add(new FeatureAttribute("bool_data", AttributeDataType.Boolean));
layer.Attributes.Add(new FeatureAttribute("float_data", AttributeDataType.Double));
```
## Adım 4: Unsurları Oluşturun ve Doldurun
Jeo-uzaysal varlıkları temsil eden özellikler oluşturun ve tanımlanan nitelikler için değerleri ayarlayın.
```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("string_data", "string value");
feature.SetValue("int_data", 10);
feature.SetValue("bool_data", true);
feature.SetValue("float_data", 3.14);
feature.Geometry = new LineString(new[] { new Point(0, 0), new Point(1, 1) });
layer.Add(feature);
```
## Adım 5: Başka Bir Özellik Ekleyin
Farklı nitelik değerlerine ve boş geometriye sahip ikinci bir özellik eklemek için işlemi tekrarlayın.
```csharp
Feature feature2 = layer.ConstructFeature();
feature2.SetValue("string_data", "string value2");
feature2.SetValue("int_data", 100);
feature2.SetValue("bool_data", false);
feature2.SetValue("float_data", 3.1415);
feature2.Geometry = Geometry.Null;
layer.Add(feature2);
```
## Çözüm
Tebrikler! Aspose.GIS for .NET'i kullanarak KML katmanlarıyla başarılı bir şekilde etkileşim kurdunuz. Bu eğitim, Aspose.GIS'in çok yönlü yeteneklerine bir bakış sunarak, .NET projelerinizde coğrafi verileri zahmetsizce değiştirmenizi sağlar.
## Sıkça Sorulan Sorular
### Aspose.GIS diğer GIS formatlarıyla uyumlu mu?
Evet, Aspose.GIS; şekil dosyası, GeoJSON ve KML dahil olmak üzere çeşitli GIS formatlarını destekler.
### Aspose.GIS kullanılarak oluşturulan coğrafi verileri görselleştirebilir miyim?
Kesinlikle! Aspose.GIS, harita kitaplıklarıyla sorunsuz bir şekilde bütünleşerek jeouzaysal verilerinizi görselleştirmenize olanak tanır.
### Aspose.GIS'in deneme sürümü mevcut mu?
 Evet, Aspose.GIS'in özelliklerini indirerek keşfedebilirsiniz.[ücretsiz deneme sürümü](https://releases.aspose.com/).
### Aspose.GIS için nasıl destek alabilirim?
 Ziyaret edin[Aspose.GIS forumu](https://forum.aspose.com/c/gis/33) topluluk desteği için veya premium destek seçeneklerini keşfedin[Burada](https://purchase.aspose.com/buy).
### Aspose.GIS için geçici lisanslar mevcut mu?
 Evet, geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
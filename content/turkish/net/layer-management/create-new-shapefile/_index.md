---
title: Yeni Şekil Dosyası Oluştur
linktitle: Yeni Şekil Dosyası Oluştur
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS for .NET kullanarak yeni bir şekil dosyasının nasıl oluşturulacağını öğrenin. Adım adım kılavuzumuzu takip edin ve mekansal veri manipülasyonunun gücünün kilidini açın.
type: docs
weight: 12
url: /tr/net/layer-management/create-new-shapefile/
---
## giriiş
.NET ile coğrafi bilgi sistemleri (GIS) geliştirmeye çalışıyorsanız Aspose.GIS sizin çözümünüzdür. Bu güçlü kitaplık, geliştiricilerin konumsal verilerle sorunsuz bir şekilde çalışmasını sağlar ve bu eğitimde Aspose.GIS for .NET'i kullanarak yeni bir şekil dosyası oluşturma sürecinde size rehberlik edeceğiz.
## Önkoşullar
Eğiticiye geçmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- C# programlama dilinin temel anlayışı.
- Makinenizde Visual Studio yüklü.
-  Aspose.GIS for .NET kütüphanesi. İndirebilirsin[Burada](https://releases.aspose.com/gis/net/).
## Ad Alanlarını İçe Aktar
Aspose.GIS'in işlevselliğinden yararlanmak için gerekli ad alanlarını içe aktararak başlayın:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## 1. Adım: Projenizi Kurun
Visual Studio'da yeni bir C# projesi oluşturarak başlayın ve Aspose.GIS kütüphanesini ekleyin.
## Adım 2: Belge Dizinini Tanımlayın
```csharp
string dataDir = "Your Document Directory";
```
"Belge Dizininiz"i, yeni şekil dosyanızı kaydetmek istediğiniz asıl yolla değiştirin.
## 3. Adım: Bir VectorLayer oluşturun
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //özellik eklemeden önce özellikleri ekleyin
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Bu kod bölümü, vektör katmanını ayarlar ve özelliklerinizin niteliklerini tanımlar.
## 4. Adım: Özellik Ekleyin
### Durum 1: Değerleri Tek Tek Ayarlayın
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
### Durum 2: Tüm Nitelikler için Yeni Değerler Belirler
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## Çözüm
 Tebrikler! Aspose.GIS for .NET'i kullanarak başarıyla yeni bir şekil dosyası oluşturdunuz. Bu eğitici projenizi kurmanın, nitelikleri tanımlamanın ve özellik eklemenin temellerini kapsıyordu. Daha fazlasını keşfederken, bkz.[dokümantasyon](https://reference.aspose.com/gis/net/) Gelişmiş özellikler ve işlevler için.
## Sıkça Sorulan Sorular
### S: Aspose.GIS'i diğer programlama dilleriyle kullanabilir miyim?
Aspose.GIS öncelikle .NET'i destekler ancak Java için de versiyonlar mevcuttur.
### S: Ücretsiz deneme mevcut mu?
 Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).
### S: Aspose.GIS desteğini nerede bulabilirim?
 Ziyaret edin[Aspose.GIS forumu](https://forum.aspose.com/c/gis/33) topluluk desteği ve tartışmalar için.
### S: Geçici lisansı nasıl alabilirim?
 Geçici lisansınızı alın[Burada](https://purchase.aspose.com/temporary-license/).
### S: Aspose.GIS for .NET'i nereden satın alabilirim?
 Kütüphaneyi satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).
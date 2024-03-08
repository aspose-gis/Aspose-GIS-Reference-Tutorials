---
title: Özellik Öznitelik Değerini Al (Varsayılan)
linktitle: Özellik Öznitelik Değerini Al (Varsayılan)
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS for .NET'in gücünü ortaya çıkarın! Bu adım adım kılavuzla özellik öznitelik değerlerini zahmetsizce alın ve değiştirin. Deneme sürümünüzü şimdi indirin!
type: docs
weight: 14
url: /tr/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---
## giriiş
Aspose.GIS for .NET dünyasına hoş geldiniz! Bu kapsamlı kılavuzda Aspose.GIS'in güçlü yeteneklerini kullanarak özellik öznitelik değerlerini almanın inceliklerini ele alacağız. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu eğitim size bu olağanüstü aracın tüm potansiyelinden yararlanmanızı sağlayacak adım adım bir yol sunacaktır.
## Önkoşullar
Bu kodlama macerasına başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- C# ve .NET framework'ü hakkında çalışma bilgisi.
-  Aspose.GIS for .NET kuruldu. Değilse, şuradan indirin:[Burada](https://releases.aspose.com/gis/net/).
- Sorunsuz bir şekilde takip edebileceğiniz Visual Studio gibi bir kod düzenleyici.
## Ad Alanlarını İçe Aktar
C# projenize gerekli ad alanlarını eklediğinizden emin olun:
```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Şimdi her örneği takip edilmesi kolay bir dizi adıma ayıralım.
## Özellik Öznitelik Değerini Al (Varsayılan)
### 1. Adım: Ortamı Ayarlayın
Belgeler dizininizin yolunu tanımlayarak başlayın:
```csharp
string dataDir = "Your Document Directory";
```
### Adım 2: GeoJson Katmanı Oluşturun
Bir GeoJson katmanı oluşturun ve varsayılan değerlere sahip bir nitelik tanımlayın:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### 3. Adım: Bir Özellik Oluşturun
Tanımlanan özniteliği kullanarak bir özellik oluşturun:
```csharp
    Feature feature = layer.ConstructFeature();
```
### Adım 4: Değerleri Alın
Özellik değerlerini çeşitli senaryolarla alın:
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // değer == boş
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // değer == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // değer == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## Varsayılan Değerleri Ayarlama
### Adım 1: Başka Bir GeoJson Katmanı Oluşturun
İşlemi farklı bir GeoJson katmanı ve double niteliğiyle tekrarlayın:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### Adım 2: Bir Özellik Oluşturun (Tekrar)
```csharp
    Feature feature = layer.ConstructFeature();
```
### 3. Adım: Değerleri Alın ve Ayarlayın
Varsayılanları gösteren öznitelik değerlerini alın ve ayarlayın:
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // değer == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // değer == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // değer == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
Tebrikler! Özellik nitelik değerlerini alma ve değiştirme konusunda Aspose.GIS for .NET'in gücünden başarıyla yararlandınız.
## Çözüm
Bu eğitimde Aspose.GIS for .NET kullanarak özellik öznitelik değerlerini almanın inceliklerini araştırdık. Sezgisel API'si ve güçlü özellikleriyle Aspose.GIS, .NET ortamlarında GIS geliştirme için fırsatlar dünyasının kapılarını açıyor.
## Sıkça Sorulan Sorular
### Aspose.GIS .NET Core ile uyumlu mu?
Evet, Aspose.GIS .NET Core ile tamamen uyumludur ve platformlar arası destek sağlar.
### Aspose.GIS'i ticari projeler için kullanabilir miyim?
Kesinlikle! Aspose.GIS, ticari uygulamalarınızda herhangi bir kısıtlama olmaksızın kullanmanıza olanak tanıyan ticari bir lisansla birlikte gelir.
### Ek destek ve kaynakları nerede bulabilirim?
 Ziyaret edin[Aspose.GIS forumu](https://forum.aspose.com/c/gis/33) topluluk desteği için ve keşfetmek için[dokümantasyon](https://reference.aspose.com/gis/net/) derinlemesine bilgi için.
### Ücretsiz deneme mevcut mu?
 Evet, Aspose.GIS'i ücretsiz deneme sürümüyle keşfedebilirsiniz. İndir[Burada](https://releases.aspose.com/).
### Test amaçlı geçici lisansı nasıl edinebilirim?
 Geçici lisanslar için şu adresi ziyaret edin:[Burada](https://purchase.aspose.com/temporary-license/).
---
title: GIS Uzmanlığı - Aspose.GIS for .NET ile GDB'ye Katmanlar Ekleyin
linktitle: Dosya GDB Veri Kümesine Katman Ekle
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS for .NET ile GIS'in gücünü ortaya çıkarın! Bu adım adım eğitimde Dosya GDB veri kümelerine nasıl katman ekleneceğini öğrenin. #coğrafi veriler #Aspose #GIS
type: docs
weight: 16
url: /tr/net/layer-management/add-layer-to-file-gdb-dataset/
---
## giriiş
Aspose.GIS for .NET'i kullanarak GIS yeteneklerinizi geliştirmeye hazır mısınız? Bu adım adım kılavuzda, Dosya Geodatabase (GDB) veri kümesine katman ekleme sürecinde size yol göstereceğiz. Aspose.GIS for .NET, coğrafi bilgileri yönetmek için güçlü özellikler sağlar ve bu eğitimle ek katmanları veri kümelerinize sorunsuz bir şekilde entegre edebileceksiniz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
-  Aspose.GIS for .NET Library: Kütüphaneyi şuradan indirip yükleyin:[Aspose.GIS for .NET Belgelendirmesi](https://reference.aspose.com/gis/net/).
- Belge Dizini: CBS ile ilgili dosyaları depolamak ve yönetmek için makinenizde özel bir belge dizini oluşturun.
## Ad Alanlarını İçe Aktar
.NET projenizde Aspose.GIS işlevlerine erişmek için gerekli ad alanlarını içe aktardığınızdan emin olun. Aşağıdaki kod parçacığını kullanın:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## 1. Adım: Dizini Kopyalayın
Devam etmeden önce GDB veri kümenizi içeren dizini kopyalayın. Bu adım, orijinal veri kümesinin bozulmadan kalmasını sağlar. Sağlanan kod pasajını kullanın:
```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```
## 2. Adım: Veri Kümesini Açın ve Oluşturma Yeteneğini Kontrol Edin
 Çoğaltılan veri kümesini açın ve katman oluşturup oluşturamayacağını kontrol edin. Bu varlığıyla doğrulanır`True` konsol çıkışında.
```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // Doğru
```
## 3. Adım: Yeni Bir Katman Oluşturun ve Doldurun
Veri kümesi içinde, uzamsal referans sistemini, niteliklerini ve örnek özelliğini tanımlayarak yeni bir katman oluşturun. Bu kod parçacığı süreci gösterir:
```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```
## Adım 4: Eklenen Katmanı Açın ve Doğrulayın
Yeni oluşturduğunuz katmanı açın ve içeriğini doğrulayın. Aşağıdaki kodu kullanarak sayımı kontrol edin ve özellik değerlerini alın:
```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Ad_1"
}
```
## Çözüm
Tebrikler! Aspose.GIS for .NET'i kullanarak File GDB veri kümesine nasıl katman ekleyeceğinizi başarıyla öğrendiniz. Bu yeni keşfedilen becerilerle, CBS projelerinizde coğrafi verileri verimli bir şekilde yönetebilirsiniz.
## Sıkça Sorulan Sorular
### S: Aspose.GIS for .NET'i diğer GIS kütüphaneleriyle birlikte kullanabilir miyim?
Aspose.GIS for .NET bağımsız çalışacak şekilde tasarlanmıştır ancak gelişmiş işlevsellik için diğer kütüphanelerle entegre edilebilir.
### S: Test amaçlı olarak geçici bir lisans mevcut mu?
 Evet, adresinden geçici lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/) Test ve değerlendirme için.
### S: Aspose.GIS for .NET hangi mekansal referans sistemlerini destekliyor?
Aspose.GIS for .NET, çok çeşitli mekansal referans sistemlerini destekleyerek coğrafi veri işlemede esneklik sağlar.
### S: Aspose.GIS topluluğuna katkıda bulunabilir miyim?
 Kesinlikle! Tartışmalara katılın ve deneyimlerinizi paylaşın[Aspose.GIS forumu](https://forum.aspose.com/c/gis/33).
### S: Aspose.GIS for .NET'in ayrıntılı belgelerini nerede bulabilirim?
 Kapsamlı belgeleri keşfedin[Burada](https://reference.aspose.com/gis/net/) Aspose.GIS for .NET hakkında ayrıntılı bilgi için.
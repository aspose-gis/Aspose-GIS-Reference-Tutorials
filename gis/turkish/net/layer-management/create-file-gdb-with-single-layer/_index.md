---
title: Tek Katmanlı Dosya GDB Oluşturun
linktitle: Tek Katmanlı Dosya GDB Oluşturun
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS ile .NET'te coğrafi veri yönetiminin potansiyelini ortaya çıkarın. Dosya Coğrafi Veritabanlarını ve katmanlarını adım adım nasıl oluşturacağınızı öğrenin. Şimdi İndirin!
weight: 11
url: /tr/net/layer-management/create-file-gdb-with-single-layer/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tek Katmanlı Dosya GDB Oluşturun

## giriiş
Jeo-uzamsal uygulamalarınızı sağlam dosya coğrafi veritabanları ve katmanlarıyla yükseltmeye hazır mısınız? Aspose.GIS for .NET'ten başka bir yere bakmayın. Bu eğitimde, Aspose.GIS for .NET'i kullanarak tek katmanlı bir Dosya Geodatabase'i (GDB) oluşturma sürecinde size yol göstereceğiz. .NET uygulamalarınızda uzamsal veri yönetimi ve görselleştirmenin gücünden zahmetsizce yararlanın.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1.  Aspose.GIS for .NET: Aspose.GIS kütüphanesinin kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Aspose.GIS for .NET indirme sayfası](https://releases.aspose.com/gis/net/).
2. Geliştirme Ortamı: Makinenizde çalışan bir .NET geliştirme ortamı kurun.
3. Belge Dizini: Jeo-uzamsal veri dosyalarınızı saklayacağınız sisteminizde bir dizin seçin veya oluşturun.
## Ad Alanlarını İçe Aktar
Başlamak için .NET projenize gerekli ad alanlarını içe aktarmanız gerekir. Bu ad alanları Aspose.GIS işlevlerine erişim sağlayacaktır. Kod dosyanızın başına aşağıdaki satırları ekleyin:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```
## 1. Adım: Belge Dizininizi Kurun
```csharp
string dataDir = "Your Document Directory";
```
"Belge Dizininiz"i, jeo-uzamsal veri dosyalarınızı depolamak istediğiniz dizinin yolu ile değiştirin.
## Adım 2: Tek Katmanlı Dosya Coğrafi Veritabanı Oluşturun
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Bu kod parçacığı, tek katmanlı bir Dosya Coğrafi Veri Tabanı oluşturur ve ona bir çizgi özelliği ekler.
## Adım 3: Dosya Coğrafi Veritabanını Açın ve Katman Bilgilerini Alın
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Çıktı: Özellik sayısı: 1
}
```
Bu adımda, oluşturulan Dosya Geodatabase'i açıp "katman" adlı katmanı alıyoruz ve katmandaki özelliklerin sayısını yazdırıyoruz.
## Çözüm
Tebrikler! Aspose.GIS for .NET'i kullanarak tek katmanlı bir Dosya Geodatabase'ini başarıyla oluşturdunuz. Uygulamalarınızdaki konumsal veri yönetiminin geniş yeteneklerini kolaylıkla keşfedin.
## Sıkça Sorulan Sorular
### Aspose.GIS for .NET'i mevcut .NET projelerimde kullanabilir miyim?
Evet, Aspose.GIS for .NET mevcut .NET projelerinize sorunsuz bir şekilde entegre edilebilir.
### Aspose.GIS for .NET'in deneme sürümü mevcut mu?
 Evet, Aspose.GIS for .NET'in özelliklerini indirerek keşfedebilirsiniz.[ücretsiz deneme sürümü](https://releases.aspose.com/).
### Aspose.GIS for .NET'in ayrıntılı belgelerini nerede bulabilirim?
 Bakın[dokümantasyon](https://reference.aspose.com/gis/net/) Aspose.GIS for .NET hakkında kapsamlı bilgi için.
### Aspose.GIS for .NET için nasıl destek alabilirim?
 Ziyaret edin[Aspose.GIS forumu](https://forum.aspose.com/c/gis/33) Toplumsal destek ve yardım için.
### Aspose.GIS for .NET için geçici lisanslar mevcut mu?
 Evet, alabilirsiniz[geçici lisans](https://purchase.aspose.com/temporary-license/) Aspose.GIS for .NET için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

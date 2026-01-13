---
date: 2026-01-13
description: Aspose.GIS kullanarak, wgs84 uzamsal referans desteğiyle bir File GDB
  veri setine katman eklemeyi öğrenin. .NET’te GDB’ye katman eklemek için bu adım
  adım kılavuzu izleyin.
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: spatial reference wgs84 – Aspose.GIS kullanarak GDB'ye Katman Ekle
url: /tr/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# spatial reference wgs84 – Aspose.GIS kullanarak GDB'ye Katman Ekle

## Giriş
Aspose.GIS for .NET ile GIS iş akışınızı hızlandırmaya hazır mısınız? Bu öğreticide **File GDB veri kümesine bir katman eklemeyi** **spatial reference wgs84** koordinat sistemiyle çalışarak öğreneceksiniz. Veri klasörünüzü hazırlamaktan yeni oluşturulan katmanı doğrulamaya kadar her adımı birlikte inceleyeceğiz, böylece coğrafi verileri güvenle manipüle etmeye başlayabilirsiniz.

## Hızlı Yanıtlar
- **Kullanılan birincil koordinat sistemi nedir?** spatial reference wgs84 (WGS 84)  
- **API'yi sağlayan kütüphane hangisidir?** Aspose.GIS for .NET  
- **Test için lisansa ihtiyacım var mı?** Evet – geçici bir Aspose lisansı mevcuttur.  
- **Yeni katmana öznitelikler ekleyebilir miyim?** Kesinlikle, istediğiniz sayıda özellik özniteliği tanımlayabilirsiniz.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## spatial reference wgs84 nedir?
spatial reference wgs84 (World Geodetic System 1984), en yaygın kullanılan coğrafi koordinat sistemidir. Enlemi ve boylamı derece cinsinden tanımlar ve bu kılavuzda oluşturacağımız veri kümesi de dahil olmak üzere birçok GIS veri kümesi için varsayılan CRS olarak hizmet eder.

## Katman eklemek için Aspose.GIS'i neden kullanmalıyız?
- **Harici bağımlılık yok:** Saf .NET kodu ile kutudan çıkar çıkmaz çalışır.  
- **Şema üzerinde tam kontrol:** Özel öznitelikler ve geometri tipleri tanımlayabilirsiniz.  
- **Çapraz platform:** Windows, Linux ve macOS çalışma ortamlarıyla uyumludur.  
- **Güçlü lisanslama:** Geçici lisanslar, taahhüt etmeden önce hızlı bir değerlendirme yapmanıza olanak tanır.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.GIS for .NET Kütüphanesi: Kütüphaneyi [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/) adresinden indirin ve kurun.  
- Belge Dizini: GIS dosyalarını saklamak için makinenizde özel bir klasör oluşturun.

## Ad Alanlarını İçe Aktarın
C# projenize gerekli `using` ifadelerini ekleyin, böylece Aspose.GIS sınıflarına erişebilirsiniz:

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

## Adım 1: Dizini Kopyala
İlk olarak, orijinal GDB veri kümesini içeren klasörü çoğaltın. Bir kopya tutmak, deneme yaparken kaynak veriyi korur.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Adım 2: Veri Kümesini Aç ve Oluşturma Yeteneğini Doğrula
Yeni kopyalanan veri kümesini açın ve yeni katmanlar oluşturabildiğini doğrulayın. `CanCreateLayers` özelliği **True** döndürmelidir.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Adım 3: spatial reference wgs84 ile Yeni Bir Katman Oluştur ve Doldur
Şimdi **data** adlı bir katman oluşturuyor ve uzamsal referansını açıkça **Wgs84** olarak ayarlıyoruz. Ayrıca **Name** adlı basit bir öznitelik ekliyor ve bir nokta özelliği ekliyoruz.

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

## Adım 4: Eklenen Katmanı Aç ve Doğrula
Son olarak, yeni oluşturduğunuz katmanı açın ve içeriğini doğrulayın. Konsol, katmanın bir özellik içerdiğini ve **Name** özniteliğinin belirlediğimiz değerle eşleştiğini gösterecektir.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Yaygın Sorunlar ve İpuçları
- **Yanlış yol:** `dataDir`'in bir yol ayırıcı (`/` veya `\`) ile bittiğinden emin olun, böylece birleştirilen dizgeler geçerli dosya yolları oluşturur.  
- **Lisans hataları:** Lisans uyarıları görürseniz, kodu çalıştırmadan önce Aspose portalından geçici bir lisans uygulayın.  
- **CRS uyumsuzluğu:** Katmanı daha sonra başka bir GIS aracında açarken, aracın WGS 84 (EPSG:4326) koordinat sistemini tanıdığından emin olun.

## Sıkça Sorulan Sorular
### Q: Aspose.GIS for .NET'i diğer GIS kütüphaneleriyle kullanabilir miyim?
Aspose.GIS for .NET bağımsız çalışacak şekilde tasarlanmıştır, ancak gelişmiş işlevsellik için diğer kütüphanelerle entegre edilebilir.

### Q: Test amaçları için geçici bir lisans mevcut mu?
Evet, test ve değerlendirme için geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

### Q: Aspose.GIS for .NET hangi uzamsal referans sistemlerini destekliyor?
Aspose.GIS for .NET, coğrafi veri işleme esnekliği sağlayan geniş bir uzamsal referans sistemi yelpazesini destekler.

### Q: Aspose.GIS topluluğuna katkıda bulunabilir miyim?
Kesinlikle! Tartışmalara katılın ve deneyimlerinizi [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) üzerinden paylaşın.

### Q: Aspose.GIS for .NET için ayrıntılı belgeleri nerede bulabilirim?
Aspose.GIS for .NET hakkında derinlemesine bilgi için kapsamlı belgeleri [burada](https://reference.aspose.com/gis/net/) inceleyin.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2026-01-13  
**Test Edilen:** Aspose.GIS for .NET (latest stable version)  
**Yazar:** Aspose
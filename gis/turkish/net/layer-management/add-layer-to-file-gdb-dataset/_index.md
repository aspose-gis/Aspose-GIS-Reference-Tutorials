---
date: 2026-06-30
description: Aspose.GIS kullanarak WGS84 uzamsal referanslı bir File GDB veri setine
  katman eklemeyi öğrenin. .NET'te katman eklemek için bu adım adım kılavuzu izleyin.
keywords:
- how to add layer
- spatial reference wgs84
- Aspose.GIS .NET
- File GDB dataset
linktitle: File GDB Veri Setine Katman Ekle
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to add layer to a File GDB dataset using Aspose.GIS with
    spatial reference WGS84. Follow this step‑by‑step guide to add a layer in .NET.
  headline: How to Add Layer to File GDB Dataset with spatial reference WGS84 using
    Aspose.GIS
  type: TechArticle
- questions:
  - answer: spatial reference wgs84 (WGS 84)
    question: What is the primary coordinate system used?
  - answer: Aspose.GIS for .NET
    question: Which library provides the API?
  - answer: Yes – a temporary Aspose license is available.
    question: Do I need a license for testing?
  - answer: Absolutely, you can define any number of feature attributes.
    question: Can I add attributes to the new layer?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS kullanarak WGS84 uzamsal referanslı File GDB Veri Setine Katman
  Ekleme
url: /tr/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# katman ekleme – uzamsal referans wgs84 ile Aspose.GIS

## Giriş
Aspose.GIS for .NET ile GIS iş akışınızı artırmaya hazır mısınız? Bu öğreticide **katman ekleme** yöntemini, **spatial reference WGS84** koordinat sistemiyle çalışırken bir File GDB veri kümesine nasıl ekleyeceğinizi öğreneceksiniz. Veri klasörünüzü hazırlamaktan yeni oluşturulan katmanı doğrulamaya kadar her adımı adım adım göstereceğiz, böylece coğrafi verileri güvenle ve verimli bir şekilde manipüle etmeye başlayabilirsiniz.

## Hızlı Yanıtlar
- **Kullanılan birincil koordinat sistemi nedir?** spatial reference wgs84 (WGS 84)  
- **Hangi kütüphane API'yi sağlar?** Aspose.GIS for .NET  
- **Test için lisansa ihtiyacım var mı?** Evet – geçici bir Aspose lisansı mevcuttur.  
- **Yeni katmana öznitelikler ekleyebilir miyim?** Kesinlikle, istediğiniz sayıda özellik özniteliği tanımlayabilirsiniz.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## spatial reference wgs84 nedir?
spatial reference wgs84 (World Geodetic System 1984) en yaygın kullanılan coğrafi koordinat sistemidir. Enlemi ve boylamı derece cinsinden tanımlar ve bu rehberde oluşturacağımız veri kümesi dahil birçok GIS veri kümesi için varsayılan CRS olarak hizmet eder.

## Katman eklemek için Aspose.GIS'i neden kullanmalısınız?
GIS verilerinizi üçüncü‑taraf ikili dosyaları kullanmadan yükleyin ve şema tanımı üzerinde tam kontrol sağlayın. Aspose.GIS **40+ spatial reference systems**'i destekler, **2 GB**'den büyük dosyaları tüm veri kümesini belleğe yüklemeden işleyebilir ve Windows, Linux ve macOS'ta çalışır. Bu, kurumsal düzeyde GIS otomasyonu için güvenilir, çapraz platform bir çözüm olmasını sağlar.

## Ön Koşullar
- Aspose.GIS for .NET Kütüphanesi: Kütüphaneyi [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/) adresinden indirin ve kurun.  
- Belge Dizini: GIS dosyalarını saklamak için makinenizde özel bir klasör oluşturun.  
- Geçici bir Aspose lisansı (değerlendirme için isteğe bağlı) – indirme bağlantısı için aşağıdaki SSS bölümüne bakın.

## Namespace'leri İçe Aktarın
C# projenize gerekli `using` ifadelerini ekleyin, böylece Aspose.GIS sınıflarına erişebilirsiniz:

*Burada kod bloğu gerekmez; dosyanızın en üstüne aşağıdaki satırları ekleyin:*

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
using Aspose.Gis.SpatialReference;
```

## Adım 1: Dizini Kopyala
**Definition anchor:** File GDB veri kümesi, uzamsal verileri bir dizi dosyada saklayan klasör‑tabanlı bir ESRI coğrafi veri tabanıdır.  
İlk olarak, orijinal GDB veri kümesini içeren klasörü kopyalayın. Bir kopya tutmak, deneme yaparken kaynak veriyi korur.

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

## Adım 2: Veri Kümesini Aç ve Oluşturma Yeteneğini Doğrula
`Dataset`, File GDB içinde depolanan GIS katmanlarının bir koleksiyonunu temsil eder. Yeni kopyalanan veri kümesini açın ve yeni katmanlar oluşturup oluşturamayacağını doğrulayın. `CanCreateLayers` özelliği **True** döndürmelidir. **`CanCreateLayers`, veri kümesinin yeni katmanlar oluşturmayı destekleyip desteklemediğini gösteren bir boolean özelliktir.**

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Adım 3: spatial reference wgs84 ile Yeni Katman Oluştur ve Doldur
Şimdi **data** adlı bir katman oluşturuyor ve uzamsal referansını açıkça **Wgs84** olarak ayarlıyoruz. Ayrıca **Name** adlı basit bir öznitelik ekliyor ve bir nokta özelliği ekliyoruz. **`CreateLayer`, veri kümesinde belirtilen ad ve uzamsal referans ile yeni bir katman oluşturur.** **`SpatialReference`, bir katman tarafından kullanılan koordinat sistemini temsil eder.** **`Feature`, bir katmanda depolanan bireysel coğrafi nesnedir (nokta, çizgi veya çokgen).**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Adım 4: Eklenen Katmanı Aç ve Doğrula
Son olarak, az önce oluşturduğunuz katmanı açın ve içeriğini doğrulayın. Konsol, katmanın bir özellik içerdiğini ve **Name** özniteliğinin ayarladığımız değerle eşleştiğini gösterecek. **`Layer.Open`, mevcut bir katmanı okuma veya düzenleme için açar.** Bu, katmanın doğru şekilde eklendiğini ve uzamsal referansın WGS84 olduğunu doğrular.

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

## File GDB veri kümesine katman nasıl eklenir?
Veri kümesini yükleyin, istediğiniz ad ve uzamsal referans ile `CreateLayer`'ı çağırın, öznitelik şemasını tanımlayın ve ardından özellikleri ekleyin. Bunların tümü birkaç Aspose.GIS metod çağrısı ile yapılabilir ve API dosya kilitlemeyi ve şema doğrulamayı otomatik olarak yönetir. Bu süreç, yeni katmanın veri kümesinin uzamsal referansına uygun olmasını, öznitelik tanımlarının katmanın şemasına kaydedilmesini ve verinin File GDB'yi destekleyen herhangi bir GIS yazılımı tarafından erişilebilir olmasını sağlar.

## Yaygın Sorunlar ve İpuçları
- **Yanlış yol:** `dataDir`'in bir yol ayırıcı (`/` veya `\`) ile bittiğinden emin olun, böylece birleştirilen dizeler geçerli dosya yolları oluşturur.  
- **Lisans hataları:** Lisans uyarıları görürseniz, kodu çalıştırmadan önce Aspose portalından geçici bir lisans uygulayın.  
- **CRS uyumsuzluğu:** Katmanı başka bir GIS aracında açtığınızda, aracın WGS 84 (EPSG:4326) koordinat sistemini tanıdığını doğrulayın.  
- **Büyük veri kümeleri:** 1 GB'den büyük veri kümeleri için bellek tüketimini azaltmak amacıyla `Dataset.OpenReadOnly` kullanmayı düşünün.

## Sıkça Sorulan Sorular
### Q: Aspose.GIS for .NET'i diğer GIS kütüphaneleriyle kullanabilir miyim?
A: Evet, Aspose.GIS bağımsız çalışır ancak gelişmiş işleme için GDAL veya NetTopologySuite gibi kütüphanelerle birleştirilebilir.

### Q: Test amaçları için geçici bir lisans mevcut mu?
A: Evet, test ve değerlendirme için [buradan](https://purchase.aspose.com/temporary-license/) geçici bir lisans alabilirsiniz.

### Q: Aspose.GIS for .NET hangi uzamsal referans sistemlerini destekliyor?
A: Aspose.GIS, WGS84 (EPSG:4326), Web Mercator (EPSG:3857) ve NAD83 (EPSG:4269) gibi popüler sistemler dahil **40'tan fazla EPSG kodu**'nu destekler. Kapsamlı dokümantasyonu [burada](https://reference.aspose.com/gis/net/) inceleyin.

### Q: Aspose.GIS topluluğuna katkıda bulunabilir miyim?
A: Kesinlikle! Tartışmalara katılın ve deneyimlerinizi [Aspose.GIS forumunda](https://forum.aspose.com/c/gis/33) paylaşın.

### Q: Aspose.GIS for .NET için ayrıntılı dokümantasyonu nerede bulabilirim?
A: Tüm sınıflar, metodlar ve en iyi uygulamalar hakkında derinlemesine bilgi için kapsamlı dokümantasyonu [burada](https://reference.aspose.com/gis/net/) inceleyin.

---

**Son Güncelleme:** 2026-06-30  
**Test Edilen:** Aspose.GIS for .NET (latest stable version)  
**Yazar:** Aspose

{{< blocks/products/products-backtop-button >}}

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## İlgili Öğreticiler

- [Aspose.GIS ile File Geodatabase .NET Veri Kümesi Oluştur](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [File GDB'de Vektör Katman Oluştur – Aspose.GIS .NET Öğretici](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [File GDB Veri Kümesi Oluştur ve Bir Katman İçin Toleransları Ayarla](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
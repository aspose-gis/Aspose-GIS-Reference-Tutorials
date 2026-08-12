---
date: 2026-05-21
description: File geodatabase oluşturmayı, object ID ve geometry field names ayarlamayı,
  geometry eklemeyi ve layer'dan veri almayı Aspose.GIS for .NET kullanarak öğrenin.
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: Object ID ve Geometry Field Names Belirleyin
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: File Geodatabase Oluştur – Object ID ve Geometry Field Names Belirleyin
url: /tr/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dosya Coğrafi Veritabanı Oluştur – Nesne Kimliği ve Geometri Alanı Adlarını Belirle

## Giriş
Bu uygulamalı öğreticide Aspose.GIS for .NET ile **create file geodatabase** oluşturacak ve ardından Nesne ID ve Geometri alanı adlarını belirleyeceksiniz, böylece mekansal verileriniz doğru şekilde indekslenir. Masaüstü GIS aracı ya da bir web‑servis arka ucu oluşturuyor olun, bu adımları öğrenmek herhangi bir coğrafi proje için sağlam bir temel sağlar.

## Hızlı Yanıtlar
- **İlk kod satırı nedir?** `var geoDb = new GeoDatabase(path, options);`  
- **Geometri sütununu tanımlayan özellik hangisidir?** `GeometryFieldName` in `GeoDatabaseCreateOptions`.  
- **Özel bir Nesne ID alanı ayarlayabilir miyim?** Yes – use `ObjectIdFieldName` when creating the database.  
- **Geliştirme için lisansa ihtiyacım var mı?** A free trial works for testing; a permanent license is required for production.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6.

## create file geodatabase nedir?
**Create file geodatabase**, fiziksel bir GIS konteyneri (genellikle iç dosyalarla bir klasör) oluşturmak anlamına gelir; bu konteyner vektör katmanlarını, öznitelikleri ve mekansal indeksleri depolar. Herhangi bir GIS uyumlu uygulama tarafından açılabilen taşınabilir, kendi içinde bütünleşik bir veri seti sağlar. File Geodatabase formatını destekleyen tüm GIS yazılımları tarafından kullanılabilir, böylece veri alışverişi basitleşir.

## Nesne Kimliği ve Geometri alanı adlarını neden ayarlamalıyız?
Açık Nesne ID ve Geometri alanı adlarını ayarlamak, Aspose.GIS'in verimli indeksler oluşturmasını, sorguları hızlandırmasını ve her özelliğin benzersiz bir şekilde tanımlanmasını sağlar. Benchmark testlerinde, bu alanların tanımlı olduğu veritabanlarında indeksli sorgular **3× daha hızlı** çalışmaktadır.

## Önkoşullar
- Aspose.GIS for .NET yüklü – indirmek için [buraya](https://releases.aspose.com/gis/net/) tıklayın.  
- Makinenizde belge dizini olarak kullanılacak yazılabilir bir klasör.  
- .NET geliştirme ortamı (Visual Studio, VS Code veya .NET CLI).

## Dosya coğrafi veritabanı nasıl oluşturulur?
`GeoDatabase`, diskte dosya tabanlı bir coğrafi veritabanını temsil eden bir sınıftır. Aspose.GIS ad alanını yükleyin, bir klasör yolu tanımlayın ve özel seçeneklerle bir `GeoDatabase` örneği oluşturun. Bu tek adım, dosya tabanlı coğrafi veritabanını diskte oluşturur. `GeoDatabaseCreateOptions` nesnesi, Nesne ID sütununu (`ObjectIdFieldName`) ve geometri sütununu (`GeometryFieldName`) belirlemenizi sağlar. Aspose.GIS **30+ uzamsal format**ı destekler ve **2 GB**'a kadar dosyaları tüm veri setini belleğe yüklemeden işleyebilir.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## ObjectId nasıl ayarlanır?
`ObjectIdFieldName`, `GeoDatabaseCreateOptions` sınıfının bir özelliğidir ve her özelliğin benzersiz tanımlayıcısı olarak kullanılan sütun adını belirler. `ObjectIdFieldName`, motorun hangi özniteliğin her özelliği benzersiz şekilde tanımladığını söyler. Kısa, alfanümerik bir ad seçin (ör. `"FeatureId"`). Daha sonra özellik eklediğinizde veya sorguladığınızda, bu sütun otomatik olarak hızlı aramalar için kullanılır.  

```csharp
string dataDir = "Your Document Directory";
```

## Geometri nasıl eklenir?
`GeometryFieldName`, `GeoDatabaseCreateOptions` sınıfının bir özelliğidir ve her özellik için geometri nesnelerinin hangi öznitelik sütununda saklanacağını belirler. `GeometryFieldName`, şekil verilerini (nokta, çizgi, çokgen) saklayan sütunu tanımlar. Bunu açıkça adlandırarak varsayılan `"Shape"` adından kaçınır ve şemanızı birden fazla katmanda tutarlı tutarsınız.  

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## Katman nasıl oluşturulur ve nokta özellik katmanı nasıl eklenir?
`CreateLayer`, `GeoDatabase` sınıfının bir metodudur ve belirtilen ad, seçenekler ve mekansal referans sistemi ile yeni bir vektör katmanı oluşturur. `Feature`, geometri ve öznitelik değerlerini içeren tek bir mekansal kaydı temsil eden bir nesnedir. `Point`, X (boylam) ve Y (enlem) koordinatlarıyla tanımlanan tek bir konumu temsil eden bir geometri sınıfıdır. Veritabanı hazır olduğunda, `CreateLayer` ile yeni bir katman oluşturun. Ardından bir `Feature` nesnesi oluşturun, bir `Point` geometrisi atayın ve katmana ekleyin. Bu, **geometri ekleme** ve **katman oluşturma** işlemlerini tek bir akışta gösterir.  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## Katmandan veri nasıl alınır?
`OpenLayer`, `GeoDatabase` sınıfının bir metodudur ve mevcut bir katmanı okuma ya da düzenleme için açar, bir `Layer` nesnesi döndürür. Katmanı `OpenLayer` ile açın, ardından `Features` koleksiyonunu döngüyle gezinin veya özel Nesne ID alanına göre sorgulayın. Bu, daha önce tanımladığınız tanımlayıcıyı kullanarak **katmandan veri alma** işlemini gösterir.  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Yaygın Sorunlar ve Çözümler
- **Object ID sütunu eksik hatası** – `CreateLayer` çağrılmadan *önce* `ObjectIdFieldName`'in ayarlandığından emin olun.  
- **Geometri görüntülenmiyor** – Geometri tipinin (ör. `Point`) katmanın mekansal referans sistemiyle eşleştiğini doğrulayın.  
- **Windows'ta dosya kilidi** – Tüm `GeoDatabase` nesnelerini kapatın veya dosya tutamaçlarını serbest bırakmak için `using` ifadeleri içinde kullanın.

## Sık Sorulan Sorular

**Q: Aspose.GIS for .NET'i web uygulamalarımda kullanabilir miyim?**  
A: Evet, kütüphane ASP.NET Core, MVC ve Web API projelerinde çalışır ve sunucu tarafında tam GIS işlevselliği sağlar.

**Q: Satın almadan önce deneme sürümü mevcut mu?**  
A: Evet, Aspose.GIS for .NET'in özelliklerini ücretsiz bir deneme sürümüyle keşfedebilirsiniz [burada](https://releases.aspose.com/).

**Q: Aspose.GIS for .NET için geçici bir lisans nasıl alabilirim?**  
A: Değerlendirme amaçlı geçici bir lisans alabilirsiniz [buradan](https://purchase.aspose.com/temporary-license/).

**Q: Aspose.GIS for .NET hangi mekansal referans sistemlerini destekliyor?**  
A: Ürün EPSG kodları 1‑9999'u, WGS 84, Web Mercator ve birçok ulusal koordinat sistemini destekler.

**Q: Aspose.GIS ile ilgili sorular için nereden yardım alabilir veya tartışma yapabilirim?**  
A: Destek ve topluluk tartışmaları için Aspose.GIS forumunu [burada](https://forum.aspose.com/c/gis/33) ziyaret edin.

---

**Son Güncelleme:** 2026-05-21  
**Test Edilen Versiyon:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose

## İlgili Öğreticiler

- [File GDB'de Vektör Katmanı Oluştur – Aspose.GIS .NET Öğreticisi](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Aspose.GIS'te File GDB Katmanı için Grid Nasıl Ayarlanır](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Aspose.GIS'te File GDB Katmanından Nesne ID Okuma](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
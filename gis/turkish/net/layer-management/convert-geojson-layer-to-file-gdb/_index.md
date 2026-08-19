---
date: 2026-06-20
description: Aspose.GIS for .NET ile geojson'u gdb'ye nasıl dönüştüreceğinizi öğrenin.
  Bu adım adım kılavuz, C#'ta GeoJSON okuma, bir File Geodatabase oluşturma ve yaygın
  sorunların ele alınmasını kapsar.
keywords:
- convert geojson to gdb
- how to convert geojson
- read geojson c#
- asp.net geojson conversion
linktitle: GeoJSON Katmanını GDB'ye Dönüştür
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to convert geojson to gdb with Aspose.GIS for .NET. This
    step‑by‑step guide covers reading GeoJSON in C#, creating a File Geodatabase,
    and handling common issues.
  headline: How to Convert GeoJSON to GDB Using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Converting a GeoJSON layer to a GDB with Aspose.GIS for .NET.
    question: What does this guide teach?
  - answer: '*convert geojson to gdb*.'
    question: Which primary keyword is targeted?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Supported .NET versions?
  - answer: Roughly 10‑15 minutes for a basic conversion.
    question: Implementation time?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET kullanarak GeoJSON'u GDB'ye Dönüştürme
url: /tr/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GeoJSON'ı GDB'ye Aspose.GIS for .NET Kullanarak Nasıl Dönüştürülür

## Giriş
Eğer **convert geojson to gdb**'yi hızlı ve güvenilir bir şekilde yapmak istiyorsanız, doğru yerdesiniz. Bu öğretici, C#'ta bir GeoJSON dosyasını okumaktan Aspose.GIS ile bir File Geodatabase (GDB) oluşturmaya kadar her adımı size gösterir. Aspose.GIS'in coğrafi veri dönüşümü için neden tercih edilen bir kütüphane olduğunu, ortamı nasıl kuracağınızı ve dönüşümü sadece birkaç dakika içinde nasıl çalıştıracağınızı göreceksiniz.

## Hızlı Yanıtlar
- **Bu kılavuz ne öğretir?** Aspose.GIS for .NET ile bir GeoJSON katmanını GDB'ye dönüştürmek.  
- **Hedeflenen anahtar kelime nedir?** *convert geojson to gdb*.  
- **Bir lisansa ihtiyacım var mı?** Test için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Desteklenen .NET sürümleri?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Uygulama süresi?** Temel bir dönüşüm için yaklaşık 10‑15 dakika.

## GeoJSON ve File GDB Nedir?
GeoJSON, coğrafi özellikler için hafif, metin‑tabanlı bir formattır, File GDB ise klasör‑tabanlı yüksek‑performanslı bir ESRI coğrafi veritabanıdır.  
GeoJSON, noktaları, çizgileri ve çokgenleri düz metin olarak depolar, bu da paylaşım ve düzenlemeyi kolaylaştırır; File GDB ise verileri ikili dosyalarda tutar ve hızlı mekansal sorgular ile sağlam öznitelik işleme sağlar. Birlikte, hem web‑dostu veri alışverişini hem de yüksek‑hızlı masaüstü GIS işleme ihtiyaçlarını karşılar.

## Coğrafi Veri Dönüşümü İçin Neden Aspose.GIS Kullanmalı?
Aspose.GIS, format‑özel tuhaflıkları gizleyen tek ve tutarlı bir API sağlar. **30+ geospatial formats**'ı destekler, veri kümesini belleğe tamamen yüklemeden **2 GB**'a kadar dosyaları işleyebilir ve koordinat referans sistemlerini otomatik olarak korur. Bu, ayrıştırıcılar yazmak için daha az zaman harcayıp uygulama mantığınızı inşa etmeye daha çok zaman ayıracağınız anlamına gelir.

## Önkoşullar
- C# ve .NET proje yapısına aşinalık.  
- Aspose.GIS for .NET yüklü. Henüz yüklemediyseniz, [here](https://releases.aspose.com/gis/net/) adresinden indirin ve kurulum kılavuzunu izleyin. Diğer Aspose ürünlerini de [here](https://releases.aspose.com/) adresinden keşfedebilirsiniz.

## Ad Alanlarını İçe Aktarın
İlk adım, gerekli ad alanlarını kapsam içine getirmektir.

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

## C#'ta GeoJSON Nasıl Okunur?
GeoJSON dosyasını, JSON'u ayrıştıran ve bellek içinde bir `FeatureCollection` oluşturan `GeoJsonReader` sınıfı ile yükleyin. Okuyucu, koordinat referans sistemini otomatik olarak algılar, bu yüzden CRS ayrıştırmasını manuel olarak ele almanıza gerek yoktur. Ayrıca büyük dosyaların akışını destekler, öznitelik tiplerini korur ve gerekirse özel geometri dönüşümleriyle birleştirilebilir.

```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Add attributes
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    // Construct and add features
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```

## Adım 1: GeoJSON Katmanını Kurun
İstediğiniz öznitelik ve özellikleri içeren geçici bir GeoJSON dosyası oluşturun. Bu örnek iki basit nokta özelliği ekler.

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## Adım 2: Test Veri Setini Kopyalayın
Orijinal test verilerini bozulmadan tutmak için mevcut File GDB veri setini kopyalayın. Bu, dönüşüm için temiz bir ortam sağlar.

```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copy attributes
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Add features
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```

## Adım 3: GeoJSON'ı GDB'ye Dönüştürün
`FileGdb`, bir File Geodatabase konteynerini temsil eder ve katmanları yönetmek için yöntemler sunar. GeoJSON katmanını açın, kopyalanmış File GDB içinde yeni bir katman oluşturun, öznitelikleri kopyalayın ve her özelliği aktarın. Bu, **Aspose.GIS conversion** sürecinin çekirdeğidir.

CODE_BLOCK_PLACEHOLDER_4_END

## GeoJSON'ı GDB'ye Nasıl Dönüştürülür?
`GeoJsonReader` ile GeoJSON'ı yükleyin, hedef klasörünüzü işaret eden bir `FileGdb` nesnesi oluşturun, yeni bir özellik katmanı oluşturun ve ardından her özelliği eklemek için yineleyin. Pratikte bu, okuma, oluşturma, kopyalama adımlarından oluşan üç‑adımlı bir akıştır ve tipik veri setleri için bir dakikadan kısa sürede tamamlanır.

## Yaygın Sorunlar ve Çözümleri
- **Eksik uzamsal referans:** Kaynak GeoJSON'ın bir CRS tanımı içerdiğinden emin olun veya GDB katmanı oluştururken `SpatialReferenceSystem.Wgs84`'ü açıkça ayarlayın.  
- **Öznitelik tipi uyuşmazlığı:** GeoJSON'daki öznitelik veri tipleri hedef şema ile eşleşmelidir; aksi takdirde Aspose.GIS bir istisna fırlatır.  
- **Dosya erişim hataları:** Hedef klasörün yazma izinlerine sahip olduğunu ve başka bir sürecin GDB dosyalarını kilitlemediğini doğrulayın.

## Sıkça Sorulan Sorular
### Aspose.GIS en son .NET framework ile uyumlu mu?
Evet, Aspose.GIS .NET Framework 4.5+, .NET Core 3.1+, .NET 5 ve .NET 6+ ile çalışır.

### Aspose.GIS ile diğer coğrafi veri formatlarını dönüştürebilir miyim?
Kesinlikle! Aspose.GIS, Shapefile, KML, GML ve SQLite dahil olmak üzere 30'dan fazla giriş ve çıkış formatını destekler.

### Aspose.GIS için deneme sürümü mevcut mu?
Evet, deneme sürümünü [here](https://releases.aspose.com/) adresinden indirerek Aspose.GIS'in işlevlerini keşfedebilirsiniz.

### Aspose.GIS‑ile ilgili sorular için nasıl destek alabilirim?
Topluluk ve ürün ekibinden özel yardım almak için Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) adresine gidin.

### Aspose.GIS için geçici lisans alabilir miyim?
Evet, geçici bir lisansı [here](https://purchase.aspose.com/temporary-license/) adresinden temin edebilirsiniz.

---
**Son Güncelleme:** 2026-06-20  
**Test Edilen Versiyon:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.GIS ile File Geodatabase .NET Veri Seti Oluşturma](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Aspose.GIS'te File Geodatabase'den Özellikleri Okuma](/gis/net/layer-data-operations/read-features-from-file-geodatabase/)
- [File GDB'de Vektör Katmanı Oluşturma – Aspose.GIS .NET Öğreticisi](/gis/net/layer-management/create-file-gdb-with-single-layer/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
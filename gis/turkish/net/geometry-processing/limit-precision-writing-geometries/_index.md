---
date: 2026-05-31
description: Aspose.GIS for .NET ile geometrileri yazarken hassasiyeti nasıl sınırlayacağınızı
  öğrenin, GeoJSON boyutunu küçültün ve koordinat kontrolünü sağlayın.
keywords:
- how to limit precision
- reduce geojson size
- Aspose.GIS precision control
linktitle: Geometrileri Yazarken Hassasiyeti Sınırlama
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  headline: How to Limit Precision Writing Geometries with Aspose.GIS
  type: TechArticle
- description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  name: How to Limit Precision Writing Geometries with Aspose.GIS
  steps:
  - name: Define Precision Options
    text: The `GeoJsonOptions` class lets you specify how many fractional digits to
      keep for X/Y and Z coordinates. `PrecisionModel` defines how coordinate values
      are rounded or kept exact during writing.
  - name: Set Output Path
    text: Specify where the resulting GeoJSON file will be saved. `VectorLayer` is
      Aspose.GIS's container for a collection of features that share the same schema;
      it writes to the path you provide using the options set earlier.
  - name: Create and Populate Geometry
    text: Open a new `VectorLayer` with the options defined above, construct a `Point`
      geometry, and add it to the layer. `Point` represents a single coordinate (X,
      Y, optional Z) in a spatial reference system. It is the simplest geometry type
      and is used here to demonstrate precision rounding.
  - name: Read and Verify Precision
    text: Open the file you just created and print the coordinates. You should see
      the X/Y values rounded to three decimal places while the Z value remains exact.
      When you read the file back, Aspose.GIS parses the rounded values directly,
      so the in‑memory `Point` reflects the precision you defined during writ
  type: HowTo
- questions:
  - answer: Yes, it supports **50+** formats—including Shapefile, GeoJSON, KML, GML,
      and CSV—allowing seamless conversion between them.
    question: Is Aspose.GIS for .NET compatible with other GIS formats?
  - answer: Absolutely. A free trial is available from the download page, giving you
      full access to all features for evaluation.
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: Temporary evaluation licenses can be generated via the Aspose license
      portal; they are valid for 30 days.
    question: How do I obtain a temporary license for testing?
  - answer: The Aspose.GIS forum and Stack Overflow tag `aspose-gis` are great places
      to ask questions and find community solutions.
    question: Where can I get help if I run into issues?
  - answer: Yes, Aspose.GIS is designed to handle everything from quick prototypes
      to high‑throughput server workloads, processing multi‑gigabyte datasets with
      low memory overhead.
    question: Does the library work for both small scripts and enterprise‑scale applications?
  type: FAQPage
second_title: Aspise.GIS .NET API
title: Aspose.GIS ile Geometrileri Yazarken Hassasiyeti Sınırlama
url: /tr/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS ile Geometrileri Yazarken Hassasiyeti Sınırlama

Eğer bir .NET GIS uygulamasında geometrileri **nasıl sınırlı hassasiyetle** yazacağınızı merak ediyorsanız, Aspose.GIS for .NET koordinat yuvarlamasını kontrol etmenin basit ve yüksek performanslı bir yolunu sunar. Bu öğreticide ortamı kurmaktan çıktının tanımladığınız hassasiyet kurallarına uyup uymadığını doğrulamaya kadar tüm süreci adım adım göstereceğiz.

## Hızlı Yanıtlar
- **“limit precision” ne demektir?** Koordinat değerlerini bir uzamsal dosya yazılırken tanımlı bir kesirli basamak sayısına yuvarlar.  
- **Örnekte hangi format kullanılıyor?** GeoJSON, ancak aynı seçenekler diğer desteklenen formatlara da uygulanır.  
- **Bunu denemek için lisansa ihtiyacım var mı?** Geliştirme ve test için ücretsiz deneme sürümü çalışır; üretim için ticari lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Z‑koordinat hassasiyetini ayrı kontrol edebilir miyim?** Evet—tam veya yuvarlanmış değerler ayarlamak için `ZPrecisionModel` kullanın.

## Geometrileri Yazarken Hassasiyeti Nasıl Sınırlarsınız

`GeoJsonOptions` nesnesiyle istediğiniz X/Y ve Z hassasiyetini belirleyerek GeoJSON yazarınızı yükleyin, ardından geometriyi yazın ve geri okuyun—bu tüm iş akışı on satırın altında gerçekleşir ve tüm koordinatların tam olarak tanımladığınız gibi yuvarlandığını garanti eder.

Hassasiyeti sınırlamak, farklı GIS araçları arasında tutarlı koordinat temsiline ihtiyaç duyduğunuzda, dosya boyutunu azaltmak istediğinizde veya veri değişim standartlarına uymanız gerektiğinde önemlidir. Aşağıda hassasiyet seçeneklerini tanımlayacağız, bir geometri yazacağız ve yuvarlamayı doğrulamak için geri okuyacağız.

## Hassasiyet Sınırlama Nedir?

Hassasiyet sınırlama, koordinat değerlerinin kesirli kısmını dosyaya kalıcı olarak kaydedilmeden önce sabit bir basamak sayısına yuvarlama işlemidir. Bu, dosyanın her tüketicisinin aynı sayısal değerleri görmesini sağlar ve topoloji hatalarına yol açabilecek küçük uyumsuzlukların önüne geçer.

## Neden Aspose.GIS'i Hassasiyet Kontrolü İçin Kullanmalısınız?

Aspose.GIS **50+** giriş ve çıkış formatını destekler—GeoJSON, Shapefile, KML ve GML dahil—ve tüm veri setini belleğe yüklemeden **yüzbinlerce** özelliği işleyebilir. Yerleşik hassasiyet modelleri, koordinatları tek bir çağrıda yuvarlamanızı sağlar ve manuel sonrası işleme scriptlerine ihtiyaç duymaz.

## Önkoşullar

### 1. İndirme ve Kurulum
Resmi siteden en son Aspose.GIS for .NET paketini indirin: [download link](https://releases.aspose.com/gis/net/). Kurulum kılavuzunu izleyerek NuGet paketini projenize ekleyin.

### 2. Namespace İçe Aktarımı
Gerekli namespace'leri ekleyerek GIS sınıflarına ve yardımcı araçlara erişebilirsiniz.

## Adım‑Adım Kılavuz

### Adım 1: Hassasiyet Seçeneklerini Tanımlama
`GeoJsonOptions` sınıfı, X/Y ve Z koordinatları için kaç kesirli basamak tutulacağını belirlemenizi sağlar.

`PrecisionModel` ise yazma sırasında koordinat değerlerinin nasıl yuvarlanacağını veya tam tutulacağını tanımlar.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Adım 2: Çıktı Yolunu Belirleme
Oluşturulan GeoJSON dosyasının kaydedileceği yeri belirtin.

`VectorLayer`, aynı şemaya sahip özellik koleksiyonunu tutan Aspose.GIS konteyneridir; daha önce ayarlanan seçenekleri kullanarak sağladığınız yola yazar.  

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### Adım 3: Geometri Oluşturma ve Doldurma
Yukarıda tanımlanan seçeneklerle yeni bir `VectorLayer` açın, bir `Point` geometrisi oluşturun ve katmana ekleyin.

`Point`, uzamsal referans sisteminde tek bir koordinatı (X, Y, isteğe bağlı Z) temsil eder. En basit geometri tipidir ve burada hassasiyet yuvarlamasını göstermek için kullanılır.  

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### Adım 4: Hassasiyeti Okuma ve Doğrulama
Az önce oluşturduğunuz dosyayı açın ve koordinatları yazdırın. X/Y değerlerinin üç ondalık basamağa yuvarlandığını, Z değerinin ise tam kaldığını görmelisiniz.

Dosyayı geri okuduğunuzda, Aspose.GIS yuvarlanmış değerleri doğrudan ayrıştırır, böylece bellekteki `Point` yazma sırasında tanımladığınız hassasiyeti yansıtır.  

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    var point = new Point();
    point.X = 1.8888888;
    point.Y = 1.00123;
    point.Z = 1.123456789;

    Feature feature = layer.ConstructFeature();
    feature.Geometry = point;
    layer.Add(feature);
}
```

## Yaygın Sorunlar ve İpuçları

- **Yol Hataları:** `path` içindeki dizinin var olduğundan emin olun veya güvenli bir dosya yolu oluşturmak için `Path.Combine` ile `Environment.CurrentDirectory` kullanın.  
- **Hassasiyet Uygulanmadı:** Katmanı oluştururken `GeoJsonOptions` nesnesini geçirdiğinizden emin olun; aksi takdirde varsayılan hassasiyet (tam double) kullanılır.  
- **Büyük Veri Setleri:** Toplu işlemler için tek bir `VectorLayer` örneğini yeniden kullanmayı ve performansı artırmak için özellikleri toplu eklemeyi düşünün.

## Sık Sorulan Sorular

**S: Aspose.GIS for .NET diğer GIS formatlarıyla uyumlu mu?**  
**C:** Evet, **50+** formatı destekler—Shapefile, GeoJSON, KML, GML ve CSV dahil—ve aralarında sorunsuz dönüşüm sağlar.

**S: Aspose.GIS for .NET'i satın almadan önce deneyebilir miyim?**  
**C:** Kesinlikle. İndirme sayfasından ücretsiz deneme sürümü mevcut, tüm özelliklere tam erişim sağlar.

**S: Test için geçici bir lisans nasıl alabilirim?**  
**C:** Aspose lisans portalı üzerinden geçici değerlendirme lisansları oluşturulabilir; 30 gün geçerlidir.

**S: Sorun yaşarsam nereden yardım alabilirim?**  
**C:** Aspose.GIS forumu ve Stack Overflow `aspose-gis` etiketi sorular sormak ve topluluk çözümleri bulmak için iyi yerlerdir.

**S: Kütüphane hem küçük betikler hem de kurumsal ölçekli uygulamalar için çalışır mı?**  
**C:** Evet, Aspose.GIS hızlı prototiplerden yüksek verimli sunucu iş yüklerine kadar her şeyi yönetmek için tasarlanmıştır; çok gigabaytlık veri setlerini düşük bellek tüketimiyle işler.

---

**Son Güncelleme:** 2026-05-31  
**Test Edilen Versiyon:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose

## İlgili Eğitimler

- [Vector Katman Oluşturma, Aspose.GIS for .NET ile Hassasiyeti Sınırlama](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [GeoJSON Nasıl Dönüştürülür – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [Geometri Nasıl Kontrol Edilir – Aspose.GIS for .NET](/gis/net/geometry-analysis/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

{{< /blocks/products/pf/main-wrap-class >}}
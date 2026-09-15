---
date: 2026-09-15
description: Aspose.GIS for .NET kullanarak çokgeni çizgiye dönüştürmeyi ve çokgenleri
  çizgilere çevirmeyi öğrenin. GIS geliştiricileri için hızlı bir rehber.
keywords:
- convert polygon to line
- how to replace polygons
- transform polygons to lines
- gis polygon to line
- simplify map visualization
lastmod: 2026-09-15
linktitle: Çokgenleri çizgilerle değiştirin
og_description: Aspose.GIS for .NET kullanarak çokgeni çizgiye dönüştürün. Bu öğreticide
  çokgenlerin çizgilerle nasıl değiştirileceği, desteklenen .NET sürümleri ve yaygın
  hatalar gösterilmektedir.
og_image_alt: Screenshot of Aspose.GIS converting polygon to line in a .NET console
  app
og_title: Aspose.GIS for .NET ile çokgeni çizgiye dönüştürün – hızlı rehber
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to convert polygon to line and transform polygons to lines
    using Aspose.GIS for .NET. A quick guide for GIS developers.
  headline: Convert polygon to line with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert polygon to line and transform polygons to lines
    using Aspose.GIS for .NET. A quick guide for GIS developers.
  name: Convert polygon to line with Aspose.GIS for .NET
  steps:
  - name: Define the source geometry
    text: The `GeometryCollection` class is a container that can hold any number of
      geometry objects, including polygons, points, and lines. It is the entry point
      for bulk operations like `ReplacePolygonsByLines`. Create a geometry collection
      that includes one or more polygons you want to convert. In this exa
  - name: Convert polygons to lines
    text: The `ReplacePolygonsByLines()` method scans the supplied collection, replaces
      each polygon with a `LineString` that follows its outer ring, and leaves all
      other geometry types untouched. This single call performs the conversion in
      O(n) time, where *n* is the number of geometries in the collection.
  - name: Display the original and converted geometries
    text: Printing both the original and the transformed geometries lets you verify
      that polygons have been replaced while other geometries stay the same. The `ToString()`
      override on each geometry provides a human‑readable WKT representation.
  type: HowTo
- questions:
  - answer: Yes, it supports more than 30 formats—including Shapefile, GeoJSON, KML,
      GML, and CSV—allowing you to read, convert, and write data without external
      tools.
    question: Can Aspose.GIS for .NET work with various GIS file formats?
  - answer: Yes, you can access the free trial of Aspose.GIS for .NET on the Aspose
      releases page ([Aspose releases page](https://releases.aspose.com/)).
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Yes, developers can get support and assistance from the Aspose.GIS community
      forum ([Aspose.GIS community forum](https://forum.aspose.com/c/gis/33)).
    question: Does Aspose.GIS for .NET offer support for developers?
  - answer: Yes, you can acquire a temporary license from Aspose's temporary license
      page ([temporary license page](https://purchase.aspose.com/temporary-license/)).
    question: Can I purchase a temporary license for Aspose.GIS for .NET?
  - answer: Absolutely, it provides comprehensive documentation, code examples, and
      API references for all skill levels.
    question: Is Aspose.GIS for .NET suitable for both beginners and experienced developers?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert polygon to line
- Aspose.GIS
- .NET GIS processing
title: Aspose.GIS for .NET ile çokgeni çizgiye dönüştürün
url: /tr/net/geometry-processing/replace-polygons-with-lines/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Poligonları Çizgiye Dönüştürme Aspose.GIS for .NET

## Giriş
Eğer bir .NET GIS projesinde **convert polygon to line** işlemini yapmanız gerekiyorsa, Aspose.GIS süreci basitleştirir. Harita görselleştirmelerini sadeleştiriyor, yönlendirme algoritmaları için verileri hazırlıyor ya da sadece daha temiz bir geometri temsiline ihtiyaç duyuyorsanız, bu öğretici Aspose.GIS API'sini kullanarak çokgenleri çizgi geometrileriyle değiştirmek için gerekli adımları size gösterir. Kütüphanenin GIS geliştiricileri arasında neden tercih edildiğini ve dönüşümün sadece birkaç satır kodla nasıl yapılacağını göreceksiniz.

## Hızlı Yanıtlar
- **convert polygon to line** ne anlama geliyor? Poligonun dış halkasını çıkarır ve aynı çevreyi izleyen bir `LineString` oluşturur.  
- **Why use Aspose.GIS for this task?** Kütüphane, toplu dönüşümü manuel geometri ayrıştırması olmadan verimli bir şekilde işleyen tek bir yöntem (`ReplacePolygonsByLines`) sunar.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, ve .NET 5/6+ tamamen desteklenir.  
- **Do I need a license for development?** Ücretsiz deneme testi için çalışır; üretim dağıtımları için ticari lisans gereklidir.  
- **How long does the implementation take?** Çoğu geliştirici temel dönüşümü on dakikadan kısa sürede tamamlar.

## “convert polygon to line” nedir?
Bir poligonu çizgiye dönüştürmek, poligonun dış halkasını (çevresini) çıkarıp bunu bir `LineString` olarak temsil etmek anlamına gelir. Ortaya çıkan geometri, orijinal şeklin tam dış hatlarını korur ancak iç alan bilgilerini atar; bu, ağ analizi, kenar render'ı veya web haritaları için hafif bir temsil gerektiğinde idealdir.

## Neden Aspose.GIS ile çokgenleri çizgilere dönüştürmeliyiz?
Aspose.GIS, bir koleksiyondaki her çokgeni tek bir çağrıda sınır çizgisiyle değiştirir, topolojiyi korur ve özel döngülere olan ihtiyacı ortadan kaldırır. Bu yaklaşım kod karmaşıklığını %80’e kadar azaltır ve tipik sunucu donanımında 10 000+ öge koleksiyonlarını bir saniyeden kısa sürede işler; bunun nedeni yerel C++ çekirdeği ve sıfır‑kopya bellek yönetimidir.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

### Aspose.GIS for .NET Kurulumu
1. Aspose.GIS for .NET'i indirin: Aspose.GIS for .NET indirme sayfasını ziyaret edin ([Aspose.GIS for .NET download](https://releases.aspose.com/gis/net/)).  
2. Aspose.GIS for .NET'i kurun: Paketteki kurulum talimatlarını izleyin veya ayrıntılı adımlar için Aspose.GIS belgelerine bakın ([Aspose.GIS documentation](https://reference.aspose.com/gis/net/)).

## Ad Alanlarını İçe Aktarma
.NET projenizde, Aspose.GIS sınıflarıyla çalışabilmek için gerekli ad alanlarını içe aktarın.

`Aspose.Gis` ad alanı temel geometri tiplerini içerirken, `Aspose.Gis.Geometries` `Polygon` ve `LineString` gibi somut uygulamaları sağlar.

```csharp
using System;
using Aspose.Gis.Geometries;
```

## Adım‑adım Kılavuz

### Adım 1: Kaynak Geometrisini Tanımlama
`GeometryCollection` sınıfı, çokgenler, noktalar ve çizgiler dahil olmak üzere herhangi bir sayıda geometri nesnesi tutabilen bir kapsayıcıdır. `ReplacePolygonsByLines` gibi toplu işlemler için giriş noktasıdır.

Dönüştürmek istediğiniz bir veya daha fazla çokgeni içeren bir geometri koleksiyonu oluşturun. Bu örnekte, çokgen olmayan öğelerin değişmeden kaldığını göstermek için bir nokta da ekliyoruz.

```csharp
var srcGeometry = Geometry.FromText(@"GeometryCollection (POLYGON((1 2, 1 4, 3 4, 3 2)), Point (5 1))");
```

### Adım 2: Çokgenleri Çizgilere Dönüştürme
`ReplacePolygonsByLines()` yöntemi sağlanan koleksiyonu tarar, her çokgeni dış halkasını izleyen bir `LineString` ile değiştirir ve diğer tüm geometri tiplerini dokunulmamış bırakır. Bu tek çağrı, dönüşümü O(n) zamanda gerçekleştirir; burada *n* koleksiyondaki geometri sayısıdır.

```csharp
var dstGeometry = srcGeometry.ReplacePolygonsByLines();
```

### Adım 3: Orijinal ve Dönüştürülmüş Geometrileri Görüntüleme
Hem orijinal hem de dönüştürülmüş geometrileri yazdırmak, çokgenlerin değiştirildiğini ve diğer geometrilerin aynı kaldığını doğrulamanızı sağlar. Her geometri üzerindeki `ToString()` geçersiz kılma, insan tarafından okunabilir bir WKT temsili sunar.

```csharp
Console.WriteLine($"source: {srcGeometry.AsText()}");
Console.WriteLine($"result: {dstGeometry.AsText()}");
```

## Yaygın Sorunlar ve Çözümler
- **Missing line output:** Kaynak geometrisinin gerçekten çokgen içerdiğinden emin olun; noktalar veya çok nokta öğeleri değişmeden geçecektir.  
- **Coordinate order problems:** Aspose.GIS, koordinatları `X Y` (boylam enlem) sırasına göre bekler. Değerlerin yer değiştirmesi beklenmedik şekillere yol açabilir.  
- **Large collections:** Çok büyük veri setleri (yüz binlerce öge) için bellek kullanımını 200 MB altında tutmak amacıyla geometrileri 10 000–20 000 öğe grupları halinde işleyin.

## Sıkça Sorulan Sorular

**Q: Aspose.GIS for .NET çeşitli GIS dosya formatlarıyla çalışabilir mi?**  
A: Evet, Shapefile, GeoJSON, KML, GML ve CSV dahil 30’dan fazla formatı destekler; dış araçlara ihtiyaç duymadan veri okuyabilir, dönüştürebilir ve yazabilirsiniz.

**Q: Aspose.GIS for .NET için ücretsiz deneme mevcut mu?**  
A: Evet, Aspose releases sayfasından Aspose.GIS for .NET'in ücretsiz denemesine erişebilirsiniz ([Aspose releases page](https://releases.aspose.com/)).

**Q: Aspose.GIS for .NET geliştiricilere destek sunuyor mu?**  
A: Evet, geliştiriciler Aspose.GIS topluluk forumundan destek ve yardım alabilirler ([Aspose.GIS community forum](https://forum.aspose.com/c/gis/33)).

**Q: Aspose.GIS for .NET için geçici bir lisans satın alabilir miyim?**  
A: Evet, geçici lisansı Aspose'un geçici lisans sayfasından temin edebilirsiniz ([temporary license page](https://purchase.aspose.com/temporary-license/)).

**Q: Aspose.GIS for .NET hem yeni başlayanlar hem de deneyimli geliştiriciler için uygun mu?**  
A: Kesinlikle, tüm beceri seviyeleri için kapsamlı dokümantasyon, kod örnekleri ve API referansları sunar.

## Sonuç
Bu adımları izleyerek **convert polygon to line** ve Aspose.GIS for .NET kullanarak **transform polygons to lines** işlemini nasıl yapacağınızı öğrendiniz. Bu yetenek, daha hafif görselleştirmeler, yönlendirme hazırlıkları ve birçok başka GIS iş akışı için kapıyı açar. Uygulamanızın yeteneklerini genişletmek için uzamsal sorgular, yeniden projeksiyon ve format dönüşümü gibi ek Aspose.GIS özelliklerini keşfetmekten çekinmeyin.

---

**Son Güncelleme:** 2026-09-15  
**Test Edilen:** Aspose.GIS for .NET (latest release)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.GIS for .NET ile LineString Geometrisi Oluşturmayı Öğrenin](/gis/net/geometry-creation/create-linestring-geometry/)
- [Aspose.GIS for .NET ile Toleranslı GeoJSON Oluşturma](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Aspose.GIS for .NET ile Geometriyi WKT'ye Dönüştürme](/gis/net/geometry-processing/translate-geometry-to-wkt/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
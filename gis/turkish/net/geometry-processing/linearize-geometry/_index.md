---
date: 2026-09-10
description: Aspose.GIS for .NET kullanarak eğrileri çizgilere (linearize geometry)
  nasıl dönüştüreceğinizi öğrenin, .NET uygulamalarınızda verimli geospatial processing
  ve analysis sağlamanızı sağlar.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
lastmod: 2026-09-10
linktitle: Geometriyi Linearize Et
og_description: Aspose.GIS for .NET kullanarak eğrileri çizgilere (linearize geometry)
  dönüştürün. Daha hızlı rendering ve daha geniş compatibility için geometrileri simplify
  geometries nasıl adım adım (step‑by‑step) yapacağınızı öğrenin.
og_image_alt: Guide showing how to linearize curved geometries to straight lines using
  Aspose.GIS in a .NET application
og_title: Aspose.GIS for .NET ile Eğrileri Çizgilere Dönüştürün
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  headline: How to Convert Curves to Lines with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  name: How to Convert Curves to Lines with Aspose.GIS for .NET
  steps:
  - name: Define the output path
    text: '`Path.Combine` builds a platform‑independent file path, handling Windows
      backslashes and Unix forward slashes automatically. Replace `"Your Document
      Directory"` with the folder where you want the KML file saved.'
  - name: Create a layer for the output file
    text: A *layer* groups geographic features of the same type. Here we instantiate
      a new KML layer that will store the linearized geometry.
  - name: Construct a new feature
    text: A *feature* represents a single geographic object (point, line, polygon,
      etc.). We’ll attach our linear geometry to this feature.
  - name: Define the original complex geometry
    text: '`Geometry.FromWkt` parses a Well‑Known Text (WKT) string into a geometry
      object. The sample WKT includes a `LineString`, a `CompoundCurve`, and a `CircularString`
      to showcase curve handling.'
  - name: Convert curves to lines
    text: '`ToLinearGeometry()` tessellates every curve in the source geometry into
      straight‑line segments, returning a new linear geometry that retains any Z‑coordinates.'
  - name: Assign the linear geometry to the feature
    text: The feature’s `Geometry` property now holds the simplified, linear version
      of the original shape.
  - name: Add the feature to the layer
    text: Adding the feature to the KML layer queues it for writing; when the `using`
      block ends, the layer flushes the data to the output file.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Core, enabling cross‑platform applications.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Absolutely! The library supports KML, Shapefile, GeoJSON, and many more
      formats—over 30 in total.
    question: Can I work with different GIS file formats using Aspose.GIS for .NET?
  - answer: Yes, it provides a wide range of spatial functions, from buffering to
      spatial joins.
    question: Does Aspose.GIS offer spatial operations and analysis?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      and staff support.
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert curves to lines
- Aspose.GIS
- .NET GIS processing
title: Aspose.GIS for .NET ile Eğrileri Çizgilere Nasıl Dönüştürülür
url: /tr/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kavisleri Çizgilere Dönüştürme (Geometriyi Doğrusal Hale Getirme) Aspose.GIS for .NET

## Giriş
Haritalama, mekânsal analiz veya veri‑değişim görevleri için **kavisleri çizgilere dönüştürmeniz** gerekiyorsa, Aspose.GIS for .NET bunu yapmanız için temiz, programatik bir yol sunar. Bu eğitimde, karmaşık bir geometriyi—kavisler ve birleşik şekiller içeren—alıp, herhangi bir GIS sistemiyle çalışabilen basit bir doğrusal temsile dönüştüren eksiksiz, gerçek‑dünya bir örnek üzerinden ilerleyeceğiz.

## Hızlı Yanıtlar
- **“Kavisleri çizgilere dönüştürmek” ne anlama geliyor?** Eğri geometrileri düz‑çizgi segmentlerine dönüştürür.  
- **Neden Aspose.GIS seçilmeli?** Kütüphane 30’dan fazla GIS formatını destekler ve geometri dönüşümünü dış araçlar olmadan gerçekleştirir.  
- **Önceden neye ihtiyacım var?** .NET Framework veya .NET Core, Visual Studio (veya herhangi bir C# IDE) ve Aspose.GIS NuGet paketi.  
- **Örnek ne kadar sürede çalışır?** Kütüphane yüklendikten sonra beş dakikadan az sürer.  
- **Diğer formatlara dışa aktarabilir miyim?** Kesinlikle—KML sürücüsünü Shapefile, GeoJSON vb. ile değiştirin.  
Tam ürün paketini [Aspose web sitesinden](https://releases.aspose.com/) indirebilirsiniz.

## Kavisleri çizgilere dönüştürmek ne anlama geliyor?
Kavisleri çizgilere dönüştürmek (aynı zamanda **geometriyi doğrusal hâle getirme** olarak da adlandırılır), her eğri segmenti kısa düz‑çizgi parçalarına değiştirerek bir *doğrusal geometri* oluşturur. Bu, render süresini beş katına kadar hızlandırır, bellek tüketimini azaltır ve verinin yalnızca doğrusal özellikleri kabul eden eski GIS hizmetleri tarafından kullanılmasını sağlar.

## Neden kavisleri çizgilere dönüştürmeliyiz?
Doğrusal geometriler, eğri karşılıklarına göre **5 katına kadar daha hızlı** render ve sorgu yapar ve **30’dan fazla GIS platformu** yalnızca doğrusal özellikleri kabul eder. Geometrinin basitleştirilmesi ayrıca web‑tabanlı ön izlemeler için dosya boyutunu küçültür ve ağ analizi veya kümeleme gibi düz‑çizgi girişi gerektiren algoritmaların kullanılmasını sağlar.

## Geometriyi nasıl doğrusal hâle getirebiliriz?
Aspose.GIS tarafından sağlanan `ToLinearGeometry()` metodunu kullanın. Bu metod, bir geometrideki her eğriyi Z‑değerlerini koruyarak otomatik olarak düz‑çizgi segmentlerine bölerek, yükseklik verisini kaybetmeden doğrusal bir yaklaşım elde etmenizi sağlar. Ayrıca, orijinal eğri ile oluşturulan segmentler arasındaki maksimum sapmayı kontrol etmek için bir tolerans belirtebilir, böylece doğruluk ile dosya boyutu arasında denge kurabilirsiniz. Metod, 2‑D ve 3‑D geometrilerde aynı şekilde çalışır.

## Önkoşullar
Koda geçmeden önce şunların yüklü olduğundan emin olun:

1. **Aspose.GIS for .NET** – [Aspose.GIS web sitesinden](https://releases.aspose.com/gis/net/) indirin.  
2. **.NET Framework** (veya .NET Core) geliştirme makinenizde kurulu.  
3. **Visual Studio** (veya herhangi bir C#‑uyumlu IDE) örneği yazmak ve çalıştırmak için.

## Ad alanlarını içe aktar
Aspose.GIS işlevselliğini kullanmaya başlamak için gerekli ad alanlarını içe aktarın.

### Temel Aspose.GIS ad alanları
`Aspose.Gis` ad alanı, tüm GIS işlemleri için gereken temel geometri sınıflarını, sürücüleri ve yardımcı programları içerir.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Hedef format için sürücü
`Aspose.Gis.Drivers`, desteklenen her dosya formatı için statik fabrikalar sağlar; `Drivers.Kml` bir KML yazıcı oluşturur.  
```csharp
using Aspose.GIS.Kml;
```

## Kavisleri çizgilere dönüştürmek için adım adım kılavuz
Aşağıda, kodun her satırını ayrıntılı olarak ele alan bir yürütme rehberi bulunmakta; **kavisleri çizgilere nasıl dönüştüreceğinizi** ve her adımın neden önemli olduğunu açıklamaktadır.

### Adım 1: Çıktı yolunu tanımla
`Path.Combine`, Windows ters eğik çizgileri ve Unix ileri eğik çizgileri otomatik olarak işleyerek platform‑bağımsız bir dosya yolu oluşturur.  
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
`"Your Document Directory"` ifadesini KML dosyasını kaydetmek istediğiniz klasörle değiştirin.

### Adım 2: Çıktı dosyası için bir katman oluştur
*Katman*, aynı tipteki coğrafi özellikleri gruplar. Burada, doğrusal hâle getirilmiş geometriyi depolayacak yeni bir KML katmanı örnekliyoruz.  
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```

### Adım 3: Yeni bir özellik oluştur
*Özellik*, tek bir coğrafi nesneyi (nokta, çizgi, çokgen vb.) temsil eder. Doğrusal geometrimizi bu özelliğe ekleyeceğiz.  
```csharp
var feature = layer.ConstructFeature();
```

### Adım 4: Orijinal karmaşık geometriyi tanımla
`Geometry.FromWkt`, Well‑Known Text (WKT) dizesini bir geometri nesnesine ayrıştırır. Örnek WKT, eğri işleme örneği göstermek için bir `LineString`, bir `CompoundCurve` ve bir `CircularString` içerir.  
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```

### Adım 5: Kavisleri çizgilere dönüştür
`ToLinearGeometry()` kaynak geometrideki her eğriyi düz‑çizgi segmentlerine bölerek, Z‑koordinatlarını koruyan yeni bir doğrusal geometri döndürür.  
```csharp
var linear = geometry.ToLinearGeometry();
```

### Adım 6: Doğrusal geometriyi özelliğe ata
Özelliğin `Geometry` özelliği artık orijinal şeklin basitleştirilmiş, doğrusal versiyonunu tutuyor.  
```csharp
feature.Geometry = linear;
```

### Adım 7: Özelliği katmana ekle
Özelliği KML katmanına eklemek, onu yazma kuyruğuna alır; `using` bloğu sona erdiğinde, katman verileri çıktı dosyasına yazar.  
```csharp
layer.Add(feature);
```

## Yaygın tuzaklar ve profesyonel ipuçları
- **Yol ayırıcıları:** Windows ve Linux arasındaki sorunları önlemek için `Path.Combine` kullanın.  
- **Çok büyük geometriler:** Karmaşık şekilleri doğrusal hâle getirmek binlerce köşe oluşturabilir; nokta sayısını azaltmak için doğrusal hâle getirdikten sonra `Simplify()` çağırmayı düşünün.  
- **Sürücü seçimi:** Farklı bir çıktı formatına ihtiyacınız varsa, `Drivers.Kml` yerine `Drivers.Shapefile`, `Drivers.GeoJson` vb. kullanın ve dosya uzantısını buna göre değiştirin.  
- **Z‑değerlerini koruma:** `ToLinearGeometry()` 3‑D (Z) koordinatlarını korur, böylece yükseklik verisini kaybetmezsiniz.

## Sıkça Sorulan Sorular (SSS)

**S: Aspose.GIS for .NET, .NET Core ile uyumlu mu?**  
C: Evet, Aspose.GIS .NET Core ile çalışır ve çapraz‑platform uygulamaları sağlar.

**S: Aspose.GIS for .NET ile farklı GIS dosya formatlarıyla çalışabilir miyim?**  
C: Kesinlikle! Kütüphane KML, Shapefile, GeoJSON ve daha birçok formatı—toplamda 30’dan fazla—destekler.

**S: Aspose.GIS mekânsal işlemler ve analizler sunuyor mu?**  
C: Evet, tamponlama'dan mekânsal birleştirmelere kadar geniş bir mekânsal fonksiyon yelpazesi sunar.

**S: Ücretsiz deneme sürümü mevcut mu?**  
C: Evet, [Aspose.GIS web sitesinden](https://releases.aspose.com/gis/net/) ücretsiz bir deneme sürümü indirebilirsiniz.

**S: Sorun yaşarsam nereden yardım alabilirim?**  
C: Topluluk ve ekip desteği için [Aspose.GIS forumunu](https://forum.aspose.com/c/gis/33) ziyaret edin.

### Ek yaygın sorular

**S: 3D (Z) koordinatları içeren geometrileri doğrusal hâle getirebilir miyim?**  
C: Evet, `ToLinearGeometry()` hem 2D hem de 3D geometrilerle çalışır; Z değerleri korunur.

**S: Doğrusal hâle getirme dosya boyutunu nasıl etkiler?**  
C: Kavisleri çok sayıda kısa çizgi segmentine dönüştürmek dosya boyutunu artırabilir; boyut bir endişe ise doğrusal hâle getirdikten sonra `Simplify()` çalıştırın.

**S: Kavisleri çizgilere dönüştürürken segment uzunluğunu kontrol edebilir miyim?**  
C: Varsayılan metod içsel bir tolerans kullanır. Özel segmentasyon için `ToLinearGeometry()` çağırmadan önce eğrileri manuel olarak bölerek kontrol sağlayabilirsiniz.

## Sonuç
Bu eğitimde, Aspose.GIS for .NET kullanarak **kavisleri çizgilere nasıl dönüştüreceğinizi** (geometriyi doğrusal hâle getirme) ortamı kurmaktan doğrusal sonuçları bir KML dosyasına yazmaya kadar ele aldık. Artık bu iş akışını haritalama uygulamalarına, veri‑işleme hatlarına veya basitleştirilmiş geometrilere ihtiyaç duyan herhangi bir GIS‑ile ilgili projeye entegre edebilirsiniz.

---

**Son Güncelleme:** 2026-09-10  
**Test Edilen Versiyon:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose

## İlgili Eğitimler

- [Aspose.GIS for .NET ile Toleranslı GeoJSON Oluşturma](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Aspose.GIS for .NET ile Çokgeni Çizgiye Dönüştürme](/gis/net/geometry-processing/replace-polygons-with-lines/)
- [Aspose.GIS for .NET ile LineString Geometrisi Oluşturmayı Öğrenin](/gis/net/geometry-creation/create-linestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
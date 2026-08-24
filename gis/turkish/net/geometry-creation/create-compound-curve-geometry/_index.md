---
date: 2026-08-24
description: Aspose.GIS for .NET kullanarak eğimli hat geometrisi oluşturmayı ve eğriler
  eklemeyi öğrenin; bu, hassas coğrafi veri işleme imkanı sağlar.
keywords:
- create curved line
- how to add curves
- create compound curve
- circular arc geometry
lastmod: 2026-08-24
linktitle: Eğrileri Eklemek – Bileşik Eğri Geometrisi
og_description: Aspose.GIS for .NET kullanarak eğimli hat geometrisi oluşturmayı öğrenin.
  Bu öğretici, adım adım eğrileri eklemeyi ve birkaç dakika içinde bileşik eğriler
  oluşturmayı gösterir.
og_image_alt: Screenshot of Aspose.GIS creating a compound curved line geometry in
  a .NET project
og_title: Aspose.GIS ile eğimli hat geometrisi oluşturma
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to create curved line geometry and add curves using Aspose.GIS
    for .NET, enabling precise geospatial data processing.
  headline: How to create curved line geometry with Aspose.GIS
  type: TechArticle
- description: Learn how to create curved line geometry and add curves using Aspose.GIS
    for .NET, enabling precise geospatial data processing.
  name: How to create curved line geometry with Aspose.GIS
  steps:
  - name: define the output path
    text: First, specify where the resulting Shapefile will be saved. Replace the
      placeholder with a valid folder on your machine.
  - name: create a vector layer
    text: '`VectorLayer` represents a spatial layer that holds features and their
      geometries within a GIS dataset. The `using` block ensures the file is closed
      properly after writing.'
  - name: construct the compound curve feature
    text: The `CompoundCurve` class is Aspose.GIS's top‑level object for a geometry
      that consists of multiple connected curve parts. Here we instantiate an empty
      compound curve that will later receive individual components.
  - name: define component curves
    text: 'We prepare five pieces—two straight `LineString`s, two `CircularString`
      arcs, and a final `LineString`. `LineString` represents a simple straight line
      defined by an ordered list of points. `CircularString` is Aspose.GIS’s representation
      of a circular arc defined by three points (start, middle, end) '
  - name: add component curves to the compound curve
    text: Each component is appended in order, preserving continuity and orientation.
      The `Add` method automatically validates that the end point of one segment matches
      the start point of the next.
  - name: assign geometry to the feature
    text: Now the assembled `CompoundCurve` becomes the geometry of the feature we
      will store in the layer.
  - name: add the feature to the layer
    text: Finally, we write the feature into the Shapefile. When the `using` block
      ends, the file is closed and ready for use in any GIS application.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard,
      covering versions from 4.6 up to .NET 7.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. It reads and writes Shapefile, GeoJSON, KML, GML, and more
      than 30 additional formats.
    question: Does Aspose.GIS support reading and writing different geospatial file
      formats?
  - answer: Yes, the library can be used in desktop, web, and cloud services without
      any platform‑specific dependencies.
    question: Is Aspose.GIS suitable for both desktop and web applications?
  - answer: Yes, you can calculate distances, execute geometric operations, and run
      spatial queries directly on the geometries.
    question: Can I perform spatial analysis with Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) to ask
      questions and share ideas with other developers.
    question: Where can I get community help for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- GIS geometry
- Aspose.GIS
- .NET geospatial
- compound curve
title: Aspose.GIS ile eğimli hat geometrisi oluşturma
url: /tr/net/geometry-creation/create-compound-curve-geometry/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS ile eğimli çizgi geometrisi nasıl oluşturulur

## Giriş
Bu kılavuzda Aspose.GIS for .NET kullanarak **eğimli çizgi geometrisi nasıl oluşturulacağını** keşfedeceksiniz. Etkileşimli haritalar oluşturuyor, mekansal analizler yürütüyor veya GIS veri setleri üretiyor olsanız, eğrileri ekleme yeteneğini ustalaşmak, gerçek dünya özelliklerini—örneğin kıvrımlı yollar veya dolambaçlı nehirler—yüksek hassasiyetle modellemenizi sağlar. Eğitim, projeyi kurmaktan yeniden kullanılabilir bir bileşik eğri geometrisi dışa aktarmaya kadar her adımı size gösterir.

## Hızlı cevaplar
- **Birincil hedef nedir?** Düz çizgileri ve dairesel yayları birleştiren bir bileşik eğri geometrisi oluşturun.  
- **Hangi kütüphane kullanılıyor?** Aspose.GIS for .NET.  
- **Önkoşullar?** Visual Studio, Aspose.GIS yüklü ve .NET 6 veya daha yeni bir sürümü hedefleyen bir C# projesi.  
- **Tipik uygulama süresi?** Çalışan bir örnek için yaklaşık 10‑15 dakika.  
- **Desteklenen çıktı formatı?** Shapefile (aynı kod ayrıca GeoJSON, KML ve diğer formatları da yazar).

## Bileşik eğri nedir?
Bileşik eğri, birden fazla bağlı eğri bileşeninden—düz `LineString`'ler ve dairesel yaylar—oluşan tek bir geometridir ve daha karmaşık bir şekil oluşturmak için birleştirilir. Tek bir basit çizgi bir yolu doğru şekilde temsil edemediğinde, örneğin yumuşak dönüşlere sahip bir otoyol veya doğal bir yay izleyen bir nehir gibi durumlarda idealdir.

## Eğri eklemek için neden Aspose.GIS kullanılmalı?
Aspose.GIS, satır dizilerini, dairesel dizileri ve bileşik eğrileri yerel olarak destekleyen **zengin bir geometri API'si** sunar, böylece harici GIS kütüphanelerine ihtiyaç kalmaz. Kütüphane **çapraz platform** olup .NET Framework 4.6+, .NET Core 2.0+, ve .NET 5/6/7+ ile çalışır. **Tüm dosyayı belleğe yüklemeden 500 sayfaya kadar vektör veri setini işleyebilir**, hızlı ve bellek‑verimli işlemler sunar. Dışa aktarma basittir: doğrudan Shapefile, GeoJSON, KML, GML ve 30'dan fazla diğer formata yazabilirsiniz.

## Bunun önemi nedir
Eğriler eklemek, gerçek dünya özelliklerini daha doğru modellemenizi sağlar, bu da harita render'larında görsel kaliteyi artırır ve yakınlık aramaları veya ağ yönlendirmesi gibi mekansal analizlerde hassasiyeti yükseltir. **Eğimli çizgi geometrisi nasıl oluşturulur** konusuna hakim olmak, böylece herhangi bir GIS‑tabanlı .NET çözümünün doğruluğunu artırır.

## Ortak kullanım senaryoları
- **Ulaşım ağları:** Yumuşak dönüşlere sahip otoyollar, demiryolları veya bisiklet yollarını modelleyin.  
- **Hidrolik:** Doğal yayları izleyen nehir hatlarını temsil edin.  
- **Kentsel planlama:** Eğri bölümler içeren mülk sınırlarını çizin.  
- **Özel semboller:** Harita lejandları için dekoratif veya şematik şekiller oluşturun.

## Önkoşullar
- Visual Studio (herhangi bir yeni sürüm).  
- Aspose.GIS for .NET, [download page](https://releases.aspose.com/gis/net/) adresinden indirilir.  
- .NET 6 (veya desteklenen herhangi bir sürüm) hedefleyen bir C# projesi.

## Ad alanlarını içe aktar
`using` yönergeleri, gerekli Aspose.GIS tiplerini kapsam içine getirir.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Bileşik eğri geometrisi oluşturmak için adım adım kılavuz

### Adım 1: çıktı yolunu tanımlayın
İlk olarak, oluşturulan Shapefile'ın nereye kaydedileceğini belirtin. Yer tutucuyu makinenizde geçerli bir klasörle değiştirin.

```csharp
string path = "Your Document Directory" + "CreateCompoundCurve_out.shp";
```

### Adım 2: bir vektör katmanı oluşturun
`VectorLayer`, bir GIS veri seti içinde özellikleri ve geometrilerini tutan bir uzamsal katmanı temsil eder. `using` bloğu, dosyanın yazma işleminden sonra düzgün bir şekilde kapanmasını sağlar.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block for creating the compound curve geometry will be inserted here.
}
```

### Adım 3: bileşik eğri özelliğini oluşturun
`CompoundCurve` sınıfı, birden fazla bağlı eğri parçasından oluşan bir geometri için Aspose.GIS'in üst‑seviye nesnesidir. Burada, daha sonra bireysel bileşenleri alacak boş bir bileşik eğri örneği oluşturuyoruz.

```csharp
var feature = layer.ConstructFeature();
var compoundCurve = new CompoundCurve();
```

### Adım 4: bileşen eğrileri tanımlayın
Beş parça hazırlıyoruz—iki düz `LineString`, iki `CircularString` yay ve son bir `LineString`. `LineString`, sıralı bir nokta listesiyle tanımlanan basit bir düz çizgiyi temsil eder. `CircularString`, aynı daire üzerinde bulunan üç nokta (başlangıç, orta, bitiş) ile tanımlanan dairesel bir yay için Aspose.GIS'in temsilidir.

```csharp
var bottom = (ILineString)Geometry.FromText("LineString (0 0, 3 0)");
var firstArc = (ICircularString)Geometry.FromText("CircularString (3 0, 4 1, 3 2)");
var middle = (ILineString)Geometry.FromText("LineString (3 2, 1 2)");
var secondArc = (ICircularString)Geometry.FromText("CircularString (1 2, 0 3, 1 4)");
var top = (ILineString)Geometry.FromText("LineString (1 4, 4 4)");
```

### Adım 5: bileşen eğrileri bileşik eğriye ekleyin
Her bileşen sırayla eklenir, süreklilik ve yön korunur. `Add` yöntemi, bir segmentin bitiş noktasının bir sonraki segmentin başlangıç noktasıyla eşleştiğini otomatik olarak doğrular.

```csharp
compoundCurve.AddCurve(bottom);
compoundCurve.AddCurve(firstArc);
compoundCurve.AddCurve(middle);
compoundCurve.AddCurve(secondArc);
compoundCurve.AddCurve(top);
```

### Adım 6: geometriyi özelliğe atayın
Şimdi, oluşturulan `CompoundCurve`, katmanda saklayacağımız özelliğin geometrisi haline gelir.

```csharp
feature.Geometry = compoundCurve;
```

### Adım 7: özelliği katmana ekleyin
Son olarak, özelliği Shapefile'a yazarız. `using` bloğu sona erdiğinde dosya kapanır ve herhangi bir GIS uygulamasında kullanılmaya hazır olur.

```csharp
layer.Add(feature);
```

## Yaygın sorunlar ve ipuçları
- **Koordinat sırası:** Aspose.GIS, koordinatları `X Y` sırasına (boylam, enlem) göre bekler. Sıralamayı değiştirmek geometrinin tersine dönmesine neden olur.  
- **CircularString sözdizimi:** Orta nokta, hedeflenen yay üzerinde bulunmalıdır; aksi takdirde eğri düz bir çizgiye dönüşür.  
- **Dosya üzerine yazma:** `VectorLayer.Create`, mevcut bir Shapefile'ı uyarı vermeden üzerine yazar—geliştirme sırasında benzersiz bir dosya adı kullanın.  
- **Performans:** Büyük veri setleri için, `using` bloğu içinde tek tek eklemek yerine toplu olarak özellik ekleyin.  
- **İpucu:** Benzer birçok özellik oluştururken aynı `CompoundCurve` örneğini yeniden kullanın; yeniden doldurmadan önce `compoundCurve.Clear()` çağırarak tahsisleri azaltın.

## Sıkça sorulan sorular

**S: Aspose.GIS for .NET'i diğer .NET framework'leriyle kullanabilir miyim?**  
C: Evet, Aspose.GIS .NET Framework, .NET Core ve .NET Standard ile çalışır; 4.6 sürümünden .NET 7'ye kadar olan sürümleri kapsar.

**S: Aspose.GIS farklı coğrafi veri dosya formatlarını okuma ve yazma desteği sunuyor mu?**  
C: Kesinlikle. Shapefile, GeoJSON, KML, GML ve 30'dan fazla ek formatı okur ve yazar.

**S: Aspose.GIS hem masaüstü hem de web uygulamaları için uygun mu?**  
C: Evet, kütüphane masaüstü, web ve bulut hizmetlerinde platform‑spesifik bağımlılık olmadan kullanılabilir.

**S: Aspose.GIS for .NET ile mekansal analiz yapabilir miyim?**  
C: Evet, mesafeleri hesaplayabilir, geometrik işlemler gerçekleştirebilir ve doğrudan geometriler üzerinde mekansal sorgular çalıştırabilirsiniz.

**S: Aspose.GIS için topluluk desteğini nereden alabilirim?**  
C: Diğer geliştiricilere sorular sorup fikir paylaşmak için [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) adresini ziyaret edin.

---

**Son Güncelleme:** 2026-08-24  
**Test Edilen:** Aspose.GIS for .NET (latest stable release)  
**Yazar:** Aspose

## İlgili Eğitimler

- [Aspose.GIS for .NET'te Vektör Katmanı ve Dairesel Dizi Oluşturma](/gis/net/geometry-creation/create-circular-string-geometry/)
- [Aspose.GIS ile vektör katmanı ve eğri çokgen oluşturma](/gis/net/geometry-creation/create-curve-polygon-geometry/)
- [WKT'yi Geometriye Dönüştür: Aspose.GIS .NET ile MultiCurve](/gis/net/geometry-creation/create-multicurve-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
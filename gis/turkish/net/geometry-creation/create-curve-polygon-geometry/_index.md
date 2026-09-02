---
date: 2026-08-24
description: Aspose.GIS for .NET kullanarak vektör katmanı ve eğri çokgen geometrisi
  oluşturmayı, iç halkalar için circular string geometrisini öğrenin.
keywords:
- create vector layer
- define curved polygon
- Aspose.GIS curve polygon
- .NET GIS development
lastmod: 2026-08-24
linktitle: Eğri Çokgen Geometrisi Oluşturma
og_description: Aspose.GIS for .NET kullanarak vektör katmanı ve eğri çokgen geometrisi
  oluşturun. Dakikalar içinde eğri kenarlı Shapefile oluşturmayı adım adım öğrenin.
og_image_alt: Screenshot showing a curve polygon Shapefile created with Aspose.GIS
  in a GIS viewer
og_title: Aspose.GIS for .NET ile vektör katmanı ve eğri çokgen oluşturma
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to create vector layer and curve polygon geometry using Aspose.GIS
    for .NET, including circular string geometry for interior rings.
  headline: Create vector layer and curve polygon with Aspose.GIS
  type: TechArticle
- description: Learn how to create vector layer and curve polygon geometry using Aspose.GIS
    for .NET, including circular string geometry for interior rings.
  name: Create vector layer and curve polygon with Aspose.GIS
  steps:
  - name: define the file path
    text: First, specify where the generated Curve Polygon Shapefile will be saved.
      **Definition anchor:** `string shapefilePath = "...";` holds the absolute or
      relative path to the Shapefile that will be created on disk. Replace `"Your
      Document Directory"` with the actual folder path on your machine.
  - name: create a vector layer
    text: 'Instantiate a new vector layer using the Shapefile driver. This is the
      **create vector layer** step that prepares the container for our geometry. **Definition
      anchor:** `VectorLayer layer = new VectorLayer(shapefilePath, Drivers.Shapefile);`
      creates a writable layer tied to a Shapefile data source. '
  - name: construct a feature
    text: Create a feature object that will hold the geometry and any attribute data.
      **Definition anchor:** `Feature feature = layer.ConstructFeature();` builds
      an empty feature ready to receive geometry and attribute values.
  - name: create curve polygon geometry
    text: Now we’ll create an empty `CurvePolygon` object. **Definition anchor:**
      `CurvePolygon curvePolygon = new CurvePolygon();` represents a polygon whose
      rings may consist of straight segments or circular strings.
  - name: define the exterior ring
    text: Add a circular string that forms the outer boundary of the polygon. **Definition
      anchor:** `CircularString exterior = new CircularString();` stores a sequence
      of points that define one or more circular arcs. The coordinates above produce
      a torus‑like shape.
  - name: define an interior ring (optional)
    text: 'If you need a hole inside the polygon, define it as another circular string.
      This demonstrates how to add an **interior ring polygon** using **circular string
      geometry**. **Definition anchor:** `CircularString interior = new CircularString();`
      creates the inner ring that will be subtracted from the '
  - name: assign geometry to the feature
    text: Link the curve polygon to the feature you created earlier. **Definition
      anchor:** `feature.Geometry = curvePolygon;` attaches the fully built geometry
      to the feature, making it ready for persistence.
  - name: add the feature to the layer
    text: Finally, add the feature to the vector layer so it becomes part of the dataset.
      **Definition anchor:** `layer.Add(feature);` writes the feature into the Shapefile;
      the `using` block will flush the data to disk when it ends. When the `using`
      block ends, the Shapefile is written to disk.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS for .NET supports interoperability with many popular GIS
      formats, allowing seamless data exchange with GDAL/OGR, Proj.NET, and other
      .NET GIS toolkits.
    question: Is Aspose.GIS for .NET compatible with other GIS libraries?
  - answer: Absolutely. The Shapefile produced can be opened in QGIS, ArcGIS, or any
      GIS tool that reads the Shapefile format and supports circular strings.
    question: Can I visualize the generated curve polygon geometry in GIS software?
  - answer: Yes, it includes spatial querying, buffering, intersection, and other
      analysis functions, enabling advanced geoprocessing directly in .NET.
    question: Does Aspose.GIS for .NET provide spatial analysis capabilities?
  - answer: Join the Aspose.GIS community forum [Aspose.GIS community forum](https://forum.aspose.com/c/gis/33)
      to connect with other developers.
    question: Where can I ask for help or discuss ideas with other users?
  - answer: Of course! You can download a free trial from the [Aspose.GIS free trial
      downloads](https://releases.aspose.com/) and evaluate all features.
    question: Is a free trial available before purchasing?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create vector layer
- Aspose.GIS
- curve polygon
- .NET GIS
- C# shapefile
title: Aspose.GIS ile vektör katmanı ve eğri çokgen oluşturma
url: /tr/net/geometry-creation/create-curve-polygon-geometry/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS ile vektör katmanı ve eğri çokgen oluşturma

## Giriş
Coğrafi Bilgi Sistemleri (GIS) geliştirme alanında, **Aspose.GIS for .NET**, mekânsal verileri oluşturma, düzenleme ve işleme konusunda güçlü bir kütüphane olarak öne çıkar. Bu öğreticide **vektör katmanı oluşturma** ve **eğri çokgen oluşturma** geometrisini adım adım öğrenecek ve böylece karmaşık şekilleri doğrudan GIS uygulamalarınıza yerleştirebileceksiniz. Kılavuzun sonunda, dış ve iç halkalara sahip bir eğri çokgen içeren, kullanıma hazır bir Shapefile elde edeceksiniz.

## Hızlı cevaplar
- **Hangi kütüphane kullanılıyor?** Aspose.GIS for .NET.  
- **Ana görev?** Bir eğri çokgen geometrisi oluşturmak, bunu Shapefile olarak kaydetmek ve veri için **vektör katmanı oluşturmak**.  
- **Tipik uygulama süresi?** Temel bir şekil için 5–10 dakika.  
- **Önkoşullar?** .NET geliştirme ortamı ve Aspose.GIS NuGet paketi.  
- **Sonucu görebilir miyim?** Evet – Shapefile destekleyen herhangi bir GIS görüntüleyici (ör. QGIS, ArcGIS).

## Eğri çokgen nedir?
Eğri çokgen, kenarları dairesel yaylar gibi eğri segmentler içerebilen bir çokgendir; bu sayede pürüzsüz ve gerçekçi sınırlar elde edilir. Bu geometri türü, göller, adalar veya eğri yol koridorları gibi doğal özellikleri modellemek için özellikle faydalıdır.

## Neden Aspose.GIS ile eğri çokgen geometrisi oluşturmalıyız?
Aspose.GIS, eğri kenarları matematiksel olarak depolayabilir, tam geometriyi korurken Shapefile spesifikasyonu ile uyumlu kalır. Kütüphane **30+ vektör formatını** destekler ve **2 GB**'a kadar dosyaları tüm veri kümesini belleğe yüklemeden işleyebilir; bu da büyük mekânsal projeler için yüksek performanslı işlem sağlar.

## Önkoşullar
İlerlemeye başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Aspose.GIS for .NET** yüklü. Bunu [Aspose.GIS for .NET releases page](https://releases.aspose.com/gis/net/) adresinden indirin.  
2. C# ve .NET ekosistemi hakkında çalışma bilgisi.  
3. Visual Studio (herhangi bir güncel sürüm) veya Visual Studio Code gibi bir IDE.

## Ad alanlarını içe aktar
Aşağıdaki `using` yönergeleri temel GIS sınıflarını kapsam içine getirir.

**Tanım bağlantısı:** `using Aspose.Gis;` bu öğreticide ihtiyaç duyulan `VectorLayer`, `Feature` ve geometri sınıflarını içeren ana GIS ad alanını içe aktarır.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım adım kılavuz

### Adım 1: dosya yolunu tanımla
İlk olarak, oluşturulan Eğri Çokgen Shapefile'ın nereye kaydedileceğini belirtin.

**Tanım bağlantısı:** `string shapefilePath = "...";` diskte oluşturulacak Shapefile'ın mutlak ya da göreli yolunu tutar.  

```csharp
string path = "Your Document Directory" + "CreateCurvePolygon_out.shp";
```

`"Your Document Directory"` ifadesini makinenizdeki gerçek klasör yolu ile değiştirin.

### Adım 2: bir vektör katmanı oluştur
Shapefile sürücüsünü kullanarak yeni bir vektör katmanı örnekleyin. Bu, geometrimiz için konteyneri hazırlayan **vektör katmanı oluşturma** adımıdır.

**Tanım bağlantısı:** `VectorLayer layer = new VectorLayer(shapefilePath, Drivers.Shapefile);` bir Shapefile veri kaynağına bağlı yazılabilir bir katman oluşturur.  

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Your code for creating the Curve Polygon Geometry will go here
}
```

`using` ifadesi kaynakların doğru bir şekilde serbest bırakılmasını garanti eder.

### Adım 3: bir özellik (feature) oluştur
Geometriyi ve herhangi bir öznitelik verisini tutacak bir feature nesnesi oluşturun.

**Tanım bağlantısı:** `Feature feature = layer.ConstructFeature();` geometri ve öznitelik değerlerini alabilecek boş bir feature oluşturur.  

```csharp
var feature = layer.ConstructFeature();
```

### Adım 4: eğri çokgen geometrisi oluştur
Şimdi boş bir `CurvePolygon` nesnesi oluşturacağız.

**Tanım bağlantısı:** `CurvePolygon curvePolygon = new CurvePolygon();` halkaları düz segmentler veya dairesel dizgilerden oluşabilen bir çokgeni temsil eder.  

```csharp
var curvePolygon = new CurvePolygon();
```

### Adım 5: dış halkayı tanımla
Poligonun dış sınırını oluşturan bir dairesel dizi ekleyin.

**Tanım bağlantısı:** `CircularString exterior = new CircularString();` bir veya daha fazla dairesel yay tanımlayan nokta dizisini saklar.  

```csharp
var exterior = new CircularString();
exterior.AddPoint(-2, 0);
exterior.AddPoint(0, 2);
exterior.AddPoint(2, 0);
exterior.AddPoint(0, -2);
exterior.AddPoint(-2, 0);
curvePolygon.ExteriorRing = exterior;
```

Yukarıdaki koordinatlar torus benzeri bir şekil üretir.

### Adım 6: iç halkayı tanımla (isteğe bağlı)
Poligon içinde bir delik ihtiyacınız varsa, bunu başka bir dairesel dizi olarak tanımlayın. Bu, **dairesel dizi geometrisi** kullanarak **iç halka çokgeni** eklemenin nasıl yapılacağını gösterir.

**Tanım bağlantısı:** `CircularString interior = new CircularString();` dış alandan çıkarılacak iç halkayı oluşturur.  

```csharp
var interior = new CircularString();
interior.AddPoint(-1, 0);
interior.AddPoint(0, 1);
interior.AddPoint(1, 0);
interior.AddPoint(0, -1);
interior.AddPoint(-1, 0);
curvePolygon.AddInteriorRing(interior);
```

### Adım 7: geometriyi feature'a ata
Eğri çokgeni daha önce oluşturduğunuz feature'a bağlayın.

**Tanım bağlantısı:** `feature.Geometry = curvePolygon;` tamamen oluşturulmuş geometriyi feature'a ekler, böylece kalıcı hale hazır olur.  

```csharp
feature.Geometry = curvePolygon;
```

### Adım 8: feature'ı katmana ekle
Son olarak, feature'ı vektör katmanına ekleyin, böylece veri kümesinin bir parçası olur.

**Tanım bağlantısı:** `layer.Add(feature);` feature'ı Shapefile'a yazar; `using` bloğu sona erdiğinde verileri diske yazar.  

```csharp
layer.Add(feature);
```

`using` bloğu bittiğinde, Shapefile diske yazılır.

## Yaygın sorunlar ve çözümler
| Sorun | Neden olur | Çözüm |
|-------|------------|-------|
| **Dosya oluşturulmadı** | Yanlış yol veya yazma izinlerinin eksik olması | Dizin mevcut mu ve uygulamanın yazma izni olup olmadığını kontrol edin. |
| **Eğri kenarlar bazı görüntüleyicilerde düz çizgi olarak görünür** | Görüntüleyici dairesel dizgileri desteklemiyor | Shapefile spesifikasyonunu tam destekleyen bir GIS uygulaması kullanın (ör. QGIS 3.28+). |
| **`AddPoint` üzerinde `ArgumentException` istisnası** | Noktalar seçilen CBS için geçerli koordinat aralığının dışındadır | Kullanmaya planladığınız koordinat referans sisteminin içinde koordinatların olduğundan emin olun. |

## Sıkça sorulan sorular

**S: Aspose.GIS for .NET diğer GIS kütüphaneleriyle uyumlu mu?**  
C: Evet, Aspose.GIS for .NET birçok popüler GIS formatı ile birlikte çalışabilirliği destekler, GDAL/OGR, Proj.NET ve diğer .NET GIS araç takımlarıyla sorunsuz veri alışverişi sağlar.

**S: Oluşturulan eğri çokgen geometrisini GIS yazılımında görselleştirebilir miyim?**  
C: Kesinlikle. Oluşturulan Shapefile QGIS, ArcGIS veya Shapefile formatını okuyup dairesel dizgileri destekleyen herhangi bir GIS aracıyla açılabilir.

**S: Aspose.GIS for .NET mekânsal analiz yetenekleri sunuyor mu?**  
C: Evet, mekânsal sorgulama, tamponlama, kesişim ve diğer analiz fonksiyonlarını içerir; böylece .NET içinde doğrudan ileri seviye coğrafi işlem yapabilirsiniz.

**S: Yardım almak ya da diğer kullanıcılarla fikir alışverişi yapmak için nereden ulaşabilirim?**  
C: Diğer geliştiricilerle bağlantı kurmak için Aspose.GIS topluluk forumuna katılın: [Aspose.GIS community forum](https://forum.aspose.com/c/gis/33)

**S: Satın almadan önce ücretsiz deneme sürümü mevcut mu?**  
C: Elbette! Tüm özellikleri değerlendirebileceğiniz ücretsiz deneme sürümünü [Aspose.GIS free trial downloads](https://releases.aspose.com/) adresinden indirebilirsiniz.

## Sonuç
Artık Aspose.GIS for .NET kullanarak **vektör katmanı oluşturma** ve **eğri çokgen oluşturma** geometrisini nasıl yapacağınızı, Shapefile olarak nasıl kaydedeceğinizi ve yaygın hatalar ile SSS'leri incelediniz. Farklı koordinat setleriyle denemeler yapmaktan, öznitelik verileri eklemekten veya katmanı daha büyük GIS iş akışlarına entegre etmekten çekinmeyin.

---

**Last Updated:** 2026-08-24  
**Tested With:** Aspose.GIS for .NET 24.11  
**Author:** Aspose

## İlgili Öğreticiler

- [Aspose.GIS for .NET'te Vektör Katmanı ve Dairesel Dizi Oluştur](/gis/net/geometry-creation/create-circular-string-geometry/)
- [Aspose.GIS for .NET kullanarak SRS ile Vektör Katmanı Nasıl Oluşturulur](/gis/net/layer-management/create-vector-layer-with-srs/)
- [Aspose.GIS kullanarak Delikli Çokgen Geometrisi Oluştur](/gis/net/geometry-creation/create-polygon-with-hole-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
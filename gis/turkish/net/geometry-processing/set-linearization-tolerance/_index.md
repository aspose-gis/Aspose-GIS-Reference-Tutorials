---
date: 2026-05-31
description: Aspose.GIS for .NET kullanarak GeoJSON oluşturmayı, GeoJSON seçeneklerini
  yapılandırmayı ve katmana özellik eklemeyi öğrenin. Bu adım adım kılavuzu izleyin.
keywords:
- how to create geojson
- add feature to layer
- configure geojson options
linktitle: Doğrusallaştırma Toleransını Ayarla
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  headline: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  name: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  steps:
  - name: Configure GeoJSON Options (how to set tolerance)
    text: '`GeoJsonOptions` specifies the serialization settings used when writing
      GeoJSON files. `GeoJsonOptions` defines how Aspose.GIS serializes GeoJSON, including
      linearization tolerance, coordinate precision, and other output settings. We’ll
      create a `GeoJsonOptions` object and tell Aspose.GIS how close '
  - name: Define the Output Path (how to export GeoJSON)
    text: Specify the full file path where the resulting GeoJSON will be saved. Ensure
      the folder exists and the application has write permissions.
  - name: '**Create Vector Layer** with the configured options'
    text: The `VectorLayer` class represents a GIS container that can read and write
      spatial data. `Drivers.GeoJson` is the driver identifier for writing GeoJSON
      format files. Using `VectorLayer.Create` together with the `Drivers.GeoJson`
      driver and the previously configured `GeoJsonOptions` creates a new Geo
  - name: Construct a Geometry (e.g., a circular string)
    text: '`CircularString` is a curved line geometry that Aspose.GIS can linearize
      based on the tolerance you set. You can replace this with any valid WKT representation
      such as `POINT`, `LINESTRING`, or `POLYGON`.'
  - name: '**Add Feature to Layer** and save'
    text: '`Feature` is the object that couples a geometry with attribute data. After
      creating a `Feature` instance, assign the geometry, optionally add attribute
      values, and call `layer.Add(feature)` to persist it. When the `using` block
      ends, the layer is automatically written to the file defined in `path`. '
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. A commercial license removes all evaluation restrictions and
      provides full technical support.
    question: Can I use Aspose.GIS in commercial projects?
  - answer: Yes, it supports over 30 formats—including Shapefile, KML, GML, and CSV—allowing
      seamless conversion between them.
    question: Does Aspose.GIS support other GIS formats besides GeoJSON?
  - answer: You can download a free 30‑day trial from the Aspose website; it includes
      all features.
    question: Is there a trial version available?
  - answer: Use the Aspose forums, the dedicated support portal, or the “Contact Support”
      link in the product dashboard.
    question: Where can I get support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile Toleranslı GeoJSON Nasıl Oluşturulur
url: /tr/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GeoJSON'i Tolerans ile Oluşturma Aspose.GIS for .NET

## Giriş
**GeoJSON** dosyaları oluşturmayı, eğri hassasiyetini kontrol etmeyi ve sonucu doğrudan kullanılabilir bir belge olarak dışa aktarmayı öğrenmek istiyorsanız, Aspose.GIS for .NET bu süreci oldukça basitleştirir. Bu öğreticide GeoJSON seçeneklerini nasıl yapılandıracağınızı, lineerleştirme toleransını nasıl ayarlayacağınızı ve **özelliği katmana ekleme** işlemini kodunuzu temiz ve üretime hazır tutarak nasıl gerçekleştireceğinizi keşfedeceksiniz.

## Hızlı Yanıtlar
- **“vektör katmanı oluştur” ne anlama geliyor?** Yeni bir GIS vektör veri kümesi (ör. bir GeoJSON dosyası) oluşturur; bu küme geometrileri ve öznitelikleri depolayabilir.  
- **Lineerleştirme toleransı nasıl ayarlanır?** Katmanı oluşturmadan önce bir `GeoJsonOptions` örneği üzerinde `LinearizationTolerance` özelliğini ayarlayın.  
- **GeoJSON dosyasını doğrudan dışa aktarabilir miyim?** Evet—`VectorLayer.Create` metodunu `Drivers.GeoJson` sürücüsü ve yapılandırılmış seçeneklerle kullanın.  
- **Lisans gerekli mi?** Geçerli bir Aspose.GIS lisansı tüm özellikleri açar; geçici değerlendirme anahtarı test amaçlı çalışır.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “Vektör katmanı oluştur” ne demektir?
Vektör katmanı oluşturmak, noktalar, çizgiler, çokgenler ve ilişkili öznitelik verilerini tutabilen yeni bir GIS konteyneri (ör. bir GeoJSON dosyası) başlatmak anlamına gelir. Bu katman, oluşturduğunuz herhangi bir geometriyi ve eklediğiniz öznitelikleri hedef alır.

## Neden GeoJSON seçeneklerini yapılandırmalıyız?
GeoJSON seçeneklerini—özellikle **lineerleştirme toleransını**—yapılandırmak, eğri geometrilerin (ör. `CircularString`) uygulamanızın doğruluk gereksinimlerine uygun bir hassasiyetle yaklaşık olarak temsil edilmesini sağlar. Doğru yapılandırma, dosya boyutunu küçültürken görsel doğruluğu korur; bu, GeoJSON'in web haritaları veya mekansal analiz araçları tarafından tüketildiği durumlarda kritiktir.

## Önkoşullar
Başlamadan önce şunların kurulu olduğundan emin olun:

1. **Visual Studio** (herhangi bir yeni sürüm).  
2. **Aspose.GIS lisansı** (veya geçici değerlendirme anahtarı).  
3. Projenizde referans olarak **Aspose.GIS for .NET** kütüphanesi.  
4. **C#** hakkında temel bilgi.

## Ad Alanlarını İçeri Aktarın
Derleyicinin GIS sınıflarını nerede bulacağını bilmesi için gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım‑Adım Kılavuz

### Adım 1: GeoJSON Seçeneklerini Yapılandırma (tolerans nasıl ayarlanır)
`GeoJsonOptions`, GeoJSON dosyaları yazılırken kullanılan serileştirme ayarlarını belirler.  
`GeoJsonOptions`, Aspose.GIS'in GeoJSON'i nasıl serileştirdiğini, lineerleştirme toleransını, koordinat hassasiyetini ve diğer çıktı ayarlarını tanımlar.  
Bir `GeoJsonOptions` nesnesi oluşturacağız ve Aspose.GIS'e lineerleştirilmiş geometrinin orijinal eğriye ne kadar yakın olması gerektiğini söyleyeceğiz.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Adım 2: Çıktı Yolunu Tanımlama (GeoJSON nasıl dışa aktarılır)
Oluşturulan GeoJSON'in kaydedileceği tam dosya yolunu belirtin. Klasörün var olduğundan ve uygulamanın yazma iznine sahip olduğundan emin olun.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Adım 3: **Vektör Katmanı Oluştur** yapılandırılmış seçeneklerle
`VectorLayer` sınıfı, mekansal verileri okuyup yazabilen bir GIS konteynerini temsil eder.  
`Drivers.GeoJson`, GeoJSON formatı dosyaları yazmak için kullanılan sürücü tanımlayıcısıdır.  
`VectorLayer.Create` metodunu `Drivers.GeoJson` sürücüsü ve önceden yapılandırılmış `GeoJsonOptions` ile birlikte kullanarak, özellik eklemeye hazır yeni bir GeoJSON dosyası oluştururuz.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Adım 4: Bir Geometri Oluşturma (ör. dairesel dize)
`CircularString`, Aspose.GIS'in ayarladığınız toleransa göre lineerleştirebileceği eğri bir çizgi geometrisidir. Bunu `POINT`, `LINESTRING` veya `POLYGON` gibi geçerli herhangi bir WKT temsiliyle değiştirebilirsiniz.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Adım 5: **Katmana Özellik Ekle** ve kaydet
`Feature`, bir geometriyi öznitelik verileriyle eşleştiren nesnedir. Bir `Feature` örneği oluşturduktan sonra geometriyi atayın, isteğe bağlı olarak öznitelik değerleri ekleyin ve `layer.Add(feature)` çağrısıyla kalıcı hâle getirin. `using` bloğu sona erdiğinde katman, `path` içinde tanımlanan dosyaya otomatik olarak yazılır.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

`using` bloğu sona erdiğinde katman, `path` içinde tanımlanan dosyaya otomatik olarak yazılır ve size kullanıma hazır bir GeoJSON dosyası sunar.

## Yaygın Sorunlar ve İpuçları
- **Yanlış yol** – Dizinin var olduğunu ve yazma izninizin bulunduğunu doğrulayın.  
- **Tolerans çok düşük** – `LinearizationTolerance` değerini çok küçük ayarlamak dosya boyutunu dramatik şekilde artırabilir; genellikle 0.001 toleransı hassasiyet ve boyut arasında iyi bir denge sağlar.  
- **Lisans hataları** – Lisans uyarıları görürseniz, herhangi bir Aspose.GIS çağrısından önce lisans dosyasının yüklendiğinden emin olun.  
- **Performans notu** – Aspose.GIS, akış mimarisi sayesinde belgeyi tamamen belleğe yüklemeden 2 GB’a kadar dosyaları işleyebilir.

## Sıkça Sorulan Sorular

**S: Aspose.GIS for .NET diğer .NET çerçeveleriyle uyumlu mu?**  
C: Evet, .NET Framework 4.5+, .NET Core 3.1+ ve .NET 5/6/7 ile çalışır.

**S: Aspose.GIS'i ticari projelerde kullanabilir miyim?**  
C: Kesinlikle. Ticari lisans tüm değerlendirme kısıtlamalarını kaldırır ve tam teknik destek sağlar.

**S: Aspose.GIS GeoJSON dışındaki GIS formatlarını destekliyor mu?**  
C: Evet, Shapefile, KML, GML, CSV gibi 30’dan fazla formatı destekler; aralarında sorunsuz dönüşüm yapabilirsiniz.

**S: Deneme sürümü mevcut mu?**  
C: Aspose web sitesinden 30 günlük ücretsiz deneme sürümünü indirebilirsiniz; tüm özellikler dahildir.

**S: Destek nereden alınır?**  
C: Aspose forumları, özel destek portalı veya ürün kontrol panelindeki “Contact Support” bağlantısı kullanılabilir.

## Sonuç
Bu adımları izleyerek **GeoJSON oluşturmayı**, lineerleştirme toleransını yapılandırmayı ve **özelliği katmana eklemeyi** öğrenmiş oldunuz; böylece GeoJSON dışa aktarımını sorunsuz bir şekilde gerçekleştirebilirsiniz. Ek geometri tiplerini, öznitelik yönetimini ve toplu işleme senaryolarını keşfederek Aspose.GIS'i .NET GIS projelerinizde tam anlamıyla kullanın.

---

**Son Güncelleme:** 2026-05-31  
**Test Edilen Sürüm:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [GeoJSON Nasıl Dönüştürülür – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [Vektör Katmanı Oluştur, Hassasiyeti Sınırla Aspose.GIS for .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [File GDB'de Vektör Katmanı Oluştur – Aspose.GIS .NET Öğreticisi](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
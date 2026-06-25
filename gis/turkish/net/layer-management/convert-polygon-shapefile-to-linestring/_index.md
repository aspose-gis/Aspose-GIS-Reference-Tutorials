---
date: 2026-06-25
description: Aspose.GIS for .NET kullanarak shapefile'ı nasıl okuyacağınızı ve bir
  polygon shapefile'ı linestring'e nasıl dönüştüreceğinizi öğrenin. Açık adım‑adım
  rehberlikle GIS geliştirme sürecinizi hızlandırın.
keywords:
- how to read shapefile
- convert polygon to line
- shapefile to geojson c#
- extract lines from polygon
linktitle: Polygon Shapefile'ı Linestring'e Dönüştürme
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  headline: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  type: TechArticle
- description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  name: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  steps:
  - name: Set the Document Directory
    text: Replace `"Your Document Directory"` with the actual path where your shapefile
      resides.
  - name: Open the Source Shapefile
    text: This line opens the source Polygon Shapefile so you can read its features.
  - name: Create the Destination Linestring Shapefile
    text: Here we create a new Linestring Shapefile that will store the converted
      geometries.
  - name: Iterate Through Source Features
    text: The loop walks through each polygon feature in the original file.
  - name: Convert Polygon to Linestring and Write to Destination
    text: The `ExteriorRing` property returns the outer boundary of a polygon as a
      `LineString`. In this block we convert polygon to line (`LineString`) and add
      the new feature to the destination shapefile.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS supports .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7, ensuring seamless integration with modern development stacks.
    question: Is Aspose.GIS compatible with all versions of .NET?
  - answer: Yes, you can. Purchase a license [here](https://purchase.aspose.com/buy)
      to remove evaluation limitations and obtain full support.
    question: Can I use Aspose.GIS for commercial projects?
  - answer: Yes, you can find comprehensive documentation and code samples on the
      [documentation page](https://reference.aspose.com/gis/net/).
    question: Are there any examples or documentation available?
  - answer: Absolutely – explore Aspose.GIS with a free trial by visiting [this link](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      assistance and official support.
    question: Where can I seek help or support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Shapefile C# Nasıl Okunur – Polygon Shapefile'ı Linestring'e Dönüştürme
url: /tr/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Shapefile C# Okuma – Polygon Shapefile'ı Linestring'e Dönüştürme

## Giriş
Eğer .NET ortamında **shapefile nasıl okunur** verilerine ihtiyacınız varsa, doğru yerdesiniz. Aspose.GIS for .NET, bir Shapefile'ın düşük seviyeli ikili formatını soyutlayarak, sadece birkaç API çağrısıyla coğrafi özellikleri yüklemenize, sorgulamanıza ve dönüştürmenize olanak tanır. Bir polygon shapefile'ını linestring'e dönüştürmek, yönlendirme, ağ analizi veya basit görselleştirme için doğrusal temsiller çıkarmak istediğinizde özellikle faydalıdır.

## Hızlı Yanıtlar
- **Hangi kütüphane shapefile c# okumanıza yardımcı olur?** Aspose.GIS for .NET – 50+ GIS formatını destekler ve tüm dosyayı belleğe yüklemeden birkaç yüz megabayta kadar dosyaları işleyebilir.  
- **Bir poligonu çizgiye dönüştürebilir misiniz?** Evet – poligonun dış halkasına `LineString` çağırın ve sonucu yeni bir shapefile'a yazın.  
- **Üretim için lisansa ihtiyacım var mı?** Üretim dağıtımları için ticari bir lisans gereklidir; değerlendirme için ücretsiz deneme sürümü çalışır.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Deneme sürümü mevcut mu?** Kesinlikle – Aspose sitesinden ücretsiz bir deneme sürümü indirin.  

`LineString` bağlı çizgi segmentlerinden oluşan bir dizi temsilen bir geometri tipidir.

## “read shapefile c#” nedir?
`Document` bir GIS veri kümesini temsil eden ve özelliklerine erişim sağlayan temel sınıftır.  
C#'ta bir shapefile okumak, `.shp` dosyasını belleğe yüklemek anlamına gelir, böylece geometrilerini sorgulayabilir, değiştirebilir veya dönüştürebilirsiniz. **`Document` sınıfını dosya yolu ile örnekleyerek, Aspose.GIS ikili yapıyı sizin için ayrıştırır**, özellikleri kullanımı kolay bir koleksiyon aracılığıyla sunar. Bu yaklaşım, düşük seviyeli dosya başlıkları veya koordinat dizileriyle manuel olarak çalışma ihtiyacını ortadan kaldırır.

## Neden Aspose.GIS ile poligonu çizgiye dönüştürmeliyiz?
Bir poligonu linestring'e dönüştürmek, iç halkaları kaldırırken dış sınırı tam olarak korur ve size temiz bir doğrusal temsil sağlar. Aspose.GIS, **tipik bir sunucuda 500 MB'a kadar veri kümesini 2 saniyenin altında işler**, toplu dönüşümleri hızlı ve bellek‑verimli hâle getirir. Kütüphane ayrıca orijinal uzamsal referansı korur, böylece ortaya çıkan çizgiler mevcut GIS katmanlarıyla mükemmel bir şekilde hizalanır.

## Önkoşullar
Öğreticiye başlamadan önce, aşağıdakilerin hazır olduğundan emin olun:

- **Aspose.GIS Kütüphanesi** – Aspose.GIS kütüphanesini [website](https://releases.aspose.com/gis/net/) adresinden indirin ve kurun.  
- **Shapefile Verisi** – Dönüştürme için bir Polygon Shapefile'ınız olsun. Yoksa örnek veri bulabilir veya kendiniz oluşturabilirsiniz.  
- **Geliştirme Ortamı** – Gerekli araçlarla (.NET SDK, Visual Studio vb.) .NET geliştirme ortamınızı kurun.

## Ad Alanlarını İçe Aktarma
`Document` sınıfı, bir GIS veri kümesini temsil eden ve shapefile'ları okuma ve yazma yöntemleri sunan Aspose.GIS'in temel nesnesidir. Kod dosyanızın başına aşağıdaki ad alanlarını ekleyin:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Shapefile nasıl okunur ve poligon linestring'e nasıl dönüştürülür?
Kaynak polygon shapefile'ını yükleyin, her poligonun dış halkasını çıkarın, o halkadan bir `LineString` oluşturun ve sonucu yeni bir shapefile'a yazın – beş basit adımda. Bu desen, herhangi bir boyuttaki veri kümesi için çalışır ve kaynağın koordinat sisteminin hedefte korunmasını sağlar.

### Adım 1: Document Dizinini Ayarla
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
`"Your Document Directory"` ifadesini shapefile'ınızın bulunduğu gerçek yol ile değiştirin.

### Adım 2: Kaynak Shapefile'ı Aç
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Bu satır, kaynak Polygon Shapefile'ı açar, böylece özelliklerini okuyabilirsiniz.

### Adım 3: Hedef Linestring Shapefile'ı Oluştur
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Burada, dönüştürülmüş geometrileri depolayacak yeni bir Linestring Shapefile oluşturuyoruz.

### Adım 4: Kaynak Özellikler Üzerinde Döngü
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
Döngü, orijinal dosyadaki her polygon özelliği üzerinde gezinir.

### Adım 5: Poligonu Linestring'e Dönüştür ve Hedefe Yaz
`ExteriorRing` özelliği, bir poligonun dış sınırını `LineString` olarak döndürür.  
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
Bu blokta poligonu çizgiye (`LineString`) dönüştürüyoruz ve yeni özelliği hedef shapefile'a ekliyoruz.

## Yaygın Sorunlar ve İpuçları
- **Koordinat Sistemi Uyumsuzluğu** – Hem kaynak hem de hedef katmanların aynı uzamsal referansı kullandığından emin olun; aksi takdirde çizgiler yer değiştirmiş görünebilir.  
- **Büyük Dosyalar** – Çok büyük shapefile'ları işlerken, tümünü bir kerede belleğe yüklemek yerine özellikleri akış olarak işlemeyi düşünün.  
- **Null Geometriler** – Çalışma zamanı istisnalarından kaçınmak için boş geometriye sahip özelliklere karşı önlem alın.  
- **Poligondan çizgi çıkarma** – Sadece dış halkaya ihtiyacınız varsa `ExteriorRing` özelliğini kullanın; iç halkalar için `InteriorRings` üzerinde döngü yapın.  

## Sıkça Sorulan Sorular

**S: Aspose.GIS tüm .NET sürümleriyle uyumlu mu?**  
C: Evet, Aspose.GIS .NET Framework 4.5+, .NET Core 3.1+, ve .NET 5/6/7'yi destekler, modern geliştirme yığınlarıyla sorunsuz entegrasyon sağlar.

**S: Aspose.GIS'i ticari projelerde kullanabilir miyim?**  
C: Evet, kullanabilirsiniz. Değerlendirme sınırlamalarını kaldırmak ve tam destek almak için bir lisans satın alın [buradan](https://purchase.aspose.com/buy).

**S: Herhangi bir örnek veya dokümantasyon mevcut mu?**  
C: Evet, kapsamlı dokümantasyon ve kod örneklerini [documentation page](https://reference.aspose.com/gis/net/) adresinde bulabilirsiniz.

**S: Deneme sürümü mevcut mu?**  
C: Kesinlikle – [bu linki](https://releases.aspose.com/) ziyaret ederek Aspose.GIS'i ücretsiz deneme sürümüyle keşfedebilirsiniz.

**S: Yardım veya destek nereden alınabilir?**  
C: Topluluk yardımı ve resmi destek için [Aspose.GIS forumunu](https://forum.aspose.com/c/gis/33) ziyaret edin.

---

**Son Güncelleme:** 2026-06-25  
**Test Edilen:** Aspose.GIS for .NET (en son sürüm)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.GIS for .NET kullanarak Shapefile'ı GeoJSON'a Dönüştürme](/gis/net/layer-management/extract-features-to-geojson/)
- [Aspose.GIS for .NET ile Akıştan GeoJSON Okuma](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Aspose.GIS for .NET ile Polygon Geometrisi Oluşturma](/gis/net/geometry-creation/create-polygon-geometry/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
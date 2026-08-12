---
date: 2026-05-21
description: Aspose.GIS for .NET kullanarak GeoJSON'u akışa nasıl yazacağınızı öğrenin.
  Bu GeoJSON .NET öğreticisi, noktaların adım adım dönüştürülmesini ve GeoJSON C#
  kodunun oluşturulmasını gösterir.
keywords:
- how to write geojson
- convert points geojson
- geojson tutorial .net
- generate geojson c#
linktitle: GeoJSON'u Akışa Yaz
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to write GeoJSON to stream using Aspose.GIS for .NET. This
    geojson tutorial .net shows step‑by‑step conversion of points and generation of
    GeoJSON C# code.
  headline: How to Write GeoJSON to Stream with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile GeoJSON'u Akışa Yazma
url: /tr/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GeoJSON'i Akışa Yazma

## Giriş
Bu eğitimde Aspose.GIS kullanarak bir .NET uygulamasında **GeoJSON'i bir akışa nasıl yazacağınızı** öğreneceksiniz. Ortamı kurmaktan geçerli bir GeoJSON belgesi üretmeye kadar her adımı adım adım inceleyeceğiz, böylece coğrafi verileri hizmetlerinize sorunsuz bir şekilde entegre edebilirsiniz.

## Hızlı Yanıtlar
- **GeoJSON çıktısı için birincil sınıf hangisidir?** `VectorLayer` ve `GeoJsonDriver`.
- **Geliştirme için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Nokta koleksiyonlarını GeoJSON'e dönüştürebilir miyim?** Evet – `Feature` sınıfını kullanın ve nokta geometrisini tanımlayın.
- **Büyük veri setleri için akış (streaming) destekleniyor mu?** Kesinlikle; `MemoryStream` ara dosyalar olmadan yazmanıza olanak tanır.

## GeoJSON Nedir?
GeoJSON, coğrafi veri yapılarını JSON kullanarak kodlamak için açık bir standart formattır. FeatureCollection, Feature ve geometri türleri (Point, LineString, Polygon) gibi nesneleri tanımlar. Bu hafif, web‑dostu temsil, birçok platform ve programlama dili arasında mekânsal verilerin kolayca değiş tokuş edilmesini ve görselleştirilmesini sağlar.

## GeoJSON Oluşturma İçin Aspose.GIS Neden Kullanılmalı?
Aspose.GIS, 30'dan fazla mekânsal dosya formatını destekler ve tüm belgeyi belleğe yüklemeden 2 GB'den büyük dosyaları işleyebilir. Yüksek performanslı akış motoru, GeoJSON'i doğrudan akışlara yazarak I/O yükünü azaltır. Bu, kurumsal ölçekli mekânsal iş yükleri, bulut hizmetleri ve gerçek zamanlı uygulamalar için idealdir.

## Önkoşullar
Eğitime başlamadan önce aşağıdaki önkoşulların sağlandığından emin olun:
1. Aspose.GIS for .NET Kütüphanesi: Aspose.GIS for .NET kütüphanesinin yüklü olduğundan emin olun. [buradan](https://releases.aspose.com/gis/net/) indirebilirsiniz.
2. Belge Dizinı: Projenizde bir belge dizini oluşturun ve yolunu not edin.

Şimdi, eğitime başlayalım!

## GeoJSON'i Akışa Nasıl Yazabilirim?
VectorLayer, GeoJSON dahil çeşitli formatlarda kaydedilebilen bir vektör veri kümesini temsil eder.  
GeoJsonDriver, Aspose.GIS'in GeoJSON dosyalarını okuma ve yazma için kullandığı sürücüdür.  
`layer.Save`, belirtilen kaydetme seçenekleriyle katman içeriğini verilen akışa yazar.  

`GeoJsonDriver` ile bir `VectorLayer` yükleyin, nokta geometrisi içeren özellikler ekleyin ve ardından `layer.Save(stream, new GeoJsonSaveOptions())` metodunu çağırın. Bu, sadece birkaç satır kodla tam, standartlara uygun bir GeoJSON belgesini verilen `MemoryStream` içine doğrudan yazar. Metot, özellik koleksiyonunu serileştirir, öznitelik verilerini ve geometri dönüşümünü otomatik olarak işler, böylece manuel dize manipülasyonu yapmadan kullanıma hazır bir JSON yükü elde edersiniz.

## Ad Alanlarını İçe Aktarma
İlk olarak, kodunuzda Aspose.GIS işlevlerine erişmek için gerekli ad alanlarını eklediğinizden emin olun:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Adım 1: Belge Dizinini Ayarlama
```csharp
string dataDir = "Your Document Directory";
```
"Your Document Directory" ifadesini belge dizininizin gerçek yolu ile değiştirin.

## Adım 2: Memory Stream Oluşturma
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Adım 3: GeoJSON Sürücüsüyle Vector Katmanı Oluşturma
`VectorLayer` sınıfı, GeoJSON dahil çeşitli formatlarda kaydedilebilen bir vektör veri kümesini temsil eder.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Adım 4: Özellik Niteliklerini Tanımlama
Özellikleriniz için öznitelik şemasını tanımlayın (ör. ID, Name).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Adım 5: Özellikleri Oluşturma ve Ekleme
`Feature` nesneleri oluşturun, nokta geometrisi atayın, öznitelik değerlerini ayarlayın ve bunları katmana ekleyin.  
```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## Adım 6: GeoJSON Çıktısını Görüntüleme
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Tebrikler! Aspose.GIS for .NET kullanarak GeoJSON'i başarıyla bir akışa yazdınız.

## Yaygın Sorunlar ve Çözümler
- **Boş çıktı akışı:** Okumadan önce akış konumunu (`stream.Position = 0`) sıfırladığınızdan emin olun.
- **Yanlış koordinat sırası:** GeoJSON uzunluk‑enlem sırasını bekler; nokta değerlerinizi kontrol edin.
- **Büyük veri setleri:** Özellikleri artımlı olarak akıta almak için `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` kullanın.

## Sık Sorulan Sorular
### Aspose.GIS for .NET'i hem Windows hem de Linux ortamlarında kullanabilir miyim?
Evet, Aspose.GIS for .NET hem Windows hem de Linux sistemleriyle uyumludur.  

### Ücretsiz deneme mevcut mu?
Kesinlikle! Ücretsiz denemeyi [buradan](https://releases.aspose.com/) keşfedebilirsiniz.  

### Ayrıntılı belgeleri nerede bulabilirim?
Belgelere [buradan](https://reference.aspose.com/gis/net/) göz atabilirsiniz.  

### Geçici lisans nasıl alabilirim?
Geçici lisanslar [buradan](https://purchase.aspose.com/temporary-license/) temin edilebilir.  

### Yardıma mı ihtiyacınız var ya da daha fazla sorunuz mu var?
Destek forumumuzu [buradan](https://forum.aspose.com/c/gis/33) ziyaret edin.  

**S: Enlem/boylam noktalarından bir koleksiyonla GeoJSON oluşturabilir miyim?**  
C: Evet – her nokta için bir `Feature` oluşturun, bir `Point` geometrisi atayın ve `VectorLayer`a ekleyin.  

**S: Aspose.GIS sıkıştırılmış GeoJSON (gzip) yazmayı destekliyor mu?**  
C: Kaydetmeden önce `MemoryStream`i bir `GZipStream` içinde sararak sıkıştırılmış bir yük oluşturabilirsiniz.  

**S: Aspose.GIS'in işleyebileceği maksimum GeoJSON dosya boyutu nedir?**  
C: Kütüphane 2 GB'den büyük dosyaları akıtabilir; veri artımlı olarak yazıldığı için bellek kullanımı düşük kalır.  

---

**Son Güncelleme:** 2026-05-21  
**Test Edildi:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Eğitimler

- [Aspose.GIS for .NET ile Akıştan GeoJSON Okuma](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Aspose.GIS ile GeoJSON'i TopoJSON'e Dönüştürme](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Aspose.GIS for .NET kullanarak Shapefile'ı GeoJSON'e Dönüştürme](/gis/net/layer-management/extract-features-to-geojson/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
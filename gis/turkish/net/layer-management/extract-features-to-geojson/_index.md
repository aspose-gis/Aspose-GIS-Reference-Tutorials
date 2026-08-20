---
date: 2026-07-05
description: Aspose.GIS for .NET kullanarak shapefile'ı geojson'a nasıl dönüştüreceğinizi
  öğrenin. Kılavuz ayrıca katmanlar arasında öznitelik kopyalamayı ve c# ile geojson
  dosyası oluşturmayı kapsar.
keywords:
- convert shapefile to geojson
- export shapefile as geojson
- aspose gis conversion
- read shapefile c#
- write geojson c#
linktitle: Özellikleri GeoJSON'a Çıkar
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  headline: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  name: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  steps:
  - name: Open Input Shapefile
    text: The `VectorLayer.Open` method reads a Shapefile and returns an enumerable
      collection of `Feature` objects that you can iterate over.
  - name: Create Output GeoJSON
    text: '`VectorLayer.Create` with the `Drivers.GeoJson` driver creates an empty
      GeoJSON file ready to receive features.'
  - name: Copy Attributes Between Layers
    text: '`CopyAttributes` copies the attribute schema (field names and data types)
      from the source Shapefile to the new GeoJSON layer in a single call.'
  - name: Process Features
    text: Iterate through each feature in the Shapefile so you can apply any custom
      logic before writing it out.
  - name: Filter Features by Date
    text: In this example we skip records whose `dob` (date of birth) field is missing
      or earlier than 1 Jan 1982. Adjust the filter to match your own data requirements.
  - name: Construct a New Feature (C# Generate GeoJSON File)
    text: A `Feature` represents a single spatial element containing geometry and
      attribute data. Here we build a new `Feature` for the GeoJSON layer, copy the
      geometry and attribute values, and add it to the output. This is the core of
      *c# generate geojson file*. Congratulations! You’ve successfully **conver
  type: HowTo
- questions:
  - answer: Visit the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/)
      for in‑depth information.
    question: Where can I find more documentation?
  - answer: You can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license?
  - answer: Join the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I seek support?
  - answer: Yes, you can find the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can buy the product [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile Shapefile'ı GeoJSON'a Dönüştür
url: /tr/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Shapefile'ı GeoJSON'a Aspose.GIS for .NET ile Dönüştür

## Giriş
Bu kapsamlı, adım‑adım öğreticide **shapefile'ı geojson'a nasıl dönüştüreceğinizi** güçlü Aspose.GIS .NET kütüphanesini kullanarak öğreneceksiniz. İster bir haritalama web servisi oluşturuyor olun, bir mobil GIS uygulaması için veri hazırlıyor olun ya da sadece formatlar arasında veri değiş tokuşu yapmanız gerekiyor olsun, bu kılavuz tam olarak ne yapmanız gerektiğini, her adımın neden önemli olduğunu ve yaygın tuzaklardan nasıl kaçınacağınızı gösterir.

## Hızlı Yanıtlar
- **Bu öğretici neyi kapsıyor?** Shapefile'ı GeoJSON dosyasına dönüştürme, katmanlar arasında öznitelikleri kopyalama ve çıktıyı C# ile oluşturma.
- **Hangi kütüphane gerekiyor?** Aspose.GIS for .NET.
- **Lisans gerekli mi?** Üretim için geçici veya tam lisans gerekir; değerlendirme için ücretsiz deneme çalışır.
- **Uygulama ne kadar sürer?** Temel bir dönüşüm için yaklaşık 10‑15 dakika.
- **Bunu .NET Core/.NET 6 üzerinde çalıştırabilir miyim?** Evet – kod tüm desteklenen .NET sürümlerinde çalışır.

## Shapefile'ı GeoJSON'a Dönüştürmek Nedir?
Shapefile'ı GeoJSON'a dönüştürmek, klasik ESRI Shapefile formatından vektör özelliklerini okuyup modern, web‑uyumlu bir GeoJSON belgesi olarak yazmak anlamına gelir. Bu dönüşüm, GIS verilerini doğrudan Leaflet veya Mapbox GL gibi JavaScript haritalama kütüphanelerine beslemenizi sağlar ve masaüstü GIS araçları ile web API'leri arasındaki veri değişimini basitleştirir.

## Bu Dönüşüm İçin Neden Aspose.GIS Kullanmalı?
Aspose.GIS, düşük seviyeli ikili ayrıştırmayı soyutlar, 50+ giriş ve çıkış formatını destekler ve tüm dosyayı belleğe yüklemeden çok sayfalı veri setlerini işleyebilir. Kütüphane ayrıca .NET Framework, .NET Core ve .NET 5/6 arasında çalışan temiz, nesne‑yönelimli bir API sunar; böylece format incelikleriyle uğraşmak yerine iş mantığına odaklanırsınız.

## Önkoşullar
- Aspose.GIS for .NET: Kütüphanenin yüklü olduğundan emin olun. Yüklü değilse, [Aspose.GIS for .NET sayfasından](https://releases.aspose.com/gis/net/) indirebilirsiniz.
- Shapefile Verileri: Giriş için hazır bir Shapefile'ınız olsun. Örnek veri gerekiyorsa, [Aspose.GIS belgelerinde](https://reference.aspose.com/gis/net/) bulabilirsiniz.
- .NET Ortamı: Sağlanan kodu çalıştırmak için bir .NET ortamı kurun.
- Belge Dizini: Kod parçacığında belge dizininizin yolunu tanımlayın.

Şimdi her şey hazır, shapefile'ı geojson'a dönüştürmeye başlayalım!

## Shapefile'ı GeoJSON'a Nasıl Dönüştürülür
Kaynak Shapefile'ı yükleyin, hedef GeoJSON katmanını oluşturun, öznitelik şemasını kopyalayın, kayıtları filtreleyin ve sonuçları yazın—tüm bunlar birkaç özlü adımda yapılır. Tam iş akışı tek bir `using` bloğu içinde rahatça sığar ve kaynakların otomatik olarak serbest bırakılmasını sağlar.

### Adım 1: Giriş Shapefile'ını Aç
`VectorLayer.Open` yöntemi bir Shapefile okur ve üzerinde dönebileceğiniz `Feature` nesnelerinin bir koleksiyonunu döndürür.

```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```

### Adım 2: Çıktı GeoJSON Oluştur
`Drivers.GeoJson` sürücüsüyle `VectorLayer.Create` boş bir GeoJSON dosyası oluşturur ve özellikleri almaya hazır hâle getirir.

```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```

### Adım 3: Katmanlar Arasında Öznitelikleri Kopyala
`CopyAttributes` tek bir çağrıyla kaynak Shapefile'dan yeni GeoJSON katmanına öznitelik şemasını (alan adları ve veri tipleri) kopyalar.

```csharp
outputLayer.CopyAttributes(inputLayer);
```

### Adım 4: Özellikleri İşle
Shapefile'daki her bir özelliği yineleyerek, yazmadan önce istediğiniz özel mantığı uygulayabilirsiniz.

```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```

### Adım 5: Özellikleri Tarihe Göre Filtrele
Bu örnekte `dob` (doğum tarihi) alanı eksik olan veya 1 Ocak 1982'den önceki kayıtları atlıyoruz. Filtreyi kendi veri gereksinimlerinize göre ayarlayın.

```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```

### Adım 6: Yeni Bir Özellik Oluştur (C# GeoJSON Dosyası Oluştur)
`Feature`, geometri ve öznitelik verilerini içeren tek bir uzamsal öğeyi temsil eder.  
Burada GeoJSON katmanı için yeni bir `Feature` oluşturuyor, geometriyi ve öznitelik değerlerini kopyalıyor ve çıktıya ekliyoruz. Bu, *c# generate geojson file* işleminin çekirdeğidir.

```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```

Tebrikler! **shapefile'ı geojson'a başarıyla dönüştürdünüz** ve bu süreçte **katmanlar arasında öznitelikleri kopyalamayı** öğrendiniz.

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden Oluşur | Çözüm |
|-------|--------------|-------|
| Çıktı dosyası boş | `CopyAttributes` çıktı katmanı kapatıldıktan sonra çağrıldı | `outputLayer` için `using` bloğunun tüm özellikler eklenene kadar açık kalmasını sağlayın. |
| Tarih filtresi tüm kayıtları kaldırıyor | Yanlış alan adı veya beklenmeyen tarih formatı | Öznitelik adını (`dob`) doğrulayın ve tarihler string olarak depolanıyorsa `GetValue<string>` kullanın. |
| Lisans istisnası | Üretimde geçerli bir Aspose.GIS lisansı olmadan çalıştırmak | Aspose belgelerinde açıklandığı gibi geçici veya tam lisans uygulayın. |

## Sıkça Sorulan Sorular
**S: Daha fazla belgeyi nerede bulabilirim?**  
C: Derinlemesine bilgi için [Aspose.GIS belgelerini](https://reference.aspose.com/gis/net/) ziyaret edin.

**S: Geçici bir lisans nasıl alabilirim?**  
C: Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

**S: Destek nereden alınır?**  
C: Topluluk desteği ve tartışmalar için [Aspose.GIS forumuna](https://forum.aspose.com/c/gis/33) katılın.

**S: Ücretsiz bir deneme mevcut mu?**  
C: Evet, ücretsiz denemeyi [buradan](https://releases.aspose.com/) bulabilirsiniz.

**S: Aspose.GIS for .NET'i nereden satın alabilirim?**  
C: Ürünü [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

## Sonuç
Bu öğreticide Aspose.GIS for .NET kullanarak **shapefile'ı geojson'a** dönüştürme sürecini, **katmanlar arasında öznitelikleri kopyalama** yöntemini ve temiz bir *c# generate geojson file* yaklaşımını gösterdik. Farklı filtreler, daha büyük veri setleri veya ek geometri dönüşümleri deneyerek kütüphanenin yeteneklerini tam anlamıyla kullanabilirsiniz.

---

**Son Güncelleme:** 2026-07-05  
**Test Edilen Versiyon:** Aspose.GIS for .NET (en son kararlı sürüm)  
**Yazar:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## İlgili Öğreticiler

- [Aspose.GIS for .NET ile GeoJSON'ı File GDB'ye Dönüştürme](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Aspose.GIS for .NET ile Akıştan GeoJSON Okuma](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Aspose.GIS ile GeoJSON'ı TopoJSON'a Dönüştürme](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
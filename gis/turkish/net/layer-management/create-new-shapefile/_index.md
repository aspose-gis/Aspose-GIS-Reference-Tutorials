---
date: 2026-06-30
description: Aspose.GIS for .NET kullanarak shapefile oluşturmayı öğrenin. Bu adım
  adım rehber, bir vektör katmanı tanımlamayı, tarih özelliği eklemeyi ve mekansal
  verileri verimli bir şekilde yönetmeyi gösterir.
keywords:
- how to create shapefile
- temporal gis shapefile
- Aspose.GIS vector layer
- GIS data automation
linktitle: Yeni Shapefile Oluştur
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create shapefile using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to define a vector layer, add a date attribute, and manage
    spatial data efficiently.
  headline: How to Create Shapefile with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS primarily supports .NET, but there are versions available for
      Java as well.
    question: Can I use Aspose.GIS with other programming languages?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I find support for Aspose.GIS?
  - answer: Get your temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license?
  - answer: You can buy the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile Shapefile Nasıl Oluşturulur
url: /tr/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Yeni Shapefile Oluştur

## Giriş
Eğer .NET ile coğrafi bilgi sistemleri (GIS) geliştirmeye dalıyorsanız, Aspose.GIS **shapefile nasıl oluşturulur** programatik olarak gerçekleştirmek için başvurmanız gereken çözümdür. Bu kütüphane, vektör katmanları, öznitelik şemaları ve dosya formatı uyumluluğu üzerinde tam kontrol sağlar; böylece veri boru hatlarını otomatikleştirebilir veya dakikalar içinde test veri setleri üretebilirsiniz.

## Hızlı Yanıtlar
- **Bu öğretici ne öğretir?** Yeni bir shapefile oluşturma, bir vektör katmanı tanımlama ve öznitelikler ekleme (tarih alanı dahil).  
- **Hangi kütüphane gereklidir?** Aspose.GIS for .NET.  
- **Lisans gerekir mi?** Öğrenme için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Hangi IDE'yi kullanmalıyım?** Visual Studio (herhangi bir son sürüm).  
- **Uygulama ne kadar sürer?** Temel örnek için yaklaşık 10‑15 dakika.

## Aspose.GIS for .NET ile shapefile nasıl oluşturulur?
Aspose.GIS kütüphanesini yükleyin, çıktı klasörünü ayarlayın, bir `VectorLayer` oluşturun, öznitelikleri tanımlayın ve özellikler ekleyin—bu tüm iş akışı C#'ta 30 satırın altında yazılabilir. Kütüphane geometri oluşturmayı, öznitelik tiplerini ve dosya yazımını otomatik olarak yönetir, böylece düşük seviyeli Shapefile spesifikasyonlarıyla uğraşmanız gerekmez.

## Önkoşullar
Öğreticiye başlamadan önce, aşağıdaki önkoşulların yerine getirildiğinden emin olun:
- C# programlama diline temel bir anlayış.  
- Makinenizde Visual Studio yüklü.  
- Aspose.GIS for .NET kütüphanesi. Bunu [buradan](https://releases.aspose.com/gis/net/) indirebilirsiniz.

## Ad Alanlarını İçe Aktarın
Aspose.GIS işlevselliğinden yararlanmak için gerekli ad alanlarını içe aktararak başlayın:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım 1: Projenizi Kurun
Visual Studio'da yeni bir C# projesi oluşturarak ve Aspose.GIS kütüphanesini ekleyerek başlayın.

## Adım 2: Belge Dizini Tanımlayın
```csharp
string dataDir = "Your Document Directory";
```
*Your Document Directory* ifadesini, yeni shapefile'inizi kaydetmek istediğiniz gerçek yol ile değiştirin.

## Adım 3: VectorLayer Oluşturun
`VectorLayer` sınıfı, geometri ve öznitelik verilerini depolayan tek bir shapefile katmanını temsil eder.  
Bu adımda bir vektör katmanı tanımlıyor ve üç öznitelik ilan ediyoruz: bir metin alanı (`name`), bir tam sayı alanı (`age`) ve bir tarih‑zaman alanı (`dob`). Tarih özniteliğini eklemek, **zaman serisi GIS shapefile** analizleri için kritik öneme sahiptir.

```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```

## Adım 4: Özellikler Ekleyin
### Durum 1: Değerleri Tek Tek Ayarlar
`SetValues` yöntemi, öznitelik değerlerini tanımlandıkları sırayla bir özelliğe atar.

```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
Burada iki nokta oluşturuyor, her özniteliği ayrı ayrı ayarlıyor ve özellikleri katmana ekliyoruz.

### Durum 2: Tüm Öznitelikler İçin Yeni Değerler Ayarlar
Alternatif olarak, `SetValues` metodunu bir nesne dizisiyle kullanarak tüm öznitelik değerlerini bir kerede sağlayabilirsiniz.

```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
Bu yaklaşımda, bir nesne dizisi kullanarak tüm öznitelik değerlerini tek bir çağrıyla doldururuz—çok sayıda öznitelik olduğunda kullanışlıdır.

## Neden Önemli?
Programatik olarak shapefile oluşturmak, veri boru hatlarını otomatikleştirmenize, test veri setleri üretmenize veya GIS çıktısını doğrudan web hizmetlerine gömmenize olanak tanır. Aspose.GIS **30+ vektör ve raster formatını** destekler ve tüm dosyayı belleğe yüklemeden çok sayfalı shapefile'ler yazabilir; bu da hem hız hem de ölçeklenebilirlik sağlar.

## Yaygın Tuzaklar ve İpuçları
- **Yol ayırıcıları:** Dize birleştirme yerine çapraz platform uyumluluğu için `Path.Combine` kullanın.  
- **Öznitelik sırası:** `SetValues` içindeki değerlerin sırası, eklediğiniz özniteliklerin sırası ile eşleşmelidir.  
- **Tarih işleme:** GIS verileriniz zaman dilimleri arasında paylaşılacaksa her zaman `DateTimeKind.Utc` kullanın.

## Sonuç
Tebrikler! Aspose.GIS for .NET kullanarak yeni bir shapefile'i başarıyla oluşturdunuz. Bu öğretici, projenizi kurma, bir vektör katmanı tanımlama ve özellik ekleme (tarih özniteliği dahil) temellerini kapsadı. Daha ileri keşiflerinizde, gelişmiş özellikler ve işlevsellikler için [belgelere](https://reference.aspose.com/gis/net/) başvurun.

## Sıkça Sorulan Sorular
**S: Aspose.GIS'i diğer programlama dilleriyle kullanabilir miyim?**  
**C: Aspose.GIS öncelikle .NET'i destekler, ancak Java için de sürümler mevcuttur.**

**S: Ücretsiz deneme mevcut mu?**  
**C: Evet, ücretsiz denemeye [buradan](https://releases.aspose.com/) ulaşabilirsiniz.**

**S: Aspose.GIS için desteği nereden bulabilirim?**  
**C: Topluluk desteği ve tartışmalar için [Aspose.GIS forumunu](https://forum.aspose.com/c/gis/33) ziyaret edin.**

**S: Geçici bir lisans nasıl alabilirim?**  
**C: Geçici lisansınızı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.**

**S: Aspose.GIS for .NET'i nereden satın alabilirim?**  
**C: Kütüphaneyi [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.**

---

**Son Güncelleme:** 2026-06-30  
**Test Edilen Versiyon:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Katman Özniteliklerini Al – Aspose.GIS for .NET ile Katman Öznitelik Bilgilerini Getir](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Vektör Katmanı Oluştur ve Katman Uzamsal Referans Sistemini Ayarla](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [File GDB'de Vektör Katmanı Oluştur – Aspose.GIS .NET Öğreticisi](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
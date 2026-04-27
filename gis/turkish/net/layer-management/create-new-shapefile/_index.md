---
date: 2026-01-13
description: Aspose.GIS for .NET ile yeni bir shapefile oluşturmayı öğrenin. Bu adım
  adım kılavuz, vektör katmanını nasıl tanımlayacağınızı, tarih özniteliği ekleyeceğinizi
  ve mekânsal verileri nasıl yöneteceğinizi gösterir.
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
title: Yeni Shapefile Oluştur
url: /tr/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Yeni Shapefile Oluşturma

## Giriş
Aspose.GIS, .NET ile coğrafi bilgi sistemleri (GIS) geliştirme için başvurabileceğiniz çözümdür. Bu güçlü kütüphane, geliştiricilerin mekanik verilerle sorunsuz bir şekilde çalışmasına olanak tanır ve bu eğitim, Aspose.GIS for .NET kullanarak adım adım yeni bir shapefile oluşturmayı gösterecektir. Vektör katmanlarını tanımlamanın ve geçmişe ait özellikleri eklemenin sağlam GIS projeleri için neden önemli adımlar olduğunu göreceksiniz.

## Hızlı Cevaplar
- **Bu eğitim neyi öğretmiyor?** Yeni bir shapefile oluşturmayı, vektör katmanı tanımlamayı ve öznitelikler (geçmişe ait olanlar dahil) eklemeyi öğretir.

- **Gerekli kütüphane?** Aspose.GIS for .NET.

- **Lisans gerekli mi?** Öğrenmek için ücretsiz deneme sürümü yeterlidir; üretim için ticari lisans gereklidir.

- **Hangi IDE kullanılacak?** Visual Studio (Herhangi bir yeni sürüm).

- **Uygulama ne kadar sürer?** Temel olarak 10-15 dakika sürer.

## Önkoşullar
Eğitime başlamadan önce aşağıdaki koşulları sağladığınızdan emin olun:
- C# programlama diline temel bir sekpeh.

- Bilgisayarınızda Visual Studio kurulu olmalı.

- .NET için Aspose.GIS kütüphaneleri. Bunu [buradan](https://releases.aspose.com/gis/net/) adresinden indirebilirsiniz.

## Ad Alanlarını İçe Aktarma
Aspose.GIS işlevselliğinden yararlanmak için, gerekli ad alanlarını girerek başlayın:

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

## Adım 2: Belge Dizinini Tanımlayın
```csharp
string dataDir = "Your Document Directory";
```
*Your Document Directory* ifadesini yeni shapefile'inizi kaydetmek istediğiniz gerçek yol ile değiştirin.

## Adım 3: Bir Vektör Katmanı Oluşturun
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Bu kod bölümü **bir vektör katmanı tanımlar** ve üç öznitelik bildirir: bir metin alanı (`name`), bir tam sayı alanı (`age`) ve bir tarih‑zaman alanı (`dob`). Tarih özniteliği eklemek, zamansal GIS analizleri için kritik öneme sahiptir.

## Adım 4: Özellikler Ekleyin
### Durum 1: Değerleri Tek Tek Ayarlayın

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

### Durum 2: Tüm Nitelikler İçin Yeni Değerler Ayarlayın
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
Bu yöntemde, bir nesne dizisi kullanarak tüm öznitelik değerlerini tek bir çağrıda dolduruyoruz—çok sayıda özniteliğiniz olduğunda kullanışlıdır.

## Neden Önemli?
Programlanabilir şekilde shapefile dosyaları oluşturmanıza, veri boru sınırlarını otomatikleştirmenize, gövde veri kümeleri oluşturmanıza veya GIS çıktısını doğrudan web servislerine entegre etmenize olanak tanır. Aspose.GIS ile **shapefile oluşturma**, özel çizgiler, geometrik özellikler, öznitelik şemaları ve dosya formatı uyumluluğu üzerinde tam kontrole sahipsiniz.

## Sık Karşılaşılan Hatalar ve İpuçları
- **Yol ayrıştırıcıları:** Çapraz platform uyumluluğu için birleştirme yerine `Path.Combine` kullanın.

- **Özniteliklerin sırası:** `SetValues` içindeki değerlerin sırası, eklediğiniz özniteliklerin sırasıyla aynı olmalıdır.

- **Tarih obsehme:** GIS verilerinizin zaman zaman zaman arındın paşılağılakasa her zaman `DateTimeKind.Utc` kullanın.

## Sonuç
Tebrikler! Aspose.GIS for .NET kullanarak yeni bir shapefile dosyasını başarıyla oluşturabilirsiniz. Bu öğretici proje, vektör katmanının tanımına ve özelliklerin (tarihsel özellikler dahil) eklenmesine dayanmaktadır. Daha fazlasını keşfetmek için, gelişmiş özellikler ve işlevsellik için [belgelere](https://reference.aspose.com/gis/net/) bakın.

## Sıkça Sorulan Sorular
### S: Aspose.GIS'i diğer programlama dilleriyle kullanabilir miyim?

Aspose.GIS öncelikle .NET'i destekler, ancak Java sürümleri de mevcuttur.

### S: Ücretsiz deneme sürümü mevcut mu?

Evet, [burada](https://releases.aspose.com/) adresinden ücretsiz deneme sürümünü edinebilirsiniz.

### S: Aspose.GIS için destek nerede bulabilirim?

Destek ve tartışmalar için [Aspose.GIS forumunu](https://forum.aspose.com/c/gis/33) ziyaret edin.

### S: Geçici lisansı nasıl edinebilirim?

Geçici lisansınızı [buradan](https://purchase.aspose.com/temporary-license/) adresinden edinebilirsiniz.

### S: Aspose.GIS for .NET'i nereden satın alabilirim?
Kütüphaneden [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

---

**Son Güncelleme:** 13.01.2026
**Test Edilen Sürüm:** Aspose.GIS 24.11 for .NET
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
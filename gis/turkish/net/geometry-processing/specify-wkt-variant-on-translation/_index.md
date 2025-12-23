---
date: 2025-12-23
description: Aspose.GIS for .NET kullanarak, geometriyi çeşitli seçeneklerle WKT'ye
  dönüştürmeyi, sayısal formatı ayarlamayı ve ondalık hassasiyeti düzenlemeyi öğrenin.
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: Aspose.GIS kullanarak Geometriyi WKT Varyant Seçeneklerine Dönüştür
url: /tr/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS ile Geometriyi WKT Varyant Seçeneklerine Dönüştürme

## Giriş
Modern .NET uygulamalarında, **geometriyi WKT'ye dönüştürmek**, mekânsal verileri diğer sistemlerle değiş tokuş etmek veya metin tabanlı bir formatta depolamak istediğinizde yaygın bir adımdır. Aspose.GIS for .NET, bu dönüşümü zahmetsizce gerçekleştirmenizi sağlarken WKT varyantı, sayısal format ve ondalık hassasiyet üzerinde tam kontrol sunar. Bu öğreticide, geometriyi WKT'ye nasıl dönüştüreceğinizi, doğru varyantı nasıl seçeceğinizi ve çıktıyı projenizin tam gereksinimlerine göre nasıl ince ayar yapacağınızı öğreneceksiniz.

## Hızlı Yanıtlar
- **“Geometriyi WKT'ye dönüştürmek” ne anlama geliyor?** Geometrik nesneleri (nokta, çizgi, çokgen) Well‑Known Text temsiline dönüştürür.  
- **Hangi WKT varyantları destekleniyor?** `Iso`, `SimpleFeatureAccessOutdated` ve `ExtendedPostGis`.  
- **Ondalık hassasiyeti nasıl kontrol edebilirim?** `General`, `RoundTrip` veya `Flat` gibi `NumericFormat` seçeneklerini kullanın.  
- **Üretim için lisansa ihtiyacım var mı?** Evet, deneme dışı kullanım için ticari bir lisans gereklidir.  
- **Hangi .NET sürümleri uyumlu?** .NET Framework 4.0+ ve .NET 5/6/7.

## “Geometriyi WKT'ye dönüştürmek” nedir?
Geometriyi WKT'ye dönüştürmek, mekânsal nesneleri tanımlayan insan tarafından okunabilir bir dize üretir. Bu format, GIS araçları, veritabanları ve web servisleri tarafından yaygın olarak kabul edilir ve veri değiş tokuşu için idealdir.

## Bu dönüşüm için Aspose.GIS neden kullanılmalı?
- **Hassasiyet kontrolü** – Kaç ondalık basamağın çıktıya dahil edileceğini seçin.  
- **Varyant esnekliği** – Aşağı akış sisteminizin gerektirdiği tam WKT lehçesine uyum sağlayın.  
- **Harici bağımlılık yok** – Saf .NET kütüphanesi, yerel ikili dosyalar içermez.

## Önkoşullar
Başlamadan önce şunların kurulu olduğundan emin olun:

1. **Aspose.GIS for .NET** – [indirme sayfasından](https://releases.aspose.com/gis/net/) indirin ve kurun.  
2. **Geliştirme Ortamı** – .NET SDK yüklü herhangi bir Visual Studio veya VS Code sürümü.  
3. **Temel C# bilgisi** – Sınıflar, nesneler ve .NET çerçevesi hakkında temel bilgi.

## Namespace'leri İçe Aktarın
İlk olarak, gerekli namespace'leri kapsam içine alın:

```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```

## Adım 1: Bir Point Nesnesi Oluşturun
Daha sonra **geometriyi WKT'ye dönüştüreceğiniz** bir `Point` oluşturun. Nokta, enlem, boylam ve isteğe bağlı ölçüm (M) değerini içerir:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Adım 2: Uzamsal Referans Sistemi (SRS) Ayarlayın
WKT çıktısının hangi koordinat sistemine referans vereceğini bilmesi için bir uzamsal referans sistemi atayın. Burada yaygın WGS84 sistemi kullanılıyor:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Adım 3: WKT Varyantını Belirleyin
**Geometriyi WKT'ye dönüştürürken** uygun WKT varyantını seçin. Her varyant çıktıyı biraz farklı biçimlendirir:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Adım 4: Sayısal Formatı Kontrol Edin (Sayısal Formatı Ayarlayın ve Ondalık Hassasiyeti Düzenleyin)
Koordinatların sayısal temsili üzerinde ince ayar yapın. `NumericFormat` sınıfı, **sayısal formatı ayarlamanıza** ve **ondalık hassasiyeti** ihtiyaçlarınıza göre düzenlemenize olanak tanır:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## Yaygın Sorunlar ve İpuçları
- **M değeri eksik** – Ölçüm (M) gerekmiyorsa `M` özelliğini atlayın; ISO varyantı otomatik olarak kaldırır.  
- **Beklenmeyen hassasiyet** – Doğru `NumericFormat` kullandığınızdan emin olun; `General` tam double hassasiyetini korurken, `Flat` belirtilen ondalık basamak sayısına yuvarlar.  
- **SRID gösterilmiyor** – Yalnızca `ExtendedPostGis` varyantı çıktının başına `SRID=` ekler. Hedef sisteminiz bir SRID bekliyorsa bu varyantı seçin.

## Sonuç
Bu adımları izleyerek artık **geometriyi WKT'ye dönüştürmeyi**, doğru varyantı seçmeyi ve sayısal çıktıyı hassas bir şekilde kontrol etmeyi biliyorsunuz. Bu, Aspose.GIS'i herhangi bir GIS iş akışı, veritabanı veya WKT tüketen web servisiyle entegre etmenize esneklik sağlar.

## SSS
### Aspose.GIS tüm .NET sürümleriyle uyumlu mu?
Evet, Aspose.GIS .NET Framework 4.0 ve üzeri sürümlerini destekler.  

### Aspose.GIS'i ticari projelerde kullanabilir miyim?
Evet, Aspose.GIS hem kişisel hem de ticari projelerde kullanılabilir.  

### Aspose.GIS diğer mekânsal veri formatlarını destekliyor mu?
Evet, Aspose.GIS ESRI Shapefile, GeoJSON ve KML dahil olmak üzere geniş bir mekânsal veri formatı yelpazesini destekler.  

### Aspose.GIS için ücretsiz deneme sürümü var mı?
Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.  

### Aspose.GIS için yardım veya destek nasıl alınır?
Sorularınızı Aspose.GIS topluluğuna [forum](https://forum.aspose.com/c/gis/33) üzerinden göndererek destek alabilirsiniz.

## Sıkça Sorulan Sorular
**S: Bir Geometry koleksiyonunu tek bir WKT dizesine nasıl dışa aktarırım?**  
C: Koleksiyondaki her geometry üzerinde döngü kurarak `AsText` sonuçlarını birleştirin; isteğe bağlı olarak virgül veya yeni satır ile ayırabilirsiniz.

**S: SRID'yi koordinatları değiştirmeden değiştirebilir miyim?**  
C: Evet, `SpatialReferenceSystem` özelliğini istediğiniz SRID'ye ayarlayın; koordinat değerleri aynı kalır.

**S: Desteklenmeyen bir WKT varyantı kullanırsam ne olur?**  
C: Aspose.GIS bir `ArgumentException` fırlatır. Her zaman varyantı `WktVariant` enum değerleriyle doğrulayın.

---

**Son Güncelleme:** 2025-12-23  
**Test Edilen Versiyon:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
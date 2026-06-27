---
date: 2026-04-09
description: Aspose.GIS for .NET ile .NET uygulamalarınızda C# noktasını oluştururken
  mekansal referansı nasıl atayacağınızı ve ondalık hassasiyeti nasıl ayarlayacağınızı
  öğrenin.
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: Çeviride WKT Varyantını Belirle
second_title: Aspose.GIS .NET API
title: Aspose.GIS Kullanarak Uzamsal Referans Atama ve WKT Varyantını Ayarlama
url: /tr/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Uzamsal Referans Ata ve WKT Varyantını Aspose.GIS ile Ayarla

## Giriş
Bu öğreticide, bir geometriye **uzamsal referans atamayı** ve Aspose.GIS for .NET ile kesin WKT çıktı formatını kontrol etmeyi öğreneceksiniz. Haritalama, analiz veya veri alışverişi için **C# nokta oluşturma** nesnelerine ihtiyacınız olsun, doğru WKT varyantını ve sayısal hassasiyeti seçebilmek, uzamsal verilerinizi birlikte çalışabilir ve okunması kolay hâle getirir. Süreci adım adım inceleyelim.

## Hızlı Yanıtlar
- **“uzamsal referans atama” ne anlama gelir?** Bir geometriyi WGS‑84 gibi belirli bir koordinat sistemine bağlar.  
- **Hangi WKT varyantları desteklenir?** Iso, SimpleFeatureAccessOutdated ve ExtendedPostGis.  
- **Ondalık hassasiyeti nasıl kontrol edebilirim?** `General`, `RoundTrip` veya `Flat` gibi `NumericFormat` seçeneklerini kullanın.  
- **Lisans gerekir mi?** Ücretsiz deneme mevcuttur; üretim için ticari lisans gereklidir.  
- **Hangi .NET sürümleri uyumludur?** .NET Framework 4.0+ ve .NET Core/5/6+.

## “Uzamsal referans atama” nedir?
Bir uzamsal referans (veya uzamsal referans sistemi, SRS) atamak, GIS yazılımına bir geometrinin koordinat değerlerini nasıl yorumlayacağını söyler. SRS olmadan, bir noktanın enlem‑boylam sayıları gerçek dünyada bir anlam taşımaz.

## Neden WKT varyantı ve sayısal formatı kontrol etmeliyiz?
Farklı GIS araçları biraz farklı WKT sözdizimleri bekler. Uygun varyantı seçmek sorunsuz veri alışverişi sağlar, sayısal hassasiyeti ayarlamak ise yuvarlama hatalarını ve günlükleri ve dosyaları gereksiz yere dolduran çok uzun sayıları önler.

## Önkoşullar
1. Aspose.GIS for .NET – [download page](https://releases.aspose.com/gis/net/) adresinden indirin.  
2. .NET geliştirme ortamı (Visual Studio, VS Code veya Rider).  
3. C# ve .NET framework'üne temel aşinalık.

## Ad Alanlarını İçe Aktarın
Herhangi bir Aspose.GIS sınıfını kullanmadan önce gerekli ad alanlarını içe aktarın:

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

## Adım 1: Bir Nokta Nesnesi Oluşturun (create point C#)
Latitude, longitude ve isteğe bağlı ölçüm (M) değeri ile bir `Point` oluşturmakla başlıyoruz:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Adım 2: Uzamsal Referans Sistemi (SRS) Ata
Şimdi noktaya **uzamsal referans atıyoruz**. Burada yaygın olarak desteklenen WGS‑84 sistemini (SRID 4326) kullanıyoruz:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Adım 3: İstenen WKT Varyantını Belirleyin
Aşağı akış uygulamanıza uyan WKT varyantını seçin:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Adım 4: WKT Çıktısı İçin Ondalık Hassasiyeti Ayarlayın
`NumericFormat` kullanarak son dizede kaç basamak görüneceğini kontrol edin:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Yaygın Tuzaklar ve İpuçları
- **Tuzak:** `AsText` çağırmadan önce SRS'i ayarlamayı unutmak, SRID bilgisinin eksik olmasına neden olabilir.  
- **İpucu:** Koordinatların kayıpsız dönüşümü gerektiğinde `NumericFormat.RoundTrip` kullanın.  
- **İpucu:** `Iso` varyantı en taşınabilir olandır; yalnızca SRID gömülü gerektiğinde `ExtendedPostGis` seçin.

## Sonuç
Artık Aspose.GIS ile **nokta C#** nesneleri **oluştururken** **uzamsal referans atamayı**, uygun WKT varyantını seçmeyi ve **ondalık hassasiyeti ayarlamayı** biliyorsunuz. Bu kontroller, basit görselleştirmeden yüksek hassasiyetli uzamsal analizlere kadar herhangi bir GIS iş akışının tam gereksinimlerini karşılamak için size esneklik sağlar.

## Sıkça Sorulan Sorular

**S:** Aspose.GIS tüm .NET sürümleriyle uyumlu mu?  
**C:** Evet, Aspose.GIS .NET Framework 4.0 ve üzeri ile, ayrıca .NET Core/5/6 ile uyumludur.

**S:** Aspose.GIS'i ticari projelerde kullanabilir miyim?  
**C:** Kesinlikle. Üretim kullanımı için ticari lisans gereklidir, ancak değerlendirme için ücretsiz bir deneme sürümü mevcuttur.

**S:** Aspose.GIS diğer uzamsal veri formatlarını destekliyor mu?  
**C:** Evet, ESRI Shapefile, GeoJSON, KML ve daha birçok formatla çalışır.

**S:** Ücretsiz deneme sürümünü nereden indirebilirim?  
**C:** Aspose.GIS'in ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.

**S:** Sorun yaşarsam nasıl yardım alabilirim?  
**C:** Sorularınızı Aspose.GIS topluluğu [forumunda](https://forum.aspose.com/c/gis/33) paylaşabilirsiniz; Aspose çalışanları ve topluluk üyeleri yardımcı olur.

---

**Son Güncelleme:** 2026-04-09  
**Test Edilen:** Aspose.GIS for .NET (latest release)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
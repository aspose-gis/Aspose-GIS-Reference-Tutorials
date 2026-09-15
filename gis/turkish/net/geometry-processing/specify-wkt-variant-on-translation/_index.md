---
date: 2026-09-15
description: C# ve Aspose.GIS for .NET ile point geometry oluştururken coordinate
  system'i atamayı, WKT variant'ını ayarlamayı ve decimal precision'ı kontrol etmeyi
  öğrenin.
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: Çeviride WKT Variant'ı Belirtin
og_description: C# ve Aspose.GIS for .NET ile point geometry oluştururken coordinate
  system'i atamayı, WKT variant'ını ayarlamayı ve decimal precision'ı kontrol etmeyi
  öğrenin.
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: Coordinate system'i atayın, WKT variant'ını ayarlayın Aspose.GIS kullanarak
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: Coordinate system'i atayın, WKT variant'ını ayarlayın Aspose.GIS kullanarak
url: /tr/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Koordinat sistemini atayın, Aspose.GIS kullanarak WKT varyantını ayarlayın

## Giriş
Bu öğreticide **koordinat sistemini atama**, doğru WKT varyantını seçme ve C# ile Aspose.GIS for .NET kullanarak **nokta geometrisi oluşturma** sırasında ondalık hassasiyeti kontrol etmeyi öğreneceksiniz. Haritalama servisi oluşturuyor, mekansal analiz yapıyor ya da GIS platformları arasında veri değiş tokuşu yapıyor olun, bu ayarlar çıktınızın hem birlikte çalışabilir hem de okunması kolay olmasını garanti eder. Süreci adım adım inceleyelim.

## Hızlı cevaplar
- **“Koordinat sistemini atama” ne anlama geliyor?** Bir geometriyi WGS‑84 gibi belirli bir koordinat referans sistemine bağlar.  
- **Hangi WKT varyantları destekleniyor?** Iso, SimpleFeatureAccessOutdated, ve ExtendedPostGis.  
- **Ondalık hassasiyeti nasıl kontrol edebilirim?** `NumericFormat` enum'ını kullanın (`General`, `RoundTrip`, `Flat`).  
- **Aspose.GIS için lisans gereklimi?** Ücretsiz deneme sürümü mevcuttur; üretim kullanımı için ticari lisans gereklidir.  
- **Hangi .NET sürümleri uyumludur?** .NET Framework 4.0+ ve .NET Core/5/6+.

## “Koordinat sistemini atama” nedir?
Bir mekansal referans (veya mekansal referans sistemi, SRS) atamak, GIS yazılımına bir geometrinin koordinat değerlerini nasıl yorumlayacağını söyler; sayıları WGS‑84 gibi gerçek dünya koordinat sistemine bağlar. SRS olmadan, bir noktanın enlem‑boylam sayıları gerçek dünya anlamı taşımaz.

## Neden WKT varyantını ve sayısal formatı kontrol etmeliyiz?
30'dan fazla GIS aracı belirli WKT sözdizimlerini bekler, bu yüzden doğru varyantı seçmek içe aktarma hatalarını önler. Sayısal formatı ayarlamak yuvarlama gürültüsünü azaltır ve çıktıyı özlü tutar; bu, günlüklerin veya dosyaların programlı olarak ayrıştırıldığı durumlarda özellikle önemlidir.

## Önkoşullar
1. Aspose.GIS for .NET – [indirme sayfasından](https://releases.aspose.com/gis/net/) indirin.  
2. .NET geliştirme ortamı (Visual Studio, VS Code veya Rider).  
3. C# ve .NET framework'üne temel aşinalık.

## Ad alanlarını içe aktar
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

## Bir noktaya koordinat sistemi nasıl atanır?
`Point` örneğini yükleyin, ardından `SpatialReference` sınıfını kullanarak bir mekansal referans sistemi (SRS) ekleyin. Bu iki adımlı desen, geometrinin dışa aktarıldığında koordinat sistemi meta verilerini taşımasını sağlar ve sonraki araçların koordinatları doğru yorumlamasına imkan verir. `Point` sınıfı, X (boylam) ve Y (enlem) koordinatlarıyla tanımlanan tek bir konumu temsil eder.

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Adım 2: mekansal referans sistemini (SRS) ata
Şimdi noktaya **mekansal referans** atıyoruz. `SpatialReference`, bir SRID ile tanımlanan koordinat referans sistemini temsil eder. Burada yaygın olarak desteklenen WGS‑84 sistemini (SRID 4326) kullanıyoruz:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Adım 3: istenen WKT varyantını belirtin
Aşağı akış uygulamanıza uyan WKT varyantını seçin:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## WKT çıktısı için ondalık hassasiyeti nasıl ayarlarsınız?
`NumericFormat` enum'ını kullanarak son dizede kaç basamak görüneceğini kontrol edin; bu enum `General`, `RoundTrip` veya `Flat` gibi biçimlendirme kurallarını tanımlar. `RoundTrip` seçimi, dönüş senaryoları için tam koordinat doğruluğunu korurken, `General` çoğu görselleştirme görevi için uygun özlü bir temsil sunar. `NumericFormat` enum'u, koordinat sayıların WKT çıktısında nasıl biçimlendirileceğini kontrol eder.

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Ortak tuzaklar ve ipuçları
- **Tuzak:** `AsText` çağırmadan önce SRS'i ayarlamayı unutmak, SRID bilgisinin eksik olmasına neden olabilir.  
- **İpucu:** Koordinatların kayıpsız dönüşümüne ihtiyaç duyduğunuzda `NumericFormat.RoundTrip` kullanın.  
- **İpucu:** `Iso` varyantı en taşınabilir olandır; yalnızca SRID gömülü gerektiğinde `ExtendedPostGis` seçin.

## Sonuç
Artık **koordinat sistemini atama**, uygun WKT varyantını seçme ve Aspose.GIS ile **nokta geometrisi oluşturma** sırasında **ondalık hassasiyeti ayarlama** konusunda bilgi sahibisiniz. Bu kontroller, basit görselleştirmeden yüksek hassasiyetli mekansal analizlere kadar herhangi bir GIS iş akışının tam gereksinimlerini karşılamak için size esneklik sağlar.

## Sıkça sorulan sorular

**S:** Aspose.GIS tüm .NET sürümleriyle uyumlu mu?  
**C:** Evet, Aspose.GIS .NET Framework 4.0 ve üzeri ile, ayrıca .NET Core/5/6 ile uyumludur.

**S:** Aspose.GIS'i ticari projelerde kullanabilir miyim?  
**C:** Kesinlikle. Üretim kullanımı için ticari lisans gereklidir, ancak değerlendirme için ücretsiz bir deneme sürümü mevcuttur.

**S:** Aspose.GIS diğer mekansal veri formatlarını destekliyor mu?  
**C:** Evet, ESRI Shapefile, GeoJSON, KML, CSV ve daha fazlası dahil 30'dan fazla formatla çalışır.

**S:** Ücretsiz deneme sürümünü nereden indirebilirim?  
**C:** Aspose.GIS'in ücretsiz deneme sürümünü [Aspose.GIS ücretsiz deneme indirme sayfasından](https://releases.aspose.com/) indirebilirsiniz.

**S:** Sorun yaşarsam nasıl yardım alabilirim?  
**C:** Sorularınızı Aspose.GIS topluluğu [forumunda](https://forum.aspose.com/c/gis/33) paylaşabilirsiniz; Aspose çalışanları ve topluluk üyeleri yardımcı olacaktır.

---

**Son Güncelleme:** 2026-09-15  
**Test Edilen:** Aspose.GIS for .NET (latest release)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Vektör Katmanı Oluşturma ve Mekansal Referans Sistemini Ayarlama](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Aspose.GIS for .NET ile Geometriyi WKT'ye Çevirme](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [Aspose.GIS ile Geometrileri Yazarken Hassasiyeti Sınırlama](/gis/net/geometry-processing/limit-precision-writing-geometries/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
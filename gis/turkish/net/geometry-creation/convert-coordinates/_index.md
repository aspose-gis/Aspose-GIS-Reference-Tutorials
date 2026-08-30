---
date: 2026-08-18
description: Aspose.GIS for .NET kullanarak decimal degrees'i dms'ye dönüştürün. Bu
  adım adım C# rehberi, latitude/longitude, decimal degrees'i dms'ye ve daha fazlasına
  nasıl dönüştürüleceğini gösterir.
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: Koordinatları Dönüştür
og_description: Aspose.GIS for .NET ile decimal degrees'tan dms'ye dönüşüm kolaylaştırıldı.
  latitude‑longitude değerlerini dakikalar içinde DMS formatına dönüştürmeyi öğrenin.
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: Aspose.GIS for .NET ile decimal degrees'i dms'ye dönüştürün
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  headline: How to convert decimal degrees to dms with Aspose.GIS for .NET
  type: TechArticle
- description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  name: How to convert decimal degrees to dms with Aspose.GIS for .NET
  steps:
  - name: start the conversion process
    text: We print a friendly message so you know the demo has begun.
  - name: convert to decimal degrees
    text: Even though the final goal is DMS, we start by showing the original decimal
      representation. This also demonstrates the **decimal degrees to dms** path you’ll
      later follow.
  - name: convert to degree decimal minutes
    text: This format (`DD°MM.m'`) is a common intermediate step when you need to
      **convert lat long degree minutes**.
  - name: convert to degree minutes seconds (dms)
    text: Here’s the core of our tutorial—**convert coordinates to dms**.
  - name: convert to GeoRef
    text: For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing
      workflows.
  type: HowTo
- questions:
  - answer: Aspose.GIS primarily targets .NET developers, but a Java version is also
      available.
    question: Is Aspose.GIS compatible with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.GIS before purchasing?
  - answer: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  - answer: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert coordinates
- Aspose.GIS
- .NET GIS processing
title: Aspose.GIS for .NET ile decimal degrees'i dms'ye nasıl dönüştürülür
url: /tr/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS ile ondalık dereceleri dms'ye dönüştürme

## Giriş
Bu öğreticide, .NET için güçlü Aspose.GIS kütüphanesini kullanarak **ondalık dereceleri dms'ye nasıl dönüştüreceğinizi** öğreneceksiniz. **c# convert lat long** yapmanız gerekse, raporlar için insan tarafından okunabilir konum dizgileri oluşturmanız ya da sadece farklı koordinat formatlarını keşfetmeniz gerekse, bu kılavuz her adımı net açıklamalar ve çalıştırmaya hazır C# kod parçacıklarıyla size gösterir.

## Hızlı cevaplar
- **“convert coordinates to dms” ne anlama geliyor?** Sayısal enlem/boylam değerlerini geleneksel derece‑dakika‑saniye gösterimine dönüştürür.  
- **Hangi kütüphane dönüşümü gerçekleştirir?** .NET için Aspose.GIS, yerleşik format desteğine sahip `GeoConvert` sınıfını sağlar.  
- **Bunu denemek için lisansa ihtiyacım var mı?** Ücretsiz deneme mevcuttur; üretim kullanımı için ticari lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+ ve .NET 5/6+.  
- **Aynı kodu diğer formatlar için kullanabilir miyim?** Evet—sadece `PointFormats` enum değerini değiştirin (ör. `DecimalDegrees`, `GeoRef`).  

## Koordinat dönüşümü dms nedir?
Koordinatları DMS'ye dönüştürmek, ondalık enlem ve boylam değerlerini `25°30'00"N 45°30'00"E` gibi bir formata yeniden yazar. İşlem, her ondalık dereceyi tam derece, dakika (bir derecenin altmışta biri) ve saniye (bir dakikanın altmışta biri) olarak ayırır, ardından uygun yarımküre göstergesini (N, S, E, W) ekler. Bu insan tarafından okunabilir biçim, birçok eski veri kümesi için ve ondalık gösterime güvenmeden kesin konumları iletmek için gereklidir.

## Koordinat dönüşümü için Aspose.GIS neden kullanılmalı?
Aspose.GIS **50+ giriş ve çıkış formatını** destekler ve tüm veri kümesini belleğe yüklemeden çok sayfalı GIS dosyalarını işleyebilir. API, negatif değerler ve yarımküre göstergeleri gibi uç durumlar için milimetrenin altında doğruluk sağlar ve Windows, Linux ve macOS .NET çalışma zamanlarında tutarlı bir şekilde çalışır.

## Önkoşullar
Başlamadan önce, şunların olduğundan emin olun:

1. **C# temellerine hâkim olmak** – değişkenler, metod çağrıları ve konsol çıktısı hakkında bilgi.  
2. **Aspose.GIS yüklü** – en son paketi [Aspose.GIS web sitesinden](https://releases.aspose.com/gis/net/) indirin. Ayrıca ana Aspose sürüm sitesini [Aspose releases web sitesinde](https://releases.aspose.com/) keşfedebilirsiniz.  

## İsim uzaylarını içe aktar
İlk olarak, GIS işlemleri için gerekli isim uzaylarını içe aktarın:

İsim uzaylarını içe aktarma yer tutucusu değişmeden kalır.

## Adım adım kılavuz

### GeoConvert sınıfı nedir?
`GeoConvert` sınıfı, ondalık dereceler, DMS ve GeoRef gibi koordinat formatları arasında dönüşüm sağlayan statik yöntemler sunar. Ham sayısal değerleri veya `Point` nesnelerini kabul eden aşırı yüklemelere sahiptir ve biçimlendirilmiş dizgeler veya yeni `Point` örnekleri döndürür. Negatif koordinatlar ve yuvarlama gibi uç durumları ele alarak, çıktının standart GIS spesifikasyonlarına uygun olmasını garanti eder ve herhangi bir .NET haritalama uygulamasına entegrasyonu basitleştirir.

### Adım 1: dönüşüm sürecini başlat
Demo'nun başladığını göstermek için dostça bir mesaj yazdırıyoruz.

```csharp
using System;
using Aspose.Gis;
```

### Adım 2: ondalık derecelere dönüştür
Son hedef DMS olsa da, önce orijinal ondalık temsili göstererek başlıyoruz. Bu aynı zamanda daha sonra izleyeceğiniz **decimal degrees to dms** yolunu da gösterir.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Adım 3: derece ondalık dakikalara dönüştür
Bu format (`DD°MM.m'`), **convert lat long degree minutes** gerektiğinde yaygın bir ara adımdır.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Adım 4: derece dakika saniye (dms) formatına dönüştür
İşte öğreticimizin özü—**convert coordinates to dms**.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Adım 5: GeoRef'e dönüştür
Tamamlayıcılık açısından, uzaktan algılama iş akışlarında faydalı olan `GeoRef` formatını da gösteriyoruz.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## Yaygın sorunlar ve çözümler
- **Yanlış yarımküre harfleri** – kuzey/doğu için pozitif, güney/batı için negatif değerler gönderdiğinizden emin olun; API otomatik olarak doğru ek'i ekler.  
- **Beklenmedik boş çıktı** – `Aspose.Gis` derlemesinin doğru referanslandığını ve projenin desteklenen bir .NET sürümünü hedeflediğini doğrulayın.  
- **Lisans bulunamadı** – Lisans dosyanızı uygulama kök dizinine yerleştirin veya programatik olarak `License license = new License(); license.SetLicense("Aspose.GIS.lic");` kodu ile ayarlayın.  

## Sıkça sorulan sorular

**S: Aspose.GIS diğer programlama dilleriyle uyumlu mu?**  
C: Aspose.GIS öncelikle .NET geliştiricilerine yöneliktir, ancak bir Java sürümü de mevcuttur.

**S: Aspose.GIS'i satın almadan deneyebilir miyim?**  
C: Evet, Aspose.GIS'in ücretsiz denemesine [web sitesinden](https://releases.aspose.com/) erişebilirsiniz.

**S: Aspose.GIS için destek nasıl alabilirim?**  
C: Aspose.GIS topluluk forumundan [burada](https://forum.aspose.com/c/gis/33) yardım isteyebilirsiniz.

**S: Aspose.GIS için geçici lisanslar mevcut mu?**  
C: Evet, geçici lisansları [geçici lisans sayfasından](https://purchase.aspose.com/temporary-license/) alabilirsiniz.

**S: Aspose.GIS'i nereden satın alabilirim?**  
C: Aspose.GIS'i [satın alma sayfasından](https://purchase.aspose.com/buy) satın alabilirsiniz.

## Sonuç
Bu adımları izleyerek, .NET için Aspose.GIS kullanarak **ondalık dereceleri dms'ye dönüştürme** ve diğer yaygın GIS formatlarını nasıl yapacağınızı artık biliyorsunuz. Bu yetenek, insan tarafından okunabilir konum dizgelerini haritalama uygulamalarına, raporlara veya herhangi bir mekânsal veri iş akışına sorunsuz bir şekilde entegre etmenizi sağlar. Farklı enlem/boylam değerleriyle denemeler yapmaktan ve `GeoConvert` sınıfının sunduğu diğer formatları keşfetmekten çekinmeyin.

---

**Son Güncelleme:** 2026-08-18  
**Test Edilen Versiyon:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## İlgili Öğreticiler

- [Aspose.GIS for .NET ile Nokta Geometrisi Oluşturma ve Geometri Tipini Alma](/gis/net/geometry-analysis/get-geometry-type/)
- [GeoJSON Dönüştürme – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [Aspose.GIS ile .NET'te Çok Nokta Geometrisi Oluşturma](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
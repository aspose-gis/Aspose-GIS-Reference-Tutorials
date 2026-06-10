---
date: 2026-02-13
description: Aspose.GIS for .NET ile koordinatları DMS'ye nasıl dönüştüreceğinizi
  öğrenin. Bu adım adım C# rehberi, C# kullanarak enlem ve boylamı, ondalık dereceleri
  DMS'ye dönüştürmeyi ve daha fazlasını gösterir.
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile Koordinatları DMS'ye Dönüştürme
url: /tr/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS ile Koordinatları DMS'ye Dönüştürme

## Giriş
Bu öğreticide, .NET için güçlü Aspose.GIS kütüphanesini kullanarak koordinatları DMS (derece, dakika, saniye) biçimine **nasıl dönüştüreceğinizi** öğreneceksiniz. **c# convert lat long** yapmanız, insan tarafından okunabilir konum dizeleri oluşturmanız veya sadece farklı koordinat biçimlerini keşfetmeniz gerekse, bu rehber her adımı net açıklamalar ve çalıştırmaya hazır C# kodu ile size gösterir.

## Hızlı Yanıtlar
- **“convert coordinates to DMS” ne anlama geliyor?** Sayısal enlem/boylam değerlerini geleneksel derece‑dakika‑saniye gösterimine dönüştürür.  
- **Hangi kütüphane dönüşümü gerçekleştirir?** .NET için Aspose.GIS, yerleşik format desteği sunan `GeoConvert` sınıfını sağlar.  
- **Denemek için lisansa ihtiyacım var mı?** Ücretsiz deneme mevcuttur; üretim kullanımı için ticari lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+ ve .NET 5/6+.  
- **Aynı kodu diğer biçimler için kullanabilir miyim?** Evet—sadece `PointFormats` enum değerini değiştirin (ör. `DecimalDegrees`, `GeoRef`).  

## Koordinatları DMS'ye Dönüştürme
Koda geçmeden önce, DMS'nin hâlâ neden değerli olduğunu açıklayalım. Haritacılar, pilotlar ve birçok GIS veri sağlayıcısı, DMS'nin insan dostu olması ve geleneksel haritalarla uyumlu olması nedeniyle ona güvenir. Aspose.GIS, manuel matematiğe olan ihtiyacı ortadan kaldırarak uygulama mantığınıza odaklanmanızı sağlar.

## Koordinat DMS'ye dönüşümü nedir?
Koordinatları DMS'ye dönüştürmek, ondalık enlem ve boylam değerlerini `25°30'00"N 45°30'00"E` gibi bir biçime yazar. Bu gösterim haritacılık, navigasyon ve GIS veri alışverişinde yaygın olarak kullanılır.

## Koordinat dönüşümü için Aspose.GIS'i neden kullanmalısınız?
- **All‑in‑one API** – Harici kütüphane veya karmaşık matematik gerekmez; Aspose.GIS, ayrıştırma ve biçimlendirmeyi dahili olarak yönetir.  
- **High accuracy** – Negatif değerler ve yarımküre işaretleyicileri gibi uç durumların hassas işlenmesi.  
- **Cross‑platform** – Windows, Linux ve macOS .NET çalışma zamanlarında aynı şekilde çalışır.  
- **Extensible** – DMS, decimal degrees, degree‑decimal‑minutes ve GeoRef biçimleri arasında kolayca geçiş yapabilirsiniz.  

## Önkoşullar
Başlamadan önce şunlara sahip olduğunuzdan emin olun:

1. **Basic knowledge of C#** – Değişkenler, metod çağrıları ve konsol çıktısı konusunda aşinalık.  
2. **Aspose.GIS installed** – En son paketi [Aspose.GIS website](https://releases.aspose.com/gis/net/) adresinden indirin.

## Ad Alanlarını İçe Aktarın
İlk olarak, GIS işlemleri için gerekli ad alanlarını içe aktarın:

```csharp
using System;
using Aspose.Gis;
```

## Adım‑adım kılavuz

### Adım 1: Dönüşüm sürecini başlatın
Demo'nun başladığını bilmeniz için dostça bir mesaj yazdırıyoruz.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Adım 2: Decimal Degrees'e Dönüştürün  
Son hedef DMS olsa da, önce orijinal ondalık gösterimi göstererek başlıyoruz. Bu aynı zamanda daha sonra izleyeceğiniz **decimal degrees to dms** yolunu da gösterir.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Adım 3: Degree Decimal Minutes'a Dönüştürün  
Bu format (`DD°MM.m'`), *convert lat long degree minutes* gerektiğinde yaygın bir ara adımdır.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Adım 4: Degree Minutes Seconds (DMS)'ye Dönüştürün  
İşte öğreticimizin özü—**convert coordinates to DMS**.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### Adım 5: GeoRef'e Dönüştürün  
Tamlık açısından, uzaktan algılama iş akışlarında faydalı olan `GeoRef` formatını da gösteriyoruz.

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Yaygın Sorunlar ve Çözümler
- **Incorrect hemisphere letters** – Kuzey/doğu için pozitif, güney/batı için negatif değerler gönderdiğinizden emin olun; API otomatik olarak doğru ek'i ekler.  
- **Unexpected blank output** – `Aspose.Gis` derlemesinin doğru referanslandığını ve projenin desteklenen bir .NET sürümünü hedeflediğini doğrulayın.  
- **License not found** – Lisans dosyanızı uygulama kök dizinine yerleştirin veya programatik olarak `License license = new License(); license.SetLicense("Aspose.GIS.lic");` kodu ile ayarlayın.  

## Sıkça Sorulan Sorular

**Q: Aspose.GIS diğer programlama dilleriyle uyumlu mu?**  
A: Aspose.GIS öncelikle .NET geliştiricilerini hedefler, ancak bir Java sürümü de mevcuttur.

**Q: Aspose.GIS'i satın almadan denemek mümkün mü?**  
A: Evet, Aspose.GIS'in ücretsiz denemesine [website](https://releases.aspose.com/) üzerinden erişebilirsiniz.

**Q: Aspose.GIS için destek nasıl alabilirim?**  
A: Aspose.GIS topluluk forumundan [here](https://forum.aspose.com/c/gis/33) yardım isteyebilirsiniz.

**Q: Aspose.GIS için geçici lisanslar mevcut mu?**  
A: Evet, geçici lisansları [temporary license page](https://purchase.aspose.com/temporary-license/) adresinden alabilirsiniz.

**Q: Aspose.GIS'i nereden satın alabilirim?**  
A: Aspose.GIS'i [purchase page](https://purchase.aspose.com/buy) üzerinden satın alabilirsiniz.

## Sonuç
Bu adımları izleyerek, artık Aspose.GIS for .NET kullanarak **convert coordinates to DMS** ve diğer yaygın GIS formatlarını nasıl dönüştüreceğinizi biliyorsunuz. Bu yetenek, insan tarafından okunabilir konum dizelerini haritalama uygulamalarına, raporlara veya herhangi bir mekansal veri iş akışına sorunsuz bir şekilde entegre etmenizi sağlar. Farklı enlem/boylam değerleriyle denemeler yapmaktan ve `GeoConvert` sınıfının sunduğu diğer formatları keşfetmekten çekinmeyin.

---

**Son Güncelleme:** 2026-02-13  
**Test Edilen:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
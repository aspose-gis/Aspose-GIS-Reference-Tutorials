---
date: 2025-12-04
description: Aspose.GIS for .NET kullanarak temas eden geometrileri nasıl kontrol
  edeceğinizi öğrenin; mekânsal verileri işlemek ve mekânsal analiz yapmak için güçlü
  bir kütüphane.
language: tr
linktitle: How to Check Touching Geometries
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile Dokunan Geometrileri Nasıl Kontrol Edilir
url: /net/geometry-analysis/check-geometries-touching/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dokunan Geometrileri Nasıl Kontrol Edebilirsiniz

## Giriş
İki uzamsal nesne arasında **dokunmayı nasıl kontrol edeceğinizi** öğrenmeniz gerekiyorsa, Aspose.GIS for .NET size işi basitleştiren temiz, tip‑güvenli bir API sunar. Bu öğreticide çizgi dizileri, noktalar oluşturmayı ve ardından `Touches` metodunu kullanarak geometrilerin yalnızca bir sınır paylaşıp paylaşmadığını belirlemeyi göreceksiniz. Bu, ağ yönlendirme, harita örtüşme doğrulama ve yakınlık kontrolleri gibi birçok .NET uzamsal analiz senaryosunda temel bir işlemdir.

## Hızlı Yanıtlar
- **“touching” ne anlama gelir?** İki geometri en az bir sınır noktasını paylaşır ancak iç kısımları kesişmez.  
- **Hangi yöntem bunu kontrol eder?** `Geometry.Touches(otherGeometry)`.  
- **Bu özellik için lisansa ihtiyacım var mı?** Geliştirme için deneme sürümü çalışır; üretim için kalıcı bir lisans gereklidir.  
- **Desteklenen .NET sürümleri?** .NET Framework, .NET Core, .NET 5/6/7 – hepsi Aspose.GIS tarafından kapsanır.  
- **Uygulama ne kadar sürer?** Temel bir örnek için yaklaşık 5‑10 dakika.

## Uzamsal Analizde “Touching” Nedir?
GIS terminolojisinde, *touching* iki geometrinin kenarlarında buluştuğu ancak üst üste gelmediği bir uzamsal ilişkiyi tanımlar. *intersects* (iç kısım çakışması dahil) ile farklıdır ve genellikle özelliklerin yalnızca bir sınırda buluştuğunu doğrulamanız gerektiğinde kullanılır—örneğin, birbirini kesmeden bir kavşakta birleşen yol segmentleri.

## Neden Aspose.GIS'i Uzamsal Analiz .NET için Kullanmalısınız?
Aspose.GIS, yerel GIS kurulumları olmadan **uzamsal verileri işleyebilmenizi** sağlayan tamamen yönetilen bir .NET kütüphanesi sunar. Shapefile, GeoJSON, KML vb. gibi geniş bir format yelpazesini destekler ve `Touches`, `Intersects`, `Contains` gibi yüksek performanslı geometri işlemleri sunar. Saf .NET olduğu için doğrudan web servislerine, masaüstü uygulamalarına veya bulut fonksiyonlarına entegre edebilirsiniz.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Visual Studio** (herhangi bir yeni sürüm) makinenize kurulu.  
2. **Aspose.GIS for .NET** – en son paketi [resmi indirme sayfasından](https://releases.aspose.com/gis/net/) indirin.  
3. **Geçerli bir lisans** (veya ücretsiz deneme) – [buradan](https://releases.aspose.com/) edinin.

### Ortamınızı Kurma
1. Visual Studio'yu henüz kurmadıysanız kurun.  
2. Yukarıdaki bağlantıdan Aspose.GIS for .NET'i indirin ve projenize NuGet paketi olarak ekleyin.  
3. Lisans dosyanızı kod içinde uygulayın (veya test için geçici bir lisans kullanın).

## Ad Alanlarını İçe Aktarın
API'yi kullanmaya başlamak için gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım 1: Çizgi Dizileri (ve bir Nokta) Oluşturun
Aşağıda dokunma ilişkisini test etmek için kullanılacak **çizgi dizi** nesnelerini ve bir noktayı oluşturuyoruz.

```csharp
var geometry1 = new LineString();
geometry1.AddPoint(0, 0);
geometry1.AddPoint(2, 2);
var geometry2 = new LineString();
geometry2.AddPoint(2, 2);
geometry2.AddPoint(3, 3);
var geometry3 = new Point(2, 2);
var geometry4 = new LineString();
geometry4.AddPoint(1, 1);
geometry4.AddPoint(4, 4);
```

*Açıklama*:  
- `geometry1` ve `geometry2` `(2, 2)` uç noktasını paylaşır.  
- `geometry3` tam olarak bu ortak uç noktada bulunan bir noktadır.  
- `geometry4` aynı alanı keser ancak `geometry1` ile bir sınır paylaşmaz.

## Adım 2: Dokunma İlişkilerini Kontrol Edin
Şimdi `Touches` metodunu çağırarak hangi çiftlerin dokunma olarak kabul edildiğini görüyoruz.

```csharp
Console.WriteLine(geometry1.Touches(geometry2)); // True
Console.WriteLine(geometry2.Touches(geometry1)); // True
Console.WriteLine(geometry1.Touches(geometry3)); // True
Console.WriteLine(geometry1.Touches(geometry4)); // False
```

*Sonuç*:  
- İlk üç kontrol **True** döner çünkü geometriler iç çakışma olmadan tek bir noktada buluşur.  
- Son kontrol **False** döner çünkü iki çizgi dizi bir çizgi segmenti üzerinde kesişir, sadece bir sınır noktasında değil.

## Yaygın Sorunlar ve İpuçları
- **Hassasiyet problemleri** – GIS hesaplamaları kayan nokta temellidir. Beklenmedik `False` sonuçlarıyla karşılaşırsanız koordinatları normalleştirmeyi veya `Geometry.EqualsExact(other, tolerance)` ile bir tolerans kullanmayı düşünün.  
- **Karışık geometri tipleri** – `Touches`, noktalar, çizgiler ve çokgenler arasında çalışır, ancak anlamları farklıdır; veri modeliniz için beklenen ilişkiyi her zaman doğrulayın.  
- **Performans** – Büyük veri setleri için kontrolleri toplu olarak yapın veya O(N²) karşılaştırmalardan kaçınmak için Aspose.GIS'in sağladığı uzamsal indeksleri (ör. R‑tree) kullanın.

## Sıkça Sorulan Sorular

**S: Aspose.GIS tüm .NET çerçeveleriyle uyumlu mu?**  
C: Evet. .NET Framework, .NET Core, .NET 5+ ve .NET 6+ destekler, masaüstü, web ve bulut projelerinde esneklik sağlar.

**S: Lisans satın almadan Aspose.GIS'i deneyebilir miyim?**  
C: Kesinlikle. Aspose web sitesinden [buradan](https://purchase.aspose.com/temporary-license/) ücretsiz bir deneme alarak `Touches` işlemi de dahil tüm özellikleri keşfedebilirsiniz.

**S: Aspose.GIS ile ilgili sorular için nereden destek bulabilirim?**  
C: Resmi [Aspose.GIS forumunu](https://forum.aspose.com/c/gis/33) ziyaret ederek sorular sorabilir, örnekler paylaşabilir ve topluluk ile Aspose mühendislerinden yardım alabilirsiniz.

**S: Aspose.GIS için güncellemeler ne sıklıkla yayınlanıyor?**  
C: Aspose, yeni format desteği, performans iyileştirmeleri ve hata düzeltmeleri ekleyen düzenli güncellemeler yayınlar; bu sayede en yeni .NET sürümleriyle uyumluluk sağlanır.

**S: Aspose.GIS için geçici bir lisans alabilir miyim?**  
C: Evet, değerlendirme amaçlı [buradan](https://purchase.aspose.com/temporary-license/) geçici bir lisans temin edilebilir.

---

**Last Updated:** 2025-12-04  
**Tested With:** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

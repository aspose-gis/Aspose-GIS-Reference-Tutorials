---
date: 2026-02-08
description: Aspose.GIS for .NET ile temas eden geometrileri tespit ederek ağ yönlendirme
  kontrolünün nasıl yapılacağını öğrenin; mekânsal verileri işlemek ve mekânsal analiz
  yapmayı sağlayan güçlü bir kütüphane.
linktitle: How to Check Touching Geometries
second_title: Aspose.GIS .NET API
title: 'Ağ Yönlendirme Kontrolü: Aspose.GIS ile Dokunan Geometriler'
url: /tr/net/geometry-analysis/check-geometries-touching/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ağ Yönlendirme Kontrolü: Aspose.GIS for .NET ile Dokunan Geometriler

## Giriş
İki uzamsal nesne arasında **ağ yönlendirme kontrolü** yapmanız gerektiğinde, Aspose.GIS for .NET size işi basitleştiren temiz, tip‑güvenli bir API sunar. Bu öğreticide, çizgi dizileri ve noktalar oluşturmayı ve ardından `Touches` metodunu kullanarak geometrilerin yalnızca bir sınır paylaşıp paylaşmadığını nasıl belirleyeceğinizi göreceksiniz. Bu işlem, rota doğrulama, harita örtüşmesi doğrulaması ve yakınlık sorguları gibi birçok **spatial analysis .NET** senaryosunun temelini oluşturur.

## Hızlı Yanıtlar
- **“Touching” ne anlama gelir?** İki geometri en az bir sınır noktasını paylaşır ancak iç kısımları kesişmez.  
- **Hangi yöntem bunu kontrol eder?** `Geometry.Touches(otherGeometry)`.  
- **Bu özellik için lisansa ihtiyacım var mı?** Geliştirme için bir deneme sürümü çalışır; üretim için kalıcı bir lisans gereklidir.  
- **Desteklenen .NET sürümleri?** .NET Framework, .NET Core, .NET 5/6/7 – hepsi Aspose.GIS tarafından kapsanır.  
- **Uygulama ne kadar sürer?** Temel bir örnek için yaklaşık 5‑10 dakika.  

## Dokunan Geometriler Kullanarak Ağ Yönlendirme Kontrolü Nasıl Yapılır
Aşağıda, **dokunan** geometrileri nasıl kontrol edeceğinize dair tam adımları ve sonucu bir yönlendirme‑doğrulama iş akışına nasıl entegre edeceğinizi adım adım inceleyeceğiz.

### Uzamsal Analizde “Touching” Nedir?
GIS terminolojisinde, *touching* iki geometrinin kenarlarında buluştuğu ancak üst üste gelmediği bir uzamsal ilişkiyi tanımlar. Bu, iç kısım çakışmasını içeren *intersects* (kesişir) yönteminden farklıdır ve özelliklerin yalnızca bir sınırda buluştuğunu doğrulamanız gerektiğinde sıkça kullanılır—örneğin, birbirini geçmeden bir kavşakta birleşen yol segmentleri.

## Neden Aspose.GIS for Spatial Analysis .NET Kullanmalı?
Aspose.GIS, yerel GIS kurulumları olmadan **uzamsal verileri işleyebileceğiniz** tam yönetilen bir .NET kütüphanesi sunar. Shapefile, GeoJSON, KML vb. gibi geniş bir format yelpazesini destekler ve `Touches`, `Intersects`, `Contains` gibi yüksek performanslı geometri işlemleri sağlar. Saf .NET olduğu için doğrudan web servislerine, masaüstü uygulamalarına veya bulut fonksiyonlarına entegre edebilirsiniz.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Visual Studio** (herhangi bir yeni sürüm) makinenize kurulu.  
2. **Aspose.GIS for .NET** – en son paketi [official download page](https://releases.aspose.com/gis/net/) adresinden indirin.  
3. **Geçerli bir lisans** (veya ücretsiz deneme) – [buradan](https://releases.aspose.com/) edinin.  

### Ortamınızı Kurma
1. Visual Studio'yu henüz kurmadıysanız kurun.  
2. Yukarıdaki bağlantıdan Aspose.GIS for .NET'i indirin ve projenize NuGet paketi olarak ekleyin.  
3. Lisans dosyanızı kod içinde uygulayın (veya test için geçici bir lisans kullanın).

## Ad Alanlarını İçe Aktarma
API'yi kullanmaya başlamak için gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım 1: Çizgi Dizileri (ve bir Nokta) Oluşturma
Aşağıda, dokunan ilişkiyi test etmek için kullanılacak **çizgi dizesi** nesneleri ve bir nokta oluşturuyoruz.

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

## Adım 2: Dokunan İlişkileri Kontrol Etme
Şimdi `Touches` metodunu çağırarak hangi çiftlerin dokunduğunu göreceğiz.

```csharp
Console.WriteLine(geometry1.Touches(geometry2)); // True
Console.WriteLine(geometry2.Touches(geometry1)); // True
Console.WriteLine(geometry1.Touches(geometry3)); // True
Console.WriteLine(geometry1.Touches(geometry4)); // False
```

*Sonuç*:  
- İlk üç kontrol **True** döner çünkü geometriler iç çakışma olmadan tek bir noktada buluşur.  
- Son kontrol **False** döner çünkü iki çizgi dizesi bir sınır noktasında değil, bir çizgi segmenti üzerinde kesişir.

## Yaygın Sorunlar ve İpuçları
- **Hassasiyet sorunları** – GIS hesaplamaları kayan nokta temellidir. Beklenmedik `False` sonuçlarıyla karşılaşırsanız, koordinatları normalleştirmeyi veya `Geometry.EqualsExact(other, tolerance)` ile bir tolerans kullanmayı düşünün.  
- **Karışık geometri tipleri** – `Touches` nokta, çizgi ve çokgenlerde çalışır, ancak anlamları farklıdır; veri modeliniz için beklenen ilişkiyi her zaman doğrulayın.  
- **Performans** – Büyük veri setlerinde, kontrolleri toplu olarak yapın veya O(N²) karşılaştırmalardan kaçınmak için Aspose.GIS'in sağladığı uzamsal indeksleri (ör. R‑tree) kullanın.

## Sıkça Sorulan Sorular

**S: Aspose.GIS tüm .NET framework'leriyle uyumlu mu?**  
C: Evet. .NET Framework, .NET Core, .NET 5+ ve .NET 6+ destekler, bu sayede masaüstü, web ve bulut projelerinde esneklik sağlar.

**S: Lisans satın almadan Aspose.GIS'i deneyebilir miyim?**  
C: Kesinlikle. Aspose web sitesinden [buradan](https://purchase.aspose.com/temporary-license/) ücretsiz bir deneme alarak `Touches` işlemi de dahil tüm özellikleri keşfedebilirsiniz.

**S: Aspose.GIS ile ilgili sorular için nereden destek bulabilirim?**  
C: Resmi [Aspose.GIS forumunu](https://forum.aspose.com/c/gis/33) ziyaret ederek sorular sorabilir, örnekler paylaşabilir ve topluluk ile Aspose mühendislerinden yardım alabilirsiniz.

**S: Aspose.GIS için güncellemeler ne sıklıkla yayınlanıyor?**  
C: Aspose, yeni format desteği, performans iyileştirmeleri ve hata düzeltmeleri ekleyen düzenli güncellemeler yayınlar, böylece en yeni .NET sürümleriyle uyumluluğu sağlar.

**S: Aspose.GIS için geçici bir lisans alabilir miyim?**  
C: Evet, değerlendirme amaçlı bir geçici lisans [buradan](https://purchase.aspose.com/temporary-license/) temin edilebilir.

**S: `Touches` metodu ağ yönlendirme kontrolüne nasıl yardımcı olur?**  
C: Yol segmentlerinin yalnızca ortak uç noktalarda (dokunarak) buluştuğunu doğrulayarak, yönlendirme ağının istenmeyen çakışmalar olmadan doğru şekilde bağlandığını doğrulayabilirsiniz.

---

**Son Güncelleme:** 2026-02-08  
**Test Edilen Versiyon:** Aspose.GIS for .NET 24.11 (yazım anındaki en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
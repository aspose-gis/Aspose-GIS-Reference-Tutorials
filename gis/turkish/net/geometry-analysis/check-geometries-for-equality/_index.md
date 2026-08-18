---
date: 2026-06-05
description: Aspose.GIS kullanarak .NET'te geometries'i nasıl karşılaştıracağınızı,
  yinelenen geometries'i nasıl tespit edeceğinizi ve uygulamalarınızda geometry eşitliğini
  nasıl kontrol edeceğinizi öğrenin.
keywords:
- how to compare geometries
- detect duplicate geometries
- Aspose.GIS geometry equality
linktitle: Geometries'i Eşitlik İçin Nasıl Karşılaştırılır
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to compare geometries in .NET using Aspose.GIS, detect duplicate
    geometries, and check geometry equality in your applications.
  headline: How to Compare Geometries for Equality using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard
      projects.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. Download a trial from the [Aspose.GIS releases page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Detailed docs are on the [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).
    question: Where can I find the full API documentation?
  - answer: Post your question on the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How do I get help if I run into an issue?
  - answer: Yes, temporary licenses are available on the [purchase page](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET kullanarak Geometries'i Eşitlik İçin Nasıl Karşılaştırılır
url: /tr/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET kullanarak Geometrileri Eşitlik İçin Karşılaştırma

## Giriş
Bu eğitimde Aspose.GIS for .NET ile **geometrileri nasıl karşılaştıracağınızı** öğreneceksiniz; bu görev, yinelenen geometrileri tespit etmeniz, mekânsal verileri doğrulamanız veya topolojik kuralları uygulamanız gerektiğinde hayati öneme sahiptir. İster bir haritalama servisi oluşturuyor, toplu mekânsal analiz çalıştırıyor, ister sadece iki şeklin aynı konumu kapladığını doğruluyor olun, bu rehber temiz, üretim‑hazır C# kodu ile geometri eşitliğini oluşturma, değiştirme ve test etme sürecinizi adım adım anlatır.

## Hızlı Yanıtlar
- **“Geometrileri karşılaştırmak” ne anlama gelir?** İki geometrik nesnenin aynı alanı kaplayıp kaplamadığını, nasıl oluşturulmuş olurlarsa olsunlar kontrol eder.  
- **Hangi yöntem kullanılır?** Aspose.GIS API'sinden `SpatiallyEquals`.  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme sürümü yeterlidir; üretim için ticari lisans gerekir.  
- **Desteklenen .NET sürümleri?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Tipik uygulama süresi?** Temel bir eşitlik kontrolü için yaklaşık 5‑10 dakika.

## Geometri Eşitliği Nedir?
Geometri eşitliği, aynı zamanda mekânsal eşitlik olarak da adlandırılır ve iki geometrinin Dünya yüzeyindeki aynı nokta kümesini temsil ettiği anlamına gelir. Bir geometri `MultiLineString` olarak, diğeri ise tek bir `LineString` olarak oluşturulmuş olsa bile, her koordinat tanımlı tolerans içinde eşleşiyorsa eşit kabul edilir. Bu tanım, geliştiricilerin heterojen veri kaynakları arasında yinelenen geometrileri güvenilir bir şekilde tespit etmelerini sağlar.

## Geometrileri Karşılaştırmak İçin Aspose.GIS Neden Kullanılır?
Aspose.GIS, harici hizmetlere ihtiyaç duymadan yüksek performanslı, çevrim dışı bir geometri motoru sunar. **30’dan fazla vektör ve raster formatını** (WKT, GeoJSON, Shapefile, KML, GML vb.) destekler ve **yüzbinlerce köşe** içeren dosyaları bellek kullanımını 50 MB’ın altında tutarak işleyebilir. Kütüphanenin `SpatiallyEquals` yöntemi hassasiyete duyarlıdır ve kayan nokta koordinatlarıyla bile deterministik sonuçlar verir.

### Bunun Geliştiriciler İçin Önemi
Yinelenen geometrileri toplu işlemlerde, gerçek‑zaman doğrulama hatlarında veya GIS veri göçlerinde **tespit etmek** gerektiğinde, kanıtlanmış bir kütüphane tahminleri ortadan kaldırır ve farklı veri sağlayıcıları arasında tutarlı sonuçlar garantiler.

## Önkoşullar
Başlamadan önce aşağıdakilerin kurulu olduğundan emin olun:

- **.NET Framework veya .NET Core** – Aspose.GIS tarafından desteklenen herhangi bir sürüm.  
- **Aspose.GIS for .NET kütüphanesi** – [Aspose.GIS indirme sayfası](https://releases.aspose.com/gis/net/) üzerinden indirin.  
- **Bir geliştirme IDE** – Visual Studio, Rider veya C# uzantılarına sahip VS Code.

## Ad Alanlarını İçe Aktarma
.NET projenizde GIS sınıflarının nerede bulunduğunu derleyicinin bilmesi için gerekli `using` ifadelerini ekleyin:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım 1: Geometrileri Tanımlama
`MultiLineString` bir dizi çizgi bileşenini temsil ederken, `LineString` tek bir sürekli çizgiyi tanımlar. Her iki sınıf da temel `Geometry` tipinden türetilir.

İlk olarak karşılaştıracağımız iki geometriyi oluşturuyoruz. Bu örnekte `geometry1`, iki çizgi segmentinden oluşan bir `MultiLineString` iken, `geometry2` aynı başlangıç ve bitiş noktalarını kapsayan tek bir `LineString`’dir.

```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```

## Adım 2: Geometrileri Eşitlik İçin Kontrol Etme
`SpatiallyEquals`, iki geometrinin aynı nokta kümesini kapsayıp kapsamadığını değerlendirir; isteğe bağlı olarak kayan‑nokta hataları için bir tolerans değeri alabilir.

Şimdi GIS motoru tarafından iki şeklin eşit kabul edilip edilmediğini görmek için `SpatiallyEquals` yöntemini kullanıyoruz.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

Konsol `True` çıktısını verir çünkü farklı bir yapılandırmaya rağmen her iki geometri de (0,0) ile (2,2) arasındaki aynı çizgiyi kapsar.

## Adım 3: Bir Geometriyi Değiştirme
Bir değişikliğin eşitliği nasıl etkilediğini göstermek için `geometry2`'ye ekstra bir nokta ekliyoruz.

```csharp
geometry2.AddPoint(3, 3);
```

## Adım 4: Değişiklik Sonrası Eşitliği Yeniden Kontrol Etme
Değişiklikten sonra geometriler artık aynı değildir, bu yüzden `SpatiallyEquals` `False` döndürür.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

`False` çıktısı, eklenen noktanın mekânsal eşitliği bozduğunu doğrular.

## Yinelenen Geometrileri Nasıl Tespit Edebilirsiniz?
Her geometriyi yükleyin, uygun bir toleransla `SpatiallyEquals` çağırın ve `True` dönenleri filtreleyin. Bu desen LINQ ile iyi ölçeklenir, büyük koleksiyonlarda birkaç satır kodla yinelenen şekilleri tanımlamanıza olanak tanır. Ayrıca `GroupBy` ile aynı geometrileri birleştirerek depolama maliyetlerini azaltabilirsiniz.

## Yaygın Sorunlar ve İpuçları
- **Hassasiyet problemleri** – Çok yüksek hassasiyetli koordinatlarla çalışıyorsanız, yuvarlama yapmayı veya `SpatiallyEquals`’ın tolerans aşırı yüklemesini kullanmayı düşünün.  
- **Farklı SRID’ler** – Karşılaştırmadan önce her iki geometrinin aynı Spatial Reference System Identifier (SRID) değerine sahip olduğundan emin olun.  
- **Performans** – Büyük koleksiyonlar için LINQ veya paralel döngülerle toplu karşılaştırmalar yapmak, yükü önemli ölçüde azaltabilir.

## Sık Sorulan Sorular
**S: Aspose.GIS for .NET’i diğer .NET framework’leriyle kullanabilir miyim?**  
C: Evet, Aspose.GIS .NET Framework, .NET Core ve .NET Standard projeleriyle çalışır.

**S: Ücretsiz bir deneme sürümü mevcut mu?**  
C: Kesinlikle. [Aspose.GIS releases sayfasından](https://releases.aspose.com/) bir deneme sürümü indirin.

**S: Tam API dokümantasyonunu nerede bulabilirim?**  
C: Ayrıntılı belgeler [Aspose.GIS dokümantasyon sayfasında](https://reference.aspose.com/gis/net/) yer alıyor.

**S: Bir sorunla karşılaşırsam nasıl destek alabilirim?**  
C: Sorunuzu Aspose.GIS topluluk forumunda [buradan](https://forum.aspose.com/c/gis/33) paylaşabilirsiniz.

**S: Değerlendirme için geçici bir lisans satın alabilir miyim?**  
C: Evet, geçici lisanslar [satın alma sayfasında](https://purchase.aspose.com/temporary-license/) mevcuttur.

## Sonuç
Artık Aspose.GIS for .NET kullanarak **geometrileri nasıl karşılaştıracağınızı** biliyorsunuz; nesneleri oluşturma, mekânsal eşitliği kontrol etme ve değişiklikleri yönetme süreçlerini öğrenmiş oldunuz. Bu yetenek, topoloji doğrulama, yinelenen tespiti ve geometri‑tabanlı filtreleme gibi daha ileri mekânsal analizlerin temelini oluşturur.

---

**Son Güncelleme:** 2026-06-05  
**Test Edilen:** Aspose.GIS for .NET 24.11  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Eğitimler

- [C# ile Poligon Geometrisi Oluşturma ve Aspose.GIS for .NET ile Kesişimini Kontrol Etme](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Aspose.GIS for .NET ile Geometrilerin Mekânsal Çakışma Analizini Nasıl Gerçekleştirirsiniz?](/gis/net/geometry-analysis/check-geometries-overlap/)
- [Ağ Yönlendirme Kontrolü: Aspose.GIS ile Dokunan Geometriler](/gis/net/geometry-analysis/check-geometries-touching/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
date: 2026-02-05
description: Aspose.GIS kullanarak .NET’te geometrileri nasıl karşılaştıracağınızı
  öğrenin ve uygulamalarınızda geometri eşitliğini kontrol edin.
linktitle: How to Compare Geometries for Equality
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET kullanarak Geometrileri Eşitlik İçin Nasıl Karşılaştırılır
url: /tr/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET kullanarak Geometrileri Eşitlik İçin Nasıl Karşılaştırılır

## Giriş
Bu öğreticide **how to compare geometries** konusunu Aspose.GIS for .NET ile keşfedeceksiniz. İster bir haritalama servisi oluşturuyor olun, ister mekansal analiz yapıyor olun ya da iki şeklin aynı konumu temsil edip etmediğini doğrulamanız gerekiyor olsun, geometrileri karşılaştırmayı bilmek çok önemlidir. Sadece birkaç satır C# koduyla nesneleri oluşturma, değiştirme ve geometri eşitliğini test etme adımlarını gösteren tam bir uçtan‑uca örnek üzerinden ilerleyeceğiz.

## Hızlı Yanıtlar
- **What does “compare geometries” mean?** İki geometrik nesnenin aynı alanı kaplayıp kaplamadığını, nasıl oluşturulmuş olurlarsa olsunlar, kontrol eder.  
- **Which method is used?** Aspose.GIS API'sinden `SpatiallyEquals`.  
- **Do I need a license for development?** Test için ücretsiz deneme sürümü yeterlidir; üretim için ticari lisans gereklidir.  
- **Supported .NET versions?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Typical implementation time?** Temel bir eşitlik kontrolü için yaklaşık 5‑10 dakika.

## Geometri Eşitliği Nedir?
Geometri eşitliği (genellikle mekansal eşitlik olarak adlandırılır), iki geometrinin yeryüzündeki aynı nokta kümesini tam olarak temsil etmesi anlamına gelir. Bir MultiLineString ile tek bir LineString farklı şekillerde oluşturulmuş olabilir, ancak hâlâ mekansal olarak eşit olabilirler.

## Aspose.GIS'i Geometrileri Karşılaştırmak İçin Neden Kullanmalısınız?
Aspose.GIS, aşağıdakileri sağlayan sağlam ve yüksek performanslı bir geometri motoru sunar:
- Geniş bir vektör formatı yelpazesi (WKT, GeoJSON, Shapefile vb.) ile çalışır.
- `SpatiallyEquals` gibi hassasiyet‑bilinçli karşılaştırma yöntemleri sunar.
- Harici servislere ihtiyaç duymadan çevrim dışı çalışır; bu da güvenli veya izole ortamlar için idealdir.

### Bunun Geliştiriciler İçin Önemi
Toplu işlemlerde, yinelenen‑tespiti rutinlerinde veya gerçek‑zaman doğrulamasında **how to compare geometries** ihtiyacınız olduğunda, güvenilir bir kütüphane tahminleri ortadan kaldırır ve farklı veri kaynakları arasında tutarlı sonuçlar sağlar.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- **.NET Framework veya .NET Core yüklü** – Aspose.GIS tarafından desteklenen herhangi bir sürüm.
- **Aspose.GIS for .NET kütüphanesi** – [Aspose.GIS download page](https://releases.aspose.com/gis/net/) adresinden indirin.
- **Bir geliştirme IDE'si** – Visual Studio, Rider veya C# uzantılarına sahip VS Code.

## Namespace'leri İçe Aktarma
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
İlk olarak karşılaştıracağımız iki geometriyi oluşturuyoruz. Bu örnekte `geometry1` iki çizgi segmentinden oluşan bir `MultiLineString`, `geometry2` ise aynı başlangıç ve bitiş noktalarına sahip tek bir `LineString` dir.

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

## Adım 2: Geometrilerin Eşitliğini Kontrol Etme
Şimdi `SpatiallyEquals` metodunu kullanarak iki şeklin GIS motoru tarafından eşit kabul edilip edilmediğini görüyoruz.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

Konsol `True` çıktısını verir çünkü farklı bir yapılandırmaya rağmen her iki geometri de (0,0) ile (2,2) arasındaki aynı çizgiyi kapsar.

## Adım 3: Bir Geometriyi Değiştirme
Eşitliğin bir değişiklikle nasıl etkilendiğini göstermek için `geometry2` ye ekstra bir nokta ekliyoruz.

```csharp
geometry2.AddPoint(3, 3);
```

## Adım 4: Değişiklik Sonrası Eşitliği Yeniden Kontrol Etme
Değişiklikten sonra geometriler artık aynı değildir, bu yüzden `SpatiallyEquals` `False` döndürür.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

`False` çıktısı, eklenen noktanın mekansal eşitliği bozduğunu doğrular.

## Yaygın Sorunlar ve İpuçları
- **Precision problems** – Çok yüksek hassasiyetli koordinatlarla çalışıyorsanız, yuvarlama yapmayı veya `SpatiallyEquals` metodunun tolerans aşırı yüklemesini kullanmayı düşünün.  
- **Different SRIDs** – Karşılaştırmadan önce her iki geometrinin aynı Spatial Reference System Identifier (SRID) değerine sahip olduğundan emin olun.  
- **Performance** – Büyük koleksiyonlarda, LINQ kullanarak toplu karşılaştırmalar yapmak yükü azaltabilir.

## Sık Sorulan Sorular
**S: Aspose.GIS for .NET'i diğer .NET framework'leriyle kullanabilir miyim?**  
C: Evet, Aspose.GIS .NET Framework, .NET Core ve .NET Standard projelerinde çalışır.

**S: Ücretsiz bir deneme sürümü mevcut mu?**  
C: Kesinlikle. Deneme sürümünü [Aspose.GIS releases page](https://releases.aspose.com/) adresinden indirebilirsiniz.

**S: Tam API dokümantasyonunu nereden bulabilirim?**  
C: Ayrıntılı belgeler [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/) adresindedir.

**S: Bir sorunla karşılaşırsam nasıl yardım alabilirim?**  
C: Sorununuzu Aspose.GIS topluluk forumunda [burada](https://forum.aspose.com/c/gis/33) paylaşabilirsiniz.

**S: Değerlendirme için geçici bir lisans satın alabilir miyim?**  
C: Evet, geçici lisanslar [purchase page](https://purchase.aspose.com/temporary-license/) üzerinden temin edilebilir.

## Sonuç
Artık Aspose.GIS for .NET kullanarak **how to compare geometries** konusunu, nesneleri oluşturma, mekansal eşitliği kontrol etme ve değişiklikleri yönetme aşamalarıyla biliyorsunuz. Bu yetenek, topoloji doğrulama, yinelenen tespiti ve geometri‑tabanlı filtreleme gibi daha ileri mekansal analizlerin temelini oluşturur.

---

**Son Güncelleme:** 2026-02-05  
**Test Edilen:** Aspose.GIS for .NET 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
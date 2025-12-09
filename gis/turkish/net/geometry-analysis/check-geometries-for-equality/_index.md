---
date: 2025-12-03
description: Aspose.GIS for .NET kullanarak geometrileri nasıl karşılaştıracağınızı
  öğrenin ve .NET uygulamalarınızda geometri eşitliğini kontrol edin.
linktitle: How to Compare Geometries for Equality
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET kullanarak Geometrileri Eşitlik İçin Nasıl Karşılaştırılır
url: /tr/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET Kullanarak Geometrileri Eşitlik İçin Nasıl Karşılaştırılır

## Introduction
Bu öğreticide **geometrileri nasıl karşılaştıracağınızı** Aspose.GIS for .NET ile keşfedeceksiniz. Haritalama servisi oluşturuyor, uzamsal analiz yapıyor veya sadece iki şeklin aynı konumu temsil edip etmediğini doğrulamanız gerekiyorsa, geometrileri karşılaştırmayı bilmek esastır. Sadece birkaç satır C# kodu ile geometri oluşturma, değiştirme ve eşitliği test etme gösteren tam bir uçtan uca örnek üzerinden ilerleyeceğiz.

## Quick Answers
- **“Geometrileri karşılaştırmak” ne anlama gelir?** İki geometrik nesnenin aynı alanı kaplayıp kaplamadığını, nasıl oluşturulduklarından bağımsız olarak kontrol eder.  
- **Hangi yöntem kullanılır?** Aspose.GIS API'sinden `SpatiallyEquals`.  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Desteklenen .NET sürümleri?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Tipik uygulama süresi?** Temel bir eşitlik kontrolü için yaklaşık 5‑10 dakika.

## What is Geometry Equality?
Geometri eşitliği (çoğu zaman uzamsal eşitlik olarak adlandırılır) iki geometrinin Dünya yüzeyindeki aynı nokta kümesini temsil etmesi anlamına gelir. İki şekil farklı şekilde oluşturulabilir—örneğin bir MultiLineString yerine tek bir LineString—ancak hâlâ uzamsal olarak eşit olabilir.

## Why Use Aspose.GIS to Compare Geometries?
Aspose.GIS, sağlam ve yüksek performanslı bir geometri motoru sağlar:
- WKT, GeoJSON, Shapefile vb. geniş bir vektör formatı yelpazesini destekler.
- `SpatiallyEquals` gibi hassasiyet‑bilinçli karşılaştırma yöntemleri sunar.
- Harici servislere ihtiyaç duymadan çevrim dışı çalışır; bu da güvenli veya izole ortamlar için idealdir.

## Prerequisites
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- **.NET Framework veya .NET Core kurulu** – Aspose.GIS tarafından desteklenen herhangi bir sürüm.
- **Aspose.GIS for .NET kütüphanesi** – [Aspose.GIS indirme sayfasından](https://releases.aspose.com/gis/net/) indirin.
- **Bir geliştirme IDE'si** – Visual Studio, Rider veya C# uzantılarına sahip VS Code.

## Import Namespaces
.NET projenizde, GIS sınıflarının nerede bulunduğunu derleyicinin bilmesi için gerekli `using` ifadelerini ekleyin:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step 1: Define the Geometries
İlk olarak, karşılaştıracağımız iki geometriyi oluşturuyoruz. Bu örnekte `geometry1` iki çizgi segmentinden oluşan bir `MultiLineString`, `geometry2` ise aynı başlangıç ve bitiş noktalarına sahip tek bir `LineString`.

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

## Step 2: Check Geometries for Equality
Şimdi `SpatiallyEquals` metodunu kullanarak iki şeklin GIS motoru tarafından eşit kabul edilip edilmediğini görüyoruz.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

Konsol `True` yazdırır çünkü farklı yapılandırmalara rağmen her iki geometri de (0,0) ile (2,2) arasındaki aynı çizgiyi kapsar.

## Step 3: Modify One Geometry
Eşitliğin bir değişiklikle nasıl etkilendiğini göstermek için `geometry2`'ye ekstra bir nokta ekliyoruz.

```csharp
geometry2.AddPoint(3, 3);
```

## Step 4: Re‑check Equality After Modification
Değişiklikten sonra geometriler artık aynı değildir, bu yüzden `SpatiallyEquals` `False` döndürür.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

`False` çıktısı, eklenen noktanın uzamsal eşitliği bozduğunu doğrular.

## Common Issues & Tips
- **Hassasiyet problemleri** – Çok yüksek hassasiyetli koordinatlarla çalışıyorsanız, yuvarlamayı veya `SpatiallyEquals`'in tolerans aşırı yüklemesini kullanmayı düşünün.  
- **Farklı SRID'ler** – Karşılaştırmadan önce her iki geometrinin aynı Spatial Reference System Identifier (SRID)'e sahip olduğundan emin olun.  
- **Performans** – Büyük koleksiyonlarda, LINQ kullanarak toplu karşılaştırmalar yükü azaltabilir.

## Frequently Asked Questions
**S: Aspose.GIS for .NET'i diğer .NET framework'leriyle kullanabilir miyim?**  
C: Evet, Aspose.GIS .NET Framework, .NET Core ve .NET Standard projeleriyle çalışır.

**S: Ücretsiz bir deneme sürümü mevcut mu?**  
C: Kesinlikle. Deneme sürümünü [Aspose.GIS releases sayfasından](https://releases.aspose.com/) indirebilirsiniz.

**S: Tam API dokümantasyonunu nerede bulabilirim?**  
C: Ayrıntılı belgeler [Aspose.GIS dokümantasyon sayfasında](https://reference.aspose.com/gis/net/) mevcuttur.

**S: Bir sorunla karşılaşırsam nasıl yardım alabilirim?**  
C: Sorunuzu Aspose.GIS topluluk forumunda [buradan](https://forum.aspose.com/c/gis/33) paylaşabilirsiniz.

**S: Değerlendirme için geçici bir lisans satın alabilir miyim?**  
C: Evet, geçici lisanslar [satın alma sayfasında](https://purchase.aspose.com/temporary-license/) bulunabilir.

## Conclusion
Artık Aspose.GIS for .NET kullanarak **geometrileri nasıl karşılaştıracağınızı** biliyorsunuz; nesneleri oluşturmak, uzamsal eşitliği kontrol etmek ve değişiklikleri yönetmek konusunda. Bu yetenek, topoloji doğrulama, yinelenen tespiti ve geometri‑tabanlı filtreleme gibi daha ileri uzamsal analizlerin temel yapı taşıdır.

---

**Son Güncelleme:** 2025-12-03  
**Test Edilen:** Aspose.GIS for .NET 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
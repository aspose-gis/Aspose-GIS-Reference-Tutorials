---
date: 2026-09-05
description: Aspose.GIS for .NET kullanarak delikli bir çokgen iç halkası oluşturmayı
  öğrenin. Bu rehber, bir çokgene delik eklemeyi ve veriyle çalışmayı gösterir.
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: Delikli Geometri ile Polygon Oluşturma
og_description: Aspose.GIS for .NET kullanarak delikli bir çokgen iç halkası oluşturmayı
  öğrenin. Bu rehber, bir çokgene delik eklemeyi ve veriyle çalışmayı gösterir.
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: Aspose.GIS kullanarak delikli bir çokgen iç halkası oluşturma
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: Aspose.GIS kullanarak delikli bir çokgen iç halkası oluşturma
url: /tr/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS kullanarak bir delikli çokgen iç halka oluşturma

## Giriş
Bu öğreticide, Aspose.GIS for .NET kullanarak bir delik içeren **çokgen iç halkası** oluşturmayı öğreneceksiniz. Haritalama uygulaması geliştiriyor, mekansal analiz yapıyor ya da GIS hizmetleri için veri hazırlıyor olun, bir çokgenin içine delik eklemek temel bir beceridir. Geliştirme ortamını kurmaktan, desteklenen herhangi bir coğrafi veri formatına kaydedilebilecek geçerli bir çokgen nesnesi üretmeye kadar tüm iş akışını adım adım göstereceğiz.

## Hızlı cevaplar
- **“delikli çokgen oluştur” ne anlama geliyor?** Bu, alan dışı bırakılan bir veya daha fazla iç halka (delik) içeren bir çokgen oluşturmak anlamına gelir.  
- **Bu işlemi hangi kütüphane gerçekleştirir?** Aspose.GIS for .NET, dış ve iç halkalar için tam destek sağlar.  
- **Lisans gerekir mi?** Geliştirme için ücretsiz deneme sürümü çalışır; üretim için ticari lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Ne kadar sürer?** Genellikle uygulama ve test için 10 dakikadan az sürer.

## Aspose.GIS kullanarak çokgene delik ekleme
GIS ortamınızı yükleyin, bir dış halka tanımlayın ve ardından bir veya daha fazla iç halka ekleyin. Aspose.GIS halkaları otomatik olarak yönlendirir ve geometriyi doğrular, böylece ihtiyacınız olan boşluğu temsil eden koordinatlara odaklanabilirsiniz.

## Çokgen iç halkası nedir?
**Çokgen iç halkası**, çokgenin dış şekilinden alanı çıkaran bir iç sınırdır.  
Bunu, Aspose.GIS'in bir delik olarak kabul ettiği ve alan hesaplaması ya da şekil render edilmesi sırasında dışlanacak kapalı bir nokta dizisi tanımlayarak oluşturursunuz.

## Aspose.GIS kullanarak çokgen iç halkası oluşturmanın nedeni
Aspose.GIS, tipik 200 noktalı çokgenler için halka yönünü 5 ms'den kısa sürede doğrular ve düzeltir, böylece özel doğrulama koduna ihtiyaç kalmaz. Ayrıca **30+ coğrafi veri dosya formatını** (Shapefile, GeoJSON, GML, KML vb.) destekler ve tüm dosyayı belleğe yüklemeden 10.000 noktaya kadar çokgenleri işleyebilir; bu da size hız ve ölçeklenebilirlik sağlar.

## Delikli çokgenler için gerçek dünya senaryoları
1. **İç gölü olan arazi parçası** – göl, bir delik olarak modellenir, böylece parselin alanına dahil edilmez.  
2. **Avlu bulunan bina ayak izleri** – avlu, binanın ayak izinden dışlanır.  
3. **Daha büyük bir koruma alanı içinde korunan bölgeler** – ayrı katmanlar oluşturmadan kısıtlı bölümleri dışlayabilirsiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Aspose.GIS for .NET Kütüphanesi: **Aspose.GIS for .NET indirme sayfasından**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)) indirebilirsiniz.  
2. Geliştirme Ortamı: Visual Studio ya da başka bir .NET IDE kurulu bir geliştirme ortamınızın olduğundan emin olun.

## Ad alanlarını içe aktar
`Aspose.Gis` ad alanı, `Polygon`, `LinearRing` ve doğrulama için yardımcı metodlar dahil olmak üzere ihtiyacınız olan tüm geometri tiplerini içerir.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Şimdi, Aspose.GIS for .NET kullanarak delikli bir çokgen geometrisi oluşturmaya devam edelim.

## Adım 1: çokgen nesnesi oluşturma
`Polygon`, isteğe bağlı iç halkalarla düzlemsel bir çokgeni temsil eden Aspose.GIS'in geometri tipidir. Önce dış ve iç halkaları daha sonra tutacak boş bir `Polygon` nesnesi örnekleyerek başlarız.

```csharp
Polygon polygon = new Polygon();
```

## Adım 2: dış halka tanımlama
`LinearRing`, dış ve iç sınırlar için kullanılan sınıftır. Dış halka, çokgenin dış sınırını tanımlar. Kapalı bir şekil oluşturmak için noktaları saat yönünde ekleyin.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Adım 3: iç halka (delik) tanımlama
`LinearRing` aynı zamanda iç halkaları da temsil eder. İç halka, çokgenin alanından dışlanacak **delik**tir. Noktalar genellikle saat yönünün tersine eklenir, ancak Aspose.GIS yönlendirmeyi otomatik olarak halleder.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Adım 4: dış halkayı atama ve iç halkayı çokgene ekleme
`AddInteriorRing` yöntemi, bir `Polygon`'a bir veya daha fazla iç halka ekler. `ExteriorRing` özelliğini ayarladıktan sonra çağırın; birden fazla delik eklemek için yöntemi tekrarlayabilirsiniz.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## İpuçları ve en iyi uygulamalar
- **Yönlendirme okunabilirlik açısından önemlidir** – Aspose.GIS yönlendirmeyi otomatik düzeltse de, dış halkaları saat yönünde ve iç halkaları saat yönünün tersinde tutmak, geometrinin GIS görüntüleyicilerinde incelenmesini kolaylaştırır.  
- **Her halkayı kapatın** – her zaman ilk koordinatı son nokta olarak tekrarlayın; bu geçerli bir kapalı şekil garantiler.  
- **Oluşturduktan sonra doğrulayın** – kaydetmeden önce geometrinin OGC standartlarına uygunluğunu sağlamak için `polygon.IsValid` metodunu çağırabilirsiniz.

## Yaygın sorunlar ve çözümler
| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| GIS görüntüleyicide delik görünmüyor | İç halkanın yönü ters | Noktaların dış halkanın ters yönünde (saat yönünün tersinde) eklendiğinden emin olun. |
| Geçersiz çokgen hatası | Halkalar kapalı değil (ilk ≠ son nokta) | Her halkada ilk noktayı son nokta olarak tekrarlayın (yukarıdaki gibi). |
| Beklenmeyen boş geometri | İç halkalar eklenmeden önce `ExteriorRing` ataması unutulmuş | `polygon.ExteriorRing`'i önce ayarlayın, ardından `AddInteriorRing`'i çağırın. |

## Sıkça Sorulan Sorular
### 1. Aspose.GIS nedir?
Aspose.GIS, geliştiricilerin coğrafi veri ile çalışmasını sağlayan bir .NET kütüphanesidir; çeşitli coğrafi dosya formatlarını oluşturma, okuma ve manipüle etme imkanı sunar.

### 2. Aspose.GIS'i ticari projelerde kullanabilir miyim?
Evet, bir lisans satın alarak Aspose.GIS'i hem kişisel hem de ticari projelerde kullanabilirsiniz. Daha fazla ayrıntı için **Aspose.GIS satın alma sayfasını**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)) ziyaret edin.

### 3. Aspose.GIS için ücretsiz deneme sürümü var mı?
Evet, **Aspose.GIS ücretsiz deneme indirme sayfasından**([https://releases.aspose.com/](https://releases.aspose.com/)) ücretsiz bir deneme sürümüne erişebilirsiniz.

### 4. Aspose.GIS için desteği nereden bulabilirim?
Aspose.GIS için desteği [Aspose.GIS forumunda](https://forum.aspose.com/c/gis/33) bulabilirsiniz.

### 5. Aspose.GIS için geçici bir lisans nasıl alabilirim?
Aspose.GIS için geçici bir lisansı **Aspose.GIS geçici lisans sayfasından**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)) alabilirsiniz.

---

**Son Güncelleme:** 2026-09-05  
**Test Edilen:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.GIS for .NET ile Çokgen Geometrisi Oluşturma](/gis/net/geometry-creation/create-polygon-geometry/)
- [Aspose.GIS ile MultiPolygon Geometrisi Oluşturmayı Öğrenin](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [Aspose.GIS for .NET ile Çokgeni Çizgiye Dönüştürme](/gis/net/geometry-processing/replace-polygons-with-lines/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
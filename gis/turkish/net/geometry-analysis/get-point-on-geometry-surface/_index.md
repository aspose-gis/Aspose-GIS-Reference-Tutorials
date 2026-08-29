---
date: 2026-08-13
description: Aspose.GIS for .NET kullanarak poligon içinde nokta kontrolünün nasıl
  yapılacağını, poligon geometrisi oluşturmayı ve C#'ta yüzey üzerindeki noktayı almayı
  öğrenin. Adım adım rehber ve tam kod örneği.
keywords:
- check point inside polygon
- how to test polygon
- Aspose.GIS geometry
- .NET spatial analysis
lastmod: 2026-08-13
linktitle: Poligon içinde nokta kontrolü ve yüzey üzerindeki nokta alınması
og_description: Aspise.GIS for .NET kullanarak poligon içinde nokta kontrolünün ve
  yüzey üzerindeki noktanın nasıl alınacağını öğrenin. Ayrıntılı C# örneği ve mekansal
  analiz için en iyi uygulamalar.
og_image_alt: Screenshot of Aspose.GIS code checking point inside polygon in C#
og_title: Poligon içinde nokta kontrolü – Aspose.GIS .NET rehberi
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to check point inside polygon using Aspose.GIS for .NET,
    create polygon geometry, and get point on surface in C#. Step‑by‑step guide with
    full code example.
  headline: Check point inside polygon and get point on surface
  type: TechArticle
- description: Learn how to check point inside polygon using Aspose.GIS for .NET,
    create polygon geometry, and get point on surface in C#. Step‑by‑step guide with
    full code example.
  name: Check point inside polygon and get point on surface
  steps:
  - name: create polygon geometry in C#
    text: First, we need to **create a polygon** geometry. We define the exterior
      ring of the polygon by specifying its vertices.
  - name: get point on surface
    text: The `GetPointOnSurface()` method returns a single interior point guaranteed
      to lie inside the polygon’s area. Next, we retrieve a point on the surface of
      the polygon using this method. This is the **get point on surface** step.
  - name: check point inside polygon
    text: The `SpatiallyContains()` method evaluates whether a geometry completely
      contains another geometry, returning true or false. We can verify whether the
      retrieved point lies inside the polygon using this method. This demonstrates
      **retrieving point on polygon** and then checking it.
  type: HowTo
- questions:
  - answer: It verifies whether a given coordinate lies within the boundaries of a
      polygon geometry.
    question: What does “check point inside polygon” mean?
  - answer: '`GetPointOnSurface()` returns a point guaranteed to be inside the polygon.'
    question: Which method returns a point on a polygon’s interior?
  - answer: A free trial works for evaluation; a full license is required for production.
    question: Do I need a license to run the example?
  - answer: .NET Framework, .NET Core, and .NET Standard are all compatible.
    question: Which .NET versions are supported?
  - answer: About 5‑10 minutes to copy, compile, and run.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- check point inside polygon
- Aspose.GIS
- .NET geometry
- C# spatial operations
title: Poligon içinde nokta kontrolü ve yüzey üzerindeki nokta alınması
url: /tr/net/geometry-analysis/get-point-on-geometry-surface/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Poligon içinde nokta kontrolü ve yüzeyde nokta elde etme

## Giriş
Bu öğreticide Aspose.GIS for .NET ile **poligon içinde nokta kontrolü** nasıl yapılacağını öğrenecek ve ayrıca bir geometrinin **yüzeyindeki noktayı** nasıl alacağınızı göreceksiniz. C#'ta bir poligon geometrisi oluşturmayı, poligonun yüzeyinde yer alan bir noktayı almayı ve bu noktanın gerçekten poligon içinde olup olmadığını doğrulamayı adım adım göstereceğiz. Sonunda, herhangi bir .NET coğrafi uygulamasına ekleyebileceğiniz hazır bir kod parçacığına sahip olacaksınız.

## Hızlı Yanıtlar
- **“poligon içinde nokta kontrolü” ne anlama geliyor?** Verilen bir koordinatın bir poligon geometrisinin sınırları içinde olup olmadığını doğrular.  
- **Hangi yöntem bir poligonun iç kısmında bir nokta döndürür?** `GetPointOnSurface()` poligon içinde olması garanti edilen bir nokta döndürür.  
- **Örneği çalıştırmak için lisansa ihtiyacım var mı?** Değerlendirme için ücretsiz deneme sürümü çalışır; üretim için tam lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework, .NET Core ve .NET Standard hepsi uyumludur.  
- **Uygulamanın süresi ne kadar?** Kopyalama, derleme ve çalıştırma için yaklaşık 5‑10 dakika.  

## “Poligon içinde nokta kontrolü” nedir?
Bir noktanın poligon içinde olup olmadığını kontrol etmek, belirli bir koordinatın poligonun köşe noktalarıyla tanımlanan kapalı alan içinde yer alıp almadığını belirler. İşlem, nokta tamamen kapsanıyorsa true, dışarıda veya sınırda ise false döndürür. Bu temel mekansal test, coğrafi çitleme, konuma dayalı analizler ve harita tabanlı doğrulama senaryolarını destekler.

## Bu görev için Aspose.GIS neden kullanılmalı?
Aspose.GIS, bellek verimli modda 200 MB'a kadar poligon işlemlerini işleyen, 50'den fazla koordinat referans sistemini destekleyen ve .NET Framework, .NET Core ve .NET Standard üzerinde yerel bağımlılık olmadan çalışan tamamen yönetilen bir .NET API sunar.  
`GetPointOnSurface()` geometrinin iç kısmında bir nokta döndürür.  
`SpatiallyContains()` bir geometrinin başka bir geometriyi tamamen içerip içermediğini belirler.  
Kütüphanenin zincirlenebilir metodları—örneğin `SpatiallyContains()` ve `GetPointOnSurface()`—belirleyici sonuçlar sağlar ve harici GIS motorlarına ihtiyaç duyulmasını ortadan kaldırır.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

### Ortam kurulumu
1. Aspose.GIS for .NET'i kurun: Aspose.GIS for .NET kitaplığını **Aspose.GIS for .NET indirme sayfasından**([burada](https://releases.aspose.com/gis/net/)) indirin ve kurun.  
2. Geliştirme ortamınızı kurun: Visual Studio, Rider veya tercih ettiğiniz herhangi bir .NET‑uyumlu IDE'yi kullanın.  
3. C# temel bilgisi: Sınıflar, metodlar ve basit konsol‑app projeleriyle rahat olmalısınız.  
4. Belgelere erişim: Öğretici boyunca başvurmak için **Aspose.GIS belgelerini**([belgeler](https://reference.aspose.com/gis/net/)) elinizin altında bulundurun.  

## Ad alanlarını içe aktar
Uygulamaya geçmeden önce, gerekli ad alanlarını içe aktararak başlayalım:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım adım kılavuz

### Adım 1: C#'ta poligon geometrisi oluştur
İlk olarak, **bir poligon** geometrisi oluşturmamız gerekiyor. Poligonun dış halkasını köşe noktalarını belirterek tanımlarız.

```csharp
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(0, 0),
});
```

### Adım 2: yüzeyde nokta al
`GetPointOnSurface()` metodu, poligon alanı içinde olması garanti edilen tek bir iç nokta döndürür. Sonra, bu metodu kullanarak poligonun yüzeyinde bir nokta alırız. Bu, **yüzeyde nokta alma** adımıdır.

```csharp
IPoint pointOnSurface = polygon.GetPointOnSurface();
```

### Adım 3: poligon içinde nokta kontrolü
`SpatiallyContains()` metodu, bir geometrinin başka bir geometriyi tamamen içerip içermediğini değerlendirir ve true ya da false döndürür. Alınan noktanın poligon içinde olup olmadığını bu metodla doğrulayabiliriz. Bu, **poligon üzerindeki noktayı alma** ve ardından kontrol etme sürecini gösterir.

```csharp
Console.WriteLine(polygon.SpatiallyContains(pointOnSurface)); // True
```

## C#'ta poligon kapsama testini nasıl yaparız
Poligon kapsama testini, poligon geometrisini oluşturarak, `GetPointOnSurface()` ile bir iç nokta elde ederek ve ardından `SpatiallyContains()` kullanarak noktanın içinde olduğunu doğrulayarak yaparsınız. Bu iki adımlı desen, geçerli herhangi bir poligon için çalışır ve tembel yükleme ile birleştirildiğinde büyük veri setlerine ölçeklenebilir.

## Yaygın sorunlar ve çözümler
- **Boş poligon** – Dış halkanın en az üç ayrı köşe noktasına sahip olduğundan emin olun; aksi takdirde `GetPointOnSurface()` tanımsız bir nokta döndürebilir.  
- **Saat yönünde vs. saat yönünün tersine** – Halkanın yönü kapsama kontrolünü etkilemez, ancak tutarlı bir sarmalama sırası diğer mekansal işlemlere yardımcı olur.  
- **Koordinat sistemi** – Örnek basit bir Kartezyen düzlem kullanır; gerçek dünya koordinatlarıyla çalışırken, CRS (koordinat referans sistemi) doğru tanımlandığından emin olun.  

## Sıkça Sorulan Sorular

### SSS
#### Aspose.GIS diğer .NET çerçeveleriyle uyumlu mu?
Evet, Aspose.GIS .NET Framework, .NET Core ve .NET Standard dahil olmak üzere çeşitli .NET çerçevelerini destekler.

#### Satın almadan önce Aspose.GIS'i deneyebilir miyim?
Evet, Aspose.GIS'in ücretsiz deneme sürümünü **Aspose.GIS ücretsiz deneme indirme sayfasından**([burada](https://releases.aspose.com/)) indirebilirsiniz.

#### Aspose.GIS için nasıl destek alabilirim?
Yardım almak ve diğer kullanıcılar ve geliştiricilerle etkileşimde bulunmak için **Aspose.GIS forumunu**([burada](https://forum.aspose.com/c/gis/33)) ziyaret edebilirsiniz.

#### Aspose.GIS geçici lisanslar sunuyor mu?
Evet, Aspose.GIS için **geçici lisans sayfasından**([burada](https://purchase.aspose.com/temporary-license/)) geçici lisanslar alabilirsiniz.

#### Aspose.GIS'i nereden satın alabilirim?
Aspose.GIS'i **Aspose.GIS satın alma sayfasından**([burada](https://purchase.aspose.com/buy)) satın alabilirsiniz.

### Ek Sorular ve Cevaplar

**Q:** Büyük poligon veri setlerini yönetmenin en iyi yolu nedir?  
**A:** Geometrileri tembel olarak yükleyin ve bellek yükünü azaltmak için tek bir `GeometryFactory` örneğini yeniden kullanın.

**Q:** Yüzeyde birden fazla nokta alabilir miyim?  
**A:** `GetPointOnSurface()` tek bir iç nokta döndürür. Birden fazla iç nokta üretmek için, poligonun sınırlayıcı kutusu içinde rastgele nokta üreteci kullanabilir ve her birini `SpatiallyContains()` ile test edebilirsiniz.

**Q:** Oluşturulduktan sonra poligonu shapefile olarak dışa aktarmak mümkün mü?  
**A:** Evet, Aspose.GIS, geometrileri Shapefile formatına yazmak için `FeatureSet` ve `ShapefileWriter` sınıflarını sağlar.

## Sonuç
Bu öğreticide, Aspose.GIS for .NET kullanarak **poligon içinde nokta kontrolü** nasıl yapılacağını, **yüzeyde bir nokta** elde etmeyi ve kapsama doğrulamayı öğrendik. Aspose.GIS ile coğrafi verileri işlemek verimli ve basit hale gelir, basit haritalardan kurumsal düzeyde mekansal analizlere kadar ölçeklenebilen sağlam coğrafi uygulamalar oluşturmanızı sağlar.

---

**Son Güncelleme:** 2026-08-13  
**Test Edilen Versiyon:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.GIS for .NET ile Poligon Geometrisi Oluşturma](/gis/net/geometry-creation/create-polygon-geometry/)
- [c# içinde poligon noktası – Geometri Başkasını İçeriyor mu Kontrol Et](/gis/net/geometry-analysis/check-geometry-contains-another/)
- [Aspose.GIS for .NET ile Geometrinin Merkezini Hesaplama](/gis/net/geometry-analysis/get-geometry-centroid/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
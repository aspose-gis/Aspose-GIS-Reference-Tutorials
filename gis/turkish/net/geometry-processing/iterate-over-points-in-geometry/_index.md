---
date: 2026-06-10
description: Aspose.GIS for .NET kullanarak, geometri üzerinde döngü yaparken şekle
  nokta eklemeyi ve koordinat eklemeyi öğrenin; .NET geliştiricileri için güçlü bir
  GIS araç seti.
keywords:
- how to add points
- add coordinates to shape
- Aspose.GIS geometry
linktitle: .NET'te Nokta Ekleme ve Geometri Üzerinde Döngü Yapma
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  headline: How to Add Points and Iterate Over Geometry in .NET
  type: TechArticle
- description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  name: How to Add Points and Iterate Over Geometry in .NET
  steps:
  - name: Create a `LineString` object
    text: '`LineString` is Aspose.GIS''s geometry type that represents an ordered
      collection of points forming a polyline.'
  - name: Add points to the `LineString`
    text: The `AddPoint` method inserts a new vertex (longitude, latitude) at the
      end of the line. Call it repeatedly to **add coordinates to shape** objects.
  - name: Iterate over the points
    text: '`LineString` implements `IEnumerable<IPoint>`, allowing you to loop through
      each point with a `foreach` statement. This makes extracting X (longitude) and
      Y (latitude) values trivial. The loop prints each point’s X (longitude) and
      Y (latitude) values to the console, allowing you to verify that the p'
  type: HowTo
- questions:
  - answer: '`LineString`'
    question: What is the primary class for point collections?
  - answer: Use `AddPoint(longitude, latitude)`
    question: How do you add a point?
  - answer: Yes, `LineString` implements `IEnumerable<IPoint>`
    question: Can you iterate with a foreach loop?
  - answer: .NET 6+ (or .NET Core 3.1/Framework 4.6+) and Aspose.GIS for .NET library
    question: Prerequisites?
  - answer: Building routes, visualizing tracks, or preprocessing data for spatial
      analysis
    question: Typical use case?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: .NET'te Nokta Ekleme ve Geometri Üzerinde Döngü Yapma
url: /tr/net/geometry-processing/iterate-over-points-in-geometry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET'te Noktalar Eklemek ve Geometri Üzerinde Döngü Yapmak

## Giriş

Bir .NET ortamında GIS verileriyle çalışıyorsanız, bilmeniz gereken ilk şeylerden biri **nokta eklemenin** nasıl yapılacağı ve ardından bu noktalarla çalışmaktır. Aspose.GIS for .NET, bu süreci basitleştiren temiz, nesne‑yönelimli bir API sunar. Bu öğreticide bir `LineString` oluşturmayı, ona nokta eklemeyi ve bu noktalar üzerinde döngü yaparak koordinatları çıkarabileceğinizi veya daha ileri analizler yapabileceğinizi göstereceğiz. Ayrıca **shape** nesnelerine koordinat eklemenin verimli yolunu da göreceksiniz.

## Hızlı Yanıtlar
- **Nokta koleksiyonları için birincil sınıf nedir?** `LineString`
- **Bir nokta nasıl eklenir?** `AddPoint(longitude, latitude)` kullanın
- **foreach döngüsüyle yineleme yapabilir misiniz?** Evet, `LineString` `IEnumerable<IPoint>` uygular
- **Önkoşullar?** .NET 6+ (veya .NET Core 3.1/Framework 4.6+) ve Aspose.GIS for .NET kütüphanesi
- **Tipik kullanım senaryosu?** Rotalar oluşturma, izleri görselleştirme veya mekansal analiz için verileri ön işleme
- **IPoint** X (boylam) ve Y (enlem) koordinatlarına sahip tek bir nokta geometrisini temsil eder.

## GIS'te “nokta ekleme” nedir?

Nokta eklemek, bireysel koordinat çiftlerini (boylam, enlem) bir `LineString`, `Polygon` veya `MultiPoint` gibi bir geometrik kapsayıcıya eklemek anlamına gelir. Her nokta, modellediğiniz şekli veya yolu tanımlayan bir köşe olur ve mekansal işlemler ile görselleştirmeleri mümkün kılar. Bu köşelere daha sonra analiz için erişilebilir, çeşitli GIS formatlarına aktarılabilir veya mesafe ölçümü ya da kesişim testi gibi mekansal hesaplamalarda kullanılabilir.

## Neden Aspose.GIS ile nokta eklenir?

Nokta eklemek için Aspose.GIS'i kullanırsınız çünkü kütüphane **tip‑güvenli geometri işleme** garantiler, **30+ vektör ve raster formatını** destekler ve **yüzlerce sayfalık veri setlerini** tüm dosyayı belleğe yüklemeden işleyebilir. API ayrıca yerleşik yineleme, mekansal işlemler ve format dönüşümü (Shapefile, GeoJSON, KML vb.) sunar ve tüm desteklenen platformlarda çalışır.

## Önkoşullar

- Visual Studio 2022 (veya herhangi bir C# IDE'si)  
- Aspose.GIS for .NET NuGet paketi yüklü  
- C# sözdizimi hakkında temel anlayış  

## Ad Alanlarını İçe Aktarma

Uygulamanızda Aspose.GIS işlevlerine erişim sağlamak için gerekli ad alanlarını içe aktararak başlayın:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Geometriye Nasıl Nokta Eklenir?

Nokta eklemek için bir `LineString` örneği oluşturur, her koordinat çifti için `AddPoint` metodunu çağırır ve gerektiğinde koleksiyon üzerinde yineleme yaparsınız. Bu üç adımlı desen, oluşturma, doldurma ve dolaşımı özlü ve okunabilir bir şekilde kapsar. **LineString, bir polilin oluşturmak için sıralı bir nokta koleksiyonunu temsil eden bir geometri tipidir.** Bu yaklaşım, geometrinin geçerli kalmasını ve uzunluk hesaplaması veya dışa aktarım gibi daha ileri mekansal işlemlere hazır olmasını sağlar.

### Adım 1: `LineString` nesnesi oluşturma  

`LineString`, Aspose.GIS'in bir polilin oluşturmak için sıralı bir nokta koleksiyonunu temsil eden geometri tipidir.

```csharp
LineString line = new LineString();
```

### Adım 2: `LineString`'e nokta ekleme  

`AddPoint` metodu, çizginin sonuna yeni bir köşe (boylam, enlem) ekler. **shape** nesnelerine koordinat eklemek için bu metodu tekrar tekrar çağırın.

```csharp
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```

### Adım 3: Noktalar üzerinde yineleme  

`LineString`, `IEnumerable<IPoint>` arayüzünü uygular, böylece bir `foreach` ifadesiyle her noktayı döngüye alabilirsiniz. Bu, X (boylam) ve Y (enlem) değerlerini çıkarmayı çok basit hale getirir.

```csharp
foreach (IPoint point in line)
{
    Console.WriteLine(point.X + "," + point.Y);
}
```

Döngü, her noktanın X (boylam) ve Y (enlem) değerlerini konsola yazar, böylece noktaların doğru eklendiğini doğrulayabilirsiniz.

## Yaygın Kullanım Durumları

- **Rota planlama** – GPS kayıtlarından bir yol oluşturun ve ardından ara noktalar arasındaki mesafeleri analiz edin.  
- **Veri doğrulama** – Noktalar üzerinde yineleme yaparak beklenen sınırlar içinde olduklarından emin olun (ör. bir ülkenin sınırları içinde).  
- **Görselleştirme** – `LineString`'i GeoJSON veya Shapefile olarak dışa aktarın ve haritalama araçlarında kullanın.

## Sıkça Sorulan Sorular

**S1: Aspose.GIS for .NET, `LineString` dışındaki diğer geometrik şekilleri işleyebilir mi?**  
C: Evet, Aspose.GIS `Point`, `Polygon`, `MultiLineString`, `MultiPolygon` ve daha birçok geometri tipini destekler.

**S2: Aspose.GIS hem ticari hem de kişisel projeler için uygun mu?**  
C: Kesinlikle. Lisans seçenekleri ticari, kişisel ve eğitim amaçlı kullanım senaryolarını kapsar.

**S3: Aspose.GIS for .NET, yeni başlayanlar için kapsamlı bir dokümantasyon sunuyor mu?**  
C: Evet, ürün kapsamlı belgeler, API referansları ve hızlı başlangıç için onlarca kod örneği içerir.

**S4: Aspose.GIS for .NET'in işlevselliğini özel geliştirme ile genişletebilir miyim?**  
C: Uzantı metodları oluşturabilir veya Aspose.GIS sınıflarını belirli iş akışlarına uyacak şekilde sarabilirsiniz; bu, özel coğrafi çözümler üzerinde tam kontrol sağlar.

**S5: Aspose.GIS kullanıcıları için teknik destek mevcut mu?**  
C: Aspose forumları ve bilet sistemi aracılığıyla özel teknik destek sağlanır, böylece hızlı yardım alırsınız.

---

**Son Güncelleme:** 2026-06-10  
**Test Edilen Versiyon:** Aspose.GIS for .NET 24.5 (yazım zamanındaki en son sürüm)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.GIS for .NET ile Geometride Noktaları Sayma](/gis/net/geometry-creation/count-points-in-geometry/)
- [Aspose.GIS ile LineString'e Nokta Ekleme ve Geometriyi Düzenlenebilir Formata Dönüştürme](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [Aspose.GIS for .NET ile MultiPoint Geometrisi Oluşturma](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
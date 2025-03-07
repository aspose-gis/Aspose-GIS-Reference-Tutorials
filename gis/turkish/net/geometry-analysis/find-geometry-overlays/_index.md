---
title: Aspose.GIS for .NET ile Geometri Kaplamalarında Uzmanlaşma
linktitle: Geometri Kaplamalarını Bul
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS for .NET'i kullanarak geometrik katmanlama işlemlerini nasıl gerçekleştireceğinizi öğrenin. Ana kesişim, birleşim, fark ve simetrik fark işlemleri.
weight: 16
url: /tr/net/geometry-analysis/find-geometry-overlays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET ile Geometri Kaplamalarında Uzmanlaşma

## giriiş
Coğrafi Bilgi Sistemleri (CBS) alanında, katmanlama işlemleri mekansal analiz için temeldir. Değerli bilgiler elde etmek için farklı mekansal veri kümelerinin karşılaştırılmasını ve birleştirilmesini sağlarlar. Aspose.GIS for .NET, geometrik katmanları verimli bir şekilde gerçekleştirmek için güçlü işlevler sağlar. Bu derste Aspose.GIS for .NET'i kullanarak Kesişme, Birleşim, Fark ve Simetrik Fark gibi çeşitli katmanlama işlemlerini inceleyeceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
### 1. .NET Geliştirme Ortamı
Makinenizde bir .NET geliştirme ortamının kurulu olduğundan emin olun. .NET SDK'yı .NET web sitesinden indirip yükleyebilirsiniz.
### 2. Aspose.GIS for .NET Kütüphanesi
 Aspose.GIS for .NET kütüphanesini şu adresten indirip yükleyin:[İnternet sitesi](https://releases.aspose.com/gis/net/).
## Ad Alanlarını İçe Aktar
Aspose.GIS for .NET'i kullanmaya başlamadan önce gerekli ad alanlarını projenize aktarmanız gerekir.
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım 1: Çokgen Nesneler Oluşturun
Öncelikle uzaysal bölgeleri temsil eden iki çokgen nesneyi tanımlayacağız.
```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```
## Adım 2: Kesişme İşlemini Gerçekleştirin
Şimdi iki çokgenin kesişimini bulalım.
```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Çokgen
```
## Adım 3: Kesişme Noktalarını Yazdırın
Kesişme çokgeninin noktalarını yazdıracağız.
```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```
## Adım 4: Birleştirme İşlemini Gerçekleştirin
Şimdi iki çokgenin birleşimini bulalım.
```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Çokgen
```
## Adım 5: Birleşim Noktalarını Yazdırın
Birleşim çokgeninin noktalarını yazdırın.
```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```
## Adım 6: Fark İşlemini Gerçekleştirin
Şimdi iki çokgen arasındaki farkı bulalım.
```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Çokgen
```
## Adım 7: Fark Noktalarını Yazdırın
Fark çokgeninin noktalarını yazdırın.
```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```
## Adım 8: Simetrik Fark İşlemini Gerçekleştirin
Son olarak iki çokgen arasındaki simetrik farkı bulalım.
```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // Çoklu Çokgen
```
## Adım 9: Simetrik Fark Çokgenlerini Yazdırın
Simetrik farktaki her çokgenin noktalarını yazdırın.
```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```
## Çözüm
Geometri katmanlarına hakim olmak, mekansal analizde çok önemlidir ve Aspose.GIS for .NET, bu işlemleri verimli bir şekilde gerçekleştirmek için kapsamlı bir araç seti sağlar. Bu eğitimi takip ederek, geometrik şekiller üzerinde kesişim, birleşim, fark ve simetrik fark işlemlerini gerçekleştirmek için Aspose.GIS for .NET'i nasıl kullanacağınızı öğrendiniz.
## SSS'ler
### S: Aspose.GIS for .NET'i ticari projelerimde kullanabilir miyim?
Evet, Aspose.GIS for .NET hem ticari hem de ticari olmayan projelerde kullanılabilir.
### S: Aspose.GIS for .NET'in deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).
### S: Aspose.GIS for .NET için nasıl destek alabilirim?
 Aspose.GIS topluluk forumundan destek alabilirsiniz[Burada](https://forum.aspose.com/c/gis/33).
### S: Aspose.GIS for .NET için herhangi bir geçici lisans mevcut mu?
 Evet, test ve değerlendirme amaçlı geçici lisanslar mevcuttur. Bunları şuradan alabilirsiniz:[Burada](https://purchase.aspose.com/temporary-license/).
### S: Aspose.GIS for .NET'i doğrudan satın alabilir miyim?
 Evet, Aspose.GIS for .NET'i web sitesinden satın alabilirsiniz.[Burada](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

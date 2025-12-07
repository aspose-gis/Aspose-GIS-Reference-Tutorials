---
date: 2025-12-07
description: Aspose.GIS for .NET kullanarak bu mekânsal bindirme öğreticisinde bindirme
  işlemlerini nasıl gerçekleştireceğinizi öğrenin. Kesişim, birleşim, fark ve simetrik
  fark konularında uzmanlaşın.
language: tr
linktitle: Find Geometry Overlays
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile Örtüşüm İşlemlerini Nasıl Gerçekleştirirsiniz
url: /net/geometry-analysis/find-geometry-overlays/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET ile Örtüşme İşlemlerini Nasıl Gerçekleştirirsiniz

## Giriş
Overlay analizi, herhangi bir **spatial overlay tutorial** içinde temel bir tekniktir—birden çok coğrafi katmanı birleştirmenize, karşılaştırmanıza ve içgörüler elde etmenize olanak tanır. Bu rehberde Intersection, Union, Difference ve Symmetric Difference gibi **ö

rtüşme** işlemlerini güçlü Aspose.GIS for .NET kütüphanesini kullanarak nasıl gerçekleştireceğinizi öğreneceksiniz. Rehberin sonunda bu yöntemleri arazi kullanım planlaması, çevresel etki çalışmaları ve rota optimizasyonu gibi gerçek dünya GIS problemlerine uygulayabileceksiniz.

## Hızlı Yanıtlar
- **Bir örtüşme işlemi nedir?** İki geometrinin birleştirilerek yeni bir geometri (intersection, union vb.) üretilen bir uzamsal yöntemdir.  
- **.NET'te örtüşmeleri yöneten kütüphane hangisidir?** Aspose.GIS for .NET.  
- **Uygulamanın süresi ne kadar?** Temel örnek için yaklaşık 10‑15 dakika.  
- **Lisans gerekli mi?** Deneme sürümü ücretsizdir; üretim için ticari lisans gerekir.  
- **Bunu .NET Core / .NET 6+ üzerinde çalıştırabilir miyim?** Evet—Aspose.GIS tüm modern .NET çalışma zamanlarını destekler.

## Örtüşme İşlemi Nedir?
Bir örtüşme işlemi iki geometrik şekli alır ve bunların uzamsal ilişkisine dayanarak yeni bir şekil hesaplar.  
- **Intersection** her iki şeklin ortak alanını döndürür.  
- **Union** şekilleri tek bir geometri içinde birleştirir.  
- **Difference** bir şekli diğerinden çıkarır.  
- **Symmetric Difference** her iki şekle ait olup aynı anda her iki şekle de ait olmayan bölümleri döndürür.

## Neden Aspose.GIS'i Örtüşme İçin Kullanmalısınız?
Aspose.GIS, düşük seviyeli matematiği soyutlayan temiz, tamamen yönetilen bir API sunar; böylece iş mantığınıza odaklanabilirsiniz. Çapraz platform çalışır, büyük veri setlerini verimli bir şekilde işler ve diğer .NET bileşenleriyle sorunsuz entegrasyon sağlar.

## Önkoşullar
- Çalışan bir .NET geliştirme ortamı (Visual Studio, VS Code veya .NET CLI).  
- Aspose.GIS for .NET kütüphanesi – en son sürümü [official site](https://releases.aspose.com/gis/net/) adresinden indirin.  

### Ad Alanlarını İçe Aktarma
Aspose.GIS for .NET'i kullanmaya başlamadan önce projenize gerekli ad alanlarını (namespaces) eklemeniz gerekir.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## .NET'te Örtüşme İşlemlerini Nasıl Gerçekleştirirsiniz
Aşağıda iki poligon oluşturup her bir örtüşme yöntemini uygulayan adım adım bir yürütme bulunmaktadır.

### Adım 1: Poligon Nesnelerini Oluşturma
İlk olarak, kısmen üst üste gelen iki basit kare poligon tanımlıyoruz. Bu poligonlar test verilerimiz olacak.

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

### Adım 2: Intersection İşlemini Gerçekleştirme
**Intersection**, iki poligonun kesişen alanını verir.

```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Polygon
```

### Adım 3: Intersection Noktalarını Yazdırma
Sonuç poligonunun koordinatlarını göstermek için yardımcı bir metod (`PrintRing`) kullanıyoruz.

```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```

### Adım 4: Union İşlemini Gerçekleştirme
**Union**, her iki poligonu da kapsayan tek bir şekil olarak birleştirir.

```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Polygon
```

### Adım 5: Union Noktalarını Yazdırma
Birleştirilmiş geometrinin koordinatlarını çıktılayın.

```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```

### Adım 6: Difference İşlemini Gerçekleştirme
**Difference**, `polygon2`yi `polygon1`den çıkarır ve `polygon1`in `polygon2` ile kesişmeyen kısmını bırakır.

```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Polygon
```

### Adım 7: Difference Noktalarını Yazdırma
Çıkarma işleminden sonra kalan köşe noktalarını gösterin.

```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```

### Adım 8: Symmetric Difference İşlemini Gerçekleştirme
**Symmetric Difference**, her iki poligona ait olup aynı anda her iki poligona da ait olmayan alanları döndürür. Sonuç bir `MultiPolygon` olur.

```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // MultiPolygon
```

### Adım 9: Symmetric Difference Poligonlarını Yazdırma
`MultiPolygon` içindeki her bir poligonu döngüye alıp noktalarını yazdırın.

```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden Oluşur | Çözüm |
|-------|----------------|-----|
| `Intersection` sonucunda `null` | Poligonlar gerçekte üst üste gelmiyor. | Koordinatları kontrol edin veya `Intersection` çağırmadan önce `Intersects` kontrolü yapın. |
| `SymDifference` sonucunda beklenmeyen `MultiPolygon` | Simetrik fark, ayrık bileşenler üretebilir. | Gösterildiği gibi `IMultiPolygon` tipine dönüştürüp döngüyle işleyin. |
| Büyük veri setlerinde performans yavaşlaması | Her işlem geometriyi sıfırdan yeniden hesaplar. | Ara sonuçları yeniden kullanın veya örtüşmeden önce `Simplify()` ile geometrileri sadeleştirin. |

## Sıkça Sorulan Sorular

**Q: Aspose.GIS for .NET'i ticari projelerimde kullanabilir miyim?**  
A: Evet, geçerli bir lisansla Aspose.GIS for .NET hem ticari hem de ticari olmayan projelerde kullanılabilir.

**Q: Aspose.GIS for .NET için bir deneme sürümü mevcut mu?**  
A: Evet, ücretsiz bir deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.

**Q: Aspose.GIS for .NET için destek nasıl alınır?**  
A: Aspose.GIS topluluk forumundan [burada](https://forum.aspose.com/c/gis/33) destek alabilirsiniz.

**Q: Aspose.GIS for .NET için geçici lisanslar mevcut mu?**  
A: Evet, test ve değerlendirme amaçlı geçici lisanslar [buradan](https://purchase.aspose.com/temporary-license/) temin edilebilir.

**Q: Aspose.GIS for .NET'i doğrudan satın alabilir miyim?**  
A: Evet, Aspose.GIS for .NET'i web sitesinden [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

---

**Son Güncelleme:** 2025-12-07  
**Test Edilen Sürüm:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
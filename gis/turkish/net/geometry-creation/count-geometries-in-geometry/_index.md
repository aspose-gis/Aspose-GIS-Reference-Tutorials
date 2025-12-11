---
date: 2025-12-11
description: Aspose.GIS for .NET kullanarak geometri sayma ve geometri koleksiyonuna
  ekleme yöntemlerini öğrenin. Geliştiriciler için kod örnekleriyle adım adım bir
  öğretici.
linktitle: Count Geometries in Geometry
second_title: Aspose.GIS .NET API
title: Aspose.GIS ile Geometri'de Geometrileri Nasıl Sayılır
url: /tr/net/geometry-creation/count-geometries-in-geometry/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS ile Geometri İçinde Geometrileri Sayma

## Introduction
Eğer birleşik bir şekil içinde **geometrileri nasıl sayacağınızı** öğrenmeniz gerekiyorsa, Aspose.GIS for .NET bunu oldukça basitleştirir. Haritalama uygulaması, konuma dayalı hizmet veya mekansal analiz motoru geliştiriyor olun, bir koleksiyondaki bireysel geometrileri sayabilmek temel bir görevdir. Bu öğreticide basit geometriler oluşturmayı, bunları bir koleksiyona eklemeyi ve sonunda API'yi kullanarak geometri sayısını almayı adım adım göstereceğiz.

## Quick Answers
- **Birincil yöntem nedir?** `GeometryCollection`'ın `Count` özelliğini kullanın.  
- **Hangi ad alanı (namespace) gereklidir?** `Aspose.Gis.Geometries`.  
- **Geliştirme için lisansa ihtiyacım var mı?** Değerlendirme için ücretsiz deneme çalışır; üretim için lisans gereklidir.  
- **Farklı geometri tipleri ekleyebilir miyim?** Evet – noktalar, çizgiler, çokgenler vb. aynı koleksiyona eklenebilir.  
- **.NET Core ile uyumlu mu?** Kesinlikle, Aspose.GIS .NET Framework ve .NET Core'u destekler.

## What is “how to count geometries”?
Geometrileri sayma, bir `GeometryCollection` gibi birleşik bir yapının içinde kaç ayrı geometrik nesnenin (nokta, çizgi, çokgen vb.) bulunduğunu belirlemek anlamına gelir. API, bu bilgiyi basit bir tamsayı özelliği aracılığıyla sunar ve manuel döngü ihtiyacını ortadan kaldırır.

## Why add geometries to collection?
Geometrileri bir koleksiyona eklemek, birden çok şekli tek bir mantıksal varlık olarak ele almanızı sağlar. Bu, toplu işleme, mekansal sorgular ve birden çok özelliği ayrı ayrı yönetmeden birlikte render etme gibi durumlarda faydalıdır.

## Prerequisites
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Visual Studio** – herhangi bir güncel sürüm (2019, 2022 veya daha yeni).  
2. **Aspose.GIS for .NET** – [indirme sayfasından](https://releases.aspose.com/gis/net/) indirip kurun.  
3. **Temel C# bilgisi** – bir konsol uygulaması oluşturma ve NuGet paketleri ekleme konusunda rahat olmalısınız.

## Import Namespaces
First, import the namespaces that give you access to the geometry classes.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step 1: Create a Point Geometry
Bir `Point`, tek bir koordinat çifti (enlem, boylam) temsil eder. Burada New York City için bir nokta oluşturuyoruz.

```csharp
Point point = new Point(40.7128, -74.006);
```

## Step 2: Create a LineString Geometry
Bir `LineString`, birbirine bağlı noktalar serisidir. İki rastgele nokta ekleyerek örnekleyeceğiz.

```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```

## Step 3: Add Geometries to a Collection
Şimdi nokta ve çizgiyi tek bir `GeometryCollection` içinde birleştiriyoruz. İşte **geometrileri koleksiyona ekleme** burada gerçekleşir.

```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```

## Step 4: How to Count Geometries
`Count` özelliği, koleksiyonda depolanan toplam geometri sayısını döndürür.

```csharp
int geometriesCount = geometryCollection.Count;
```

## Step 5: Display the Count
Son olarak sayıyı konsola yazdırıyoruz. Bu örnekte sonuç `2` olacaktır.

```csharp
Console.WriteLine(geometriesCount); // 2
```

## Common Issues and Solutions
| Sorun | Neden Oluşur | Çözüm |
|-------|----------------|-----|
| **Count always returns 0** | Koleksiyon hiç doldurulmadı. | `Count` özelliğine erişmeden önce her geometri için `Add` çağrısı yaptığınızdan emin olun. |
| **Invalid coordinate order** | Point yapıcı metodu önce enlemi, sonra boylamı bekler. | `Point` veya `LineString` oluştururken parametre sırasını kontrol edin. |
| **Missing namespace error** | `Aspose.Gis.Geometries` içe aktarılmadı. | Dosyanın en üstüne `using Aspose.Gis.Geometries;` ekleyin. |

## Frequently Asked Questions

**S: Aynı koleksiyonda farklı geometri tiplerini karıştırabilir miyim?**  
C: Evet, noktalar, çizgiler, çokgenler ve hatta diğer koleksiyonları tek bir `GeometryCollection` içine ekleyebilirsiniz.

**S: Aspose.GIS bir koleksiyon için GeoJSON dışa aktarımını destekliyor mu?**  
C: Kesinlikle. Koleksiyonu serileştirmek için `geometryCollection.ToGeoJson()` kullanabilirsiniz.

**S: Saydıktan sonra her bir geometri üzerinde döngü kurabilir miyim?**  
C: Evet, `foreach (var geom in geometryCollection)` ile her geometriyi ayrı ayrı işleyebilirsiniz.

**S: Geliştirme sürümleri için lisansa ihtiyacım var mı?**  
C: Değerlendirme için ücretsiz deneme yeterli, ancak üretim dağıtımları için lisanslı bir sürüm gereklidir.

### Aspose.GIS for .NET hem masaüstü hem de web uygulamaları için uygun mu?
Evet, Aspose.GIS for .NET hem masaüstü hem de web uygulamalarında sorunsuz bir şekilde kullanılabilir.

### Aspose.GIS for .NET ile mekansal sorgular yapabilir miyim?
Kesinlikle, Aspose.GIS for .NET geometriler üzerinde mekansal sorgular gerçekleştirmek için güçlü bir destek sunar.

### Aspose.GIS for .NET çeşitli GIS dosya formatlarını destekliyor mu?
Evet, Aspose.GIS for .NET SHP, KML ve GeoJSON dahil olmak üzere geniş bir GIS dosya formatı yelpazesini destekler.

### Aspose.GIS for .NET için ücretsiz bir deneme mevcut mu?
Evet, ücretsiz denemeyi [web sitesinden](https://releases.aspose.com/) indirebilirsiniz.

### Aspose.GIS for .NET için destek nereden bulunur?
Destek için [Aspose.GIS forumunu](https://forum.aspose.com/c/gis/33) ziyaret edebilirsiniz.

## Conclusion
Bu rehberde **GeometryCollection** içinde **geometrileri nasıl sayacağınızı** ele aldık ve Aspose.GIS for .NET kullanarak **geometrileri koleksiyona ekleme** adımlarını gösterdik. Bu temellerle artık daha zengin mekansal özellikler oluşturabilir, toplu işlemler yapabilir ve herhangi bir .NET uygulamasına coğrafi zekâ entegrasyonu sağlayabilirsiniz.

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
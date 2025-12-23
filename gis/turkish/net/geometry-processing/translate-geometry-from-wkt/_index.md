---
date: 2025-12-23
description: Aspose.GIS for .NET kullanarak WKT'yi geometriye dönüştürmeyi ve nokta
  saymayı öğrenin. Geliştiriciler için adım adım rehber.
linktitle: Translate Geometry from WKT
second_title: Aspose.GIS .NET API
title: Aspose.GIS kullanarak .NET'te WKT'yi Geometriye Dönüştürme
url: /tr/net/geometry-processing/translate-geometry-from-wkt/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS ile .NET'te WKT'yi Geometriye Dönüştürme

## Introduction
Bu öğreticide Aspose.GIS for .NET ile **WKT'yi geometriye nasıl dönüştüreceğinizi** keşfedecek ve ortaya çıkan şekilde **nokta sayısını nasıl sayacağınızı** gösteren pratik bir örnek göreceksiniz. Harita hizmeti oluşturuyor, GIS verilerini işliyor ya da bir .NET uygulamasında Well‑Known Text (WKT) okumanız gerekiyorsa, bu adımlar sizi hızlıca çalışır hale getirecek.

## Quick Answers
- **Aspose.GIS WKT'yi okuyabilir mi?** Evet – `Geometry.FromText` yöntemi WKT dizgilerini doğrudan ayrıştırır.  
- **Kaç satır kod gerekir?** Temel bir dönüşüm ve nokta sayımı için yaklaşık 5‑6 satır.  
- **Üretim için lisans gerekiyor mu?** Evet, deneme dışı kullanım için ticari bir lisans gereklidir.  
- **Desteklenen .NET sürümleri?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6+.  
- **Nokta sayma yerleşik mi?** Kesinlikle – geometri nesneleri bir `Count` özelliği sunar.

## What is “convert WKT to geometry”?
Well‑Known Text (WKT), geometrik nesneleri temsil eden düz‑metin bir işaretlemedir. WKT'yi geometriye dönüştürmek, bu metni programatik olarak manipüle edebileceğiniz bir nesne modeline (ör. `ILineString`, `IPolygon`) dönüştürmek anlamına gelir.

## Why use Aspose.GIS for this conversion?
- **Sıfır bağımlılık ayrıştırma** – harici kütüphanelere gerek yok.  
- **Tam GIS özellik seti** – 2D/3D koordinatları, SRID yönetimini ve birçok dosya formatını destekler.  
- **Yüksek performans** – büyük veri setleri ve çok iş parçacıklı senaryolar için optimize edilmiştir.  

## Prerequisites
Before we begin, make sure you have:

1. Aspose.GIS for .NET API – bunu [buradan](https://releases.aspose.com/gis/net/) indirin.  
2. C# temelleri ve bir .NET geliştirme ortamı (Visual Studio, VS Code vb.) bilgisi.

## Import Namespaces
First, add the required namespaces to your C# file:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step 1: Create a LineString from WKT
Now we’ll **convert WKT to geometry** by creating a `LineString` object from a WKT string that includes Z‑coordinates:

```csharp
ILineString line = (ILineString)Geometry.FromText("LINESTRING Z (0.1 0.2 0.3, 1 2 1, 12 23 2)");
```

> *Pro tip:* `FromText` yöntemi geometri tipini otomatik olarak algılar, böylece uygun arayüze (`ILineString`, `IPolygon` vb.) dönüştürebilirsiniz.

## How to count points in a LineString?
To answer the secondary keyword **how to count points**, simply read the `Count` property of the `ILineString` instance:

```csharp
Console.WriteLine(line.Count); // Output: 3
```

Çıktı, çizginin üç köşe noktasına sahip olduğunu gösterir; bu, dönüşümün başarılı olduğunu ve nokta sayısının doğru olduğunu doğrular.

## Conclusion
Artık Aspose.GIS for .NET kullanarak **WKT'yi geometriye nasıl dönüştüreceğinizi** ve tek bir özellik çağrısıyla nokta sayısını nasıl alacağınızı biliyorsunuz. Bu temeller, GIS veri işleme yeteneklerini masaüstü araçlarından bulut hizmetlerine kadar herhangi bir .NET uygulamasına entegre etmenizi sağlar.

## FAQ's
### Can I use Aspose.GIS for .NET in my commercial projects?
Evet, kullanabilirsiniz. Aspose.GIS for .NET geliştirici başına lisanslanmıştır ve ticari projelerde herhangi bir kısıtlama olmaksızın kullanılabilir.

### Does Aspose.GIS for .NET support other geometric formats besides WKT?
Evet, Aspose.GIS for .NET WKB, GeoJSON ve Shapefile dahil olmak üzere çeşitli geometrik formatları destekler.

### Is there a free trial available for Aspose.GIS for .NET?
Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) alabilirsiniz.

### Where can I find documentation for Aspose.GIS for .NET?
Belgeleri [burada](https://reference.aspose.com/gis/net/) bulabilirsiniz.

### How can I get support for Aspose.GIS for .NET?
Destek alabileceğiniz Aspose.GIS forumu [burada](https://forum.aspose.com/c/gis/33) mevcuttur.

## Frequently Asked Questions (Additional)

**Q: WKT dizgim geçersiz sözdizimi içerirse ne olur?**  
A: `Geometry.FromText` bir `FormatException` fırlatır. Bozuk WKT'yi nazikçe işlemek için çağrıyı bir try‑catch bloğuna sarın.

**Q: WKT dizgileri koleksiyonunu tek seferde dönüştürebilir miyim?**  
A: Evet – dizi listeniz üzerinde döngü kurun, her öğe için `Geometry.FromText` çağırın ve sonuçları bir `List<IGeometry>` içinde saklayın.

**Q: Aspose.GIS dönüşüm sırasında Z değerlerini korur mu?**  
A: Kesinlikle. WKT bir Z koordinatı içerdiğinde (örnekte gösterildiği gibi), ortaya çıkan geometri bu değerleri tutar.

**Q: Manipülasyon sonrası geometriyi tekrar WKT'ye dışa aktarmak mümkün mü?**  
A: Herhangi bir `IGeometry` örneğinde `ToText()` metodunu kullanarak WKT temsiline ulaşabilirsiniz.

---

**Son Güncelleme:** 2025-12-23  
**Test Edilen:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
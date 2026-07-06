---
date: 2026-04-09
description: Aspose.GIS for .NET kullanarak eğrileri çizgilere (geometrileri doğrusal
  hâle getirerek) dönüştürmeyi öğrenin; bu sayede .NET uygulamalarınızda verimli coğrafi
  veri işleme ve analizi sağlayabilirsiniz.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
linktitle: Geometriyi Doğrusallaştır
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile Eğrileri Çizgilere Dönüştürme
url: /tr/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Eğrileri Çizgilere Dönüştürme (Geometriyi Doğrusal Hale Getirme) Aspose.GIS for .NET ile

## Giriş
If you need to **convert curves to lines** for mapping, spatial analysis, or data‑exchange tasks, Aspose.GIS for .NET gives you a clean, programmatic way to do it. In this tutorial we’ll walk through a complete, real‑world example that shows you how to take a complex geometry—containing curves and compound shapes—and turn it into a simple linear representation that works with any GIS system.

## Hızlı Yanıtlar
- **“Eğrileri çizgilere dönüştürmek” ne anlama geliyor?** It transforms curved geometries into straight‑line segments.  
- **Neden Aspose.GIS seçilmeli?** The library supports dozens of GIS formats and handles geometry conversion without external tools.  
- **Önceden neye ihtiyacım var?** .NET Framework or .NET Core, Visual Studio (or any C# IDE), and the Aspose.GIS NuGet package.  
- **Örnek ne kadar sürede çalışır?** Less than five minutes once the library is installed.  
- **Diğer formatlara dışa aktarabilir miyim?** Absolutely—swap the KML driver for Shapefile, GeoJSON, etc.

## Eğrileri Çizgilere Dönüştürmek Ne Anlama Geliyor?
Converting curves to lines (also called **linearizing geometry**) breaks down any curved or composite shape into a series of straight‑line segments, known as a “linear geometry.” This simplification makes rendering faster, improves compatibility with older GIS services, and reduces the complexity of spatial algorithms.

## Neden Eğrileri Çizgilere Dönüştürmeliyiz?
- **Performans:** Linear geometries render and query much faster.  
- **Uyumluluk:** Many GIS platforms (especially legacy services) only accept linear features.  
- **Basitleştirme:** Ideal for thumbnails, quick previews, or feeding data into algorithms that require linear input.

## Ön Koşullar
Before diving into the code, make sure you have:

1. **Aspose.GIS for .NET** – download it from the [Aspose.GIS website](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (or .NET Core) installed on your development machine.  
3. **Visual Studio** (or any C#‑compatible IDE) for writing and executing the sample.

## Ad Alanlarını İçe Aktarma
To start using Aspose.GIS functionality, import the required namespaces.

### Adım 1: Temel Aspose.GIS Ad Alanları
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Adım 2: Hedef Format İçin Sürücü
For this example we’ll write the result to a KML file:
```csharp
using Aspose.GIS.Kml;
```

## Adım Adım Eğrileri Çizgilere Dönüştürme Kılavuzu
Below is a detailed walk‑through of each line of code, explaining **how to convert curves to lines** and why each step matters.

### Adım 1: Çıktı Yolunu Tanımlama
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Replace `"Your Document Directory"` with the folder where you want the KML file saved. Using `Path.Combine` is recommended for cross‑platform compatibility.

### Adım 2: Çıktı Dosyası İçin Katman Oluşturma
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
A *layer* is a container for geographic features. Here we create a new KML layer that will hold our linearized geometry.

### Adım 3: Yeni Bir Özellik Oluşturma
```csharp
var feature = layer.ConstructFeature();
```
A *feature* represents a single geographic object (point, line, polygon, etc.). We’ll attach our linear geometry to this feature.

### Adım 4: Orijinal Karmaşık Geometriyi Tanımlama
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
We create a geometry from a Well‑Known Text (WKT) string. This example includes a `LineString`, a `CompoundCurve`, and a `CircularString`—perfect for demonstrating **convert curves to lines**.

### Adım 5: Eğrileri Çizgilere Dönüştürme
```csharp
var linear = geometry.ToLinearGeometry();
```
The `ToLinearGeometry()` method converts all curves into straight‑line segments, producing a *linear* version of the original geometry.

### Adım 6: Doğrusal Geometriyi Özelliğe Atama
```csharp
feature.Geometry = linear;
```
Now the feature holds the simplified, linear geometry.

### Adım 7: Özelliği Katmana Ekleme
```csharp
layer.Add(feature);
```
Finally, we add the feature to the KML layer, which writes the linear geometry to the output file when the `using` block ends.

## Yaygın Tuzaklar ve Profesyonel İpuçları
- **Yol ayırıcıları:** Use `Path.Combine` to avoid issues on Windows vs. Linux.  
- **Çok büyük geometriler:** Linearizing intricate shapes can generate thousands of vertices; consider calling `Simplify()` after linearization to reduce point count.  
- **Sürücü seçimi:** If you need a different output format, replace `Drivers.Kml` with `Drivers.Shapefile`, `Drivers.GeoJson`, etc., and change the file extension accordingly.  
- **Z değerlerini koruma:** `ToLinearGeometry()` retains 3‑D (Z) coordinates, so you don’t lose elevation data.

## Sıkça Sorulan Sorular (SSS)

**S: Aspose.GIS for .NET .NET Core ile uyumlu mu?**  
C: Yes, Aspose.GIS works with .NET Core, enabling cross‑platform applications.

**S: Aspose.GIS for .NET ile farklı GIS dosya formatlarıyla çalışabilir miyim?**  
C: Absolutely! The library supports KML, Shapefile, GeoJSON, and many more formats.

**S: Aspose.GIS mekansal işlemler ve analiz sunuyor mu?**  
C: Yes, it provides a wide range of spatial functions, from buffering to spatial joins.

**S: Ücretsiz deneme sürümü mevcut mu?**  
C: Yes, you can download a free trial from the [Aspose website](https://releases.aspose.com/).

**S: Sorun yaşarsam nereden yardım alabilirim?**  
C: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community and staff support.

### Ek Yaygın Sorular

**S: 3D (Z) koordinatları içeren geometrileri doğrusal hale getirebilir miyim?**  
C: Yes, `ToLinearGeometry()` works with both 2D and 3D geometries; Z values are preserved.

**S: Doğrusal hale getirme dosya boyutunu nasıl etkiler?**  
C: Converting curves to many short line segments can increase file size. Use `Simplify()` after linearization if size is a concern.

**S: Eğrileri çizgilere dönüştürürken segment uzunluğunu kontrol edebilir miyim?**  
C: The default method uses an internal tolerance. For custom segmentation you can manually tessellate curves before calling `ToLinearGeometry()`.

## Sonuç
In this tutorial we covered **how to convert curves to lines** (linearize geometry) using Aspose.GIS for .NET, from setting up the environment to writing the linearized result to a KML file. You can now embed this workflow into mapping applications, data‑processing pipelines, or any GIS‑related project that requires simplified geometries.

---

**Son Güncelleme:** 2026-04-09  
**Test Edilen Versiyon:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
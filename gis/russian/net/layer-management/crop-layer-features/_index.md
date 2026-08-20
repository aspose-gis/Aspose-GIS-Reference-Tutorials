---
date: 2026-07-05
description: Узнайте, как обрезать элементы слоя с помощью Aspose.GIS for .NET, включая
  обрезку растра полигоном, извлечение размера ячейки растра и получение границ растра.
  Скачайте бесплатную пробную версию сейчас.
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: Как обрезать элементы слоя
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to crop layer features with Aspose.GIS for .NET, including
    how to crop raster with polygon, extract raster cell size, and retrieve raster
    extent. Download your free trial now.
  headline: How to Crop Layer Features with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for Aspose.GIS for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find comprehensive documentation for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support
      and community engagement.
    question: How can I seek support or connect with the community for Aspose.GIS
      for .NET?
  - answer: Yes, you can download a free trial [here](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.GIS for .NET?
  - answer: You can purchase the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Как обрезать элементы слоя с помощью Aspose.GIS for .NET
url: /ru/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как обрезать объекты слоя

## Введение
В этом руководстве вы узнаете **how to crop layer** объекты, используя Aspose.GIS для .NET, мощную библиотеку, позволяющую **crop raster with polygon**, **extract raster cell size** и **retrieve raster extent** для точного геопространственного анализа. Независимо от того, готовите ли вы данные для веб‑карты, обрезаете спутниковые изображения или изолируете интересующий регион, это пошаговое руководство покажет, как быстро и надёжно выполнить задачу.

## Быстрые ответы
- **What does “crop layer” mean?** It trims a raster or vector layer to the bounds of a supplied geometry, discarding everything outside.  
- **Which geometry is used in this example?** A polygon defined in WKT (Well‑Known Text) format.  
- **Can I extract cell size after cropping?** Yes – the `CellSize` property returns the width and height of a raster cell.  
- **Do I need a license to run the code?** A temporary license works for evaluation; a full license is required for production use.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Что такое “how to crop layer”?
**Cropping a layer means restricting the dataset to a specific geographic area, discarding everything outside.** This operation reduces file size, speeds up subsequent processing, and focuses analysis on the region you care about. By limiting the data to the area of interest, you also simplify downstream workflows such as styling, analysis, and publishing, while preserving the original coordinate reference system and metadata.

## Почему использовать Aspose.GIS для обрезки?
**Aspose.GIS processes raster files up to 2 GB without loading the entire image into memory and supports more than 30 raster formats, including GeoTIFF, JPEG2000, and PNG.** The library offers a single‑line `Crop` call, automatic CRS handling, and multi‑threaded performance that can trim a 500‑MB GeoTIFF in under a second on a typical server.

## Предварительные требования
Перед тем как приступить к магии геопространственной манипуляции, убедитесь, что у вас есть следующие условия:

- Aspose.GIS for .NET Library: Ensure that you have the Aspose.GIS library installed in your .NET project. You can download it from [here](https://releases.aspose.com/gis/net/).  
- Document Directory: Set up a directory to store your documents. Replace `"Your Document Directory"` in the provided code with the actual path to your document directory.

Now, let's dive into the step‑by‑step guide.

## Импорт пространств имён
The `Aspose.Gis` namespace contains all core types for raster and vector handling. Import it to gain access to the `Layer`, `Geometry`, and related classes.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Как обрезать слой полигоном?
`Crop` is a method of the `Layer` class that extracts a raster subset defined by a geometry.  
Load the source raster, define a polygon geometry, and call the `Crop` method – the entire operation is performed in a single line of code. The method returns a new raster that contains only the pixels inside the polygon, preserving the original spatial reference automatically.

## Шаг 1: Открыть и обрезать слой (crop raster with polygon)
`Layer` represents a raster dataset that can be opened, queried, and edited.  
The `Layer` class represents a raster dataset that can be opened, queried, and edited. Opening a GeoTIFF and cropping it with a polygon isolates the area of interest in just a few statements.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Шаг 2: Получить информацию о растре (extract raster cell size & retrieve raster extent)
`CellSize` provides the width and height of each raster cell in coordinate units.  
`Extent` returns the geographic bounding box of the raster.  
The `CellSize` property provides the width and height of each raster cell in coordinate units, while the `Extent` property returns the geographic bounding box of the cropped raster. Both pieces of information are essential for downstream calculations such as area measurement or re‑projection.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## Шаг 3: Отобразить информацию
Print the extracted information to understand the impact of the cropping process on your geospatial data.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

Repeat these steps as needed to refine and tailor your geospatial data to meet specific project requirements.

## Распространённые проблемы и решения
| Проблема | Решение |
|-------|----------|
| **Incorrect polygon orientation** | Ensure the WKT polygon follows the right‑hand rule (counter‑clockwise for outer rings). |
| **Missing spatial reference** | Verify that the source GeoTiff contains a CRS; otherwise, set one manually before cropping. |
| **Performance slowdown on huge rasters** | Use `layer.Crop` on a down‑sampled copy or process the raster in tiles. |

## Часто задаваемые вопросы
**Q: Доступна ли временная лицензия для Aspose.GIS for .NET?**  
A: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).

**Q: Где можно найти полную документацию по Aspose.GIS for .NET?**  
A: The documentation is available [here](https://reference.aspose.com/gis/net/).

**Q: Как получить поддержку или связаться с сообществом Aspose.GIS for .NET?**  
A: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support and community engagement.

**Q: Можно ли скачать бесплатную пробную версию Aspose.GIS for .NET?**  
A: Yes, you can download a free trial [here](https://releases.aspose.com/).

**Q: Где можно приобрести Aspose.GIS for .NET?**  
A: You can purchase the library [here](https://purchase.aspose.com/buy).

**Q: Можно ли обрезать несколько слоёв за один запуск?**  
A: Yes—loop over each layer and apply the same `Crop` call with the desired geometry.

**Q: Поддерживает ли API другие форматы растра (например, JPEG2000)?**  
A: Aspose.GIS supports all formats exposed by the underlying GDAL drivers, including JPEG2000, PNG, and more.

## Заключение
By following this guide you now know **how to crop layer** features efficiently with Aspose.GIS for .NET. You can easily **crop raster with polygon**, **extract raster cell size**, and **retrieve raster extent** to fit any project’s needs. Explore further APIs for re‑projection, raster styling, and vector analysis to unlock the full potential of your geospatial workflows.

---

**Последнее обновление:** 2026-07-05  
**Тестировано с:** Aspose.GIS 24.10 for .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Как создать полигональную геометрию с Aspose.GIS для .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Получить атрибуты слоя – Информация об атрибутах слоя с Aspose.GIS для .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Создать полигональную геометрию C# и проверить пересечение с Aspose.GIS для .NET](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
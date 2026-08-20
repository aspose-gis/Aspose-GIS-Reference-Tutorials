---
date: 2026-07-05
description: 了解如何使用 Aspose.GIS for .NET 裁剪图层要素，包括如何使用 polygon 裁剪 raster、提取 raster
  cell size，以及检索 raster extent。立即下载免费试用版。
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: 如何裁剪图层要素
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
title: 如何使用 Aspose.GIS for .NET 裁剪图层要素
url: /zh/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何裁剪图层要素

## 介绍
在本教程中，您将学习使用 Aspose.GIS for .NET **裁剪图层** 要素，这是一款强大的库，可让您 **使用多边形裁剪栅格**、**提取栅格单元格大小**，以及 **获取栅格范围**，以进行精确的地理空间分析。无论是为网络地图准备数据、裁剪卫星影像，还是隔离感兴趣区域，本分步指南都将向您展示如何快速且可靠地完成此任务。

## 快速答案
- **“裁剪图层”是什么意思？** 它将栅格或矢量图层裁剪到提供的几何形状的边界，丢弃所有位于外部的内容。  
- **本示例使用哪种几何形状？** 使用 WKT（Well‑Known Text）格式定义的多边形。  
- **裁剪后我可以提取单元格大小吗？** 可以——`CellSize` 属性返回栅格单元格的宽度和高度。  
- **运行代码是否需要许可证？** 临时许可证可用于评估；生产环境需要正式许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 什么是“裁剪图层”？
**裁剪图层是指将数据集限制在特定的地理区域内，丢弃所有位于该区域之外的内容。** 此操作可减小文件大小，加快后续处理速度，并将分析聚焦于您关心的区域。通过将数据限制在感兴趣区域，还能简化后续工作流，如样式设置、分析和发布，同时保留原始坐标参考系统和元数据。

## 为什么使用 Aspose.GIS 进行裁剪？
**Aspose.GIS 能在不将整个图像加载到内存的情况下处理高达 2 GB 的栅格文件，并支持超过 30 种栅格格式，包括 GeoTIFF、JPEG2000 和 PNG。** 该库提供一行代码的 `Crop` 调用、自动坐标参考系统处理以及多线程性能，能够在普通服务器上在一秒钟内裁剪 500 MB 的 GeoTIFF。

## 前置条件
在深入地理空间操作的细节之前，请确保已具备以下前置条件：

- Aspose.GIS for .NET 库：确保已在 .NET 项目中安装 Aspose.GIS 库。您可以从 [here](https://releases.aspose.com/gis/net/) 下载。  
- 文档目录：设置一个目录用于存放文档。将示例代码中的 `"Your Document Directory"` 替换为实际的文档目录路径。

现在，让我们进入分步指南。

## 导入命名空间
`Aspose.Gis` 命名空间包含用于栅格和矢量处理的所有核心类型。导入该命名空间即可访问 `Layer`、`Geometry` 以及相关类。

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## 如何使用多边形裁剪图层？
`Crop` 是 `Layer` 类的一个方法，用于提取由几何形状定义的栅格子集。  
加载源栅格，定义多边形几何形状，然后调用 `Crop` 方法——整个操作只需一行代码。该方法返回一个仅包含多边形内部像素的新栅格，并自动保留原始空间参考。

## 步骤 1：打开并裁剪图层（使用多边形裁剪栅格）
`Layer` 代表一个可打开、查询和编辑的栅格数据集。  
`Layer` 类代表一个可打开、查询和编辑的栅格数据集。打开 GeoTIFF 并使用多边形进行裁剪，只需几行代码即可隔离感兴趣区域。

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## 步骤 2：获取栅格信息（提取栅格单元格大小并获取栅格范围）
`CellSize` 提供每个栅格单元格在坐标单位下的宽度和高度。  
`Extent` 返回栅格的地理边界框。  
`CellSize` 属性提供每个栅格单元格的宽度和高度（坐标单位），而 `Extent` 属性返回裁剪后栅格的地理边界框。这两项信息对于后续计算（如面积测量或再投影）至关重要。

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## 步骤 3：显示信息
打印提取的信息，以了解裁剪过程对地理空间数据的影响。

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

根据需要重复这些步骤，以细化和定制您的地理空间数据，满足特定项目需求。

## 常见问题及解决方案
| 问题 | 解决方案 |
|-------|----------|
| **多边形方向错误** | 确保 WKT 多边形遵循右手规则（外环逆时针）。 |
| **缺少空间参考** | 确认源 GeoTiff 包含坐标参考系统；如果没有，请在裁剪前手动设置。 |
| **大栅格性能下降** | 在下采样的副本上使用 `layer.Crop`，或将栅格分块处理。 |

## 常见问题
**Q: Aspose.GIS for .NET 是否提供临时许可证？**  
A: 是的，您可以在 [here](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

**Q: 在哪里可以找到 Aspose.GIS for .NET 的完整文档？**  
A: 文档可在 [here](https://reference.aspose.com/gis/net/) 查看。

**Q: 如何获取支持或加入 Aspose.GIS for .NET 社区？**  
A: 请访问 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 获取支持并参与社区交流。

**Q: 我可以下载 Aspose.GIS for .NET 的免费试用吗？**  
A: 是的，您可以在 [here](https://releases.aspose.com/) 下载免费试用版。

**Q: 在哪里可以购买 Aspose.GIS for .NET？**  
A: 您可以在 [here](https://purchase.aspose.com/buy) 购买该库。

**Q: 我可以在一次运行中裁剪多个图层吗？**  
A: 可以——遍历每个图层并使用相同的 `Crop` 调用和所需的几何形状。

**Q: API 是否支持其他栅格格式（例如 JPEG2000）？**  
A: Aspose.GIS 支持底层 GDAL 驱动提供的所有格式，包括 JPEG2000、PNG 等。

## 结论
通过本指南，您已经掌握了使用 Aspose.GIS for .NET 高效 **裁剪图层** 要素的方法。您可以轻松 **使用多边形裁剪栅格**、**提取栅格单元格大小**，以及 **获取栅格范围**，以满足任何项目需求。进一步探索再投影、栅格样式和矢量分析等 API，释放地理空间工作流的全部潜力。

---

**最后更新：** 2026-07-05  
**测试环境：** Aspose.GIS 24.10 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [如何使用 Aspose.GIS for .NET 创建多边形几何](/gis/net/geometry-creation/create-polygon-geometry/)
- [获取图层属性 – 使用 Aspose.GIS for .NET 检索图层属性信息](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [使用 C# 创建多边形几何并检查交叉 – Aspose.GIS for .NET](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
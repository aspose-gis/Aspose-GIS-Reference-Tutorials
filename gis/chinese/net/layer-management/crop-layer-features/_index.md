---
date: 2026-01-13
description: 了解如何使用 Aspose.GIS for .NET 裁剪图层要素，包括如何使用多边形裁剪栅格、提取栅格像元大小以及获取栅格范围。立即下载免费试用版。
linktitle: How to Crop Layer Features
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
在本教程中，您将学习使用 Aspose.GIS for .NET **how to crop layer** 要素的强大方法，该方法可让您 **crop raster with polygon**、**extract raster cell size** 和 **retrieve raster extent**，以进行精确的地理空间分析。无论是为网络地图准备数据、裁剪卫星影像，还是隔离感兴趣区域，本分步指南都将准确展示如何完成此任务。

## 快速回答
- **What does “crop layer” mean?** 它将栅格或矢量图层裁剪到提供的几何形状的边界。  
- **Which geometry is used in this example?** 一个以 WKT 格式定义的多边形。  
- **Can I extract cell size after cropping?** 是的 – `CellSize` 属性提供该信息。  
- **Do I need a license to run the code?** 临时许可证可用于评估；生产环境需要正式许可证。  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7。

## 什么是 “how to crop layer”？
裁剪图层是指将数据集限制在特定的地理区域内，丢弃定义形状之外的所有内容。这可以减小文件大小、加快处理速度，并将分析聚焦于您关注的区域。

## 为什么在裁剪时使用 Aspose.GIS？
- **High‑performance raster handling** – 适用于大型 GeoTiff 文件。  
- **Simple API** – 使用任意几何形状的一行 `Crop` 调用。  
- **Full .NET compatibility** – 可在桌面、服务器和云应用中使用。  
- **Accurate spatial reference handling** – 自动保留 CRS 信息。  

## 先决条件
在深入地理空间操作的技巧之前，请确保已具备以下先决条件：

- Aspose.GIS for .NET 库：确保已在 .NET 项目中安装 Aspose.GIS 库。您可以从 [here](https://releases.aspose.com/gis/net/) 下载。  
- 文档目录：设置一个目录用于存放文档。将提供的代码中的 `"Your Document Directory"` 替换为实际的文档目录路径。

现在，让我们深入分步指南。

## 导入命名空间
首先导入必要的命名空间，以充分利用 Aspose.GIS 的强大功能：

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## 步骤 1：打开并裁剪图层（crop raster with polygon）
首先打开 GeoTiff 图层，并根据定义的多边形进行裁剪。这可确保您的地理空间数据被细化到特定的感兴趣区域。

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## 步骤 2：获取栅格信息（extract raster cell size & retrieve raster extent）
图层裁剪完成后，提取栅格数据的关键信息，如单元格大小、空间参考系统和边界。

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
| Issue | Solution |
|-------|----------|
| **Incorrect polygon orientation** | 确保 WKT 多边形遵循右手规则（外环逆时针）。 |
| **Missing spatial reference** | 验证源 GeoTiff 是否包含 CRS；如果没有，请在裁剪前手动设置。 |
| **Performance slowdown on huge rasters** | 对下采样副本使用 `layer.Crop`，或将栅格分块处理。 |

## 常见问题
### Q: Aspose.GIS for .NET 是否提供临时许可证？
A: 是的，您可以在 [here](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

### Q: 在哪里可以找到 Aspose.GIS for .NET 的完整文档？
A: 文档可在 [here](https://reference.aspose.com/gis/net/) 获取。

### Q: 如何获取支持或加入 Aspose.GIS for .NET 社区？
A: 请访问 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 获取支持并参与社区交流。

### Q: 我可以下载 Aspose.GIS for .NET 的免费试用吗？
A: 是的，您可以在 [here](https://releases.aspose.com/) 下载免费试用版。

### Q: 在哪里可以购买 Aspose.GIS for .NET？
A: 您可以在 [here](https://purchase.aspose.com/buy) 购买该库。

### Q: 我可以在一次运行中裁剪多个图层吗？
A: 可以——遍历每个图层，并使用所需的几何形状调用相同的 `Crop`。

### Q: API 是否支持其他栅格格式（例如 JPEG2000）？
A: Aspose.GIS 支持底层 GDAL 驱动所提供的所有格式，包括 JPEG2000、PNG 等。

## 结论
通过本指南，您现在已经掌握了使用 Aspose.GIS for .NET 高效 **how to crop layer** 图层要素的方法。您可以轻松 **crop raster with polygon**、**extract raster cell size** 和 **retrieve raster extent**，以满足任何项目需求。进一步探索重新投影、栅格样式和矢量分析等 API，释放地理空间工作流的全部潜力。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新:** 2026-01-13  
**已测试:** Aspose.GIS 24.10 for .NET  
**作者:** Aspose
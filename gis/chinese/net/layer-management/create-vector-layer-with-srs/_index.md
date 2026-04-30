---
date: 2026-01-15
description: 探索 Aspose.GIS for .NET，创建带空间参考系统的矢量图层。了解如何设置 SRS、创建图层以及管理 GIS 数据。立即下载！
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: 创建带 SRS 的矢量图层
url: /zh/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建带 SRS 的矢量图层

## Introduction
Aspose.GIS for .NET 是一个强大的库，能够帮助开发者 **创建矢量图层** 对象，并在 .NET 应用程序中无缝处理地理信息系统（GIS）数据。在本教程中，我们将逐步演示如何使用空间参考系统（SRS）创建矢量图层，为什么需要设置空间参考，以及这对实际项目带来的好处。阅读完本指南后，您将能够自信地在 .NET 解决方案中集成 GIS 功能。

## Quick Answers
- **本教程的主要目的是什么？** 演示如何使用 Aspose.GIS for .NET 创建带指定 SRS 的矢量图层。  
- **示例中使用的是哪种投影？** 世界墨卡托投影 (EPSG:3395)。  
- **运行代码是否需要许可证？** 开发阶段可以使用免费试用版；生产环境需要商业许可证。  
- **可以将相同方法用于其他 GIS 格式吗？** 可以，SRS 处理同样适用于 Shapefile、GeoJSON、KML 等。  
- **支持哪些 .NET 版本？** .NET Framework 4.5 及以上、.NET Core 3.1 及以上、.NET 5/6/7。

## What is a vector layer and why set its spatial reference?
**矢量图层** 用于存储几何要素（点、线、面）以及属性数据。为其分配 **空间参考**（SRS）可以告诉 GIS 软件如何在地球表面解释这些坐标。正确的 SRS 能确保测量精度、与其他图层的正确叠加以及可靠的地图可视化。

## Prerequisites
在开始之前，请确保您具备以下条件：

- 基本的 C# 与 .NET 开发知识。  
- 已安装 Aspose.GIS for .NET 库。您可以在 **[此处](https://releases.aspose.com/gis/net/)** 下载。  
- 开发环境（Visual Studio、VS Code 或任意 C# IDE）。

## Import Namespaces
确保在 C# 文件顶部引入必要的命名空间：

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## How to set spatial reference (SRS) – Step 1
让我们以世界墨卡托投影为例，创建一个 **投影空间参考系统**，演示如何为图层 **设置 SRS**。

```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```

## How to create layer – Step 2
接下来，我们 **创建矢量图层**（Shapefile），并添加使用刚才定义的 SRS 的要素。此步骤回答了如何使用 Aspose.GIS **创建图层**。

```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // This will throw an exception as the geometry has a different SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```

> **Pro tip:** 在添加要素之前，请始终确认几何体的 `SpatialReferenceSystem` 与图层的 SRS 相匹配。若 SRS 不一致，会抛出 `GisException`，如上所示。

## Verify Spatial Reference System – Step 3
最后，打开图层并确认 SRS 已正确应用。

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

如果 `IsEquivalent` 调用返回 `true`，则说明您已成功 **创建带所需空间参考的矢量图层**。

## Common Issues & Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| `GisException` when adding a feature | Geometry uses a different SRS than the layer | Set `feature.Geometry.SpatialReferenceSystem` to the layer’s SRS before adding |
| Layer appears empty in GIS software | The shapefile was created without a proper `.prj` file | Ensure the `projectedSrs` object is passed when creating the layer |
| Unexpected coordinate values | Wrong projection parameters (e.g., central meridian) | Double‑check the parameters passed to `AddProjectionParameter` |

## FAQs
### Is Aspose.GIS compatible with all GIS file formats?
Aspose.GIS 支持多种 GIS 格式，包括 Shapefile、GeoJSON、KML 等。完整列表请参阅 **[文档](https://reference.aspose.com/gis/net/)**。

### Can I use Aspose.GIS in a web application?
完全可以！Aspose.GIS for .NET 适用于 Web 应用、桌面应用，甚至移动应用。

### Where can I get support for Aspose.GIS?
您可以在 **[Aspose.GIS 论坛](https://forum.aspose.com/c/gis/33)** 找到社区帮助，解答各种疑问和问题。

### Is there a free trial available?
是的，您可以在 **[此处](https://releases.aspose.com/)** 获取免费试用版，体验 Aspose.GIS 的全部功能。

### How can I purchase a license for Aspose.GIS?
购买许可证请访问 **[购买页面](https://purchase.aspose.com/buy)**。

## Frequently Asked Questions (Additional)

**Q: 如果尝试添加一个使用不同 SRS 的几何体会怎样？**  
A: Aspose.GIS 会抛出 `GisException`。您必须重新投影该几何体，或确保其使用与图层相同的 SRS。

**Q: 能否更改已有图层的 SRS？**  
A: 可以。您可以创建一个带期望 SRS 的新图层，然后将要素复制过去，并在需要时进行投影转换。

**Q: 是否支持 3D 坐标？**  
A: Aspose.GIS 支持 Z 坐标，只需使用接受 Z 值的几何体构造函数即可。

**Q: 库会自动处理基准面转换吗？**  
A: 当使用 `Geometry.Transform` 进行投影时，Aspose.GIS 会自动执行必要的基准面平移。

**Q: 官方测试了哪些 .NET 版本？**  
A: 已在 .NET Framework 4.5 及以上、.NET Core 3.1 及以上、以及 .NET 5/6/7 上进行测试。

## Conclusion
您现在已经掌握了如何使用 Aspose.GIS for .NET **创建带自定义空间参考系统的矢量图层**。通过正确设置 SRS、统一几何体处理并验证图层元数据，您可以构建与任何标准 GIS 软件互操作的稳健 GIS 应用程序。

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
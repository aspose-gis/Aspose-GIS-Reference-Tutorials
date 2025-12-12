---
date: 2025-12-12
description: 学习如何使用 Aspose.GIS for .NET 创建矢量图层并添加圆形线几何——构建 GIS 应用程序的快速方法。
linktitle: Create Circular String Geometry
second_title: Aspose.GIS .NET API
title: 在 Aspose.GIS for .NET 中创建矢量图层和圆形字符串
url: /zh/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS for .NET 创建矢量图层和圆形串几何

## Introduction
如果您正在 .NET 平台上构建 GIS 应用程序，第一步通常是 **创建矢量图层** 对象以存储空间要素。Aspose.GIS for .NET 使此过程简便，并让您使用高级几何（如圆形串）来丰富这些图层。在本教程中，您将学习如何创建矢量图层、添加圆形串几何，并将结果保存为 Shapefile——全部使用干净、可用于生产的 C# 代码。

## Quick Answers
- **“创建矢量图层” 是什么意思？** 它创建一个新的容器（图层），可以容纳点、线或多边形等空间要素。  
- **哪个类表示圆形串？** `CircularString` 来自 `Aspose.Gis.Geometries`。  
- **我可以将图层保存为 Shapefile 吗？** 可以——在创建图层时使用 `Drivers.Shapefile`。  
- **开发时需要许可证吗？** 临时许可证可用于评估；生产环境需要正式许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5 及以上、.NET Core 3.1 及以上、.NET 5/6/7。

## What is “create vector layer”?
矢量图层是将矢量要素（点、线、多边形）逻辑分组在单一数据源中的容器。在 Aspose.GIS 中，您通过调用 `VectorLayer.Create` 并传入目标文件路径和所需驱动（例如 Shapefile）来实例化图层。图层创建后，您可以添加要素、分配几何并执行空间操作。

## Why add a circular string?
圆形串是一种 **线性几何**，使用一系列点来近似弧线。它们适用于表示弯曲道路、河流拐弯或任何需要平滑曲线而不使用大量小线段的要素。

## Prerequisites
在开始之前，请确保您已具备：

- **.NET Framework 或 .NET Core** 已在您的机器上安装。  
- **Aspose.GIS for .NET** 库——从官方站点 **[here](https://releases.aspose.com/gis/net/)** 下载。  
- IDE，例如 **Visual Studio** 或 **JetBrains Rider**。  
- 具备 **C#** 编程的基本了解。

## Import Namespaces
Add the required namespaces to your C# file:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step‑by‑Step Guide

### Step 1: Define the output file path
Set the location where the Shapefile will be written.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

Replace `"Your Document Directory"` with the actual folder path on your system.

### Step 2: **Create vector layer**
Open a `VectorLayer` using the `Create` method. This is the core of the **create vector layer** operation.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### Step 3: Construct a new feature
A feature represents a single spatial record inside the layer.

```csharp
    var feature = layer.ConstructFeature();
```

### Step 4: Build the circular string geometry
Add the points that define the curved shape. The sequence of points creates an arc that starts and ends at the same location, forming a closed circular string.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### Step 5: Assign geometry and add the feature to the layer
Link the geometry to the feature and store it in the layer.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

When the `using` block ends, the layer is automatically flushed to the Shapefile on disk.

## Common Issues & Solutions
| Issue | Solution |
|-------|----------|
| **文件路径无效** | 确保目录存在且您具有写入权限。 |
| **CircularString 显示为直线** | 确认点的添加顺序正确；首尾点应相同以形成闭合形状。 |
| **许可证异常** | 在开发期间使用临时许可证，或为生产使用购买正式许可证。 |

## Frequently Asked Questions

### Aspose.GIS for .NET 是否兼容所有 .NET Framework 版本？
是的，Aspose.GIS for .NET 设计用于兼容广泛的 .NET 版本，从 Framework 4.5 到最新的 .NET 8 发布。

### 我可以将 Aspose.GIS for .NET 与其他 GIS 库集成吗？
当然可以！您可以使用其他库读取数据，使用 Aspose.GIS 进行处理，然后再写回，得益于其灵活的 API。

### Aspose.GIS for .NET 是否支持空间数据可视化？
是的，库中包含渲染工具，可生成地图和几何的可视化表示。

### 是否有社区论坛可以寻求 Aspose.GIS for .NET 的帮助？
有，您可以访问 Aspose.GIS 论坛 **[here](https://forum.aspose.com/c/gis/33)** 提问并分享经验。

### 我可以获取临时许可证来评估 Aspose.GIS for .NET 吗？
当然！临时评估许可证可在 **[here](https://purchase.aspose.com/temporary-license/)** 获取。

### 如何向同一图层添加更复杂的几何（例如 MultiLineString）？
创建相应的几何对象（例如 `MultiLineString`），用单独的 `LineString` 对象填充它，将其分配给 `feature.Geometry`，然后像对圆形串那样添加要素。

## Conclusion
通过上述步骤，您现在了解如何使用 Aspose.GIS for .NET **创建矢量图层** 对象并为其添加圆形串几何。这一基础使您能够构建更丰富的 GIS 解决方案——无论是绘制交通网络、可视化环境数据，还是开发自定义空间分析工具。

---

**Last Updated:** 2025-12-12  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
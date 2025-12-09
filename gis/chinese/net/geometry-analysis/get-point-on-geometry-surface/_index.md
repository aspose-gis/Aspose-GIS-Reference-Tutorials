---
date: 2025-12-09
description: 学习如何使用 Aspose.GIS for .NET 检查点是否在多边形内部。一步一步的指南，获取表面上的点，使用 C# 创建多边形，并检索多边形上的点。
linktitle: Check Point Inside Polygon and Get Point on Surface
second_title: Aspose.GIS .NET API
title: 检查点是否在多边形内部并获取表面上的点
url: /zh/net/geometry-analysis/get-point-on-geometry-surface/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 检查点是否在多边形内部并获取表面上的点

## Introduction
在本教程中，您将学习 **如何使用 Aspose.GIS for .NET 检查点是否在多边形内部**，并了解 **如何获取几何体表面上的点**。我们将演示在 C# 中创建多边形，检索位于多边形表面上的点，并验证该点确实位于多边形内部。完成后，您将拥有一个可直接放入任何 .NET 地理空间应用程序的代码片段。

## Quick Answers
- **“检查点是否在多边形内部”是什么意思？** 它用于验证给定坐标是否位于多边形几何的边界之内。  
- **哪个方法返回多边形内部的点？** `GetPointOnSurface()` 返回一个保证位于多边形内部的点。  
- **运行示例是否需要许可证？** 免费试用可用于评估；生产环境需要正式许可证。  
- **支持哪些 .NET 版本？** .NET Framework、.NET Core 和 .NET Standard 均兼容。  
- **实现大约需要多长时间？** 复制、编译并运行大约需要 5‑10 分钟。

## Prerequisites
在开始之前，请确保您具备以下条件：

### Environment Setup
1. 安装 Aspose.GIS for .NET：从 [here](https://releases.aspose.com/gis/net/) 下载并安装 Aspose.GIS for .NET 库。  
2. 设置开发环境：确保您拥有可用于 .NET 编程的工作开发环境。如未安装，可自行搭建 Visual Studio 或其他任意 .NET 开发环境。  
3. C# 基础知识：如果尚未熟悉，请先了解 C# 编程语言的基础。  
4. 获取文档：请随时打开 [documentation](https://reference.aspose.com/gis/net/) 以便在教程中查阅。

## Import Namespaces
导入命名空间

在深入实现之前，让我们先导入必要的命名空间：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

现在我们已经完成环境设置并导入所需的命名空间，下面将示例拆分为多个步骤，以便更好地理解。

## How to Create Polygon C#  
如何在 C# 中创建多边形  
首先，我们需要 **创建一个多边形** 几何体。我们通过指定顶点来定义多边形的外环。

```csharp
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(0, 0),
});
```

## How to Get Point on Surface  
如何获取表面上的点  
接下来，使用 `GetPointOnSurface()` 方法检索多边形表面上的一点。这就是 **获取表面点** 的步骤。

```csharp
IPoint pointOnSurface = polygon.GetPointOnSurface();
```

## How to Check Point Inside Polygon  
如何检查点是否在多边形内部  
我们可以使用 `SpatiallyContains()` 方法验证检索到的点是否位于多边形内部。这演示了 **检索多边形上的点** 并随后进行检查。

```csharp
Console.WriteLine(polygon.SpatiallyContains(pointOnSurface)); // True
```

## Common Issues and Solutions
常见问题及解决方案
- **空多边形** – 确保外环至少有三个不同的顶点；否则 `GetPointOnSurface()` 可能返回未定义的点。  
- **顺时针 vs. 逆时针** – 环的方向不影响包含检查，但保持一致的走向有助于其他空间操作。  
- **坐标系统** – 示例使用简单的笛卡尔平面；在处理真实坐标时，请确保正确定义 CRS（坐标参考系统）。

## Conclusion
结论  
在本教程中，我们学习了如何使用 Aspose.GIS for .NET **检查点是否在多边形内部**，获取 **表面上的点**，并验证其包含关系。借助 Aspose.GIS，处理地理空间数据变得高效且直观，帮助开发者构建稳健的地理空间应用程序。

## FAQ's
常见问答
### Aspose.GIS 是否兼容其他 .NET 框架？
是的，Aspose.GIS 支持多种 .NET 框架，包括 .NET Framework、.NET Core 和 .NET Standard。

### 我可以在购买前试用 Aspose.GIS 吗？
可以，您可以从 [here](https://releases.aspose.com/) 下载 Aspose.GIS 免费试用版。

### 如何获取 Aspose.GIS 的支持？
您可以访问 Aspose.GIS 论坛 [here](https://forum.aspose.com/c/gis/33) 寻求帮助并与其他用户和开发者交流。

### Aspose.GIS 是否提供临时许可证？
是的，您可以从 [here](https://purchase.aspose.com/temporary-license/) 获取 Aspose.GIS 的临时许可证。

### 在哪里可以购买 Aspose.GIS？
您可以在购买页面 [here](https://purchase.aspose.com/buy) 购买 Aspose.GIS。

**Additional Q&A**

**Q:** 处理大型多边形数据集的最佳方式是什么？  
**A:** 懒加载几何体并复用单个 `GeometryFactory` 实例，以降低内存开销。

**Q:** 我可以获取多个表面点吗？  
**A:** `GetPointOnSurface()` 只返回单个内部点。若需生成多个内部点，可在多边形的包围盒内使用随机点生成器，并使用 `SpatiallyContains()` 对每个点进行测试。

**Q:** 创建后能将多边形导出为 shapefile 吗？  
**A:** 可以，Aspose.GIS 提供 `FeatureSet` 和 `ShapefileWriter` 类，可将几何体写入 Shapefile 格式。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

---
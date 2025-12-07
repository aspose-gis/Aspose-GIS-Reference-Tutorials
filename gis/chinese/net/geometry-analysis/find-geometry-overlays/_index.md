---
date: 2025-12-07
description: 学习如何在本空间叠加教程中使用 Aspose.GIS for .NET 执行叠加操作。掌握交集、并集、差集和对称差集。
language: zh
linktitle: Find Geometry Overlays
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 执行叠加操作
url: /net/geometry-analysis/find-geometry-overlays/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS for .NET 执行叠加操作

## 介绍
叠加分析是任何 **空间叠加教程** 的核心技术——它可以将多个地理图层组合、比较并提取洞察。在本指南中，您将学习如何使用功能强大的 Aspose.GIS for .NET 库执行 **叠加** 操作，如 Intersection、Union、Difference 和 Symmetric Difference。完成本教程后，您将能够将这些方法应用于实际 GIS 场景，如土地利用规划、环境影响评估和路径优化。

## 快速答案
- **什么是叠加操作？** 一种空间方法，将两个几何体组合生成新的几何体（交集、并集等）。  
- **哪个库在 .NET 中处理叠加？** Aspose.GIS for .NET。  
- **实现大约需要多长时间？** 基本示例约 10‑15 分钟。  
- **需要许可证吗？** 试用版免费；生产环境需商业许可证。  
- **可以在 .NET Core / .NET 6+ 上运行吗？** 可以——Aspose.GIS 支持所有现代 .NET 运行时。

## 什么是叠加操作？
叠加操作接受两个几何形状，并根据它们的空间关系计算出一个新形状。  
- **Intersection** 返回两个形状的公共区域。  
- **Union** 将两个形状合并为单一几何体。  
- **Difference** 从一个形状中减去另一个形状。  
- **Symmetric Difference** 返回属于任一形状但不同时属于两者的部分。

## 为什么使用 Aspose.GIS 进行叠加？
Aspose.GIS 提供了简洁、完全托管的 API，抽象了底层数学，让您专注于业务逻辑。它跨平台运行，高效处理大数据集，并能无缝集成到其他 .NET 组件中。

## 前置条件
- 一个可用的 .NET 开发环境（Visual Studio、VS Code 或 .NET CLI）。  
- Aspose.GIS for .NET 库——从[官方站点](https://releases.aspose.com/gis/net/)下载最新版本。  

### 导入命名空间
在开始使用 Aspose.GIS for .NET 之前，需要在项目中导入必要的命名空间。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 在 .NET 中执行叠加操作的步骤
下面提供了创建两个多边形并对每种叠加方法进行操作的逐步演示。

### 步骤 1：创建多边形对象
首先，定义两个部分重叠的简单正方形多边形，作为测试数据。

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

### 步骤 2：执行 Intersection 操作
**Intersection** 为我们提供两个多边形的重叠区域。

```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Polygon
```

### 步骤 3：打印 Intersection 点
使用辅助方法 (`PrintRing`) 显示结果多边形的坐标。

```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```

### 步骤 4：执行 Union 操作
**Union** 将两个多边形合并为一个覆盖任一多边形所有区域的形状。

```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Polygon
```

### 步骤 5：打印 Union 点
输出合并后几何体的坐标。

```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```

### 步骤 6：执行 Difference 操作
**Difference** 从 `polygon1` 中减去 `polygon2`，仅保留 `polygon1` 中未与 `polygon2` 相交的部分。

```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Polygon
```

### 步骤 7：打印 Difference 点
显示减法后剩余的顶点。

```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```

### 步骤 8：执行 Symmetric Difference 操作
**Symmetric Difference** 返回属于任一多边形但不同时属于两者的区域。结果为 `MultiPolygon`。

```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // MultiPolygon
```

### 步骤 9：打印 Symmetric Difference 多边形
遍历 `MultiPolygon` 中的每个多边形并打印其点。

```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```

## 常见问题及解决方案
| 问题 | 产生原因 | 解决办法 |
|------|----------|----------|
| `Intersection` 返回 `null` | 多边形实际上并未重叠。 | 检查坐标或在调用 `Intersection` 前使用 `Intersects` 进行检查。 |
| `SymDifference` 产生意外的 `MultiPolygon` | 对称差可能生成不相连的组件。 | 按示例将结果强制转换为 `IMultiPolygon` 并遍历。 |
| 大数据集性能下降 | 每次操作都会从头重新计算几何体。 | 重用中间结果或在叠加前使用 `Simplify()` 简化几何体。 |

## 常见问答

**问：我可以在商业项目中使用 Aspose.GIS for .NET 吗？**  
答：可以，持有有效许可证后，Aspose.GIS for .NET 可用于商业和非商业项目。

**问：是否提供 Aspose.GIS for .NET 的试用版？**  
答：是的，您可以从[此处](https://releases.aspose.com/)下载免费试用版。

**问：如何获取 Aspose.GIS for .NET 的技术支持？**  
答：您可以在 Aspose.GIS 社区论坛[此处](https://forum.aspose.com/c/gis/33)获取支持。

**问：是否有临时许可证可供 Aspose.GIS for .NET 使用？**  
答：有，临时许可证可用于测试和评估。请从[此处](https://purchase.aspose.com/temporary-license/)获取。

**问：我可以直接购买 Aspose.GIS for .NET 吗？**  
答：可以，您可以在网站[此处](https://purchase.aspose.com/buy)直接购买。

---

**最后更新：** 2025-12-07  
**测试环境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
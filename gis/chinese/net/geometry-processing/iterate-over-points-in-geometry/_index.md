---
date: 2026-06-10
description: 了解如何使用 Aspose.GIS for .NET（适用于 .NET 开发者的强大 GIS 工具包）在遍历几何体时添加点并向形状添加坐标。
keywords:
- how to add points
- add coordinates to shape
- Aspose.GIS geometry
linktitle: 如何在 .NET 中添加点并遍历几何体
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  headline: How to Add Points and Iterate Over Geometry in .NET
  type: TechArticle
- description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  name: How to Add Points and Iterate Over Geometry in .NET
  steps:
  - name: Create a `LineString` object
    text: '`LineString` is Aspose.GIS''s geometry type that represents an ordered
      collection of points forming a polyline.'
  - name: Add points to the `LineString`
    text: The `AddPoint` method inserts a new vertex (longitude, latitude) at the
      end of the line. Call it repeatedly to **add coordinates to shape** objects.
  - name: Iterate over the points
    text: '`LineString` implements `IEnumerable<IPoint>`, allowing you to loop through
      each point with a `foreach` statement. This makes extracting X (longitude) and
      Y (latitude) values trivial. The loop prints each point’s X (longitude) and
      Y (latitude) values to the console, allowing you to verify that the p'
  type: HowTo
- questions:
  - answer: '`LineString`'
    question: What is the primary class for point collections?
  - answer: Use `AddPoint(longitude, latitude)`
    question: How do you add a point?
  - answer: Yes, `LineString` implements `IEnumerable<IPoint>`
    question: Can you iterate with a foreach loop?
  - answer: .NET 6+ (or .NET Core 3.1/Framework 4.6+) and Aspose.GIS for .NET library
    question: Prerequisites?
  - answer: Building routes, visualizing tracks, or preprocessing data for spatial
      analysis
    question: Typical use case?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 如何在 .NET 中添加点并遍历几何体
url: /zh/net/geometry-processing/iterate-over-points-in-geometry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 .NET 中添加点并遍历几何体

## 介绍

如果您在 .NET 环境中处理 GIS 数据，首先需要了解的就是 **如何向几何体添加点** 并对这些点进行操作。Aspose.GIS for .NET 提供了简洁的面向对象 API，使此过程变得直观。在本教程中，我们将演示如何创建 `LineString`、向其添加点以及遍历这些点，以便提取坐标或进行进一步分析。您还将看到如何高效地 **向 shape 对象添加坐标**。

## 快速答案
- **点集合的主要类是什么？** `LineString`
- **如何添加点？** 使用 `AddPoint(longitude, latitude)`
- **可以使用 foreach 循环遍历吗？** 可以，`LineString` 实现了 `IEnumerable<IPoint>`
- **前置条件？** .NET 6+（或 .NET Core 3.1/Framework 4.6+）以及 Aspose.GIS for .NET 库
- **典型用例？** 构建路线、可视化轨迹或为空间分析预处理数据  
- **IPoint** 表示具有 X（经度）和 Y（纬度）坐标的单点几何体。

## 在 GIS 中“添加点”是什么意思？

添加点意味着将单个坐标对（经度、纬度）插入到几何容器中，例如 `LineString`、`Polygon` 或 `MultiPoint`。每个点都会成为定义您所建模的形状或路径的顶点，从而支持空间操作和可视化。这些顶点随后可以用于分析、导出为各种 GIS 格式，或在距离测量、交叉测试等空间计算中使用。

## 为什么使用 Aspose.GIS 添加点？

您使用 Aspose.GIS 添加点是因为该库保证 **类型安全的几何处理**，支持 **30 多种矢量和栅格格式**，并且能够在不将整个文件加载到内存的情况下处理 **数百页的数据集**。API 还提供内置的遍历、空间操作以及格式转换（Shapefile、GeoJSON、KML 等）功能，适用于所有受支持的平台。

## 前置条件

- Visual Studio 2022（或任何 C# IDE）  
- 已安装 Aspose.GIS for .NET NuGet 包  
- 对 C# 语法有基本了解  

## 导入命名空间

首先导入必要的命名空间，以便在 .NET 应用程序中使用 Aspose.GIS 功能：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 如何向几何体添加点？

您通过创建 `LineString` 实例、对每个坐标对调用其 `AddPoint` 方法，然后在需要时遍历集合来添加点。这种三步模式以简洁、易读的方式覆盖了创建、填充和遍历。**LineString 是一种几何类型，表示形成折线的有序点集合。** 这种方法确保几何体保持有效，并可用于后续的空间操作，如长度计算或导出。

### 步骤 1：创建 `LineString` 对象  

`LineString` 是 Aspose.GIS 的几何类型，表示形成折线的有序点集合。

```csharp
LineString line = new LineString();
```

### 步骤 2：向 `LineString` 添加点  

`AddPoint` 方法在折线末尾插入一个新的顶点（经度、纬度）。重复调用它即可 **向 shape 对象添加坐标**。

```csharp
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```

### 步骤 3：遍历点  

`LineString` 实现了 `IEnumerable<IPoint>`，可以使用 `foreach` 语句遍历每个点。这使得提取 X（经度）和 Y（纬度）值变得非常简单。

```csharp
foreach (IPoint point in line)
{
    Console.WriteLine(point.X + "," + point.Y);
}
```

循环将每个点的 X（经度）和 Y（纬度）值打印到控制台，以便验证点是否已正确添加。

## 常见使用场景

- **路线规划** – 根据 GPS 日志构建路径，然后分析路点之间的距离。  
- **数据验证** – 遍历点以确保它们位于预期范围内（例如，位于某国边界内）。  
- **可视化** – 将 `LineString` 导出为 GeoJSON 或 Shapefile，以供制图工具使用。

## 常见问题

**Q1：Aspose.GIS for .NET 能处理除 `LineString` 之外的其他几何形状吗？**  
A：可以，Aspose.GIS 支持 `Point`、`Polygon`、`MultiLineString`、`MultiPolygon` 等多种几何类型。

**Q2：Aspose.GIS 适用于商业项目和个人项目吗？**  
A：当然。许可选项覆盖商业、个人和教育使用场景。

**Q3：Aspose.GIS for .NET 为初学者提供全面的文档吗？**  
A：是的，产品包含丰富的文档、API 参考以及数十个代码示例，帮助您快速入门。

**Q4：我可以通过自定义开发扩展 Aspose.GIS for .NET 的功能吗？**  
A：您可以构建扩展方法或封装 Aspose.GIS 类以适配特定工作流，从而完全掌控自定义地理空间解决方案。

**Q5：Aspose.GIS 用户是否提供技术支持？**  
A：通过 Aspose 论坛和工单系统提供专门的技术支持，确保您及时获得帮助。

---

**最后更新：** 2026-06-10  
**测试环境：** Aspose.GIS for .NET 24.5（撰写时的最新版本）  
**作者：** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [如何使用 Aspose.GIS for .NET 统计几何体中的点](/gis/net/geometry-creation/count-points-in-geometry/)
- [如何向 LineString 添加点并将几何体转换为可编辑格式（使用 Aspose.GIS）](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [使用 Aspose.GIS for .NET 创建 MultiPoint 几何体](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
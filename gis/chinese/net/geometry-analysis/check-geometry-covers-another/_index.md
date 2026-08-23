---
date: 2026-08-03
description: 了解如何使用 Aspose.GIS for .NET 创建 linestring c#，向 linestring 添加点，并使用 covers
  方法执行 point on line 检查。
keywords:
- create linestring c#
- point on line check
- add points to linestring
- use covers method
lastmod: 2026-08-03
linktitle: 创建 linestring c# – 检查 geometry 是否覆盖另一个
og_description: 使用 Aspose.GIS covers 方法创建 linestring c# 并验证 point on line。了解针对 .NET
  应用的精确 geometry 检查。（150‑160 字符）
og_image_alt: Developer guide showing linestring creation and covers check in C# with
  Aspose.GIS
og_title: 创建 linestring c# – 检查 geometry 是否覆盖另一个（50‑60 字符）
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  headline: Create linestring c# – Check geometry covers another
  type: TechArticle
- description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  name: Create linestring c# – Check geometry covers another
  steps:
  - name: create a linestring object
    text: The `LineString` class represents a sequence of points connected by straight
      line segments in a two‑dimensional plane. Here, we instantiate a new `LineString`
      object, which represents a sequence of connected line segments in a two‑dimensional
      space.
  - name: add points to linestring
    text: '`AddPoint` appends a coordinate pair to the end of the `LineString` collection,
      preserving the order of insertion. We **add points to linestring** using the
      `AddPoint` method. In this example, we add two points: (0, 0) and (1, 1), forming
      a simple diagonal line segment.'
  - name: create a point object
    text: The `Point` class models a single location in a two‑dimensional coordinate
      system. Instantiate a `Point` object representing a single point in a two‑dimensional
      space. Here, we create a point at coordinates (0, 0).
  - name: perform a point on line check – does the line cover the point?
    text: '`Covers` determines whether the first geometry completely contains the
      second geometry, returning true only when every point of the second geometry
      lies inside the first. Use the `Covers` method to check if the line covers the
      point. In this case, it returns `True` because the point (0, 0) lies exac'
  - name: verify the reverse relationship – is the point covered by the line?
    text: '`CoveredBy` is the inverse of `Covers`; it returns true when the invoking
      geometry is entirely inside the target geometry. Similarly, use the `CoveredBy`
      method to check if the point is covered by the line. Since the point (0, 0)
      lies on the line, it also returns `True`.'
  type: HowTo
- questions:
  - answer: Yes, you can use Aspose.GIS for .NET in both commercial and non‑commercial
      projects after obtaining the appropriate license.
    question: Can I use Aspose.GIS for .NET in my commercial projects?
  - answer: Yes, Aspose.GIS for .NET is compatible with both .NET Framework and .NET
      Core environments.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Yes, Aspose.GIS for .NET supports a wide range of GIS formats including
      Shapefile, GeoJSON, KML, and more.
    question: Does Aspose.GIS for .NET support various GIS formats?
  - answer: Aspose.GIS for .NET is a proprietary library developed by Aspose, so external
      contributions are not accepted. However, you can provide feedback and suggestions
      to improve the library.
    question: Can I contribute to the development of Aspose.GIS for .NET?
  - answer: Updates for Aspose.GIS for .NET are released regularly to introduce new
      features, enhancements, and bug fixes. Check the [website](https://releases.aspose.com/gis/net/)
      for the latest releases.
    question: How often are updates released for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create linestring
- Aspose.GIS
- C# geometry analysis
title: 创建 linestring c# – 检查 geometry 是否覆盖另一个
url: /zh/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 检查几何体是否覆盖另一个

## 介绍
在本教程中，您将学习使用 Aspose.GIS for .NET **创建 linestring c#**，向 linestring 添加点，并使用 `Covers` 和 `CoveredBy` 方法执行可靠的 **点在线检查**。无论您是构建制图工具、进行空间分析，还是仅需验证几何关系，掌握这些操作都能为您的应用提供所需的精确度。

## 快速答案
- **“create linestring c#” 是什么意思？** 它指的是实例化一个 `LineString` 几何对象并用坐标点填充它。  
- **哪个方法检查点是否位于线上？** 在 `LineString` 上使用 `Covers` 方法，或在 `Point` 上使用 `CoveredBy` 方法。  
- **运行示例是否需要许可证？** 临时许可证可用于评估；生产环境需要正式许可证。  
- **可以在 .NET Core 中使用吗？** 可以，Aspose.GIS 支持 .NET Framework 和 .NET Core。  
- **可以向 linestring 添加多少点？** 没有硬性限制，您可以根据空间分析的需要添加任意数量的点。  

## 什么是 create linestring c#？
`LineString` 是一种几何形状，由按顺序连接的点组成，点之间通过直线段相连。在 C# 中，您可以通过实例化 `Aspose.Gis.Geometries` 命名空间中的 `LineString` 类来创建它，然后使用 `AddPoint` 方法 **向 linestring 添加点**。该对象是任何线性空间分析的基础，例如路径映射或网络追踪。

## 为什么在点在线检查中使用 Aspose.GIS？
`Covers` 是一种空间谓词方法，当第一个几何体完全包含第二个几何体时返回 true。  
Aspose.GIS 提供确定性、高精度的空间谓词实现。它支持 50 多种输入和输出 GIS 格式，能够在不将整个数据集加载到内存的情况下处理数百公里的线网，并可在 .NET Framework、.NET Core 和 .NET 5/6+ 上运行。使用其 `Covers` 方法可确保考虑浮点舍入误差，即使在高要求的企业场景中也能提供可靠的点在线结果。

## 前提条件
在深入使用 Aspose.GIS for .NET 之前，请确保已完成以下前提条件的设置：

### 1. 安装 Visual Studio
确保您的系统已安装 Visual Studio。Aspose.GIS for .NET 可无缝集成到 Visual Studio 中，提供流畅的开发体验。

### 2. 获取 Aspose.GIS for .NET
从[网站](https://releases.aspose.com/gis/net/)下载 Aspose.GIS for .NET 库。您可以直接下载库文件，或使用 NuGet 等包管理器将其安装到项目中。

### 3. 熟悉 .NET Framework
熟悉 .NET 框架和 C# 编程语言的基础知识对于有效使用 Aspose.GIS for .NET 至关重要。

### 4. 访问文档和支持
请参考[文档](https://reference.aspose.com/gis/net/)获取关于 Aspose.GIS API 和功能的详细信息。如遇问题或有疑问，可在[Aspose.GIS 论坛](https://forum.aspose.com/c/gis/33)寻求帮助。

### 5. 可选：临时许可证
如果您正在尝试 Aspose.GIS for .NET，可以从[临时许可证页面](https://purchase.aspose.com/temporary-license/)获取临时许可证，以评估库的功能。

## 导入命名空间
在项目中使用 Aspose.GIS for .NET 之前，需要导入必要的命名空间：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

现在，让我们将示例拆分为多个步骤，以了解如何使用 Aspose.GIS for .NET **检查一个几何体是否覆盖另一个几何体**。

## 如何创建 linestring c# – 分步指南
加载项目，导入所需的命名空间，然后按照以下五个简明步骤操作。仅需几行代码，即可得到一个 `LineString` 对象、一个 `Point` 对象，以及两个布尔检查，分别指示线是否覆盖点以及点是否被线覆盖。

### 步骤 1：创建 linestring 对象
`LineString` 类表示二维平面上由直线段连接的点序列。  
```csharp
var line = new LineString();
```
这里，我们实例化一个新的 `LineString` 对象，表示二维空间中一系列相连的线段。

### 步骤 2：向 linestring 添加点
`AddPoint` 将坐标对追加到 `LineString` 集合的末尾，保持插入顺序。  
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
我们使用 `AddPoint` 方法 **向 linestring 添加点**。在本例中，添加了两个点：(0, 0) 和 (1, 1)，形成一条简单的对角线段。

### 步骤 3：创建 point 对象
`Point` 类表示二维坐标系中的单个位置。  
```csharp
var point = new Point(0, 0);
```
实例化一个 `Point` 对象，表示二维空间中的单个点。这里，我们在坐标 (0, 0) 处创建一个点。

### 步骤 4：执行点在线检查 – 线是否覆盖点？
`Covers` 判断第一个几何体是否完全包含第二个几何体，仅当第二个几何体的每个点都位于第一个几何体内部时返回 true。  
```csharp
Console.WriteLine(line.Covers(point));    // True
```
使用 `Covers` 方法检查线是否覆盖点。在本例中返回 `True`，因为点 (0, 0) 正好位于线段上。

### 步骤 5：验证反向关系 – 点是否被线覆盖？
`CoveredBy` 是 `Covers` 的逆操作；当调用几何体完全位于目标几何体内部时返回 true。  
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
同样，使用 `CoveredBy` 方法检查点是否被线覆盖。由于点 (0, 0) 位于线段上，亦返回 `True`。

## 常见问题及解决方案
| 问题 | 产生原因 | 解决方案 |
|-------|----------------|-----|
| `line.Covers(point)` 返回 `False`，即使点看起来在直线上 | 由于浮点精度，点坐标并不完全相同。 | 对坐标使用 `Math.Round`，或使用基于容差的检查，例如 `line.Distance(point) < epsilon`。 |
| 缺少 `using Aspose.Gis.Geometries;` | 未导入命名空间，导致编译错误。 | 确保已包含导入语句（参见 **导入命名空间** 部分）。 |
| 运行时许可证异常 | 生产环境未加载有效许可证。 | 使用 `License license = new License(); license.SetLicense("Aspose.GIS.lic");` 加载临时或正式许可证。 |

## 常见问题

**问：我可以在商业项目中使用 Aspose.GIS for .NET 吗？**  
答：可以，在获取相应许可证后，您可以在商业和非商业项目中使用 Aspose.GIS for .NET。

**问：Aspose.GIS for .NET 是否兼容 .NET Core？**  
答：是的，Aspose.GIS for .NET 兼容 .NET Framework 和 .NET Core 环境。

**问：Aspose.GIS for .NET 是否支持多种 GIS 格式？**  
答：是的，Aspose.GIS for .NET 支持包括 Shapefile、GeoJSON、KML 等在内的多种 GIS 格式。

**问：我可以为 Aspose.GIS for .NET 的开发做贡献吗？**  
答：Aspose.GIS for .NET 是 Aspose 开发的专有库，不接受外部贡献。但您可以提供反馈和建议，以帮助改进该库。

**问：Aspose.GIS for .NET 的更新频率如何？**  
答：Aspose.GIS for .NET 会定期发布更新，包含新功能、改进和错误修复。请访问[网站](https://releases.aspose.com/gis/net/)获取最新版本。

## 结论
通过上述步骤，您现在已经掌握了如何 **创建 linestring c#**、**向 linestring 添加点**，以及使用 `Covers` 和 `CoveredBy` 方法执行可靠的 **点在线检查**。此功能提升了软件的空间分析能力，并为更高级的 GIS 操作打开了大门，例如路线验证、网络拓扑检查和邻近查询。

---

**Last Updated:** 2026-08-03  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [了解如何使用 Aspose.GIS for .NET 创建 LineString 几何体](/gis/net/geometry-creation/create-linestring-geometry/)
- [如何向 LineString 添加点并使用 Aspose.GIS 将几何体转换为可编辑格式](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [point inside polygon c# – 检查几何体是否包含另一个](/gis/net/geometry-analysis/check-geometry-contains-another/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
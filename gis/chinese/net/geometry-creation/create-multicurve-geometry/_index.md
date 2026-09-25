---
date: 2026-09-25
description: 了解如何使用 Aspose.GIS 在 .NET 中将 WKT 转换为 compound curve geometry 并添加 line
  string。本指南展示了使用 MultiCurve 从 WKT 创建几何。
keywords:
- compound curve geometry
- geometry from wkt
- add line string .net
lastmod: 2026-09-25
linktitle: 创建 MultiCurve Geometry
og_description: 了解如何使用 Aspose.GIS 在 .NET 中将 WKT 转换为 compound curve geometry 并添加 line
  string。本指南展示了使用 MultiCurve 从 WKT 创建几何。
og_image_alt: 'Tutorial: Convert WKT to compound curve geometry using Aspose.GIS in
  .NET'
og_title: 使用 Aspose.GIS for .NET 将 WKT 转换为 compound curve geometry
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  headline: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  name: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  steps:
  - name: Define the document directory and file name
    text: Set the folder where the shapefile will be saved. Replace `"Your Document
      Directory"` with the actual path on your machine.
  - name: Initialize a `VectorLayer` with the Shapefile driver
    text: VectorLayer represents a vector dataset such as a shapefile and enables
      reading and writing of geometries. The `VectorLayer` object represents a vector
      dataset (in this case, a shapefile) that you can write geometries to.
  - name: Construct a new feature
    text: Feature is a container that holds a geometry and its attribute values. A
      feature is a container for geometry and attribute data.
  - name: Create a `MultiCurve` geometry instance
    text: '`MultiCurve` is a geometry type that aggregates multiple curve components
      into a single spatial object. `MultiCurve` can hold several curve geometries,
      allowing you to combine them into a single spatial object.'
  - name: Add curve geometries to the `MultiCurve`
    text: 'Here we **convert WKT to geometry** for three different curve types: *
      a simple **line string**, * a circular arc (`CircularString`), * and a compound
      curve that mixes straight segments with a circular arc.'
  - name: Assign the `MultiCurve` to the feature
    text: Now the feature’s geometry is the composite `MultiCurve` we just built.
  - name: Add the feature to the `VectorLayer`
    text: The feature is persisted to the shapefile when the `using` block ends.
  type: HowTo
- questions:
  - answer: Yes, it supports .NET Framework, .NET Core, .NET Standard, and .NET 5/6+.
    question: Is Aspose.GIS for .NET compatible with all versions of the .NET Framework?
  - answer: Absolutely. The API lets you read, write, and transform many standard
      formats, and you can extend it for proprietary ones.
    question: Can I create custom spatial data formats using Aspose.GIS for .NET?
  - answer: Yes, it includes distance calculations, intersection detection, buffering,
      and other geometric operations.
    question: Does Aspose.GIS provide spatial analysis capabilities?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/)
      to explore its features before purchasing.
    question: Is there a trial version available for Aspose.GIS for .NET?
  - answer: Reach out via the Aspose.GIS community forums or consult the official
      support resources included with your license.
    question: How can I get help if I encounter problems?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- compound curve geometry
- Aspose.GIS
- C# GIS
- MultiCurve
- WKT conversion
title: 使用 Aspose.GIS for .NET 将 WKT 转换为 compound curve geometry
url: /zh/net/geometry-creation/create-multicurve-geometry/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将 WKT 转换为复合曲线几何（使用 Aspose.GIS for .NET）

## 介绍
如果您需要在 .NET GIS 应用程序中**将 WKT 转换为复合曲线几何**，Aspose.GIS 可以让整个过程平稳可靠。在本教程中，我们将演示如何从 Well‑Known Text（WKT）字符串创建 `MultiCurve` 几何——这非常适合需要向单个要素添加**线串**组件、圆弧或复合曲线的场景。完成后，您将拥有一个可直接使用的 shapefile，展示如何将多个曲线几何合并为一个 `MultiCurve` 对象。

## 快速答案
- **什么是“convert WKT to geometry”？** 这意味着将文本形式的 WKT 表示转换为 GIS 库可以操作的具体几何对象。  
- **哪个 Aspose.GIS 类处理 WKT？** `Geometry.FromText()` 可将 WKT 字符串解析为几何实例。  
- **我可以添加简单的线串吗？** 可以——只需在 WKT 中包含类似 `"LineString (0 0, 1 0)"` 的 `LineString`。  
- **示例中使用的文件格式是什么？** 使用 Shapefile 驱动创建的 Shapefile（`.shp`）。  
- **开发时需要许可证吗？** 免费试用可用于测试；生产环境需要商业许可证。

## 什么是“convert WKT to geometry”？
将 WKT 转换为几何即将文本的 Well‑Known Text 格式解析为内存中的对象模型，如 `MultiCurve` 或 `LineString`。**`Geometry.FromText`** 能即时创建这些对象，使您能够使用任何支持 OGC 标准的 GIS 工具存储、查询和渲染它们。

## 为什么使用 Aspose.GIS 创建 MultiCurve？
Aspose.GIS 让您能够在一次 API 调用中创建**复合曲线几何**。它支持三种高级曲线类型（CircularString、CompoundCurve 和 CurveString），并且在批处理场景下可在不将整个文件加载到内存的情况下处理高达 500 MB 的数据集，速度提升约 30 %。

## 前置条件
1. 对 C# 编程语言有基本了解。  
2. 已安装 Visual Studio（或其他 .NET IDE）。  
3. Aspose.GIS for .NET 库——请从 [Aspose.GIS website](https://releases.aspose.com/gis/net/) 下载。  
4. 熟悉空间概念，如点、线和曲线。

## 导入命名空间
要开始使用 Aspose.GIS for .NET，请在 C# 项目中导入所需的命名空间。

`Geometry` 提供将 WKT 解析为几何对象的静态方法。  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

这些命名空间让您能够访问创建和管理 `MultiCurve` 几何所需的类。

## 步骤指南

### 步骤 1：定义文档目录和文件名
设置保存 shapefile 的文件夹。将 `"Your Document Directory"` 替换为您机器上的实际路径。

### 步骤 2：使用 Shapefile 驱动初始化 `VectorLayer`
`VectorLayer` 表示诸如 shapefile 的矢量数据集，并支持几何的读取和写入。  
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block goes here
}
```
`VectorLayer` 对象代表一个矢量数据集（此处为 shapefile），您可以向其中写入几何。

### 步骤 3：构建新要素
`Feature` 是一个容器，用于保存几何及其属性值。  
```csharp
var feature = layer.ConstructFeature();
```
要素是几何和属性数据的容器。

### 步骤 4：创建 `MultiCurve` 几何实例
`MultiCurve` 是一种将多个曲线组件聚合为单一空间对象的几何类型。  
```csharp
var multiCurve = new MultiCurve();
```
`MultiCurve` 可以容纳多个曲线几何，便于将它们合并为一个空间对象。

### 步骤 5：向 `MultiCurve` 添加曲线几何
这里我们为三种不同的曲线类型**将 WKT 转换为几何**：
* 一个简单的 **line string**，  
* 一个圆弧（`CircularString`），  
* 以及一个将直线段与圆弧混合的复合曲线。  
```csharp
multiCurve.Add(Geometry.FromText("LineString (0 0, 1 0)"));
multiCurve.Add(Geometry.FromText("CircularString (2 2, 3 3, 4 2)"));
multiCurve.Add(Geometry.FromText("CompoundCurve ((0 1, 0 0), CircularString (0 0, 3 3, 6 0))"));
```

### 步骤 6：将 `MultiCurve` 分配给要素
现在要素的几何就是我们刚构建的复合 `MultiCurve`。  
```csharp
feature.Geometry = multiCurve;
```

### 步骤 7：将要素添加到 `VectorLayer`
当 `using` 块结束时，要素会被持久化到 shapefile 中。  
```csharp
layer.Add(feature);
```

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| **`ArgumentException` on `Geometry.FromText`** | 无效的 WKT 语法 | 验证 WKT 字符串符合 OGC 规范（例如，坐标之间使用逗号，括号正确）。 |
| **Shapefile not created** | `path` 不正确或缺少写入权限 | 确保目录存在且应用程序具有写入权限。 |
| **Curves appear as straight lines in some viewers** | 查看器不支持圆弧/复合曲线 | 使用能够识别 `ARC` 几何类型的 GIS 查看器（例如 QGIS）。 |

## 常见问题

**Q: Aspose.GIS for .NET 是否兼容所有版本的 .NET Framework？**  
A: 是的，它支持 .NET Framework、.NET Core、.NET Standard 以及 .NET 5/6+。

**Q: 我可以使用 Aspose.GIS for .NET 创建自定义空间数据格式吗？**  
A: 当然。该 API 允许您读取、写入和转换多种标准格式，并可扩展以支持专有格式。

**Q: Aspose.GIS 提供空间分析功能吗？**  
A: 提供，包括距离计算、相交检测、缓冲区生成以及其他几何操作。

**Q: 是否有 Aspose.GIS for .NET 的试用版？**  
A: 有，您可以从 [Aspose.GIS website](https://releases.aspose.com/gis/net/) 下载免费试用版，以在购买前体验其功能。

**Q: 遇到问题时如何获取帮助？**  
A: 可通过 Aspose.GIS 社区论坛寻求帮助，或查阅随许可证提供的官方支持资源。

**最后更新：** 2026-09-25  
**测试环境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose

## 相关教程

- [创建复合曲线几何](/gis/net/geometry-creation/create-compound-curve-geometry/)
- [使用 Aspose.GIS for .NET 从 WKT 计数点](/gis/net/geometry-processing/translate-geometry-from-wkt/)
- [使用 Aspose.GIS for .NET 创建 MultiLineString 几何](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
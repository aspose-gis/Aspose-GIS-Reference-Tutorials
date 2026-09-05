---
date: 2026-09-05
description: 了解如何使用 Aspose.GIS for .NET 创建带孔的多边形内部环。本指南展示了如何向多边形添加孔并处理数据。
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: 创建带孔的 Polygon 几何
og_description: 了解如何使用 Aspose.GIS for .NET 创建带孔的多边形内部环。本指南展示了如何向多边形添加孔并处理数据。
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: 使用 Aspose.GIS 在 .NET 中创建带孔的多边形内部环
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: 使用 Aspose.GIS 在 .NET 中创建带孔的多边形内部环
url: /zh/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS 创建带孔的多边形内部环

## 简介
在本教程中，您将学习如何使用 Aspose.GIS for .NET **create a polygon interior ring**，即在多边形中包含一个孔。无论您是构建地图应用、进行空间分析，还是为 GIS 服务准备数据，在多边形内部嵌入孔都是一项核心技能。我们将完整演示工作流程——从设置开发环境到生成可保存为任何受支持的地理空间格式的有效多边形对象。

## 快速答案
- **“create polygon with hole” 是什么意思？** 它指的是构建一个包含一个或多个内部环（孔）的多边形，这些孔的面积会被排除在外。  
- **哪个库处理此功能？** Aspose.GIS for .NET 提供对外环和内环的完整支持。  
- **我需要许可证吗？** 免费试用可用于开发；生产环境需要商业许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **需要多长时间？** 通常在 10 分钟以内即可实现并测试。

## 如何使用 Aspose.GIS 为多边形添加孔
加载 GIS 环境，定义外环，然后附加一个或多个内环。Aspose.GIS 会自动调整环的方向并验证几何形状，让您专注于表示空洞的坐标。

## 什么是多边形内部环？
**polygon interior ring** 是一个内部边界，用于从多边形的外部形状中减去面积。  
您可以通过定义一系列闭合的点来创建它，Aspose.GIS 将其视为孔，在计算面积或渲染形状时会被排除。

## 为什么使用 Aspose.GIS 创建多边形内部环？
Aspose.GIS 能在 5 毫秒以内为典型的 200 点多边形验证并纠正环的方向，省去自定义验证代码的需求。它还支持 **30+ 地理空间文件格式**（Shapefile、GeoJSON、GML、KML 等），并且能够在不将整个文件加载到内存的情况下处理多达 10,000 点的多边形，为您提供速度和可扩展性。

## 带孔多边形的真实场景
1. **内部有湖泊的土地块** – 将湖泊建模为孔，以便不计入土地块的面积。  
2. **带庭院的建筑足迹** – 庭院被排除在建筑足迹之外。  
3. **大型保护区内的受保护区域** – 您可以在不创建单独图层的情况下排除受限区域。

## 先决条件
在开始之前，请确保您具备以下先决条件：
1. Aspose.GIS for .NET 库：您可以从 **Aspose.GIS for .NET 下载页面**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)) 下载。  
2. 开发环境：确保已安装 Visual Studio 或其他 .NET IDE 并完成开发环境的配置。

## 导入命名空间
`Aspose.Gis` 命名空间包含您需要的所有几何类型，包括 `Polygon`、`LinearRing` 以及用于验证的辅助方法。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

现在，让我们继续使用 Aspose.GIS for .NET 创建带孔的多边形几何。

## 步骤 1：创建多边形对象
`Polygon` 是 Aspose.GIS 的几何类型，表示具有可选内部环的平面多边形。我们首先实例化一个空的 `Polygon` 对象，稍后将用于保存外环和内环。

```csharp
Polygon polygon = new Polygon();
```

## 步骤 2：定义外环
`LinearRing` 是用于外部和内部边界的类。外环定义多边形的外部边界。按顺时针顺序添加点以形成闭合形状。

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## 步骤 3：定义内部环（孔）
`LinearRing` 也用于表示内部环。内部环即 **孔**，在多边形面积中被排除。点通常按逆时针顺序添加，但 Aspose.GIS 会自动处理方向。

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## 步骤 4：分配外环并向多边形添加内部环
`AddInteriorRing` 方法将一个或多个内部环附加到 `Polygon`。在设置 `ExteriorRing` 属性后调用它；您可以多次调用以添加多个孔。

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## 提示与最佳实践
- **方向影响可读性** – 虽然 Aspose.GIS 会自动纠正方向，但将外环保持顺时针、内环保持逆时针可使几何在 GIS 查看器中更易检查。  
- **闭合每个环** – 始终将第一个坐标重复为最后一点，以确保形成有效的闭合形状。  
- **创建后进行验证** – 您可以调用 `polygon.IsValid` 来确保几何符合 OGC 标准后再保存。

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| GIS 查看器中未显示孔 | 内环方向相反 | 确保点的添加方向与外环相反（逆时针）。 |
| 多边形无效错误 | 环未闭合（首点 ≠ 末点） | 在每个环中将首点重复为末点（如上所示）。 |
| 意外的空几何 | 在添加内环之前忘记分配 `ExteriorRing` | 首先设置 `polygon.ExteriorRing`，然后调用 `AddInteriorRing`。 |

## 常见问题
### 1. 什么是 Aspose.GIS？
Aspose.GIS 是一个 .NET 库，使开发人员能够处理地理空间数据，能够创建、读取和操作各种地理空间文件格式。

### 2. 我可以在商业项目中使用 Aspose.GIS 吗？
是的，您可以通过购买许可证在个人和商业项目中使用 Aspose.GIS。访问 **Aspose.GIS 购买页面**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)) 获取更多详情。

### 3. Aspose.GIS 是否提供免费试用？
是的，您可以从 **Aspose.GIS 免费试用下载页面**([https://releases.aspose.com/](https://releases.aspose.com/)) 获取 Aspose.GIS 的免费试用。

### 4. 我在哪里可以找到 Aspose.GIS 的支持？
您可以在 [Aspose.GIS 论坛](https://forum.aspose.com/c/gis/33) 上找到 Aspose.GIS 的支持。

### 5. 我如何获取 Aspose.GIS 的临时许可证？
您可以从 **Aspose.GIS 临时许可证页面**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)) 获取 Aspose.GIS 的临时许可证。

---

**最后更新：** 2026-09-05  
**测试环境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose

## 相关教程

- [如何使用 Aspose.GIS for .NET 创建多边形几何](/gis/net/geometry-creation/create-polygon-geometry/)
- [学习如何使用 Aspose.GIS 创建 MultiPolygon 几何](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [使用 Aspose.GIS for .NET 将多边形转换为线](/gis/net/geometry-processing/replace-polygons-with-lines/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
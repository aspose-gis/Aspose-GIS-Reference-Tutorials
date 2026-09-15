---
date: 2026-09-15
description: 了解如何在使用 Aspose.GIS for .NET 的 C# 中创建点几何时，分配 coordinate system、设置 WKT
  variant 并控制 decimal precision。
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: 在翻译时指定 WKT Variant
og_description: 了解如何在使用 Aspose.GIS for .NET 的 C# 中创建点几何时，分配 coordinate system、设置 WKT
  variant 并控制 decimal precision。
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: 使用 Aspose.GIS 分配 coordinate system，设置 WKT variant
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: 使用 Aspose.GIS 分配 coordinate system，设置 WKT variant
url: /zh/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 分配坐标系统，使用 Aspose.GIS 设置 WKT 变体

## 介绍
在本教程中，您将学习如何 **assign coordinate system**，选择正确的 WKT 变体，并在使用 C# 的 Aspose.GIS for .NET **create point geometry** 时控制小数精度。无论您是构建地图服务、执行空间分析，还是在 GIS 平台之间交换数据，这些设置都能确保您的输出既可互操作，又易于阅读。让我们一步一步地完成整个过程。

## 快速答案
- **What does “assign coordinate system” mean?** 它将几何对象绑定到特定的坐标参考系统，例如 WGS‑84。  
- **Which WKT variants are supported?** Iso、SimpleFeatureAccessOutdated 和 ExtendedPostGis。  
- **How can I control decimal precision?** 使用 `NumericFormat` 枚举（`General`、`RoundTrip`、`Flat`）。  
- **Do I need a license for Aspose.GIS?** 提供免费试用；生产环境需要商业许可证。  
- **What .NET versions are compatible?** .NET Framework 4.0+ 和 .NET Core/5/6+。

## 什么是 “assign coordinate system”？
为几何对象分配空间参考（或空间参考系统，SRS）告诉 GIS 软件如何解释几何的坐标值，将这些数字与诸如 WGS‑84 的真实世界坐标系统关联起来。如果没有 SRS，点的纬度‑经度数值将没有实际意义。

## 为什么要控制 WKT 变体和数值格式？
超过 30 种 GIS 工具要求特定的 WKT 语法，因此选择正确的变体可以避免导入错误。设置数值格式可以减少四舍五入噪声并保持输出简洁，这在日志或文件被程序化解析时尤为重要。

## 先决条件
1. Aspose.GIS for .NET – 从 [download page](https://releases.aspose.com/gis/net/) 下载。  
2. .NET 开发环境（Visual Studio、VS Code 或 Rider）。  
3. 熟悉 C# 和 .NET 框架的基础知识。

## 导入命名空间
在使用任何 Aspose.GIS 类之前，导入所需的命名空间：

```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```

## 如何为点分配坐标系统？
加载一个 `Point` 实例，然后使用 `SpatialReference` 类附加空间参考系统（SRS）。这种两步模式确保几何在导出时携带坐标系统元数据，使下游工具能够正确解释坐标。`Point` 类表示由 X（经度）和 Y（纬度）坐标定义的单一点位置。

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## 步骤 2：分配空间参考系统 (SRS)
现在我们 **assign spatial reference** 到该点。`SpatialReference` 表示由 SRID 标识的坐标参考系统。这里我们使用广泛支持的 WGS‑84 系统（SRID 4326）：

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## 步骤 3：指定所需的 WKT 变体
选择与下游应用匹配的 WKT 变体：

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## 如何设置 WKT 输出的小数精度？
使用 `NumericFormat` 枚举控制最终字符串中出现的数字位数，该枚举定义了 `General`、`RoundTrip` 或 `Flat` 等格式规则。选择 `RoundTrip` 可在往返传输场景中保留完整的坐标精度，而 `General` 则提供适用于大多数可视化任务的简洁表示。`NumericFormat` 枚举决定了坐标数字在 WKT 输出中的格式化方式。

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### 常见陷阱与技巧
- **Pitfall:** 在调用 `AsText` 之前忘记设置 SRS 可能导致缺少 SRID 信息。  
- **Tip:** 当需要无损的坐标往返时使用 `NumericFormat.RoundTrip`。  
- **Tip:** `Iso` 变体是最通用的；仅在需要嵌入 SRID 时才选择 `ExtendedPostGis`。

## 结论
现在您已经了解如何 **assign coordinate system**，选择合适的 WKT 变体，以及在使用 Aspose.GIS **create point geometry** 时 **set decimal precision**。这些控制让您能够灵活满足任何 GIS 工作流的精确需求，从简单的可视化到高精度空间分析。

## 常见问题

**Q:** Aspose.GIS 是否兼容所有 .NET 版本？  
**A:** 是的，Aspose.GIS 支持 .NET Framework 4.0 及更高版本，以及 .NET Core/5/6。

**Q:** 我可以在商业项目中使用 Aspose.GIS 吗？  
**A:** 当然可以。生产使用需要商业许可证，但提供免费试用供评估。

**Q:** Aspose.GIS 是否支持其他空间数据格式？  
**A:** 是的，它支持 30 多种格式，包括 ESRI Shapefile、GeoJSON、KML、CSV 等。

**Q:** 我在哪里可以下载免费试用版？  
**A:** 您可以从 [Aspose.GIS free trial download page](https://releases.aspose.com/) 下载 Aspose.GIS 的免费试用版。

**Q:** 如果遇到问题，我该如何获取帮助？  
**A:** 在 Aspose.GIS 社区的 [forum](https://forum.aspose.com/c/gis/33) 发帖提问，Aspose 员工和社区成员都会提供帮助。

---

**最后更新:** 2026-09-15  
**测试环境:** Aspose.GIS for .NET (latest release)  
**作者:** Aspose

## 相关教程

- [创建矢量图层并设置其空间参考系统](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [如何使用 Aspose.GIS for .NET 将几何转换为 WKT](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [如何使用 Aspose.GIS 限制写入几何的精度](/gis/net/geometry-processing/limit-precision-writing-geometries/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
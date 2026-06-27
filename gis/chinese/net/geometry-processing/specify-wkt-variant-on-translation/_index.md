---
date: 2026-04-09
description: 学习在 .NET 应用程序中使用 Aspose.GIS for .NET 用 C# 创建点时，如何分配空间参考并设置小数精度。
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: 在翻译时指定 WKT 变体
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS 分配空间参考并设置 WKT 变体
url: /zh/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 分配空间参考并使用 Aspose.GIS 设置 WKT 变体

## 介绍
在本教程中，您将学习如何使用 Aspose.GIS for .NET **分配空间参考** 给几何对象，并控制精确的 WKT 输出格式。无论您是需要为制图、分析或数据交换 **创建 point C#** 对象，能够选择合适的 WKT 变体和数值精度都能使您的空间数据具有互操作性且易于阅读。让我们一步一步地完成此过程。

## 快速答案
- **“assign spatial reference” 是什么意思？** 它将几何对象绑定到特定的坐标系统，例如 WGS‑84。  
- **支持哪些 WKT 变体？** Iso、SimpleFeatureAccessOutdated 和 ExtendedPostGis。  
- **如何控制小数精度？** 使用 `NumericFormat` 选项，如 `General`、`RoundTrip` 或 `Flat`。  
- **我需要许可证吗？** 有免费试用版；生产环境需要商业许可证。  
- **兼容哪些 .NET 版本？** .NET Framework 4.0+ 和 .NET Core/5/6+。

## 什么是 “assign spatial reference”？
为几何对象分配空间参考（或空间参考系统，SRS）告诉 GIS 软件如何解释坐标值。如果没有 SRS，点的纬度‑经度数值就没有实际意义。

## 为什么要控制 WKT 变体和数值格式？
不同的 GIS 工具对 WKT 语法的期望略有不同。选择合适的变体可确保无缝的数据交换，而设置小数精度可以防止四舍五入误差或过长的数字导致日志和文件混乱。

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

## 步骤 1：创建 Point 对象（create point C#）
我们首先构造一个带有纬度、经度以及可选测量值 (M) 的 `Point`：

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## 步骤 2：分配空间参考系统 (SRS)
现在我们 **分配空间参考** 给该点。这里使用广泛支持的 WGS‑84 系统 (SRID 4326)：

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

## 步骤 4：为 WKT 输出设置小数精度
使用 `NumericFormat` 控制最终字符串中出现的数字位数：

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### 常见陷阱与技巧
- **陷阱：** 在调用 `AsText` 之前忘记设置 SRS 可能导致缺少 SRID 信息。  
- **技巧：** 当需要坐标的无损往返时，使用 `NumericFormat.RoundTrip`。  
- **技巧：** `Iso` 变体是最通用的；仅在需要嵌入 SRID 时才选择 `ExtendedPostGis`。

## 结论
现在您已经了解如何 **分配空间参考**、选择合适的 WKT 变体，以及在使用 Aspose.GIS **创建 point C#** 对象时 **设置小数精度**。这些控制使您能够灵活满足任何 GIS 工作流的精确需求，从简单的可视化到高精度的空间分析。

## 常见问题

**Q:** Aspose.GIS 是否兼容所有 .NET 版本？  
**A:** 是的，Aspose.GIS 支持 .NET Framework 4.0 及更高版本，以及 .NET Core/5/6。

**Q:** 我可以在商业项目中使用 Aspose.GIS 吗？  
**A:** 当然。生产使用需要商业许可证，但可提供免费试用版供评估。

**Q:** Aspose.GIS 是否支持其他空间数据格式？  
**A:** 是的，它支持 ESRI Shapefile、GeoJSON、KML 等多种格式。

**Q:** 我在哪里可以下载免费试用版？  
**A:** 您可以从 [here](https://releases.aspose.com/) 下载 Aspose.GIS 的免费试用版。

**Q:** 如果遇到问题，我该如何获取帮助？  
**A:** 在 Aspose.GIS 社区的 [forum](https://forum.aspose.com/c/gis/33) 发帖提问，Aspose 员工和社区成员都会提供帮助。

---

**最后更新**: 2026-04-09  
**测试环境**: Aspose.GIS for .NET (latest release)  
**作者**: Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2025-12-23
description: 了解如何使用 Aspose.GIS for .NET 将几何对象转换为 WKT（可选多种方式），设置数值格式并调整小数精度。
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS 将几何转换为 WKT 变体选项
url: /zh/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS 将几何转换为 WKT 变体选项

## 介绍
在现代 .NET 应用程序中，**将几何转换为 WKT** 是在需要与其他系统交换空间数据或以基于文本的格式存储时的常见步骤。Aspose.GIS for .NET 使此转换轻而易举，同时让您完全控制 WKT 变体、数字格式和小数精度。在本教程中，您将学习如何将几何转换为 WKT，选择正确的变体，并微调输出以满足项目的精确要求。

## 快速答案
- **“将几何转换为 WKT” 是什么意思？** 它将几何对象（点、线、多边形）转换为 Well‑Known Text 表示。  
- **支持哪些 WKT 变体？** `Iso`、`SimpleFeatureAccessOutdated` 和 `ExtendedPostGis`。  
- **如何控制小数精度？** 使用 `NumericFormat` 选项，如 `General`、`RoundTrip` 或 `Flat`。  
- **生产环境是否需要许可证？** 是的，非试用使用需要商业许可证。  
- **.NET 版本兼容性？** .NET Framework 4.0+ 和 .NET 5/6/7。

## 什么是 “将几何转换为 WKT”？
将几何转换为 WKT 会生成一个人类可读的字符串，描述空间对象。此格式被 GIS 工具、数据库和 Web 服务广泛接受，因而非常适合数据交换。

## 为什么使用 Aspose.GIS 进行此转换？
- **精度控制** – 选择输出的小数位数。  
- **变体灵活性** – 匹配下游系统所需的精确 WKT 方言。  
- **无外部依赖** – 纯 .NET 库，无本机二进制文件。

## 前置条件
在开始之前，请确保您已具备：

1. **Aspose.GIS for .NET** – 从 [download page](https://releases.aspose.com/gis/net/) 下载并安装。  
2. **开发环境** – 任意近期版本的 Visual Studio 或带 .NET SDK 的 VS Code。  
3. **基本的 C# 知识** – 熟悉类、对象和 .NET 框架。

## 导入命名空间
首先，将所需的命名空间引入作用域：

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

## 步骤 1：创建 Point 对象
创建一个 `Point`，稍后您将 **将几何转换为 WKT**。该点包含纬度、经度以及可选的测量（M）值：

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## 步骤 2：设置空间参考系统 (SRS)
指定空间参考系统，使 WKT 输出知道使用哪个坐标系。这里我们使用常用的 WGS84 系统：

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## 步骤 3：指定 WKT 变体
在 **将几何转换为 WKT** 时选择合适的 WKT 变体。每个变体的输出略有不同：

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## 步骤 4：控制数字格式（设置数字格式并调整小数精度）
微调坐标的数字表示。`NumericFormat` 类让您 **设置数字格式** 并 **调整小数精度** 以满足需求：

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## 常见问题与技巧
- **缺少 M 值** – 如果不需要测量值，省略 `M` 属性；ISO 变体会自动去除。  
- **意外的精度** – 再次确认使用了正确的 `NumericFormat`；`General` 保留完整的 double 精度，而 `Flat` 会四舍五入到指定的小数位数。  
- **SRID 未显示** – 仅 `ExtendedPostGis` 变体会在输出前加上 `SRID=`。当目标系统期望 SRID 时请选择此变体。

## 结论
通过上述步骤，您现在了解如何 **将几何转换为 WKT**、选择正确的变体，并精确控制数字输出。这为您将 Aspose.GIS 集成到任何 GIS 工作流、数据库或消费 WKT 的 Web 服务中提供了灵活性。

## 常见问题
### Aspose.GIS 是否兼容所有 .NET 版本？
是的，Aspose.GIS 支持 .NET Framework 4.0 及更高版本。  

### 我可以在商业项目中使用 Aspose.GIS 吗？
可以，Aspose.GIS 可用于个人和商业项目。  

### Aspose.GIS 是否提供对其他空间数据格式的支持？
是的，Aspose.GIS 支持多种空间数据格式，包括 ESRI Shapefile、GeoJSON 和 KML。  

### 是否有 Aspose.GIS 的免费试用版？
是的，您可以从 [here](https://releases.aspose.com/) 下载 Aspose.GIS 的免费试用版。  

### 在哪里可以获得 Aspose.GIS 的帮助或支持？
您可以在 [forum](https://forum.aspose.com/c/gis/33) 发帖提问或寻求 Aspose.GIS 社区的帮助。

## Frequently Asked Questions
**Q: How do I export a Geometry collection to a single WKT string?**  
A: Iterate over each geometry in the collection and concatenate their `AsText` results, optionally separating them with commas or newlines.

**Q: Can I change the SRID without altering the coordinates?**  
A: Yes, set the `SpatialReferenceSystem` property to the desired SRID; the coordinate values remain unchanged.

**Q: What happens if I use an unsupported WKT variant?**  
A: Aspose.GIS will throw an `ArgumentException`. Always validate the variant against `WktVariant` enum values.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
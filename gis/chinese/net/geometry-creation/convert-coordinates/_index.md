---
date: 2026-08-18
description: 使用 Aspose.GIS for .NET 将十进制度转换为 DMS。本分步 C# 指南展示了如何将纬度/经度、十进制度转换为 DMS
  等。
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: 转换坐标
og_description: 使用 Aspose.GIS for .NET，轻松实现十进制度到 DMS 的转换。了解如何将纬度‑经度值转换为以分钟为单位的 DMS
  格式。
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: 将十进制度转换为 DMS，使用 Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  headline: How to convert decimal degrees to dms with Aspose.GIS for .NET
  type: TechArticle
- description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  name: How to convert decimal degrees to dms with Aspose.GIS for .NET
  steps:
  - name: start the conversion process
    text: We print a friendly message so you know the demo has begun.
  - name: convert to decimal degrees
    text: Even though the final goal is DMS, we start by showing the original decimal
      representation. This also demonstrates the **decimal degrees to dms** path you’ll
      later follow.
  - name: convert to degree decimal minutes
    text: This format (`DD°MM.m'`) is a common intermediate step when you need to
      **convert lat long degree minutes**.
  - name: convert to degree minutes seconds (dms)
    text: Here’s the core of our tutorial—**convert coordinates to dms**.
  - name: convert to GeoRef
    text: For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing
      workflows.
  type: HowTo
- questions:
  - answer: Aspose.GIS primarily targets .NET developers, but a Java version is also
      available.
    question: Is Aspose.GIS compatible with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.GIS before purchasing?
  - answer: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  - answer: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert coordinates
- Aspose.GIS
- .NET GIS processing
title: 如何使用 Aspose.GIS for .NET 将十进制度转换为 DMS
url: /zh/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS 将十进制度转换为 DMS

## 介绍
在本教程中，您将学习 **如何将十进制度转换为 DMS**，使用强大的 Aspose.GIS .NET 库。无论您需要 **C# 转换经纬度**、为报告生成可读的位置信息字符串，还是仅仅探索不同的坐标格式，本指南都会通过清晰的解释和可直接运行的 C# 代码片段，逐步带您完成整个过程。

## 快速回答
- **“将坐标转换为 DMS”是什么意思？** 它将数值纬度/经度转换为传统的度‑分‑秒表示法。  
- **哪个库负责转换？** Aspose.GIS for .NET 提供了具有内置格式支持的 `GeoConvert` 类。  
- **我需要许可证才能试用吗？** 有免费试用版；生产环境需要商业许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+ 和 .NET 5/6+。  
- **我可以使用相同的代码处理其他格式吗？** 可以——只需更改 `PointFormats` 枚举值（例如 `DecimalDegrees`、`GeoRef`）。

## 什么是坐标转换为 DMS？
将坐标转换为 DMS 将十进制度的纬度和经度值重新写成类似 `25°30'00"N 45°30'00"E` 的格式。该过程将每个十进制度拆分为整数度、分钟（度的六十分之一）和秒（分钟的六十分之一），然后附加相应的半球指示符（N、S、E、W）。这种可读形式对于许多传统数据集以及在不使用十进制度的情况下传达精确位置至关重要。

## 为什么使用 Aspose.GIS 进行坐标转换？
Aspose.GIS 支持 **50+ 输入和输出格式**，并且能够在不将整个数据集加载到内存的情况下处理数百页的 GIS 文件。API 在处理负值和半球指示符等边缘情况时提供亚毫米级精度，并且在 Windows、Linux 和 macOS .NET 运行时上表现一致。

## 前置条件
在开始之前，请确保您具备以下条件：

1. **C# 基础知识**——熟悉变量、方法调用和控制台输出。  
2. **已安装 Aspose.GIS**——从 [Aspose.GIS website](https://releases.aspose.com/gis/net/) 下载最新包。您也可以在 [Aspose releases website](https://releases.aspose.com/) 浏览主要的 Aspose 发布。

## 导入命名空间
首先，导入进行 GIS 操作所需的命名空间：

导入命名空间占位符保持不变。

## 步骤指南

### 什么是 GeoConvert 类？
`GeoConvert` 类提供了用于在十进制度、DMS 和 GeoRef 等坐标格式之间转换的静态方法。它包含接受原始数值或 `Point` 对象的重载，并返回格式化字符串或新的 `Point` 实例。通过处理负坐标和四舍五入等边缘情况，该类确保输出符合标准 GIS 规范，简化了在任何 .NET 制图应用中的集成。

### 步骤 1：启动转换过程
我们打印一条友好的信息，以便您知道演示已经开始。

```csharp
using System;
using Aspose.Gis;
```

### 步骤 2：转换为十进制度
即使最终目标是 DMS，我们仍先展示原始的十进制度表示。这也演示了稍后将要走的 **十进制度到 DMS** 路径。

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### 步骤 3：转换为度十进制分钟
这种格式（`DD°MM.m'`）是在需要 **转换经纬度度分钟** 时常用的中间步骤。

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### 步骤 4：转换为度分秒（DMS）
这就是本教程的核心——**将坐标转换为 DMS**。

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### 步骤 5：转换为 GeoRef
为了完整性，我们还演示了 `GeoRef` 格式，它在遥感工作流中很有用。

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## 常见问题及解决方案
- **半球字母不正确**——确保北/东使用正值，南/西使用负值；API 会自动添加正确的后缀。  
- **意外的空输出**——确认已正确引用 `Aspose.Gis` 程序集，并且项目针对受支持的 .NET 版本。  
- **未找到许可证**——将许可证文件放在应用程序根目录，或使用代码 `License license = new License(); license.SetLicense("Aspose.GIS.lic");` 进行编程设置。

## 常见问答

**问：Aspose.GIS 是否兼容其他编程语言？**  
**答：** Aspose.GIS 主要面向 .NET 开发者，但也提供 Java 版本。

**问：我可以在购买前试用 Aspose.GIS 吗？**  
**答：** 可以，您可以从[website](https://releases.aspose.com/)获取 Aspose.GIS 的免费试用版。

**问：如何获取 Aspose.GIS 的支持？**  
**答：** 您可以在 Aspose.GIS 社区论坛[here](https://forum.aspose.com/c/gis/33)寻求帮助。

**问：Aspose.GIS 是否提供临时许可证？**  
**答：** 是的，可从[temporary license page](https://purchase.aspose.com/temporary-license/)获取临时许可证。

**问：在哪里购买 Aspose.GIS？**  
**答：** 您可以在[purchase page](https://purchase.aspose.com/buy)购买 Aspose.GIS。

## 结论
通过遵循这些步骤，您现在了解如何使用 Aspose.GIS for .NET **将十进制度转换为 DMS** 以及其他常见 GIS 格式。此功能让您能够将可读的位置信息字符串无缝集成到地图应用、报告或任何空间数据工作流中。欢迎尝试不同的纬度/经度值，并探索 `GeoConvert` 类提供的其他格式。

---

**最后更新:** 2026-08-18  
**测试环境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## 相关教程

- [如何使用 Aspose.GIS for .NET 创建点几何并获取几何类型](/gis/net/geometry-analysis/get-geometry-type/)
- [如何转换 GeoJSON – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [使用 Aspose.GIS 在 .NET 中创建 MultiPoint 几何](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
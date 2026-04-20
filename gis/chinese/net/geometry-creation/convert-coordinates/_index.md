---
date: 2026-02-13
description: 了解如何使用 Aspose.GIS for .NET 将坐标转换为 DMS。此一步步的 C# 指南展示了 C# 将纬度经度、十进制度数转换为
  DMS 等操作。
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 将坐标转换为度分秒
url: /zh/net/geometry-creation/convert-coordinates/
weight: 25
---

_0}} etc.

Now produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS 将坐标转换为 DMS 的方法

## Introduction
在本教程中，您将学习 **如何将坐标** 转换为 DMS（degrees, minutes, seconds）使用功能强大的 Aspose.GIS .NET 库。无论您需要 **c# convert lat long**，生成可读的位置信息字符串，或仅仅探索不同的坐标格式，本指南都将通过清晰的解释和可直接运行的 C# 代码，带您一步步完成。

## Quick Answers
- **将坐标转换为 DMS 是什么意思？** 它将数值纬度/经度转换为传统的度‑分‑秒表示法。  
- **哪个库负责转换？** Aspose.GIS for .NET 提供了带有内置格式支持的 `GeoConvert` 类。  
- **我需要许可证才能试用吗？** 有免费试用版；生产环境需要商业许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+ 以及 .NET 5/6+。  
- **我可以用相同的代码处理其他格式吗？** 可以——只需更改 `PointFormats` 枚举值（例如 `DecimalDegrees`、`GeoRef`）。  

## How to Convert Coordinates to DMS
在深入代码之前，让我们先说明为什么 DMS 仍然有价值。制图师、飞行员以及许多 GIS 数据提供商都依赖 DMS，因为它对人类友好并且与传统地图保持一致。Aspose.GIS 消除了手动数学的需求，让您专注于应用逻辑。

## What is coordinate conversion to DMS?
将坐标转换为 DMS 会把十进制纬度和经度值重新写成类似 `25°30'00"N 45°30'00"E` 的格式。这种表示在制图、导航和 GIS 数据交换中被广泛使用。

## Why use Aspose.GIS for coordinate conversion?
- **一站式 API** – 无需外部库或复杂数学；Aspose.GIS 在内部处理解析和格式化。  
- **高精度** – 精确处理负值和半球指示符等边缘情况。  
- **跨平台** – 在 Windows、Linux 和 macOS .NET 运行时上表现一致。  
- **可扩展** – 可轻松在 DMS、十进制度、度‑十进制‑分以及 GeoRef 格式之间切换。

## Prerequisites
在开始之前，请确保您具备以下条件：

1. **基本的 C# 知识** – 熟悉变量、方法调用和控制台输出。  
2. **已安装 Aspose.GIS** – 从 [Aspose.GIS website](https://releases.aspose.com/gis/net/) 下载最新包。

## Import Namespaces
首先，导入进行 GIS 操作所需的命名空间：

```csharp
using System;
using Aspose.Gis;
```

## Step‑by‑step guide

### Step 1: Start the conversion process
我们打印一条友好的信息，以便您知道演示已经开始。

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Step 2: Convert to Decimal Degrees  
即使最终目标是 DMS，我们仍先展示原始的十进制度表示。这也演示了稍后将要使用的 **decimal degrees to dms** 路径。

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Step 3: Convert to Degree Decimal Minutes  
这种格式 (`DD°MM.m'`) 是在需要 *convert lat long degree minutes* 时常用的中间步骤。

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Step 4: Convert to Degree Minutes Seconds (DMS)  
这就是本教程的核心——**convert coordinates to DMS**。

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### Step 5: Convert to GeoRef  
为了完整性，我们还演示了 `GeoRef` 格式，在遥感工作流中很有用。

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Common Issues and Solutions
- **半球字母不正确** – 确保对北/东传入正值，对南/西传入负值；API 会自动添加正确的后缀。  
- **意外的空输出** – 检查是否正确引用了 `Aspose.Gis` 程序集，并且项目目标为受支持的 .NET 版本。  
- **未找到许可证** – 将许可证文件放在应用根目录，或使用 `License license = new License(); license.SetLicense("Aspose.GIS.lic");` 以编程方式设置。

## Frequently Asked Questions

**问：Aspose.GIS 是否兼容其他编程语言？**  
答：Aspose.GIS 主要面向 .NET 开发者，但也提供 Java 版本。

**问：我可以在购买前试用 Aspose.GIS 吗？**  
答：可以，您可以从 [website](https://releases.aspose.com/) 获取 Aspose.GIS 的免费试用版。

**问：如何获取 Aspose.GIS 的支持？**  
答：您可以在 Aspose.GIS 社区论坛 [here](https://forum.aspose.com/c/gis/33) 寻求帮助。

**问：Aspose.GIS 是否提供临时许可证？**  
答：可以，从 [temporary license page](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

**问：在哪里购买 Aspose.GIS？**  
答：您可以在 [purchase page](https://purchase.aspose.com/buy) 进行购买。

## Conclusion
通过遵循这些步骤，您现在了解了如何使用 Aspose.GIS for .NET **将坐标转换为 DMS** 以及其他常见 GIS 格式。这一功能让您能够将可读的位置信息字符串无缝集成到地图应用、报告或任何空间数据工作流中。**随意**尝试不同的纬度/经度值，并探索 `GeoConvert` 类提供的其他格式。

---

**最后更新：** 2026-02-13  
**测试环境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2025-12-11
description: 学习如何使用 Aspose.GIS for .NET 将坐标转换为 DMS。包括 C# 示例、C# 转换纬度经度，以及一步步指南。
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS for .NET 将坐标转换为 DMS
url: /zh/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将坐标转换为 DMS（度、分、秒） 使用 Aspose.GIS

## 介绍
在本教程中，您将学习如何使用功能强大的 Aspose.GIS .NET 库 **将坐标转换为 DMS**（度、分、秒）。无论是需要 **c# 将纬度经度转换** 用于制图应用、生成可读的位置信息字符串，还是仅仅想探索不同的坐标格式，本指南都将通过清晰的说明和可直接运行的 C# 代码，逐步带您完成整个过程。

## 快速答案
- **“将坐标转换为 DMS” 是什么意思？** 它将数值形式的纬度/经度转换为传统的度‑分‑秒表示法。  
- **哪个库负责转换？** Aspose.GIS for .NET 提供了 `GeoConvert` 类，内置多种格式支持。  
- **试用需要许可证吗？** 提供免费试用版；生产环境需要商业许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、以及 .NET 5/6+。  
- **可以用相同代码转换为其他格式吗？** 可以——只需更改 `PointFormats` 枚举值（例如 `DecimalDegrees`、`GeoRef`）。  

## 什么是坐标转换为 DMS？
将坐标转换为 DMS 会把十进制的纬度和经度值重新写成类似 `25°30'00"N 45°30'00"E` 的格式。这种表示法在制图、导航和 GIS 数据交换中被广泛使用。

## 为什么选择 Aspose.GIS 进行坐标转换？
- **一站式 API** – 无需外部库或复杂数学，Aspose.GIS 在内部完成解析和格式化。  
- **高精度** – 精确处理负值和半球标识等边界情况。  
- **跨平台** – 在 Windows、Linux 和 macOS 的 .NET 运行时上表现一致。  
- **可扩展** – 可轻松在 DMS、十进制度、度‑十进制‑分以及 GeoRef 格式之间切换。

## 前置条件
在开始之前，请确保您已具备以下条件：

1. **基本的 C# 知识** – 熟悉变量、方法调用和控制台输出。  
2. **已安装 Aspose.GIS** – 从 [Aspose.GIS website](https://releases.aspose.com/gis/net/) 下载最新包。  

## 导入命名空间
首先，导入进行 GIS 操作所需的命名空间：

```csharp
using System;
using Aspose.Gis;
```

## 步骤指南

### 步骤 1：启动转换过程
我们打印一条友好的信息，以便您知道演示已经开始。

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### 步骤 2：转换为十进制度  
虽然最终目标是 DMS，但我们先展示原始的十进制度表示。

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### 步骤 3：转换为度‑十进制‑分  
这种格式（`DD°MM.m'`）是常见的中间步骤，适用于 *convert lat long degree minutes* 场景。

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### 步骤 4：转换为度‑分‑秒（DMS）  
下面是本教程的核心——**将坐标转换为 DMS**。

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### 步骤 5：转换为 GeoRef  
为了完整性，我们还演示 `GeoRef` 格式，在遥感工作流中非常有用。

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## 常见问题与解决方案
- **半球字母不正确** – 确保对北/东使用正值，对南/西使用负值；API 会自动添加正确的后缀。  
- **输出为空** – 检查是否正确引用了 `Aspose.Gis` 程序集，并确认项目目标为受支持的 .NET 版本。  
- **未找到许可证** – 将许可证文件放在应用根目录，或使用代码 `License license = new License(); license.SetLicense("Aspose.GIS.lic");` 进行设置。

## 常见问答

**Q: Aspose.GIS 能否兼容其他编程语言？**  
A: Aspose.GIS 主要面向 .NET 开发者，但也提供了 Java 版本。

**Q: 我可以在购买前试用 Aspose.GIS 吗？**  
A: 可以，您可以从 [website](https://releases.aspose.com/) 获取免费试用版。

**Q: 如何获取 Aspose.GIS 的技术支持？**  
A: 您可以在 Aspose.GIS 社区论坛 [here](https://forum.aspose.com/c/gis/33) 寻求帮助。

**Q: 是否提供临时许可证？**  
A: 可以，从 [temporary license page](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

**Q: 哪里可以购买 Aspose.GIS？**  
A: 请前往 [purchase page](https://purchase.aspose.com/buy) 进行购买。

## 结论
通过上述步骤，您现在已经掌握了使用 Aspose.GIS for .NET **将坐标转换为 DMS** 以及其他常见 GIS 格式的方法。这一能力让您能够轻松将可读的位置信息字符串集成到制图应用、报告或任何空间数据工作流中。欢迎尝试不同的纬度/经度值，并探索 `GeoConvert` 类提供的其他格式。

---

**最后更新：** 2025-12-11  
**测试环境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-07-05
description: 学习如何使用 Aspose.GIS for .NET 将 shapefile 转换为 geojson。指南还涵盖在图层之间复制属性以及使用
  c# 生成 geojson 文件。
keywords:
- convert shapefile to geojson
- export shapefile as geojson
- aspose gis conversion
- read shapefile c#
- write geojson c#
linktitle: 提取要素为 GeoJSON
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  headline: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  name: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  steps:
  - name: Open Input Shapefile
    text: The `VectorLayer.Open` method reads a Shapefile and returns an enumerable
      collection of `Feature` objects that you can iterate over.
  - name: Create Output GeoJSON
    text: '`VectorLayer.Create` with the `Drivers.GeoJson` driver creates an empty
      GeoJSON file ready to receive features.'
  - name: Copy Attributes Between Layers
    text: '`CopyAttributes` copies the attribute schema (field names and data types)
      from the source Shapefile to the new GeoJSON layer in a single call.'
  - name: Process Features
    text: Iterate through each feature in the Shapefile so you can apply any custom
      logic before writing it out.
  - name: Filter Features by Date
    text: In this example we skip records whose `dob` (date of birth) field is missing
      or earlier than 1 Jan 1982. Adjust the filter to match your own data requirements.
  - name: Construct a New Feature (C# Generate GeoJSON File)
    text: A `Feature` represents a single spatial element containing geometry and
      attribute data. Here we build a new `Feature` for the GeoJSON layer, copy the
      geometry and attribute values, and add it to the output. This is the core of
      *c# generate geojson file*. Congratulations! You’ve successfully **conver
  type: HowTo
- questions:
  - answer: Visit the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/)
      for in‑depth information.
    question: Where can I find more documentation?
  - answer: You can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license?
  - answer: Join the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I seek support?
  - answer: Yes, you can find the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can buy the product [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS for .NET 将 Shapefile 转换为 GeoJSON
url: /zh/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将 Shapefile 转换为 GeoJSON 使用 Aspose.GIS for .NET

## 介绍
在本全面的分步教程中，您将学习使用强大的 Aspose.GIS for .NET 库**将 shapefile 转换为 geojson**的方法。无论您是构建地图 Web 服务、为移动 GIS 应用准备数据，还是仅需在不同格式之间交换数据，本指南都会准确告诉您该怎么做、每一步为何重要，以及如何避免常见陷阱。

## 快速答案
- **本教程涵盖什么内容？** 将 Shapefile 转换为 GeoJSON 文件，在图层之间复制属性，并使用 C# 生成输出。
- **需要哪个库？** Aspose.GIS for .NET。
- **我需要许可证吗？** 生产环境需要临时或正式许可证；免费试用可用于评估。
- **实现需要多长时间？** 基本转换大约需要 10‑15 分钟。
- **我可以在 .NET Core/.NET 6 上运行吗？** 可以——代码在所有受支持的 .NET 版本上均可运行。

## 什么是将 Shapefile 转换为 GeoJSON？
将 Shapefile 转换为 GeoJSON 是指从经典的 ESRI Shapefile 格式读取矢量要素，并将其写入现代的、适合 Web 的 GeoJSON 文档。此转换使您能够直接将 GIS 数据输入到如 Leaflet 或 Mapbox GL 等 JavaScript 地图库中，并简化了桌面 GIS 工具与 Web API 之间的数据交换。

## 为什么在此转换中使用 Aspose.GIS？
Aspose.GIS 抽象了底层二进制解析，支持 50 多种输入和输出格式，并且能够在不将整个文件加载到内存的情况下处理数百页的数据集。该库还提供了简洁的面向对象 API，兼容 .NET Framework、.NET Core 和 .NET 5/6，让您将时间花在业务逻辑上，而不是格式细节上。

## 前置条件
- Aspose.GIS for .NET：确保已安装该库。如未安装，可从 [Aspose.GIS for .NET 页面](https://releases.aspose.com/gis/net/) 下载。
- Shapefile 数据：准备好用于输入的 Shapefile。如需示例数据，可在 [Aspose.GIS 文档](https://reference.aspose.com/gis/net/) 中找到。
- .NET 环境：搭建 .NET 环境以运行提供的代码。
- 文档目录：在代码片段中定义文档目录的路径。

既然已准备就绪，让我们开始将 shapefile 转换为 geojson！

## 如何将 Shapefile 转换为 GeoJSON
加载源 Shapefile，创建目标 GeoJSON 图层，复制属性模式，过滤记录并写入结果——所有这些都在几个简洁的步骤中完成。完整的工作流可以轻松放入单个 `using` 块中，确保资源自动释放。

### 步骤 1：打开输入 Shapefile
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```

### 步骤 2：创建输出 GeoJSON
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```

### 步骤 3：在图层之间复制属性
```csharp
outputLayer.CopyAttributes(inputLayer);
```

### 步骤 4：处理要素
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```

### 步骤 5：按日期过滤要素
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```

### 步骤 6：构建新要素（C# 生成 GeoJSON 文件）
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```

恭喜！您已成功**将 shapefile 转换为 geojson**，并在此过程中学习了如何**在图层之间复制属性**。

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|-------|----------------|-----|
| 输出文件为空 | 在输出图层关闭后调用了 `CopyAttributes` | 确保 `outputLayer` 的 `using` 块保持打开，直至所有要素添加完毕。 |
| 日期过滤导致所有记录被移除 | 字段名错误或日期格式异常 | 验证属性名 (`dob`) 并在日期以字符串存储时使用 `GetValue<string>`。 |
| 许可证异常 | 生产环境中未使用有效的 Aspose.GIS 许可证 | 按 Aspose 文档说明应用临时或正式许可证。 |

## 常见问答
**问：在哪里可以找到更多文档？**  
答：访问 [Aspose.GIS 文档](https://reference.aspose.com/gis/net/) 获取深入信息。

**问：如何获取临时许可证？**  
答：您可以在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

**问：在哪里可以寻求支持？**  
答：加入 [Aspose.GIS 论坛](https://forum.aspose.com/c/gis/33) 获取社区支持和讨论。

**问：是否提供免费试用？**  
答：是的，您可以在[此处](https://releases.aspose.com/)找到免费试用。

**问：在哪里可以购买 Aspose.GIS for .NET？**  
答：您可以在[此处](https://purchase.aspose.com/buy)购买该产品。

## 结论
在本教程中，我们使用 Aspose.GIS for .NET 探讨了完整的 **将 shapefile 转换为 geojson** 过程，演示了如何 **在图层之间复制属性**，并展示了生成 *c# geojson 文件* 的简洁方法。尝试不同的过滤条件、更大的数据集或额外的几何转换，以充分发挥该库的功能。

**最后更新:** 2026-07-05  
**测试环境:** Aspose.GIS for .NET (latest stable release)  
**作者:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 相关教程

- [如何使用 Aspose.GIS for .NET 将 GeoJSON 转换为 File GDB](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [如何使用 Aspose.GIS for .NET 从流中读取 GeoJSON](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [如何使用 Aspose.GIS 将 GeoJSON 转换为 TopoJSON](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
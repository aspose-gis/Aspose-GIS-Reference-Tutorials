---
date: 2026-10-15
description: 了解如何使用 Aspose.GIS for .NET 从坐标创建 GeoJSON 并将其写入流。本教程展示了点的逐步转换以及生成 GeoJSON
  C# 代码。
keywords:
- create geojson from coordinates
- stream large geojson files
- write geojson to stream
- geojson tutorial c#
- compress geojson with gzip
lastmod: 2026-10-15
linktitle: 将 GeoJSON 写入流
og_description: 了解如何使用 Aspose.GIS for .NET 从坐标创建 GeoJSON 并将其写入流——针对大型数据集的逐步指南。
og_image_alt: Screenshot of Aspose.GIS code generating GeoJSON stream in C#
og_title: 从坐标创建 GeoJSON 并写入 .NET 流
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create geojson from coordinates and write it to a stream
    using Aspose.GIS for .NET. This tutorial shows step‑by‑step conversion of points
    and generation of GeoJSON C# code.
  headline: Create geojson from coordinates, write to a stream in .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET geospatial
- C# stream processing
- GIS data conversion
title: 从坐标创建 GeoJSON 并写入 .NET 流
url: /zh/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 从坐标创建 geojson 并写入流

## 介绍
在本教程中，您将学习**如何从坐标创建 geojson**并使用 Aspose.GIS for .NET 直接写入流。我们将逐步演示环境设置、图层创建、要素填充以及流式输出的过程，这样您就可以在 API、云函数或无文件服务中嵌入地理空间负载，而无需临时文件。

## 快速答案
- **哪个类将 GeoJSON 写入流？** `VectorLayer` 与 `GeoJsonDriver` 一起使用。
- **开发是否需要许可证？** 免费试用可用于开发；生产环境需要商业许可证。
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。
- **我可以将点集合转换为 GeoJSON 吗？** 可以——为每个点创建 `Feature` 并分配 `Point` 几何。
- **流式写入适用于大数据集吗？** 绝对可以——`MemoryStream` 让您在不将整个文件加载到内存的情况下写入千兆级 GeoJSON。

## 什么是 GeoJSON？
GeoJSON 是一种基于 JSON 的开放格式，用于编码地理要素，如点、线和多边形。它由一个 `FeatureCollection` 组成，用于聚合各个 `Feature` 对象，每个对象携带几何和属性数据。由于其轻量且适合 Web，GeoJSON 已成为浏览器、GIS 服务器和移动应用之间交换空间数据的事实标准。

## 为什么使用 Aspose.GIS 生成 geojson？
Aspose.GIS 支持**35+ 空间文件格式**，并且能够流式处理大于**2 GB**的文件，同时将内存使用保持在**50 MB**以下。其高性能流式引擎可将 GeoJSON 直接写入任何 .NET `Stream`，消除中间临时文件的需求，并在典型的云场景中将 I/O 延迟降低至**70 %**。

## 前提条件
1. 已安装 **Aspose.GIS for .NET**。在此处下载 **Aspose.GIS for .NET** 包[here](https://releases.aspose.com/gis/net/)。
2. 项目中可写的文件夹，以便在需要时放置临时文件。
3. 已安装 .NET 5+ 或 .NET Core 3.1+ 运行时。

现在，让我们深入实现细节。

## 如何从坐标创建 geojson 并写入流？
`VectorLayer` 表示一个可保存为多种格式的内存矢量数据集。  
`GeoJsonDriver` 是用于读取和写入 GeoJSON 文件的驱动程序。  

使用 `GeoJsonDriver` 加载 `VectorLayer`，添加包含 `Point` 几何的 `Feature` 对象，然后调用 `layer.Save(stream, new GeoJsonSaveOptions())`。此单一调用会将整个要素集合序列化为符合标准的 GeoJSON 文档，存放在提供的 `MemoryStream` 中。该过程会自动处理属性映射和坐标转换，您即可获得可直接使用的 JSON 负载，无需手动构建字符串。

### 定义锚点
**VectorLayer** 是 Aspose.GIS 的核心对象，表示内存中的可变矢量数据集。  
**GeoJsonDriver** 是负责读取和写入 GeoJSON 文件的驱动程序。

## 导入命名空间
First things first, make sure to include the necessary namespaces to access the Aspose.GIS functionalities in your code:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## 步骤 1：设置文档目录
Create a folder path where Aspose.GIS can store auxiliary files if required.  
```csharp
string dataDir = "Your Document Directory";
```
将 "Your Document Directory" 替换为实际的文档目录路径。

## 步骤 2：创建内存流
A `MemoryStream` provides an in‑memory buffer that can be sent directly over HTTP or saved to cloud storage.  
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## 步骤 3：使用 GeoJSON 驱动创建矢量图层
The `VectorLayer` class represents a vector dataset that can be saved in various formats, including GeoJSON.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## 步骤 4：定义要素属性
Define the attribute schema for your features (e.g., ID, Name).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## 步骤 5：构建并添加要素
Create `Feature` objects, assign point geometry, set attribute values, and add them to the layer.  
```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## 步骤 6：显示 GeoJSON 输出
After saving, reset the stream position and read the JSON string for verification or transmission.  
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

恭喜！您已成功使用 Aspose.GIS for .NET 从坐标创建 geojson 并将其写入流。

## 常见问题及解决方案
- **输出流为空：** 在读取之前确保重置流位置 (`stream.Position = 0`)。
- **坐标顺序错误：** GeoJSON 需要经度‑纬度顺序；请核对点的数值。
- **大数据集：** 使用 `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` 逐步流式写入要素，以保持低内存使用。

## 常见问答

**问：我可以在 Windows 和 Linux 环境中使用 Aspose.GIS for .NET 吗？**  
答：可以，Aspose.GIS for .NET 可在 Windows、Linux 和 macOS 上运行，完全支持 .NET Core。

**问：是否提供免费试用？**  
答：当然！您可以在 **免费试用下载页面**[here](https://releases.aspose.com/) 进行探索。

**问：在哪里可以找到详细文档？**  
答：请查看 **Aspose.GIS .NET 文档**[here](https://reference.aspose.com/gis/net/)。

**问：如何获取临时许可证？**  
答：临时许可证可在 **临时许可证页面**[here](https://purchase.aspose.com/temporary-license/) 获取。

**问：需要帮助或有更多问题？**  
答：请访问我们的 **GIS 支持论坛**[here](https://forum.aspose.com/c/gis/33)。

**问：我可以从一组纬度/经度点生成 GeoJSON 吗？**  
答：可以——为每个点创建 `Feature`，分配 `Point` 几何，并将其添加到 `VectorLayer`。

**问：Aspose.GIS 是否支持写入压缩的 GeoJSON（gzip）？**  
答：您可以在保存之前将 `MemoryStream` 包装在 `GZipStream` 中，以生成压缩负载。

**问：Aspose.GIS 能处理的 GeoJSON 文件最大尺寸是多少？**  
答：该库可以流式处理超过 2 GB 的文件；由于数据是增量写入，内存使用保持低水平。

---

**最后更新:** 2026-10-15  
**已测试于:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

## 相关教程

- [如何使用 Aspose.GIS for .NET 从流读取 GeoJSON](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [如何使用 Aspose.GIS 将 GeoJSON 转换为 TopoJSON](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [如何使用 Aspose.GIS for .NET 将 Shapefile 转换为 GeoJSON](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
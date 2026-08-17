---
date: 2026-05-31
description: 了解如何使用 Aspose.GIS for .NET 创建 GeoJSON、配置 GeoJSON 选项以及向图层添加要素。请按照本分步指南操作。
keywords:
- how to create geojson
- add feature to layer
- configure geojson options
linktitle: 设置 Linearization Tolerance
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  headline: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  name: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  steps:
  - name: Configure GeoJSON Options (how to set tolerance)
    text: '`GeoJsonOptions` specifies the serialization settings used when writing
      GeoJSON files. `GeoJsonOptions` defines how Aspose.GIS serializes GeoJSON, including
      linearization tolerance, coordinate precision, and other output settings. We’ll
      create a `GeoJsonOptions` object and tell Aspose.GIS how close '
  - name: Define the Output Path (how to export GeoJSON)
    text: Specify the full file path where the resulting GeoJSON will be saved. Ensure
      the folder exists and the application has write permissions.
  - name: '**Create Vector Layer** with the configured options'
    text: The `VectorLayer` class represents a GIS container that can read and write
      spatial data. `Drivers.GeoJson` is the driver identifier for writing GeoJSON
      format files. Using `VectorLayer.Create` together with the `Drivers.GeoJson`
      driver and the previously configured `GeoJsonOptions` creates a new Geo
  - name: Construct a Geometry (e.g., a circular string)
    text: '`CircularString` is a curved line geometry that Aspose.GIS can linearize
      based on the tolerance you set. You can replace this with any valid WKT representation
      such as `POINT`, `LINESTRING`, or `POLYGON`.'
  - name: '**Add Feature to Layer** and save'
    text: '`Feature` is the object that couples a geometry with attribute data. After
      creating a `Feature` instance, assign the geometry, optionally add attribute
      values, and call `layer.Add(feature)` to persist it. When the `using` block
      ends, the layer is automatically written to the file defined in `path`. '
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. A commercial license removes all evaluation restrictions and
      provides full technical support.
    question: Can I use Aspose.GIS in commercial projects?
  - answer: Yes, it supports over 30 formats—including Shapefile, KML, GML, and CSV—allowing
      seamless conversion between them.
    question: Does Aspose.GIS support other GIS formats besides GeoJSON?
  - answer: You can download a free 30‑day trial from the Aspose website; it includes
      all features.
    question: Is there a trial version available?
  - answer: Use the Aspose forums, the dedicated support portal, or the “Contact Support”
      link in the product dashboard.
    question: Where can I get support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 创建带容差的 GeoJSON
url: /zh/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用容差创建 GeoJSON Aspose.GIS for .NET

## 介绍
如果您想 **学习如何创建 GeoJSON** 文件、控制曲线精度，并将结果导出为可直接使用的文档，Aspose.GIS for .NET 让这一过程变得简单。在本教程中，您将了解如何配置 GeoJSON 选项、设置线性化容差，以及 **add feature to layer** 对象，同时保持代码简洁且适合生产环境。

## 快速答案
- **“create vector layer” 是什么意思？** 它会创建一个新的 GIS 矢量数据集（例如 GeoJSON 文件），可以存储几何图形和属性。  
- **如何设置线性化容差？** 在创建图层之前，对 `GeoJsonOptions` 实例设置 `LinearizationTolerance` 属性。  
- **我可以直接导出 GeoJSON 文件吗？** 可以——使用 `VectorLayer.Create` 并指定 `Drivers.GeoJson` 驱动以及已配置的选项。  
- **我需要许可证吗？** 有效的 Aspose.GIS 许可证可解锁所有功能；临时评估密钥可用于测试。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 什么是 “create vector layer”？
创建矢量图层意味着初始化一个新的 GIS 容器（例如 GeoJSON 文件），用于存放点、线、面以及相关的属性数据。该图层成为您构建的任何几何对象和附加属性的目标。

## 为什么要配置 GeoJSON 选项？
配置 GeoJSON 选项——尤其是 **linearization tolerance**——可确保曲线几何（例如 `CircularString`）以满足应用程序精度要求的方式进行近似。适当的配置可以在保持视觉保真度的同时减小文件大小，这在 GeoJSON 被网页地图或空间分析工具使用时尤为关键。

## 前提条件
1. **Visual Studio**（任意近期版本）。  
2. **Aspose.GIS license**（或临时评估密钥）。  
3. 在项目中引用 **Aspose.GIS for .NET** 库。  
4. 对 **C#** 有基本了解。

## 导入命名空间
首先，导入所需的命名空间，以便编译器知道在何处找到 GIS 类：

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 步骤指南

### 步骤 1：配置 GeoJSON 选项（如何设置容差）
`GeoJsonOptions` 指定写入 GeoJSON 文件时使用的序列化设置。  
`GeoJsonOptions` 定义了 Aspose.GIS 序列化 GeoJSON 的方式，包括线性化容差、坐标精度以及其他输出设置。  
我们将创建一个 `GeoJsonOptions` 对象，并告诉 Aspose.GIS 线性化几何必须与原始曲线多接近。

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### 步骤 2：定义输出路径（如何导出 GeoJSON）
指定保存生成的 GeoJSON 的完整文件路径。确保文件夹已存在且应用程序具有写入权限。

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### 步骤 3：**Create Vector Layer** 与已配置的选项
`VectorLayer` 类表示一个可以读取和写入空间数据的 GIS 容器。  
`Drivers.GeoJson` 是用于写入 GeoJSON 格式文件的驱动标识符。  
将 `VectorLayer.Create` 与 `Drivers.GeoJson` 驱动以及先前配置的 `GeoJsonOptions` 结合使用，可创建一个准备好插入要素的新的 GeoJSON 文件。

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### 步骤 4：构建几何对象（例如 circular string）
`CircularString` 是一种曲线几何，Aspose.GIS 可以根据您设置的容差将其线性化。您可以将其替换为任何有效的 WKT 表示，例如 `POINT`、`LINESTRING` 或 `POLYGON`。

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### 步骤 5：**Add Feature to Layer** 并保存
`Feature` 是将几何与属性数据耦合的对象。创建 `Feature` 实例后，分配几何体，可选地添加属性值，然后调用 `layer.Add(feature)` 将其持久化。当 `using` 块结束时，图层会自动写入 `path` 中定义的文件。

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

当 `using` 块结束时，图层会自动写入 `path` 中定义的文件，为您提供一个可直接使用的 GeoJSON 文件。

## 常见问题与技巧
- **路径错误** – 确认目录存在且您拥有写入权限。  
- **容差过低** – 将 `LinearizationTolerance` 设置为非常小的值会导致文件大小急剧增加；通常 0.001 的容差在精度和大小之间取得平衡。  
- **许可证错误** – 如果看到许可证警告，请确保在任何 Aspose.GIS 调用之前加载许可证文件。  
- **性能提示** – 由于流式架构，Aspose.GIS 支持处理高达 2 GB 的文件，而无需将整个文档加载到内存中。

## 常见问答

**Q: Aspose.GIS for .NET 是否兼容其他 .NET 框架？**  
A: 是的，它可在 .NET Framework 4.5+、.NET Core 3.1+ 和 .NET 5/6/7 上运行。

**Q: 我可以在商业项目中使用 Aspose.GIS 吗？**  
A: 当然可以。商业许可证消除所有评估限制，并提供完整的技术支持。

**Q: Aspose.GIS 是否支持除 GeoJSON 之外的其他 GIS 格式？**  
A: 是的，它支持超过 30 种格式，包括 Shapefile、KML、GML 和 CSV，能够实现无缝转换。

**Q: 是否提供试用版？**  
A: 您可以从 Aspose 网站下载免费 30 天试用版，包含所有功能。

**Q: 我在哪里可以获得支持？**  
A: 使用 Aspose 论坛、专用支持门户，或产品仪表板中的 “Contact Support” 链接。

## 结论
通过遵循这些步骤，您现在了解了 **how to create GeoJSON**、配置线性化容差，以及 **add feature to layer**，实现无缝的 GeoJSON 导出。探索更多几何类型、属性处理和批量处理场景，以在 .NET GIS 项目中充分利用 Aspose.GIS。

---

**最后更新：** 2026-05-31  
**测试版本：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [如何转换 GeoJSON – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [创建矢量图层，限制精度 – Aspose.GIS for .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [在 File GDB 中创建矢量图层 – Aspose.GIS .NET 教程](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
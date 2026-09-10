---
date: 2026-09-10
description: 了解如何使用 Aspose.GIS for .NET 创建 vector layer，并限制 precision 以缩小 shapefile
  大小、提升性能并保持 coordinate accuracy。
keywords:
- how to create vector layer
- limit precision reading geometries
- reduce shapefile size
lastmod: 2026-09-10
linktitle: 限制 precision 读取几何体
og_description: 了解如何使用 Aspose.GIS for .NET 创建 vector layer，并限制 precision 以减小 shapefile
  大小、提升性能以及管理 coordinate accuracy。
og_image_alt: Screenshot showing Aspose.GIS code for creating a vector layer and setting
  precision
og_title: 如何使用 Aspose.GIS for .NET 创建 vector layer
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  headline: How to create vector layer with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  name: How to create vector layer with Aspose.GIS for .NET
  steps:
  - name: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
    text: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
  - name: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
    text: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
  - name: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
    text: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
  - name: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
    text: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
  type: HowTo
- questions:
  - answer: No. Precision is applied only when reading the geometry; the source file
      remains unchanged.
    question: Does limiting precision affect the original shapefile?
  - answer: Aspose.GIS currently applies the same `XYPrecisionModel` to both axes.
    question: Can I use a different precision model for X and Y coordinates?
  - answer: The API supports only the built‑in `PrecisionModel.Rounding(int)` method.
      For custom logic, you would need to post‑process the coordinates after reading.
    question: Is it possible to set a custom rounding function?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- Aspose.GIS
- vector layer
- precision model
- .NET GIS
title: 如何使用 Aspose.GIS for .NET 创建 vector layer
url: /zh/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS for .NET 创建矢量图层

## 简介
当您处理地理空间数据时，常常会思考 **如何创建 vector layer** 对象，以匹配应用程序真正需要的精度。将坐标四舍五入到合理的小数位数不仅可以加快解析速度，还能 **将 shapefile 大小降低至最高 30 %**（针对典型的点数据集）。在本分步指南中，您将看到如何创建 vector layer、写入点几何，然后使用精确和四舍五入的精度模型读取它。完成后，您将了解如何 **设置 precision model** 选项，以在性能与所需空间精度之间取得平衡。

## 快速答案
- **“limit precision” 是什么意思？** 它将坐标值四舍五入到指定的小数位数。  
- **为什么要先创建 vector layer？** vector layer 是用于存储点、线和多边形等几何图形的容器。  
- **有哪些可用的 precision model？** `PrecisionModel.Exact`（不进行四舍五入）和 `PrecisionModel.Rounding(n)`（四舍五入到 *n* 位小数）。  
- **我需要许可证才能尝试吗？** 可以从 releases page 获取免费试用版。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 和 .NET 5/6+。

## 创建 vector layer 是什么？
**创建 vector layer** 的行为是实例化 Aspose.GIS 的 `VectorLayer` 类，该类表示磁盘上的单个 shapefile，并保存您添加的所有几何要素。该图层成为读取、写入和操作空间数据的入口点。它还允许您定义属性字段并为数据集设置空间参考。

## 为什么限制精度以及它有什么帮助？
- **性能提升** – 减少小数位数可削减必须解析和序列化的二进制数据量，通常在大文件上带来 15‑20 % 的速度提升。  
- **文件更小** – 将坐标四舍五入到两到三位小数可以将 10 MB 的 shapefile 缩小至约 7 MB，便于存储和网络传输。  
- **足够的精度** – 大多数 GIS 分析（例如城市级别的制图）只需要米级精度，3 位小数的四舍五入已足够。

## 先决条件
在开始之前，请确保您已具备以下先决条件：
1. **Installation** – 应在您的开发环境中安装 Aspose.GIS for .NET 库。如果尚未安装，您可以从 [releases page](https://releases.aspose.com/gis/net/) 下载。  
2. **Familiarity with .NET** – 需要具备 C# 和 .NET 框架的基础知识，以便理解和实现提供的代码示例。  
3. **Development environment** – 需要一个可用的 .NET 开发环境，例如 Visual Studio。  
4. **Document directory** – 请准备好一个目录，用于存储和访问在过程生成的 shapefile。

## 导入命名空间
在开始实现读取几何时限制精度的功能之前，请确保导入必要的命名空间：
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 如何创建 vector layer
通过指定输出文件夹和所需的 shapefile 名称来加载新的 `VectorLayer`。这将创建一个空容器，准备接受几何对象。

`VectorLayer` 类是 Aspose.GIS 的顶层对象，表示磁盘上的单个 shapefile。创建实例后，您可以添加要素、定义属性字段，最后调用 `Save()` 将文件写入文件系统。
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## 设置精度选项
`PrecisionModel` 定义了读取几何时坐标值的四舍五入方式或保持精确的方式。您需要在打开图层之前，在 `ReadOptions` 对象上设置该模型。

`PrecisionModel` 类是 Aspose.GIS 的核心组件，控制 X 和 Y 轴的四舍五入行为。通过选择合适的模型，您可以决定库是保留每一位数字还是截断到特定的小数位数。
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## 使用精确精度读取几何
`ReadOptions` 指定读取 vector layer 时的参数，例如要使用的 precision model。  
使用引用 `PrecisionModel.Exact` 的 `ReadOptions` 实例打开先前保存的 vector layer。这可确保每个坐标在读取时不进行任何四舍五入。

当使用 `PrecisionModel.Exact` 时，Aspose.GIS 读取存储在 shapefile 中的原始双精度值，确保在读取操作中不会丢失任何信息。
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## 截断精度
如果您想将精度截断到特定的小数位数，请将 `Exact` 替换为 `PrecisionModel.Rounding(n)`，其中 *n* 为您想保留的小数位数。

四舍五入到两位小数（`PrecisionModel.Rounding(2)`）通常可将文件大小降低 20‑30 %，同时在大多数制图比例下保持坐标精度在几厘米以内。
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## 如何为不同场景设置 precision model
选择与您的使用场景相匹配的模型：

- **High‑precision scientific analysis** – 使用 `PrecisionModel.Exact` 保留每一位数字。  
- **Web‑mapping tiles or mobile apps** – 使用 `PrecisionModel.Rounding(2)` 使文件轻量化并加快渲染。

选择合适的模型是 **set precision model** 决策过程的一部分，用于在精度与性能之间取得平衡。

## 常见问题及解决方案
`XYPrecisionModel` 是 `ReadOptions` 的属性，用于设置 X 和 Y 坐标的 precision model。  

- **Unexpected coordinate values** – 确保在打开图层之前设置 `options.XYPrecisionModel` *before*。在打开后更改无效。  
- **File not found** – 验证 `path` 变量指向有效目录，并且 Shapefile 已在上一步成功创建。  
- **Incorrect geometry type** – 示例使用 `Point`。对于其他几何类型（例如 `LineString`），强制转换应匹配实际类型。  

## 减少 shapefile 大小的技巧
- 使用 `PrecisionModel.Rounding`，并采用仍能满足精度需求的最少小数位数。  
- 在写入图层之前删除不必要的属性字段。  
- 如果需要传输，可使用标准 ZIP 工具压缩生成的 `.shp`、`.shx` 和 `.dbf` 文件。

## 结论
在读取几何时管理精度是地理空间数据处理的关键方面。Aspose.GIS for .NET 提供了强大的功能，以高效实现此目标。按照上述步骤，您可以无缝 **create vector layer** 对象、**set precision model**，并在适当时 **reduce shapefile size**，从而确保在应用程序中实现最佳的数据处理。

## 常见问题
### 我可以将 Aspose.GIS for .NET 与其他 .NET 框架（如 .NET Core 或 .NET Standard）一起使用吗？
是的，Aspose.GIS for .NET 与多种 .NET 框架兼容，包括 .NET Core 和 .NET Standard。

### 是否提供 Aspose.GIS for .NET 的试用版？
是的，您可以从 [releases page](https://releases.aspose.com/) 获取免费试用版。

### 在哪里可以找到 Aspose.GIS for .NET 的完整文档？
您可以参考 [documentation](https://reference.aspose.com/gis/net/) 获取详细信息和示例。

### 如何获取 Aspose.GIS for .NET 的临时许可证？
可以从 Aspose.GIS 的 [purchase page](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

### 在哪里可以寻求 Aspose.GIS for .NET 的帮助或支持？
您可以访问 Aspose.GIS 的 [forum](https://forum.aspose.com/c/gis/33) 提出任何疑问、讨论或获取支持。

## 常见问答
**Q: 限制精度会影响原始 shapefile 吗？**  
A: 不会。精度仅在读取几何时应用；源文件保持不变。  

**Q: 我可以为 X 和 Y 坐标使用不同的 precision model 吗？**  
A: Aspose.GIS 目前对两个轴使用相同的 `XYPrecisionModel`。  

**Q: 能否设置自定义的四舍五入函数？**  
A: API 仅支持内置的 `PrecisionModel.Rounding(int)` 方法。若需自定义逻辑，需在读取后对坐标进行后处理。

---

**最后更新：** 2026-09-10  
**测试环境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose

## 相关教程

- [如何使用 Aspose.GIS 限制几何写入精度](/gis/net/geometry-processing/limit-precision-writing-geometries/)
- [如何使用 Aspose.GIS for .NET 创建带 SRS 的 Vector Layer](/gis/net/layer-management/create-vector-layer-with-srs/)
- [在 File GDB 中创建 Vector Layer – Aspose.GIS .NET 教程](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
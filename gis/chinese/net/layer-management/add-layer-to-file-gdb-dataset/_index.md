---
date: 2026-01-13
description: 了解如何使用 Aspose.GIS 向 File GDB 数据集添加图层，并支持空间参考 WGS84。请按照本分步指南在 .NET 中向
  GDB 添加图层。
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: 空间参考 WGS84 – 使用 Aspose.GIS 向 GDB 添加图层
url: /zh/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# spatial reference wgs84 – 使用 Aspose.GIS 向 GDB 添加图层

## Introduction
准备好使用 Aspose.GIS for .NET 提升您的 GIS 工作流了吗？在本教程中，您将学习**如何向 File GDB 数据集添加图层**，并使用**spatial reference wgs84**坐标系统。我们将逐步演示，从准备数据文件夹到验证新创建的图层，让您能够自信地操作地理数据。

## Quick Answers
- **使用的主要坐标系统是什么？** spatial reference wgs84 (WGS 84)  
- **哪个库提供了 API？** Aspose.GIS for .NET  
- **测试是否需要许可证？** 是 – 可使用临时 Aspose 许可证。  
- **可以向新图层添加属性吗？** 当然，您可以定义任意数量的要素属性。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6。

## What is spatial reference wgs84?
spatial reference wgs84（World Geodetic System 1984，世界大地测量系统 1984）是最广泛使用的地理坐标系统。它以度为单位定义纬度和经度，并作为许多 GIS 数据集的默认 CRS，包括本指南中将创建的数据集。

## Why use Aspose.GIS to add a layer?
- **无外部依赖：** 开箱即用，使用纯 .NET 代码。  
- **完全控制模式：** 您可以定义自定义属性和几何类型。  
- **跨平台：** 兼容 Windows、Linux 和 macOS 运行时。  
- **灵活授权：** 临时许可证让您在正式使用前快速评估。

## Prerequisites
在开始之前，请确保您已具备：

- Aspose.GIS for .NET 库：从 [Aspose.GIS for .NET 文档](https://reference.aspose.com/gis/net/) 下载并安装该库。  
- 文档目录：在您的机器上创建专用文件夹以存储 GIS 文件。

## Import Namespaces
将所需的 `using` 语句添加到您的 C# 项目中，以便访问 Aspose.GIS 类：

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step 1: Copy Directory
首先，复制包含原始 GDB 数据集的文件夹。保留副本可以在实验时保护源数据。

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Step 2: Open Dataset and Verify Creation Capability
打开新复制的数据集，并确认它能够创建新图层。`CanCreateLayers` 属性应返回 **True**。

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Step 3: Create and Populate a New Layer with spatial reference wgs84
现在我们创建一个名为 **data** 的图层，并显式将其空间参考设置为 **Wgs84**。我们还添加一个名为 **Name** 的简单属性，并插入一个点要素。

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## Step 4: Open and Validate the Added Layer
最后，打开刚创建的图层并验证其内容。控制台将显示该图层包含一个要素，并且 **Name** 属性与我们设置的值相匹配。

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Common Issues & Tips
- **路径错误：** 确保 `dataDir` 以路径分隔符（`/` 或 `\`）结尾，以便拼接的字符串形成有效的文件路径。  
- **许可证错误：** 如果看到许可证警告，请在运行代码前从 Aspose 门户申请临时许可证。  
- **CRS 不匹配：** 在其他 GIS 工具中打开该图层时，确认该工具识别 WGS 84（EPSG:4326）为坐标系统。

## Frequently Asked Questions
### Q: 我可以将 Aspose.GIS for .NET 与其他 GIS 库一起使用吗？
Aspose.GIS for .NET 设计为独立工作，但可以与其他库集成以实现更强的功能。

### Q: 是否提供用于测试的临时许可证？
是的，您可以从 [此处](https://purchase.aspose.com/temporary-license/) 获取临时许可证用于测试和评估。

### Q: Aspose.GIS for .NET 支持哪些空间参考系统？
Aspose.GIS for .NET 支持广泛的空间参考系统，为地理数据处理提供灵活性。

### Q: 我可以为 Aspose.GIS 社区做贡献吗？
当然！加入讨论并在 [Aspose.GIS 论坛](https://forum.aspose.com/c/gis/33) 分享您的经验。

### Q: 在哪里可以找到 Aspose.GIS for .NET 的详细文档？
在 [此处](https://reference.aspose.com/gis/net/) 查看完整文档，获取 Aspose.GIS for .NET 的深入信息。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-01-13  
**测试环境：** Aspose.GIS for .NET (latest stable version)  
**作者：** Aspose
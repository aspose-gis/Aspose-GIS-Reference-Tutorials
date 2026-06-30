---
date: 2026-06-30
description: 了解如何使用 Aspose.GIS for .NET 在 File Geodatabase 中创建矢量图层。使用 spatial reference
  WGS84 和 file gdb 选项管理地理空间数据。
keywords:
- create vector layer
- add line feature
- manage geospatial data
- feature count example
- file gdb compression
linktitle: 使用单图层创建 File GDB
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  headline: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  type: TechArticle
- description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  name: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  steps:
  - name: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
    text: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
  - name: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
    text: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
  type: HowTo
- questions:
  - answer: It means adding a new vector dataset (points, lines, or polygons) to a
      geodatabase file.
    question: What does “create vector layer” mean?
  - answer: Aspose.GIS for .NET provides full support for File GDB creation and editing.
    question: Which library should I use?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `SpatialReferenceSystem.Wgs84` for the common WGS84 datum.
    question: Can I set the spatial reference?
  - answer: Less than 30 lines to create the GDB, add a line feature, and read back
      the feature count.
    question: How many lines of code?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 在 File GDB 中创建矢量图层 – Aspose.GIS .NET 教程
url: /zh/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在文件 GDB 中创建矢量图层

## 介绍
如果您需要在文件地理数据库（GDB）中**创建矢量图层**并高效管理地理空间数据，Aspose.GIS for .NET 为您提供了简洁的代码优先方法。在本分步指南中，我们将展示如何写入线要素、配置文件 GDB 选项，并使用空间参考 WGS84——全部只需几行 C# 代码。完成后，您将能够统计图层中的要素数量，并将生成的 GDB 集成到任何 .NET 制图或分析工作流中。

## 快速解答
- **“create vector layer” 是什么意思？** 它指的是向地理数据库文件中添加一个新的矢量数据集（点、线或多边形）。  
- **我应该使用哪个库？** Aspose.GIS for .NET 完全支持文件 GDB 的创建和编辑。  
- **开发时需要许可证吗？** 免费试用可用于测试；生产环境需要商业许可证。  
- **我可以设置空间参考吗？** 可以——使用 `SpatialReferenceSystem.Wgs84` 来指定常用的 WGS84 基准。  
- **需要多少行代码？** 少于 30 行代码即可创建 GDB、添加线要素并读取要素计数。

## 什么是“创建矢量图层”操作？
创建矢量图层即在地理数据库中定义一个新表，用于存储几何对象（点、线、多边形）及其属性。每一行代表一个要素，几何列保存其形状。在 Aspose.GIS 中，您可以通过在 `FileGdbDataSource` 中实例化 `FeatureClass` 并指定几何类型来创建它。

## 为什么使用 Aspose.GIS 来创建矢量图层？
Aspose.GIS 消除外部依赖并支持 **50+** 种 GIS 格式，成为 .NET 开发者的一站式解决方案。  
它内置文件 GDB 压缩（对典型矢量数据可降低至 70 %），空间索引，并开箱即用地完整支持 WGS84。该库兼容 .NET Framework 4.6+、.NET Core 2.0+ 以及 .NET 5/6，您可以针对任何现代 Windows 或跨平台环境，无需额外的本机库。

## 前置条件
在开始之前，请确保您已具备以下条件：

1. **Aspose.GIS for .NET** – 从 [Aspose.GIS for .NET 下载页面](https://releases.aspose.com/gis/net/) 下载。  
2. **.NET 开发环境** – Visual Studio、Rider 或 `dotnet` CLI。  
3. **一个文件夹** 用于创建 File GDB（我们将其称为 *Your Document Directory*）。

## 导入命名空间
`using` 语句将所需类型引入作用域。  

`Document` 命名空间提供核心 GIS 对象，而 `System.IO` 负责文件路径。

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```

## 步骤 1：设置文档目录
将 `"Your Document Directory"` 替换为您希望 File GDB 所在的绝对路径。  
提前创建目录可避免新手常遇到的 “File not found” 错误。

```csharp
string dataDir = "Your Document Directory";
```

## 步骤 2：创建带单一图层的文件地理数据库
FileGdbOptions 是一个类，可让您配置文件地理数据库的压缩、空间索引等设置。  
此代码片段使用 `FileGdbOptions` **创建矢量图层**，写入一个简单的线要素，并将其存储在使用 **空间参考 WGS84** 的 File GDB 中。

```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```

## 步骤 3：打开文件地理数据库并获取图层信息
`FileGdbDataSource` 是创建和打开文件地理数据库的入口点。  
`FeatureClass` 表示地理数据库中的矢量图层，并提供对其要素的访问。  
这里我们通过打开数据集并打印要素数量来 **统计图层中的要素**——本例中为 `1`。

```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```

## 如何验证图层是否正确创建？
使用 `FileGdbDataSource.Open` 打开地理数据库并查询 `FeatureClass`。`Count` 属性返回要素总数，确认该线要素已持久化。此快速验证步骤有助于及早发现问题，尤其在批量导入自动化时。

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| **`File not found`** | `path` 变量不正确 | 验证 `dataDir` 指向现有文件夹，并且 `path` 正确组合文件名，例如 `Path.Combine(dataDir, "MyData.gdb")`。 |
| **`Unsupported geometry`** | 使用了 File GDB 不支持的几何类型 | 对基本图层请使用 `Point`、`LineString` 或 `Polygon`。 |
| **`License not set`** | 生产环境未设置有效许可证 | 使用 `License license = new License(); license.SetLicense("Aspose.GIS.lic");` 注册许可证。 |

## 常见问题
### 我可以在现有的 .NET 项目中使用 Aspose.GIS for .NET 吗？
可以，Aspose.GIS for .NET 可以无缝集成到您现有的 .NET 项目中。

### 是否提供 Aspose.GIS for .NET 的试用版？
是的，您可以通过下载 [免费试用版](https://releases.aspose.com/) 来体验 Aspose.GIS for .NET 的功能。

### 在哪里可以找到 Aspose.GIS for .NET 的详细文档？
请参阅 [文档](https://reference.aspose.com/gis/net/) 获取关于 Aspose.GIS for .NET 的完整信息。

### 如何获取 Aspose.GIS for .NET 的支持？
访问 [Aspose.GIS 论坛](https://forum.aspose.com/c/gis/33) 获取社区支持和帮助。

### 是否提供 Aspose.GIS for .NET 的临时许可证？
是的，您可以获取 Aspose.GIS for .NET 的 [临时许可证](https://purchase.aspose.com/temporary-license/)。

---

**最后更新：** 2026-06-30  
**测试环境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose

## 相关教程

- [使用 Aspose.GIS 创建文件地理数据库 .NET 数据集](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [创建矢量图层并设置图层空间参考系统](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [如何使用 Aspose.GIS 从文件 GDB 数据集删除图层](/gis/net/layer-data-operations/remove-layers-from-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
date: 2026-01-10
description: 学习如何使用 Aspose.GIS for .NET 在文件地理数据库中创建矢量图层。使用空间参考 WGS84 和文件 gdb 选项管理地理空间数据。
linktitle: Create File GDB with Single Layer
second_title: Aspose.GIS .NET API
title: 在 File GDB 中创建矢量图层 – Aspose.GIS .NET 教程
url: /zh/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 File GDB 中创建矢量图层

## 介绍
如果您需要在文件地理数据库（File Geodatabase，GDB）中**创建矢量图层**并高效管理空间数据，Aspose.GIS for .NET 为您提供了简洁的代码优先（code‑first）方式。在本分步指南中，我们将演示如何写入线要素、配置 File GDB 选项以及使用空间参考 WGS84——全部只需几行 C# 代码。完成后，您即可统计图层中的要素数量，并将生成的 GDB 集成到任何 .NET 制图或分析工作流中。

## 快速答案
- **“创建矢量图层”是什么意思？** 这指的是向地理数据库文件中添加一个新的矢量数据集（点、线或面）。  
- **应该使用哪个库？** Aspose.GIS for .NET 完全支持 File GDB 的创建与编辑。  
- **开发阶段需要许可证吗？** 免费试用可用于测试；生产环境需购买商业许可证。  
- **可以设置空间参考吗？** 可以——使用 `SpatialReferenceSystem.Wgs84` 来指定常用的 WGS84 基准。  
- **需要多少行代码？** 不到 30 行代码即可完成 GDB 的创建、线要素的添加以及要素计数的读取。

## “创建矢量图层”操作是什么？
创建矢量图层意味着在地理数据库内部定义一个新表，用于存储几何对象（点、线、面）及其属性。此操作是任何需要**管理空间数据**的 GIS 应用的基础。

## 为什么使用 Aspose.GIS 来创建矢量图层？
- **零外部依赖** —— API 可直接在 .NET Framework、.NET Core 以及 .NET 5/6 上使用。  
- **完整支持 File GDB** —— 您可以通过 `FileGdbOptions` 配置压缩、空间索引等参数。  
- **内置空间参考处理** —— 只需传入 `SpatialReferenceSystem.Wgs84` 即可在全球坐标系下工作。  
- **简洁的 API** —— 编写线要素、将其添加到图层，并通过少量方法调用获取要素计数。

## 前置条件
在开始之前，请确保您已具备以下条件：

1. **Aspose.GIS for .NET** —— 请从[Aspose.GIS for .NET 下载页面](https://releases.aspose.com/gis/net/)获取。  
2. **.NET 开发环境** —— Visual Studio、Rider 或 `dotnet` CLI。  
3. **一个文件夹** 用于存放将要创建的 File GDB（我们称之为 *Your Document Directory*）。

## 导入命名空间
在 C# 文件顶部添加所需的 `using` 语句：

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
```csharp
string dataDir = "Your Document Directory";
```
将 `"Your Document Directory"` 替换为您希望 File GDB 所在的绝对路径。

## 步骤 2：创建仅包含单一图层的 File Geodatabase
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
此代码片段使用 `FileGdbOptions` **创建矢量图层**，写入一个简单的线要素，并将其存储在使用**空间参考 WGS84**的 File GDB 中。

## 步骤 3：打开 File Geodatabase 并获取图层信息
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```
这里我们通过打开数据集并打印要素数量来**统计图层要素**——本例中为 `1`。

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **`File not found`** | `path` 变量不正确 | 确认 `dataDir` 指向已存在的文件夹，并且 `path` 正确组合了文件名，例如 `Path.Combine(dataDir, "MyData.gdb")`。 |
| **`Unsupported geometry`** | 使用了 File GDB 不支持的几何类型 | 对基本图层请仅使用 `Point`、`LineString` 或 `Polygon`。 |
| **`License not set`** | 生产环境未使用有效许可证 | 使用 `License license = new License(); license.SetLicense("Aspose.GIS.lic");` 注册许可证。 |

## 常见问答
### 我可以在现有的 .NET 项目中使用 Aspose.GIS for .NET 吗？
可以，Aspose.GIS for .NET 可无缝集成到您现有的 .NET 项目中。

### 是否提供 Aspose.GIS for .NET 的试用版？
可以，您可以通过下载[免费试用版本](https://releases.aspose.com/)来体验 Aspose.GIS for .NET 的功能。

### 哪里可以找到 Aspose.GIS for .NET 的详细文档？
请参阅[文档](https://reference.aspose.com/gis/net/)获取 Aspose.GIS for .NET 的完整信息。

### 如何获取 Aspose.GIS for .NET 的技术支持？
访问[Aspose.GIS 论坛](https://forum.aspose.com/c/gis/33)获取社区支持与帮助。

### 是否提供 Aspose.GIS for .NET 的临时许可证？
可以，您可以获取[Aspose.GIS for .NET 的临时许可证](https://purchase.aspose.com/temporary-license/)。

---

**最后更新：** 2026-01-10  
**测试环境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
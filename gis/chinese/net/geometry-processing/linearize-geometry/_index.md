---
date: 2025-12-21
description: 学习如何使用 Aspose.GIS for .NET 对几何进行线性化，实现 .NET 应用中的高效地理空间数据处理、空间分析和几何操作。
linktitle: Linearize a Geometry
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 将几何体线性化
url: /zh/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 线性化几何

## 介绍
如果您需要**如何线性化几何**用于制图、空间分析或数据交换任务，Aspose.GIS for .NET 为您提供了一种简洁的编程方式来实现。在本教程中，我们将通过一个完整的真实案例，展示如何将包含曲线和复合形状的复杂几何体转换为可在任何 GIS 系统中使用的简单线性表示。

## 快速答案
- **线性化几何意味着什么？** 将曲线和复杂形状转换为直线段。  
- **为什么使用 Aspose.GIS？** 它支持数十种 GIS 格式，并且在无需外部工具的情况下处理几何转换。  
- **前提条件？** .NET Framework 或 .NET Core、Visual Studio 和 Aspose.GIS 库。  
- **示例运行需要多长时间？** 安装库后运行时间不到五分钟。  
- **我可以保存为其他格式吗？** 可以——将 KML 驱动程序替换为 Shapefile、GeoJSON 等。

## 什么是线性化几何？
线性化几何是指将任何曲线或复合形状拆分为一系列直线段（即“线性几何”）。这简化了渲染、分析以及与仅能识别线和点的工具之间的互操作性。

## 为什么要线性化几何？
- **性能：** 线性几何在渲染和查询时更快。  
- **兼容性：** 许多 GIS 平台（例如旧的地图服务）仅接受线性要素。  
- **简化：** 适用于创建缩略图、快速预览或向需要线性输入的算法提供数据。

## 前提条件
在深入代码之前，请确保您已拥有：

1. **Aspose.GIS for .NET** – 从 [Aspose.GIS 网站](https://releases.aspose.com/gis/net/) 下载。  
2. **.NET Framework**（或 .NET Core）已在开发机器上安装。  
3. **Visual Studio**（或任何兼容 C# 的 IDE）用于编写和执行示例。

## 导入命名空间
要开始使用 Aspose.GIS 功能，请导入所需的命名空间。

### 步骤 1：导入 Aspose.GIS 核心命名空间
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### 步骤 2：导入目标格式的驱动程序
在本示例中，我们将把结果写入 KML 文件：
```csharp
using Aspose.GIS.Kml;
```

## 如何线性化几何 – 步骤指南
下面是对每行代码的详细讲解，解释**如何线性化几何**以及每一步的重要性。

### 步骤 1：定义输出路径
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
将 `"Your Document Directory"` 替换为您希望保存 KML 文件的文件夹路径。

### 步骤 2：为输出文件创建图层
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
*图层*是地理要素的容器。这里我们创建一个新的 KML 图层，用于保存线性化后的几何体。

### 步骤 3：构建新要素
```csharp
var feature = layer.ConstructFeature();
```
*要素*代表单个地理对象（点、线、多边形等）。我们将把线性几何附加到此要素上。

### 步骤 4：定义原始复杂几何体
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
我们使用 Well‑Known Text（WKT）字符串创建几何体。此示例包括 `LineString`、`CompoundCurve` 和 `CircularString`——非常适合演示线性化。

### 步骤 5：线性化几何体
```csharp
var linear = geometry.ToLinearGeometry();
```
`ToLinearGeometry()` 方法将所有曲线转换为直线段，生成原始几何体的*线性*版本。

### 步骤 6：将线性几何分配给要素
```csharp
feature.Geometry = linear;
```
现在要素包含了简化后的线性几何体。

### 步骤 7：将要素添加到图层
```csharp
layer.Add(feature);
```
最后，我们将要素添加到 KML 图层，当 `using` 块结束时，它会将线性几何写入输出文件。

## 常见问题与技巧
- **路径分隔符：** 使用 `Path.Combine` 进行跨平台路径构建。  
- **大型几何体：** 对非常复杂的形状进行线性化可能会产生大量顶点；如果需要更少的点，可在线性化后使用 `Simplify()`。  
- **驱动程序选择：** 如需不同的输出格式，可将 `Drivers.Kml` 替换为 `Drivers.Shapefile`、`Drivers.GeoJson` 等，并相应调整文件扩展名。

## 结论
在本教程中，我们介绍了使用 Aspose.GIS for .NET **线性化几何**的完整过程，从环境搭建到将线性化结果写入 KML 文件。您现在可以将此工作流集成到制图应用、数据处理管道或任何需要简化几何体的 GIS 项目中。

## 常见问答
### 问：Aspose.GIS for .NET 是否兼容 .NET Core？
是的，Aspose.GIS for .NET 与 .NET Core 兼容，您可以构建跨平台应用程序。

### 问：我可以使用 Aspose.GIS for .NET 处理不同的 GIS 文件格式吗？
当然可以！Aspose.GIS 支持多种 GIS 文件格式，包括 KML、Shapefile、GeoJSON 等。

### 问：Aspose.GIS 是否提供空间操作和分析的支持？
是的，Aspose.GIS 提供广泛的空间操作和分析功能，以处理复杂的地理空间任务。

### 问：是否有 Aspose.GIS for .NET 的免费试用？
是的，您可以从 [Aspose 网站](https://releases.aspose.com/) 下载免费试用版。

### 问：在哪里可以找到 Aspose.GIS 的帮助和支持？
您可以访问 [Aspose.GIS 论坛](https://forum.aspose.com/c/gis/33) 获取社区和 Aspose 支持人员的帮助。

## 常见问题（补充）
**问：我可以线性化包含 3D（Z）坐标的几何体吗？**  
答：可以，`ToLinearGeometry()` 支持 2D 和 3D 几何体，Z 值会在生成的线段中保留。

**问：线性化会对输出文件的大小产生什么影响？**  
答：将曲线转换为大量短线段可能会增大文件大小。如果文件大小是关注点，可在线性化后使用 `Simplify()`。

**问：线性化时可以控制段长吗？**  
答：默认方法使用内部容差。若需自定义分段，可在调用 `ToLinearGeometry()` 前手动对曲线进行镶嵌。

---

**最后更新：** 2025-12-21  
**测试环境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
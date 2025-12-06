---
date: 2025-12-06
description: 学习如何使用 Aspose.GIS for .NET 在 C# 中创建 LineString，向 LineString 添加点，并检查几何对象是否覆盖另一个几何对象。
language: zh
linktitle: Create LineString C# – Check Geometry Covers Another
second_title: Aspose.GIS .NET API
title: 创建 LineString（C#）– 检查几何对象是否覆盖另一个
url: /net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 检查几何体覆盖另一个

## 介绍
Aspose.GIS for .NET 是一个功能强大的库，为开发人员提供在 .NET 应用程序中高效处理地理数据的工具。无论您是构建地图应用、分析空间数据，还是将地理功能集成到软件中，Aspose.GIS 都提供了一整套功能，帮助简化开发过程。在本教程中，您将学习 **如何在 C# 中创建 LineString**，向线段添加点，并使用 `Covers` 和 `CoveredBy` 方法执行 **点在线上检查**。

## 快速答案
- **“在 C# 中创建 LineString” 是什么意思？** 这意味着实例化一个 `LineString` 几何对象并向其填充坐标点。  
- **哪个方法用于检查点是否位于线上？** 在 `LineString` 上使用 `Covers` 方法，或在 `Point` 上使用 `CoveredBy` 方法。  
- **运行示例是否需要许可证？** 评估期间可使用临时许可证；生产环境需要正式许可证。  
- **可以在 .NET Core 上使用吗？** 可以，Aspose.GIS 支持 .NET Framework 和 .NET Core。  
- **LineString 可以添加多少个点？** 没有硬性限制，您可以根据空间分析的需要添加任意数量的点。

## 什么是 **create LineString C#**？
`LineString` 是一种几何形状，由按顺序连接的点组成的直线段构成。在 C# 中，您可以通过实例化 `Aspose.Gis.Geometries` 命名空间下的 `LineString` 类，然后使用 `AddPoint` 方法 **向 LineString 添加点**。

## 为什么使用 Aspose.GIS 进行点在线上检查？
- **精度** – 准确处理浮点计算和空间谓词。  
- **跨平台** – 支持 .NET Framework、.NET Core 以及 .NET 5/6+。  
- **丰富的 API** – 提供完整的空间关系方法集合（`Covers`、`CoveredBy`、`Intersects` 等）。  

## 前置条件
在使用 Aspose.GIS for .NET 之前，请确保已完成以下准备工作：

### 1. 安装 Visual Studio
确保系统已安装 Visual Studio。Aspose.GIS for .NET 可无缝集成到 Visual Studio 中，提供流畅的开发体验。

### 2. 获取 Aspose.GIS for .NET
从[官方网站](https://releases.aspose.com/gis/net/)下载 Aspose.GIS for .NET 库。您可以直接下载库文件，或使用 NuGet 等包管理器将其安装到项目中。

### 3. 熟悉 .NET Framework
掌握 .NET 框架和 C# 编程语言的基础知识，以便有效使用 Aspose.GIS for .NET。

### 4. 访问文档和支持
请参考[文档](https://reference.aspose.com/gis/net/)获取 Aspose.GIS API 和功能的详细信息。如遇问题或有疑问，可前往[Aspose.GIS 论坛](https://forum.aspose.com/c/gis/33)寻求帮助。

### 5. 可选：临时许可证
如果您正在试用 Aspose.GIS for .NET，可从[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证，以评估库的功能。

## 导入命名空间
在项目中使用 Aspose.GIS for .NET 之前，需要导入必要的命名空间：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

下面，我们将示例拆解为多个步骤，帮助您了解如何使用 Aspose.GIS for .NET **检查一个几何体是否覆盖另一个**。

## 如何 **create LineString C#** – 步骤指南

### 步骤 1：创建 LineString 对象
```csharp
var line = new LineString();
```
此处实例化一个新的 `LineString` 对象，表示二维空间中一系列相连的线段。

### 步骤 2：**向 LineString 添加点**
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
我们使用 `AddPoint` 方法 **向 LineString 添加点**。本例中添加了两个点：(0, 0) 和 (1, 1)，形成一条简单的对角线段。

### 步骤 3：创建 Point 对象
```csharp
var point = new Point(0, 0);
```
实例化一个 `Point` 对象，表示二维空间中的单个点。本例在坐标 (0, 0) 处创建了一个点。

### 步骤 4：执行 **点在线上检查** – 线段是否覆盖该点？
```csharp
Console.WriteLine(line.Covers(point));    // True
```
使用 `Covers` 方法检查线段是否覆盖该点。此情况下返回 `True`，因为点 (0, 0) 正好位于该线段上。

### 步骤 5：验证反向关系 – 点是否被线段覆盖？
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
同样使用 `CoveredBy` 方法检查点是否被线段覆盖。由于点 (0, 0) 位于线段上，返回 `True`。

## 常见问题及解决方案
| 问题 | 产生原因 | 解决办法 |
|------|----------|----------|
| `line.Covers(point)` 返回 `False`，即使点看起来在直线上 | 由于浮点精度，点坐标并非完全相同 | 对坐标使用 `Math.Round`，或使用容差检查 `line.Distance(point) < epsilon` |
| 缺少 `using Aspose.Gis.Geometries;` | 未导入命名空间导致编译错误 | 确认已添加导入语句（参见 **导入命名空间** 部分） |
| 运行时出现许可证异常 | 未加载有效许可证 | 使用 `License license = new License(); license.SetLicense("Aspose.GIS.lic");` 加载临时或正式许可证 |

## 常见问答

**问：我可以在商业项目中使用 Aspose.GIS for .NET 吗？**  
答：可以，获取相应许可证后，您可以在商业和非商业项目中使用 Aspose.GIS for .NET。

**问：Aspose.GIS for .NET 是否兼容 .NET Core？**  
答：是的，Aspose.GIS for .NET 同时兼容 .NET Framework 和 .NET Core 环境。

**问：Aspose.GIS for .NET 支持哪些 GIS 格式？**  
答：多种 GIS 格式，包括 Shapefile、GeoJSON、KML 等。

**问：我可以为 Aspose.GIS for .NET 的开发做贡献吗？**  
答：Aspose.GIS for .NET 为 Aspose 的专有库，不接受外部代码贡献。但您可以提供反馈和建议，以帮助改进产品。

**问：Aspose.GIS for .NET 的更新频率如何？**  
答：Aspose.GIS for .NET 会定期发布更新，包含新功能、改进和 bug 修复。请访问[官方网站](https://releases.aspose.com/gis/net/)获取最新版本信息。

## 结论
总之，Aspose.GIS for .NET 为 .NET 应用程序提供了强大的地理数据处理工具。通过上述步骤，您可以高效地 **在 C# 中创建 LineString**、**向 LineString 添加点**，并执行 **点在线上检查**，判断一个几何体是否覆盖另一个。这一能力提升了软件的空间分析功能，并为更高级的 GIS 操作打开了大门。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2025-12-06  
**测试环境：** Aspose.GIS for .NET（最新发布）  
**作者：** Aspose
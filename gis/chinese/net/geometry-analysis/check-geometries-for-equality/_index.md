---
title: 检查几何形状是否相等
linktitle: 检查几何形状是否相等
second_title: Aspose.GIS .NET API
description: 通过这个综合教程，了解如何使用 Aspose.GIS for .NET 检查 .NET 应用程序中的几何图形是否相等。
type: docs
weight: 10
url: /zh/net/geometry-analysis/check-geometries-for-equality/
---
## 介绍
Aspose.GIS for .NET 是一个功能强大的库，使开发人员能够在其 .NET 应用程序中高效地处理地理空间数据。无论您是构建地图应用程序、空间分析工具，还是将地理空间功能集成到现有软件中，Aspose.GIS 都能提供完成工作所需的工具。
## 先决条件
在深入使用 Aspose.GIS for .NET 之前，请确保满足以下先决条件：
### 安装.NET框架
确保您的系统上安装了 .NET Framework。您可以从 Microsoft 网站下载它。
### Aspose.GIS for .NET 库
从以下位置下载并安装 Aspose.GIS for .NET 库[下载页面](https://releases.aspose.com/gis/net/)。请按照文档中提供的安装说明进行操作。
### 开发环境
为 .NET 开发设置您的首选开发环境，例如 Visual Studio。

## 导入命名空间
在您的 .NET 应用程序中，导入必要的命名空间以使用 Aspose.GIS 功能：
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 第 1 步：定义几何形状
首先，定义要比较的几何形状。在此示例中，我们有两个几何图形：`geometry1`和`geometry2`.
```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```
## 第 2 步：检查几何形状是否相等
现在，使用以下命令检查几何图形在空间上是否相等`SpatiallyEquals`Aspose.GIS提供的方法。
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); //真的
```
这将打印`True`到控制台，因为`geometry1`和`geometry2`空间上是相等的。
## 第 3 步：修改几何图形
接下来我们来修改一下`geometry2`通过添加一个新点。
```csharp
geometry2.AddPoint(3, 3);
```
## 第 4 步：重新检查平等性
现在，重新检查修改后几何图形的相等性。
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); //错误的
```
这次，输出将是`False`因为由于进行了修改，几何形状在空间上不再相等`geometry2`.

## 结论
总之，Aspose.GIS for .NET 提供了在 .NET 应用程序中处理地理空间数据的强大工具。通过遵循此分步指南，您可以使用 Aspose.GIS 方法轻松检查几何图形是否相等。
## 常见问题解答
### 我可以将 Aspose.GIS for .NET 与其他 .NET 框架一起使用吗？
是的，Aspose.GIS for .NET 与各种 .NET 框架兼容，包括 .NET Core 和 .NET Standard。
### Aspose.GIS for .NET 是否有免费试用版？
是的，您可以从以下位置下载免费试用版：[发布页面](https://releases.aspose.com/).
### 在哪里可以找到 Aspose.GIS for .NET 的文档？
您可以在以下位置找到详细文档[Aspose.GIS 文档页面](https://reference.aspose.com/gis/net/).
### 如何获得 Aspose.GIS for .NET 支持？
您可以从 Aspose.GIS 社区论坛获得支持[这里](https://forum.aspose.com/c/gis/33).
### 我可以购买 Aspose.GIS for .NET 的临时许可证吗？
是的，您可以从[购买页面](https://purchase.aspose.com/temporary-license/).
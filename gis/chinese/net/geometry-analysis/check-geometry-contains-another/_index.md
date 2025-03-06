---
title: 检查几何体是否包含另一个几何体
linktitle: 检查几何体是否包含另一个几何体
second_title: Aspose.GIS .NET API
description: 探索 Aspose.GIS for .NET，这是一个强大的库，可在 .NET 应用程序中无缝集成地理空间数据。
weight: 14
url: /zh/net/geometry-analysis/check-geometry-contains-another/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 检查几何体是否包含另一个几何体

## 介绍
Aspose.GIS for .NET 是一个功能强大的库，使开发人员能够在其 .NET 应用程序中无缝地处理地理空间数据。无论您是构建地图应用程序、执行地理空间分析，还是将基于位置的功能集成到您的软件中，Aspose.GIS 都可以通过提供直观的 API 和强大的功能来简化流程。
## 先决条件
在深入使用 Aspose.GIS for .NET 之前，请确保您具备以下先决条件：
### 1..NET开发环境搭建
确保您的计算机上设置了有效的 .NET 开发环境。这包括正确安装和配置 .NET SDK。
### 2.Aspose.GIS安装
通过从发布页面下载库来安装 Aspose.GIS for .NET[这里](https://releases.aspose.com/gis/net/) 。按照文档中提供的安装说明进行操作[这里](https://reference.aspose.com/gis/net/)将 Aspose.GIS 集成到您的项目中。
### 3.C#的基本理解
熟悉 C# 编程语言，因为 Aspose.GIS for .NET 主要与 C# 一起使用。

## 导入命名空间
在您的 C# 项目中，导入必要的命名空间以利用 Aspose.GIS 功能：
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 第 1 步：定义几何对象
首先，使用 Aspose.GIS 类定义几何对象：
```csharp
var geometry1 = new Polygon();
geometry1.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 4),
    new Point(4, 4),
    new Point(4, 0),
    new Point(0, 0),
});
geometry1.AddInteriorRing(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 3),
    new Point(3, 3),
    new Point(3, 1),
    new Point(1, 1),
}));
var geometry2 = new Point(2, 2);
```
## 第 2 步：检查空间遏制
接下来，检查一个几何图形是否包含另一个几何图形：
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry2)); //错误的
```
## 第 3 步：定义另一个几何图形
定义另一个几何对象：
```csharp
var geometry3 = new Point(0.5, 0.5);
```
## 第 4 步：再次检查空间遏制
检查新定义的几何图形是否包含在第一个几何图形中：
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry3)); //真的
```
## 第 5 步：等效功能
明白`a.SpatiallyContains(b)`相当于`b.Within(a)`:
```csharp
Console.WriteLine(geometry3.Within(geometry1)); //真的
```

## 结论
总之，Aspose.GIS for .NET 提供了强大的工具来处理 .NET 应用程序中的地理空间数据。通过遵循本指南并利用提供的示例，您可以有效地执行空间包含检查并利用项目中的其他地理空间功能。
## 常见问题解答
### Q1：Aspose.GIS 与.NET Core 兼容吗？
答：是的，Aspose.GIS完全支持.NET Core，允许您跨不同平台开发地理空间应用程序。
### Q2：我可以使用 Aspose.GIS 执行地理空间分析吗？
答：当然，Aspose.GIS 提供了各种地理空间分析功能，包括空间查询、距离计算和几何操作。
### Q3：Aspose.GIS 的更新频率如何？
答：Aspose.GIS 定期发布更新以提高性能、添加新功能并解决任何报告的问题。您可以通过访问发布页面来了解最新情况。
### Q4：有 Aspose.GIS 用户的社区论坛吗？
答：是的，您可以加入 Aspose.GIS 社区论坛[这里](https://forum.aspose.com/c/gis/33)与其他用户联系、提出问题并分享您的经验。
### Q5：我可以在购买前试用Aspose.GIS吗？
答：当然，您可以通过下载免费试用版来探索 Aspose.GIS[这里](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

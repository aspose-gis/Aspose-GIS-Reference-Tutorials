---
title: 使用 Aspose.GIS 指定翻译时的 WKT 变体
linktitle: 指定翻译时的 WKT 变体
second_title: Aspose.GIS .NET API
description: 了解如何在 Aspose.GIS for .NET 中指定 WKT 变体，以有效控制空间数据表示格式和精度。
weight: 19
url: /zh/net/geometry-processing/specify-wkt-variant-on-translation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS 指定翻译时的 WKT 变体

## 介绍
Aspose.GIS for .NET 是一个功能强大的库，允许开发人员在其 .NET 应用程序中轻松使用地理信息系统 (GIS) 数据。 Aspose.GIS 提供的基本功能之一是能够在翻译过程中指定众所周知的文本 (WKT) 变体，使用户能够控制空间数据表示的格式和精度。在本教程中，我们将探索如何使用 Aspose.GIS for .NET 逐步指定 WKT 变体。
## 先决条件
在我们开始之前，请确保您具备以下先决条件：
1. Aspose.GIS for .NET：从以下位置下载并安装 Aspose.GIS for .NET[下载页面](https://releases.aspose.com/gis/net/).
2. 开发环境：确保您已设置 .NET 开发环境。
3. 基础知识：熟悉C#编程语言和.NET框架。

## 导入命名空间
在代码中使用 Aspose.GIS 功能之前，请导入必要的命名空间：
```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```
## 第 1 步：创建点对象
首先，创建一个`Point`具有纬度、经度和可选度量 (M) 值的对象：
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## 步骤 2：设置空间参考系统 (SRS)
将空间参考系统 (SRS) 分配给点对象。在本例中，我们使用 WGS84 空间参考系统：
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## 第 3 步：指定 WKT 变体
现在，指定要翻译的 WKT 变体。 Aspose.GIS 支持各种 WKT 变体，包括`Iso`, `SimpleFeatureAccessOutdated`， 和`ExtendedPostGis`。根据您的要求选择合适的变体：
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // M 点 (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); //点 (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```
## 第 4 步：控制数字格式
您可以控制 WKT 表示形式中坐标的数字格式。 Aspose.GIS 提供了指定小数精度的选项：
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); //点 M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // M 点 (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // M 点 (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // M 点 (23.573 25.342 40.3)
```

## 结论
在本教程中，我们学习了如何使用 Aspose.GIS for .NET 指定翻译时的 WKT 变体。通过遵循上述步骤，开发人员可以有效地控制.NET应用程序中空间数据表示的格式和精度，从而增强地理信息系统的灵活性和可用性。
## 常见问题解答
### Aspose.GIS 是否与所有版本的.NET 兼容？
是的，Aspose.GIS 支持 .NET Framework 4.0 及更高版本。
### 我可以将 Aspose.GIS 用于商业项目吗？
是的，Aspose.GIS 可用于个人和商业项目。
### Aspose.GIS是否提供对其他空间数据格式的支持？
是的，Aspose.GIS 支持多种空间数据格式，包括 ESRI Shapefile、GeoJSON 和 KML。
### Aspose.GIS 是否有免费试用版？
是的，您可以从以下位置下载 Aspose.GIS 的免费试用版：[这里](https://releases.aspose.com/).
### 我在哪里可以获得 Aspose.GIS 的帮助或支持？
您可以在 Aspose.GIS 社区发布您的疑问或寻求帮助：[论坛](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

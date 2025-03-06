---
title: 指定对象 ID 和几何字段名称
linktitle: 指定对象 ID 和几何字段名称
second_title: Aspose.GIS .NET API
description: 使用 Aspose.GIS for .NET 探索 GIS 魔力！轻松管理地理空间数据。立即下载并释放空间智能的力量。
weight: 20
url: /zh/net/layer-data-operations/specify-object-id-and-geometry-field-names/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 指定对象 ID 和几何字段名称

## 介绍
使用 Aspose.GIS for .NET 踏上地理信息系统 (GIS) 领域的旅程，为开发人员和爱好者打开了一个充满可能性的世界。这个强大的库使您能够轻松处理地理空间数据。在本教程中，我们将指导您完成指定对象 ID 和几何字段名称的过程，为您的 GIS 工作奠定基础。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
-  Aspose.GIS for .NET：从以下位置下载并安装该库[这里](https://releases.aspose.com/gis/net/).
- 文档目录：为文档设置一个目录以存储地理数据库。
- .NET 环境：确保您有一个有效的 .NET 环境。
## 导入命名空间
首先，您需要将必要的命名空间导入到您的项目中。这些命名空间提供了与 Aspose.GIS for .NET 交互的基本类和方法。
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```
## 第 1 步：指定对象 ID 和几何字段名称
在此步骤中，您将了解如何为 GIS 数据设置对象 ID 和几何字段名称。这对于高效的数据管理至关重要。
## 步骤1.1：设置文档目录
首先定义文档目录的路径：
```csharp
string dataDir = "Your Document Directory";
```
## 步骤1.2：创建地理数据库并定义选项
创建具有指定对象 ID 和几何字段名称的地理数据库：
```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         //指定对象 ID 字段名称
        GeometryFieldName = "POINT",       //指定几何字段名称
    };
```
## 步骤1.3：创建并添加图层
在地理数据库中创建一个图层并添加具有特定几何图形的要素：
```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  //指定几何形状（在本例中为点）
    layer.Add(feature);
}
```
## 步骤1.4：打开并检索层中的数据
打开图层并根据指定的对象 ID 从中检索数据：
```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); //输出：1
}
```
## 结论
恭喜！您已成功完成使用 Aspose.GIS for .NET 指定对象 ID 和几何字段名称的过程。这为您的 GIS 项目奠定了坚实的基础，使您能够轻松管理地理空间数据。
## 经常问的问题
### 问：我可以在我的 Web 应用程序中使用 Aspose.GIS for .NET 吗？
答：是的，Aspose.GIS for .NET 适用于桌面和 Web 应用程序，提供多种地理空间功能。
### 问：购买前有试用版吗？
答：是的，您可以通过免费试用版探索 Aspose.GIS for .NET 的功能[这里](https://releases.aspose.com/).
### 问：如何获得 Aspose.GIS for .NET 的临时许可证？
答：您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/)出于评估目的。
### 问：Aspose.GIS for .NET 支持哪些空间参考系统？
答：Aspose.GIS for .NET 支持各种空间参考系统，为不同的地理数据集提供了灵活性。
### 问：我可以在哪里寻求帮助或讨论与 Aspose.GIS 相关的问题？
答：访问 Aspose.GIS 论坛[这里](https://forum.aspose.com/c/gis/33)以寻求支持和讨论。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

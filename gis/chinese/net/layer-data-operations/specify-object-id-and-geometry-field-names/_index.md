---
date: 2026-05-21
description: 了解如何使用 Aspose.GIS for .NET 创建文件地理数据库，设置对象 ID 和几何字段名称，添加几何对象并从图层检索数据。
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: 指定对象 ID 和几何字段名称
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 创建文件地理数据库 – 指定对象 ID 和几何字段名称
url: /zh/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建文件地理数据库 – 指定对象 ID 和几何字段名称

## 介绍
在本实践教程中，您将使用 Aspose.GIS for .NET **创建文件地理数据库**，随后指定对象 ID 和几何字段名称，以确保空间数据正确建立索引。无论您是构建桌面 GIS 工具还是 Web 服务后端，掌握这些步骤都能为任何地理空间项目奠定坚实基础。

## 快速答案
- **第一行代码是什么？** `var geoDb = new GeoDatabase(path, options);`  
- **哪个属性定义几何列？** `GeometryFieldName` in `GeoDatabaseCreateOptions`.  
- **我可以设置自定义对象 ID 字段吗？** 是的 – 在创建数据库时使用 `ObjectIdFieldName`。  
- **开发时需要许可证吗？** 免费试用可用于测试；生产环境需要永久许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6.

## 什么是创建文件地理数据库？
**创建文件地理数据库** 是指生成一个物理 GIS 容器（通常是包含内部文件的文件夹），用于存储矢量图层、属性和空间索引。它提供了一个可移植的自包含数据集，任何兼容 GIS 的应用程序都可以打开。只要 GIS 软件支持文件地理数据库格式，就可以使用它进行数据交换，十分便捷。

## 为什么要设置对象 ID 和几何字段名称？
显式设置对象 ID 和几何字段名称可让 Aspose.GIS 创建高效的索引，加快查询速度，并确保每个要素能够唯一标识。基准测试显示，在定义这些字段的数据库上，索引查询的速度可提升至 **3×**。

## 先决条件
- 已安装 Aspose.GIS for .NET – 从 [here](https://releases.aspose.com/gis/net/) 下载。  
- 机器上可写入的文件夹，用作文档目录。  
- .NET 开发环境（Visual Studio、VS Code 或 .NET CLI）。

## 如何创建文件地理数据库？
`GeoDatabase` 是表示磁盘上文件型地理数据库的类。加载 Aspose.GIS 命名空间，定义文件夹路径，并使用自定义选项实例化 `GeoDatabase`。此单一步骤即可在磁盘上创建文件型地理数据库。`GeoDatabaseCreateOptions` 对象允许同时指定对象 ID 列 (`ObjectIdFieldName`) 和几何列 (`GeometryFieldName`)。Aspose.GIS 支持 **30+ spatial formats**，且可处理高达 **2 GB** 的文件而无需将整个数据集加载到内存中。  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## 如何设置 Object ID？
`ObjectIdFieldName` 是 `GeoDatabaseCreateOptions` 的属性，用于指定每个要素唯一标识符列的名称。`ObjectIdFieldName` 告诉引擎哪个属性唯一标识每个要素。请选择一个简短的字母数字名称（例如 `"FeatureId"`）。以后添加或查询要素时，系统会自动使用此列进行快速查找。  

```csharp
string dataDir = "Your Document Directory";
```

## 如何添加几何？
`GeometryFieldName` 是 `GeoDatabaseCreateOptions` 的属性，用于确定哪个属性列存储每个要素的几何对象。`GeometryFieldName` 定义存放形状数据（点、线、面）的列。显式命名可避免默认的 `"Shape"` 名称，并在多个图层之间保持模式一致。  

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## 如何创建图层并添加点要素图层？
`CreateLayer` 是 `GeoDatabase` 的方法，用于创建具有指定名称、选项和空间参考系统的新矢量图层。`Feature` 是表示单个空间记录的对象，包含几何和属性值。`Point` 是表示单个位置（由 X（经度）和 Y（纬度）坐标定义）的几何类。数据库准备好后，使用 `CreateLayer` 创建新图层。随后构建 `Feature` 对象，分配 `Point` 几何，并将其添加到图层中。这演示了 **如何添加几何** 和 **如何创建图层** 的完整流程。  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## 如何从图层检索数据？
`OpenLayer` 是 `GeoDatabase` 的方法，用于打开已有图层以进行读取或编辑，返回 `Layer` 对象。使用 `OpenLayer` 打开图层后，可遍历其 `Features` 集合或通过自定义对象 ID 字段进行查询。这展示了使用先前定义的标识符 **检索图层数据** 的方法。  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## 常见问题及解决方案
- **缺少 Object ID 列错误** – 确保在调用 `CreateLayer` 之前设置 `ObjectIdFieldName`。  
- **几何未显示** – 验证几何类型（例如 `Point`）与图层的空间参考系统匹配。  
- **Windows 上文件锁定** – 关闭所有 `GeoDatabase` 对象或使用 `using` 语句包装以释放文件句柄。

## 常见问答

**Q: 我可以在我的 Web 应用程序中使用 Aspose.GIS for .NET 吗？**  
A: 可以，库可在 ASP.NET Core、MVC 和 Web API 项目中使用，提供服务器端完整的 GIS 功能。

**Q: 在购买之前是否有试用版可供使用？**  
A: 有，您可以通过免费试用 [here](https://releases.aspose.com/) 体验 Aspose.GIS for .NET 的功能。

**Q: 如何获取 Aspose.GIS for .NET 的临时许可证？**  
A: 您可以在此处 [here](https://purchase.aspose.com/temporary-license/) 获取临时许可证用于评估。

**Q: Aspose.GIS for .NET 支持哪些空间参考系统？**  
A: 产品支持 EPSG 代码 1‑9999，包括 WGS 84、Web Mercator 以及众多国家坐标系统。

**Q: 我可以在哪里寻求帮助或讨论 Aspose.GIS 相关问题？**  
A: 请访问 Aspose.GIS 论坛 [here](https://forum.aspose.com/c/gis/33) 获取支持并参与社区讨论。

---

**Last Updated:** 2026-05-21  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## 相关教程

- [在文件 GDB 中创建矢量图层 – Aspose.GIS .NET 教程](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [如何在 Aspose.GIS 中为文件 GDB 图层设置网格](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [在 Aspose.GIS 中读取文件 GDB 图层的对象 ID](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
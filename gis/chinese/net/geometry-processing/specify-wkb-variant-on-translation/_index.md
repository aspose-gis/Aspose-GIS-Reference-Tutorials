---
date: 2026-06-10
description: 了解如何在 .NET 中创建 linestring 几何体，并使用 Aspose.GIS for .NET 的 ExtendedPostGis
  变体将几何体转换为 WKB。
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: 在翻译时指定 WKB 变体
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  headline: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  name: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  steps:
  - name: Creating a Geometry Object
    text: The `Geometry` class is Aspose.GIS's base type that represents any spatial
      object in memory. Linestring represents a series of connected points forming
      a linear geometry. In this step we instantiate a `Linestring` with a collection
      of coordinate pairs that model a simple road segment.
  - name: Generating WKB Representation
    text: '`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to
      include SRID in the output binary. Here we call the `AsBinary` method, passing
      the EWKB variant, which returns a `byte[]` containing the full binary representation.'
  - name: Writing to File
    text: '`File.WriteAllBytes` writes the binary array to disk. The resulting file
      (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB`
      function.'
  type: HowTo
- questions:
  - answer: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which
      PostGIS reads directly via `ST_GeomFromEWKB`.
    question: Can I use the EWKB file with PostGIS?
  - answer: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry
      from its binary form.
    question: Is it possible to read a WKB file back into a geometry object?
  - answer: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons,
      and many more spatial types.
    question: Does the library support other geometry types like polygons?
  - answer: Set the `SRID` property on the geometry object before calling `AsBinary`,
      e.g., `linestring.SRID = 4326;`.
    question: How do I specify a different SRID when creating the geometry?
  - answer: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6
      without modification.
    question: Will this code work on .NET Core?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 在 Aspose.GIS for .NET 中创建 Linestring 几何体并使用 WKB 变体
url: /zh/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.GIS for .NET 中创建线串几何和 WKB 变体

## 简介
如果您需要 **create linestring geometry .NET** 并将该几何体转换为二进制形式，Aspose.GIS for .NET 为您提供了一个简洁、高性能的 API，能够在 .NET Framework、.NET Core 和 .NET 5/6+ 上运行。在本教程中，我们将逐步演示所有步骤——从导入命名空间到写入 EWKB 文件——让您能够保留 SRID 信息，并将 GIS 数据集成到 PostgreSQL/PostGIS 或任何基于二进制的工作流中，轻松无忧。

## 快速答疑
- **What does WKB stand for?** Well‑Known Binary，是几何对象的紧凑二进制表示。  
- **Which WKB variant stores SRID?** `ExtendedPostGis` (EWKB) 变体会将 SRID 直接嵌入二进制中。  
- **Do I need a license?** 在生产部署中需要临时或完整的 Aspose.GIS 许可证。  
- **Which .NET versions are supported?** 支持 .NET Framework 4.5+、.NET Core 3.1+ 和 .NET 5/6+。  
- **How long does the implementation take?** 基本示例通常在 10 分钟以内完成。

## 什么是线串几何？
线串几何是一种由有序点列表通过直线段连接而成的简单形状。它是空间数据库中用于表示道路、管道或河流路径等线性要素的首选形式。

## 为什么要指定 WKB 变体？
使用正确的 WKB 变体可确保关键元数据——尤其是空间参考系统标识符 (SRID)——随几何体一起传递。`ExtendedPostGis` (EWKB) 变体将 SRID 存储在二进制负载中，从而实现与 PostGIS、Oracle Spatial 或任何需要 SRID 感知二进制的系统之间的无缝往返。

## 先决条件
在开始之前，请确保您具备以下条件：

### 安装 Aspose.GIS for .NET
1. 下载 Aspose.GIS：访问 [download link](https://releases.aspose.com/gis/net/) 获取最新的包。  
2. 将 NuGet 包添加到项目中（例如 `Install-Package Aspose.GIS`）。  

### 熟悉 C# 编程
- 基本了解 C# 语法和项目结构。  
- 能够运行 .NET 控制台或类库项目。

## 导入命名空间
`Aspose.GIS` 命名空间为您提供对所有几何相关类的访问。  

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

这些命名空间提供核心 GIS 功能，包括几何创建、转换和二进制序列化。

## 如何创建线串几何？
要创建线串，需要实例化一个带有有序坐标对列表的 `Linestring` 对象，如有必要设置其 SRID，然后将其序列化为所需的 WKB 变体。该过程包括三个步骤：构建几何体、选择 `ExtendedPostGis` 变体以保留 SRID，以及将生成的字节数组写入文件。

### 步骤 1：创建几何对象
`Geometry` 类是 Aspose.GIS 的基类型，表示内存中的任何空间对象。  
Linestring 表示一系列连接点，形成线性几何体。  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
在此步骤中，我们实例化一个 `Linestring`，使用一组坐标对来模拟一个简单的道路段。

### 步骤 2：生成 WKB 表示
`WkbVariant.ExtendedPostGis` 是一个枚举值，指示 Aspose.GIS 在输出二进制中包含 SRID。  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
这里我们调用 `AsBinary` 方法，传入 EWKB 变体，返回一个包含完整二进制表示的 `byte[]`。

### 步骤 3：写入文件
`File.WriteAllBytes` 将二进制数组写入磁盘。  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
生成的文件（`EWkbFile.ewkb`）可以使用 `ST_GeomFromEWKB` 函数直接导入到 PostGIS 表中。

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|-------|--------|----------|
| **Empty file** | `Path.Combine` 指向一个不存在的目录。 | 确保目标目录存在，或使用 `Directory.CreateDirectory` 创建它。 |
| **Incorrect SRID** | 使用默认的 `WkbVariant.Standard` 会丢失 SRID。 | 在需要保留 SRID 时，请始终使用 `WkbVariant.ExtendedPostGis`。 |
| **License exception** | 在生产环境中未使用有效许可证运行。 | 在生产环境中执行代码前，请应用临时或完整许可证。 |

## 常见问答
**Q: 我可以在 PostGIS 中使用 EWKB 文件吗？**  
A: 是的，`ExtendedPostGis` 变体生成包含 SRID 的 EWKB，PostGIS 可以通过 `ST_GeomFromEWKB` 直接读取。  

**Q: 是否可以将 WKB 文件读取回几何对象？**  
A: 当然。使用 `Geometry.FromBinary(byteArray)` 可以从二进制形式重建几何体。  

**Q: 该库是否支持其他几何类型，如多边形？**  
A: 是的，Aspose.GIS 支持点、线串、多边形、多多边形等多种空间类型。  

**Q: 创建几何体时如何指定不同的 SRID？**  
A: 在调用 `AsBinary` 之前，设置几何对象的 `SRID` 属性，例如 `linestring.SRID = 4326;`。  

**Q: 这段代码能在 .NET Core 上运行吗？**  
A: 可以，相同的 API 在 .NET Framework、.NET Core 和 .NET 5/6 上均可使用，无需修改。

---

**最后更新：** 2026-06-10  
**测试环境：** Aspose.GIS for .NET 23.9 (latest at time of writing)  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [使用 Aspose.GIS for .NET 将几何转换为 WKB 格式](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [使用 Aspose.GIS 指定 WKT 变体进行转换](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [使用 Aspose.GIS for .NET 创建 MultiLineString 几何](/gis/net/geometry-creation/create-multilinestring-geometry/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
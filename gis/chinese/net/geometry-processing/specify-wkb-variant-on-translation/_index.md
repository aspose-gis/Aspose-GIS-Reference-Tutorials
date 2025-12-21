---
date: 2025-12-21
description: 学习如何使用 Aspose.GIS for .NET 的 ExtendedPostGis 变体创建线串几何并将几何转换为 WKB。
linktitle: Specify WKB Variant on Translation
second_title: Aspose.GIS .NET API
title: 在 Aspose.GIS .NET 中创建线串几何和 WKB 变体
url: /zh/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.GIS for .NET 中指定 WKB 变体进行转换

## 介绍
在地理信息系统（GIS）开发领域，Aspose.GIS for .NET 以其强大的工具集脱颖而出。如果您需要 **创建 linestring 几何体** 并随后 **将几何体转换为 WKB**，这里就是您的理想之地。其多功能性和高效性使其成为开发者在 .NET 应用程序中无缝集成 GIS 功能的首选。本篇文章提供了使用 Aspose.GIS for .NET 的完整指南，特别聚焦于在转换过程中指定 WKB（Well‑Known Binary）变体。

## 快速答案
- **WKB 代表什么？** Well‑Known Binary，几何对象的紧凑二进制表示。  
- **哪种 WKB 变体可以存储 SRID 信息？** `ExtendedPostGis`（EWKB）变体。  
- **运行代码是否需要许可证？** 生产环境需要临时或正式许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+，以及 .NET 5/6+。  
- **实现大概需要多长时间？** 基本示例通常在 10 分钟以内完成。

## 什么是 Linestring 几何体？
Linestring 是由一系列点通过直线段相连组成的简单几何形状。它常用于表示道路、河流或 GIS 数据中的任何线性特征。

## 为什么要指定 WKB 变体？
选择合适的 WKB 变体可确保在存储或交换几何数据时保留重要的元数据——例如空间参考系统标识符（SRID）。`ExtendedPostGis` 变体（EWKB）在处理 PostgreSQL/PostGIS 或任何需要在二进制中嵌入 SRID 信息的系统时尤为有用。

## 前置条件
在深入了解 Aspose.GIS for .NET 中指定 WKB 变体的细节之前，请确保已满足以下前置条件：

### 安装 Aspose.GIS for .NET
1. 下载 Aspose.GIS：访问 [download link](https://releases.aspose.com/gis/net/) 获取 Aspose.GIS for .NET 包。  
2. 安装包：按照文档中的安装说明，将 Aspose.GIS 无缝集成到您的 .NET 环境中。

### 熟悉 C# 编程
1. 基础 C# 知识：确保您具备 C# 编程语言的基本语法和概念。

## 导入命名空间
要启动 Aspose.GIS for .NET 并有效利用其功能，您需要在项目中导入必要的命名空间。以下是分步指南：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

这些命名空间提供了对 Aspose.GIS 功能的访问，使您能够轻松处理地理数据。

## 如何创建 linestring 几何体？
让我们将示例拆解为多个步骤，深入了解在转换过程中指定 WKB 变体的完整流程。

### 步骤 1：创建几何对象
```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
在此步骤中，我们 **创建一个 linestring 几何体**，该几何体使用指定的坐标表示线性特征。

### 步骤 2：生成 WKB 表示
```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
这里，我们 使用 `ExtendedPostGis` 变体 **将几何体转换为 WKB**，该变体会嵌入 SRID 信息。

### 步骤 3：写入文件
```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
最后，我们将生成的 WKB 二进制数据写入名为 `EWkbFile.ewkb` 的文件，存放在您选择的目录中。

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **文件为空** | `Path.Combine` 指向了不存在的目录。 | 确保目标目录存在，或使用 `Directory.CreateDirectory` 创建它。 |
| **SRID 不正确** | 使用默认的 `WkbVariant.Standard` 会丢失 SRID。 | 在需要保留 SRID 时始终使用 `WkbVariant.ExtendedPostGis`。 |
| **许可证异常** | 在生产环境中未使用有效许可证运行。 | 在生产环境执行代码前应用临时或正式许可证。 |

## 常见问答
### Aspose.GIS for .NET 是否兼容所有 .NET 版本？
Aspose.GIS for .NET 设计为兼容多种 .NET 版本，确保开发者拥有灵活性和可访问性。

### 使用 Aspose.GIS for .NET 时，我可以请求支持或帮助吗？
可以，您可以通过专门的 [Aspose.GIS 论坛](https://forum.aspose.com/c/gis/33) 寻求支持，专家和其他开发者会帮助解答您的疑问。

### Aspose.GIS for .NET 是否提供免费试用？
是的，您可以通过 [此链接](https://releases.aspose.com/) 获取免费试用，体验 Aspose.GIS for .NET 的功能与能力。

### 如何获取 Aspose.GIS for .NET 的临时许可证？
请访问 [temporary license page](https://purchase.aspose.com/temporary-license/) 并按照说明获取临时许可证。

### 在哪里可以购买 Aspose.GIS for .NET 的许可证？
您可以在购买页面通过 [此链接](https://purchase.aspose.com/buy) 进行购买。

## Frequently Asked Questions
**Q: 可以在 PostGIS 中使用 EWKB 文件吗？**  
A: 可以，`ExtendedPostGis` 变体生成的 EWKB 包含 SRID，PostGIS 能直接读取。

**Q: 能否将 WKB 文件读取回几何对象？**  
A: 完全可以。使用 `Geometry.FromBinary(byteArray)` 即可重建几何体。

**Q: 库是否支持其他几何类型，如多边形？**  
A: 支持，Aspose.GIS 能处理点、linestring、polygon、multipolygon 等多种类型。

**Q: 创建几何体时如何指定不同的 SRID？**  
A: 在调用 `AsBinary` 之前设置几何体的 SRID，例如 `geometry.SRID = 4326;`。

**Q: 这段代码能在 .NET Core 上运行吗？**  
A: 能，相同的 API 在 .NET Framework、.NET Core 以及 .NET 5/6 上均可使用。

---

**最后更新：** 2025-12-21  
**测试环境：** Aspose.GIS for .NET 23.9（撰写时最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
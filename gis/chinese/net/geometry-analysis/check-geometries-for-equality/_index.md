---
date: 2026-06-05
description: 了解如何在 .NET 中使用 Aspose.GIS 比较几何体、检测重复几何体，并在应用程序中检查几何体是否相等。
keywords:
- how to compare geometries
- detect duplicate geometries
- Aspose.GIS geometry equality
linktitle: 如何比较几何体相等性
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to compare geometries in .NET using Aspose.GIS, detect duplicate
    geometries, and check geometry equality in your applications.
  headline: How to Compare Geometries for Equality using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard
      projects.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. Download a trial from the [Aspose.GIS releases page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Detailed docs are on the [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).
    question: Where can I find the full API documentation?
  - answer: Post your question on the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How do I get help if I run into an issue?
  - answer: Yes, temporary licenses are available on the [purchase page](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS for .NET 比较几何体相等性的方法
url: /zh/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS for .NET 比较几何体相等性的方法

## 介绍
在本教程中，您将学习如何使用 Aspose.GIS for .NET **比较几何体**，这在需要检测重复几何体、验证空间数据或强制拓扑规则时至关重要。无论您是构建地图服务、运行批量空间分析，还是仅仅验证两个形状是否占据相同位置，本指南都将带您通过创建、修改和测试几何体相等性，使用干净、可用于生产的 C# 代码。

## 快速答案
- **“比较几何体”是什么意思？** 它检查两个几何对象是否占据相同的空间，无论它们是如何构建的。  
- **使用哪种方法？** 来自 Aspose.GIS API 的 `SpatiallyEquals`。  
- **开发是否需要许可证？** 免费试用可用于测试；生产环境需要商业许可证。  
- **支持的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **典型实现时间？** 基本相等性检查大约需要 5‑10 分钟。

## 什么是几何体相等性？
几何体相等性，也称为空间相等性，指两个几何体在地表上表示完全相同的一组点。即使一个几何体是以 `MultiLineString` 构建，而另一个是单个 `LineString`，只要每个坐标在定义的容差范围内匹配，它们也被视为相等。此定义使开发者能够可靠地在异构数据源中检测重复几何体。

## 为什么使用 Aspose.GIS 来比较几何体？
Aspose.GIS 提供高性能的离线几何引擎，消除对外部服务的需求。它 **支持 30 多种矢量和栅格格式**（包括 WKT、GeoJSON、Shapefile、KML、GML），并且能够在内存使用低于 50 MB 的情况下处理 **数十万顶点**的文件。库的 `SpatiallyEquals` 方法具备精度感知，即使在浮点坐标下也能提供确定性的结果。

### 为什么这对开发者很重要
当您需要在批处理、实时验证管道或 GIS 数据迁移中 **检测重复几何体** 时，成熟的库可以消除猜测并确保在不同数据提供商之间获得一致的结果。

## 前提条件
- **已安装 .NET Framework 或 .NET Core** – 任意 Aspose.GIS 支持的版本。  
- **Aspose.GIS for .NET 库** – 从 [Aspose.GIS download page](https://releases.aspose.com/gis/net/) 下载。  
- **开发 IDE** – Visual Studio、Rider 或带有 C# 扩展的 VS Code。

## 导入命名空间
在您的 .NET 项目中，添加所需的 `using` 语句，以便编译器知道在哪里找到 GIS 类：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 第一步：定义几何体
`MultiLineString` 表示一组线段的集合，而 `LineString` 定义单条连续的线。两个类都继承自基类 `Geometry`。

首先，我们创建两个要比较的几何体。在本例中，`geometry1` 是由两段线组成的 `MultiLineString`，而 `geometry2` 是跨越相同起止点的单个 `LineString`。

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

## 第二步：检查几何体是否相等
`SpatiallyEquals` 评估两个几何体是否占据相同的点集合，可选地接受用于浮点误差的容差值。

现在我们使用 `SpatiallyEquals` 方法查看 GIS 引擎是否认为这两个形状相等。

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

控制台打印 `True`，因为尽管构造方式不同，两者都覆盖了从 (0,0) 到 (2,2) 的相同线段。

## 第三步：修改一个几何体
为了演示更改如何影响相等性，我们向 `geometry2` 添加一个额外的点。

```csharp
geometry2.AddPoint(3, 3);
```

## 第四步：修改后重新检查相等性
修改后，几何体不再相同，因此 `SpatiallyEquals` 返回 `False`。

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

输出 `False` 证实额外的点破坏了空间相等性。

## 如何检测重复几何体？
加载每个几何体，使用适当的容差调用 `SpatiallyEquals`，并过滤出返回 `True` 的对象。此模式与 LINQ 结合良好，能够仅用几行代码在大型集合中识别重复形状。您还可以将其与 `GroupBy` 结合，以聚合相同几何体并降低存储成本。

## 常见问题与技巧
- **精度问题** – 如果使用非常高精度的坐标，考虑进行四舍五入或使用 `SpatiallyEquals` 的容差重载。  
- **不同的 SRID** – 在比较之前确保两个几何体具有相同的空间参考系统标识符 (SRID)。  
- **性能** – 对于大规模集合，使用 LINQ 或并行循环进行批量比较可以显著降低开销。

## 常见问答
**Q: 我可以在其他 .NET 框架中使用 Aspose.GIS for .NET 吗？**  
A: 可以，Aspose.GIS 可在 .NET Framework、.NET Core 和 .NET Standard 项目中使用。

**Q: 是否提供免费试用？**  
A: 当然。可从 [Aspose.GIS releases page](https://releases.aspose.com/) 下载试用版。

**Q: 我在哪里可以找到完整的 API 文档？**  
A: 详细文档位于 [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/)。

**Q: 如果遇到问题，我该如何获取帮助？**  
A: 请在 Aspose.GIS 社区论坛 [here](https://forum.aspose.com/c/gis/33) 提问。

**Q: 我可以购买临时许可证进行评估吗？**  
A: 可以，临时许可证可在 [purchase page](https://purchase.aspose.com/temporary-license/) 获取。

## 结论
您现在已经了解如何使用 Aspose.GIS for .NET **比较几何体**，从创建对象到检查空间相等性以及处理修改。这一能力是更高级空间分析的基石，如拓扑验证、重复检测和基于几何体的过滤。

---

**最后更新:** 2026-06-05  
**测试环境:** Aspose.GIS for .NET 24.11  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [使用 Aspose.GIS for .NET 创建多边形几何体并检查相交](/gis/net/geometry-analysis/check-geometries-intersection/)
- [使用 Aspose.GIS for .NET 执行几何体空间重叠分析](/gis/net/geometry-analysis/check-geometries-overlap/)
- [网络路由检查：使用 Aspose.GIS 检测相接几何体](/gis/net/geometry-analysis/check-geometries-touching/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
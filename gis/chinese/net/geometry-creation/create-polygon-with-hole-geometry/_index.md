---
date: 2025-12-20
description: 学习如何使用 Aspose.GIS for .NET 创建带孔的多边形几何体。本指南向您展示如何在多边形中创建孔并处理地理空间数据。
linktitle: Create Polygon with Hole Geometry
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS 创建带孔的多边形几何
url: /zh/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS 创建带孔多边形几何

## 介绍
在本教程中，您将使用 Aspose.GIS for .NET **create polygon with hole** 几何。无论是构建地图应用、执行空间分析，还是为 GIS 服务准备数据，了解如何在多边形内部嵌入孔都是必备技能。我们将一步步演示完整过程，从环境搭建到生成最终的多边形对象。

## 快速答案
- **“create polygon with hole” 是什么意思？** 它指的是构建一个包含一个或多个内部环（孔）的多边形，这些内部环的面积被排除在外。
- **哪个库处理此功能？** Aspose.GIS for .NET 完全支持外环和内环。
- **需要许可证吗？** 免费试用可用于开发；生产环境需要商业许可证。
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。
- **需要多长时间？** 通常在 10 分钟内实现并测试完毕。

## 什么是“create polygon with hole”？
创建带孔的多边形涉及定义一个 **exterior ring** 来描绘外部边界，以及一个或多个 **interior rings** 来划出空白区域。内部环通常称为 *holes*，因为它们代表不属于多边形表面的区域。

## 为什么使用 Aspose.GIS 在多边形中创建孔？
- **精确的空间建模：** 像地块内部的湖泊或建筑物内部的庭院等真实世界特征需要孔。
- **互操作性：** Shapefile、GeoJSON、GML 等格式原生支持内部环；Aspose.GIS 能完整保留它们。
- **性能：** 库会自动管理几何有效性，您无需编写自定义验证代码。

## 前置条件
1. Aspose.GIS for .NET Library：您可以从 [here](https://releases.aspose.com/gis/net/) 下载。
2. 开发环境：确保已安装 Visual Studio 或其他 .NET IDE，并完成相应的开发环境配置。

## 导入命名空间
首先，需要导入使用 Aspose.GIS 功能所必需的命名空间。操作如下：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

现在，让我们继续使用 Aspose.GIS for .NET 创建带孔的多边形几何。

## 步骤 1：创建 Polygon 对象
我们首先实例化一个空的 `Polygon` 对象，稍后将用于保存外环和内环。

```csharp
Polygon polygon = new Polygon();
```

## 步骤 2：定义外环
外环定义了多边形的外部边界。按顺时针顺序添加点以形成闭合形状。

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## 步骤 3：定义内环（孔）
接下来，我们创建一个内环——这就是将从多边形面积中排除的 **hole**。点通常按逆时针顺序添加，但 Aspose.GIS 会自动处理方向。

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## 步骤 4：分配外环并将内环添加到 Polygon
最后，将外环附加到多边形，然后添加内环（孔）。如果需要多个孔，可多次调用 `AddInteriorRing` 方法。

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|------|------|----------|
| GIS 查看器中未显示孔 | 内环方向相反 | 确保点的添加方向与外环相反（逆时针）。 |
| 多边形无效错误 | 环未闭合（首点 ≠ 末点） | 在每个环的最后重复首点（如上所示）。 |
| 意外的空几何 | 在添加内环前忘记分配 `ExteriorRing` | 首先设置 `polygon.ExteriorRing`，然后再调用 `AddInteriorRing`。 |

## 结论
恭喜！您已成功学习如何使用 Aspose.GIS for .NET **create polygon with hole** 几何。此技术是许多需要表示内部空洞的复杂形状的地理空间场景的基础。

## 常见问题
### 1. 什么是 Aspose.GIS？
Aspose.GIS 是一个 .NET 库，帮助开发者处理地理空间数据，能够创建、读取和操作各种地理空间文件格式。

### 2. 我可以在商业项目中使用 Aspose.GIS 吗？
可以，您可以通过购买许可证在个人和商业项目中使用 Aspose.GIS。详情请访问 [here](https://purchase.aspose.com/buy)。

### 3. Aspose.GIS 是否提供免费试用？
可以，您可以从 [here](https://releases.aspose.com/) 获取 Aspose.GIS 的免费试用版。

### 4. 我在哪里可以找到 Aspose.GIS 的支持？
您可以在 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 获取支持。

### 5. 如何获取 Aspose.GIS 的临时许可证？
您可以从 [here](https://purchase.aspose.com/temporary-license/) 获取 Aspose.GIS 的临时许可证。

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
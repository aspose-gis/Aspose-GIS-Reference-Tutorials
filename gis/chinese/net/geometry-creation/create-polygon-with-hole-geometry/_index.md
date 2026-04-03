---
date: 2026-04-03
description: 了解如何使用 Aspose.GIS for .NET 创建带孔的多边形几何体。本指南向您展示如何在多边形中创建孔并处理地理空间数据。
keywords:
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
linktitle: 创建带孔的多边形几何
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
在本教程中，您将使用 Aspose.GIS for .NET **创建带孔的多边形** 几何。无论您是构建地图应用程序、执行空间分析，还是为 GIS 服务准备数据，了解如何在多边形内部嵌入孔都是必不可少的。我们将一步一步地完整演示整个过程，从环境设置到生成最终的多边形对象。

## 快速答案
- **“create polygon with hole” 是什么意思？** 它指的是构建一个包含一个或多个内部环（孔）的多边形，这些内部环的面积被排除在外。  
- **哪个库处理此功能？** Aspose.GIS for .NET 提供对外环和内环的完整支持。  
- **我需要许可证吗？** 免费试用可用于开发；生产环境需要商业许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5 及以上，.NET Core 3.1 及以上，.NET 5/6/7。  
- **需要多长时间？** 通常在 10 分钟以内即可实现并测试。

## 如何使用 Aspose.GIS 向多边形添加孔
添加孔只需定义一个 **内部环** 并将其附加到多边形。库会处理方向和有效性，您只需关注表示空洞的坐标即可。

## 什么是“创建带孔的多边形”？
创建带孔的多边形涉及定义一个 **外部环** 来勾勒外部边界，以及一个或多个 **内部环** 来划出空白区域。内部环通常被称为 *孔*，因为它们代表不属于多边形表面的区域。

## 为什么使用 Aspose.GIS 在多边形中创建孔？
- **精确的空间建模：** 像土地块内部的湖泊或建筑物内部的庭院等真实特征需要孔。  
- **互操作性：** Shapefile、GeoJSON 和 GML 等格式原生支持内部环；Aspose.GIS 能保留它们。  
- **性能：** 库管理几何有效性，您无需编写自定义验证代码。

## 带孔多边形的真实场景
1. **内部有湖泊的土地块** – 将湖泊建模为孔，以便不计入土地块的面积。  
2. **带庭院的建筑足迹** – 庭院从建筑足迹中排除。  
3. **大型保护区内的受保护区域** – 您可以在不创建单独图层的情况下排除受限区域。

## 先决条件
在开始之前，请确保您具备以下先决条件：
1. Aspose.GIS for .NET 库：您可以从 [here](https://releases.aspose.com/gis/net/) 下载。  
2. 开发环境：确保已安装 Visual Studio 或其他 .NET IDE 并完成开发环境的配置。

## 导入命名空间
首先，您需要导入必要的命名空间以使用 Aspose.GIS 功能。下面是具体做法：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

现在，让我们继续使用 Aspose.GIS for .NET 创建带孔的多边形几何。

## 步骤 1：创建多边形对象
我们首先实例化一个空的 `Polygon` 对象，稍后将用于保存外部环和内部环。

```csharp
Polygon polygon = new Polygon();
```

## 步骤 2：定义外部环
外部环定义多边形的外部边界。按顺时针顺序添加点以形成闭合形状。

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## 步骤 3：定义内部环（孔）
接下来，我们创建一个内部环——这就是将从多边形面积中排除的 **孔**。点通常按逆时针顺序添加，但 Aspose.GIS 会自动处理方向。

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## 步骤 4：分配外部环并向多边形添加内部环
最后，将外部环附加到多边形，然后添加内部环（孔）。如果需要多个孔，可以多次调用 `AddInteriorRing` 方法。

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## 提示和最佳实践
- **方向影响可读性** – 虽然 Aspose.GIS 会自动纠正方向，但保持外部环顺时针、内部环逆时针可使几何在 GIS 查看器中更易检查。  
- **闭合每个环** – 始终将第一个坐标重复为最后一点；这可确保形状有效闭合。  
- **创建后进行验证** – 您可以调用 `polygon.IsValid` 来确保几何符合 OGC 标准后再保存。

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| GIS 查看器中未显示孔 | 内部环方向相反 | 确保点的添加方向与外部环相反（逆时针）。 |
| 多边形无效错误 | 环未闭合（首点 ≠ 末点） | 在每个环中将首点重复为末点（如上所示）。 |
| 意外的空几何 | 在添加内部环之前忘记分配 `ExteriorRing` | 先设置 `polygon.ExteriorRing`，然后调用 `AddInteriorRing`。 |

## 常见问题
### 1. 什么是 Aspose.GIS？
Aspose.GIS 是一个 .NET 库，使开发人员能够处理地理空间数据，能够创建、读取和操作各种地理空间文件格式。

### 2. 我可以在商业项目中使用 Aspose.GIS 吗？
是的，您可以通过购买许可证在个人和商业项目中使用 Aspose.GIS。访问 [here](https://purchase.aspose.com/buy) 获取更多详情。

### 3. Aspose.GIS 是否提供免费试用？
是的，您可以从 [here](https://releases.aspose.com/) 获取 Aspose.GIS 的免费试用。

### 4. 我在哪里可以找到 Aspose.GIS 的支持？
您可以在 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 上找到 Aspose.GIS 的支持。

### 5. 我如何获取 Aspose.GIS 的临时许可证？
您可以从 [here](https://purchase.aspose.com/temporary-license/) 获取 Aspose.GIS 的临时许可证。

---

**最后更新：** 2026-04-03  
**测试环境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
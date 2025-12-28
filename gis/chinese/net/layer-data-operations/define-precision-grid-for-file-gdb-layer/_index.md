---
date: 2025-12-28
description: 学习如何使用 Aspose.GIS for .NET 为 File GDB 图层设置网格，包括向图层添加要素和验证坐标范围。
linktitle: Define Precision Grid for File GDB Layer
second_title: Aspose.GIS .NET API
title: 如何在 Aspose.GIS 中为 File GDB 图层设置网格
url: /zh/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.GIS 中为 File GDB 图层设置网格

## 介绍
在本教程中，您将学习如何使用 Aspose.GIS for .NET 为 File Geodatabase (GDB) 图层 **设置网格**。设置精度网格有助于 **验证坐标范围**，防止超出范围的错误，并确保您 **向图层添加要素** 的数据保持准确可靠。我们将逐步演示每一步，解释设置的重要性，并展示如何处理常见的陷阱。

## 快速答疑
- **“设置网格”是什么意思？** 它定义了 GIS 图层的坐标精度和有效范围。  
- **为什么使用精度网格？** 它可以保护您的数据免受无效坐标的影响，并提升存储效率。  
- **哪个库提供此功能？** Aspose.GIS for .NET。  
- **我需要许可证吗？** 提供试用版；生产环境需要商业许可证。  
- **我可以在 .NET Core 上使用吗？** 可以，Aspose.GIS 支持 .NET Framework 和 .NET Core。

## 什么是精度网格以及为何要设置它？
精度网格是一组参数（原点、比例等），用于指示 GIS 引擎如何对坐标值进行四舍五入和存储。通过定义网格，您可以自动 **验证坐标范围**，任何尝试在网格外插入点的操作都会抛出异常——帮助您在开发早期 **处理超出范围** 的情况。

## 先决条件
在开始之前，请确保已安装以下内容：

1. **Visual Studio** – 任意近期版本（Community、Professional 或 Enterprise）。  
2. **Aspose.GIS for .NET** – 从[网站](https://releases.aspose.com/gis/net/)下载。  
3. **基本的 C# 知识** – 您应熟悉创建 .NET 控制台项目。

## 导入命名空间
首先，导入使用 Aspose.GIS 所需的命名空间：

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## 如何在 File GDB 图层中设置网格
以下是一步步指南，展示如何配置网格、创建图层，并安全地 **向图层添加要素**。

### 步骤 1：创建数据集
我们首先创建一个新的 File Geodatabase 数据集。图层将在此数据集中存在。

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### 步骤 2：定义精度网格选项
在这里我们指定网格参数。请根据项目的坐标系统调整原点和比例。

```csharp
var options = new FileGdbOptions
{
    CoordinatePrecisionGrid = new FileGdbCoordinatePrecisionGrid
    {
        XOrigin = -400,
        YOrigin = -400,
        XYScale = 1e10,
        MOrigin = 0,
        MScale = 1e4,
    },
    EnsureValidCoordinatesRange = true,
};
```

*`EnsureValidCoordinatesRange = true` 标志指示 Aspose.GIS 为您添加的每个要素 **验证坐标范围**。*

### 步骤 3：使用网格创建图层
现在我们在数据集中创建一个新图层，应用刚才定义的网格选项。我们将使用 WGS84 空间参考系统。

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### 步骤 4：向图层添加要素
我们构造两个点要素。第一个点位于网格内部，第二个点故意位于网格外部，以演示 **如何处理超出范围** 错误。

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### 步骤 5：处理添加超出范围要素时的异常
尝试添加第二个要素时会触发异常，因为其 X 坐标 (`-410`) 超出定义的网格范围。我们捕获该异常并输出清晰的提示信息。

```csharp
try
{
    layer.Add(feature);
}
catch (GisException e)
{
    Console.WriteLine(e.Message); // X value -410 is out of valid range.
}
```

### 步骤 6：清理
`using` 语句会自动关闭并释放数据集和图层，确保所有资源得到释放。

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **Exception: “X value … is out of valid range.”** | 坐标超出精度网格。 | 调整 `XOrigin`、`YOrigin` 或 `XYScale` 以覆盖您的数据，或确保输入数据在定义的范围内。 |
| **Features not appearing in GIS viewer** | 图层未保存或空间参考错误。 | 确认 `SpatialReferenceSystem.Wgs84` 与查看器的 CRS 匹配，并且 `Dataset.Create` 已成功。 |
| **M values ignored** | `MScale` 设置为 0 或太低。 | 设置合理的 `MScale`（例如 `1e4`）以存储测量值。 |

## 常见问题解答

**问：我可以在 .NET 中使用 Aspose.GIS 处理其他 GIS 文件格式吗？**  
答：可以，Aspose.GIS 支持 Shapefile、GeoJSON、KML 等多种格式。

**问：Aspose.GIS for .NET 是否兼容 .NET Core？**  
答：完全兼容。该库可在 .NET Framework、.NET Core 以及 .NET 5/6+ 上运行。

**问：我能执行缓冲区或相交等空间操作吗？**  
答：可以，API 包含缓冲、相交和距离计算等方法。

**问：Aspose.GIS 是否提供坐标转换功能？**  
答：是的，您可以使用内置的再投影工具在不同空间参考系统之间转换几何体。

**问：是否提供试用版？**  
答：是的，您可以从[网站](https://releases.aspose.com/gis/net/)下载免费试用版。

---

**最后更新：** 2025-12-28  
**测试环境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
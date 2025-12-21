---
date: 2025-12-21
description: 学习如何使用 Aspose.GIS for .NET 创建矢量图层、设置线性化容差并向图层添加要素。请按照本分步指南导出 GeoJSON
  文件。
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS for .NET 创建矢量图层并设置线性化容差
url: /zh/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS for .NET 创建矢量图层并设置线性化容差

## 介绍
如果您需要 **创建矢量图层** 文件、控制曲线精度，并将结果导出为 GeoJSON 文档，Aspose.GIS for .NET 可以让这一过程变得简单。在本教程中，您将学习如何配置 GeoJSON 选项、设置线性化容差，以及 **向图层添加要素**，同时保持代码整洁、可用于生产环境。

## 快速回答
- **“创建矢量图层”是什么意思？** 它会创建一个新的 GIS 矢量数据集（例如 GeoJSON 文件），用于存储几何图形和属性。  
- **如何设置容差？** 使用 `GeoJsonOptions` 的 `LinearizationTolerance` 属性。  
- **我可以导出 GeoJSON 文件吗？** 可以——只需使用 `Drivers.GeoJson` 驱动创建 `VectorLayer`。  
- **需要许可证吗？** 有效的 Aspose.GIS 许可证可解锁全部功能；临时许可证可用于评估。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 什么是 “创建矢量图层”？
创建矢量图层意味着初始化一个新的 GIS 容器（如 GeoJSON 文件），该容器可以保存点、线、面等几何要素以及相应的属性。该图层将成为您构建几何图形和附加属性的目标。

## 为什么要配置 GeoJSON 选项？
配置 GeoJSON 选项——尤其是 **线性化容差**——可以确保曲线几何（例如 `CircularString`）以满足应用精度要求的方式近似。这一步在您随后 **导出 GeoJSON 文件** 用于 Web 地图或空间分析时至关重要。

## 前置条件
在开始之前，请确保您已具备：

1. 已安装 **Visual Studio**（任意近期版本）。  
2. **Aspose.GIS 许可证**（或临时评估密钥）。  
3. 已下载并在项目中引用 **Aspose.GIS for .NET** 库。  
4. 对 **C#** 有基本了解。

## 导入命名空间
首先，导入所需的命名空间，以便编译器能够找到 GIS 类：

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 步骤指南

### 步骤 1：配置 GeoJSON 选项（如何设置容差）
我们将创建一个 `GeoJsonOptions` 对象，并告诉 Aspose.GIS 线性化后的几何应与原始曲线保持多近的距离。

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### 步骤 2：定义输出路径（如何导出 GeoJSON）
指定生成文件的保存位置。将占位符替换为您实际的文件夹路径。

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### 步骤 3：使用已配置的选项 **创建矢量图层**
现在我们使用 `VectorLayer.Create` 方法真正 **创建矢量图层**。`using` 块可确保资源得到正确释放。

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### 步骤 4：构建几何对象（例如圆弧串）
这里我们构建一个示例几何——`CircularString`。您可以将其替换为任何有效的 WKT。

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### 步骤 5：**向图层添加要素** 并保存
最后，我们创建要素、分配几何并将其添加到图层中。这就是 **向图层添加要素** 操作的核心。

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

当 `using` 块结束时，图层会自动写入 `path` 中定义的文件，生成可直接使用的 GeoJSON 文件。

## 常见问题与技巧
- **路径错误** – 确保目录存在且您拥有写入权限。  
- **容差设置过低** – 将 `LinearizationTolerance` 设置得过小可能会显著增大文件体积。请根据精度需求进行调整。  
- **许可证错误** – 若出现许可证警告，请确认在任何 Aspose.GIS 调用之前已正确加载许可证文件。

## 常见问答

**问：Aspose.GIS for .NET 是否兼容其他 .NET 框架？**  
答：是的，支持 .NET Framework、.NET Core 以及 .NET 5/6/7。

**问：我可以在商业项目中使用 Aspose.GIS 吗？**  
答：当然。商业许可证可移除所有评估限制。

**问：Aspose.GIS 是否支持除 GeoJSON 之外的其他 GIS 格式？**  
答：是的，支持 Shapefile、KML、GML 等多种格式。

**问：是否有试用版本？**  
答：您可以从 Aspose 官网下载免费试用版。

**问：在哪里可以获得支持？**  
答：使用 Aspose 论坛或资源章节中的支持链接。

## 结论
通过本教程，您已经掌握了如何 **创建矢量图层**、配置线性化容差，以及 **向图层添加要素**，从而实现无缝的 **导出 GeoJSON 文件**。探索更多几何类型和属性处理，以充分利用 Aspose.GIS 在 .NET GIS 项目中的强大功能。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2025-12-21  
**测试环境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

---
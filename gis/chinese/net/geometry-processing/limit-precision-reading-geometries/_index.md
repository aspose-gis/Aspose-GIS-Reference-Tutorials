---
date: 2025-12-20
description: 学习如何使用 Aspose.GIS for .NET 创建矢量图层并在读取几何时限制精度。一步步指南，帮助实现最佳的地理空间数据处理。
linktitle: Limit Precision Reading Geometries
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS for .NET 创建矢量图层并限制精度
url: /zh/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建矢量图层，并使用 Aspose.GIS for .NET 限制精度

## 介绍
在处理地理空间数据时，您经常需要 **create vector layer** 对象，并在读取时控制保留多少数值细节。Aspose.GIS for .NET 使限制精度变得简单，这可以在不需要超高精度的情况下提升性能并减少存储空间。在本教程中，您将看到如何创建矢量图层、写入一个简单的点几何体，然后使用精确和截断两种精度读取它。

## 快速回答
- **“限制精度”是什么意思？** 它会将坐标值四舍五入到指定的小数位数。  
- **为什么要先创建矢量图层？** 矢量图层是存储点、线、面等几何体的容器。  
- **有哪些精度模型可用？** `PrecisionModel.Exact`（不四舍五入）和 `PrecisionModel.Rounding(n)`（四舍五入到 *n* 位小数）。  
- **尝试此功能需要许可证吗？** 可以从 releases 页面获取免费试用版。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 和 .NET 5/6+。

## 先决条件
在开始之前，请确保具备以下条件：
1. **Installation** – 应在开发环境中安装 Aspose.GIS for .NET 库。如未安装，可从 [releases page](https://releases.aspose.com/gis/net/) 下载。  
2. **Familiarity with .NET** – 需要具备 C# 和 .NET 框架的基础知识，以便理解并实现示例代码。  
3. **Development Environment** – 需要一个可用的 .NET 开发环境，例如 Visual Studio。  
4. **Document Directory** – 请准备好一个目录，用于存放并访问本过程生成的 shapefile。

## 导入命名空间
在实现读取几何体时限制精度的功能之前，先确保导入必要的命名空间：
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 如何创建矢量图层
第一步是 **create vector layer**，它将保存我们的几何体。该图层将保存为 Shapefile，以便后续使用不同的精度设置重新打开。
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## 设置精度选项
接下来，需要为读取几何体定义选项，指定所需的精度模型。我们可以先使用精确精度：
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## 使用精确精度读取几何体
现在，使用指定的选项打开矢量图层，以精确精度读取几何体：
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## 截断精度
如果希望将精度截断到特定的小数位数，可相应地调整精度模型：
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## 常见问题及解决方案
- **Unexpected coordinate values** – 确保在打开图层之前设置 `options.XYPrecisionModel`。在打开后再更改无效。  
- **File not found** – 验证 `path` 变量指向有效目录，并且前一步已成功创建 Shapefile。  
- **Incorrect geometry type** – 示例使用 `Point`。对于其他几何类型（例如 `LineString`），强制转换应匹配实际类型。

## 结论
总之，在读取几何体时管理精度是地理空间数据处理的关键环节。Aspose.GIS for .NET 提供了强大的功能，能够高效实现此目标。按照本教程的步骤，您可以轻松 **create vector layer** 对象，并根据需求限制精度，从而在应用程序中实现最佳的数据处理。

## 常见问答
### 我可以在 .NET Core 或 .NET Standard 等其他 .NET 框架中使用 Aspose.GIS for .NET 吗？
可以，Aspose.GIS for .NET 与多种 .NET 框架兼容，包括 .NET Core 和 .NET Standard。  
### Aspose.GIS for .NET 是否提供试用版？
是的，您可以从 [releases page](https://releases.aspose.com/) 获取免费试用版。  
### 哪里可以找到 Aspose.GIS for .NET 的完整文档？
请参考 [documentation](https://reference.aspose.com/gis/net/) 获取详细信息和示例。  
### 如何获取 Aspose.GIS for .NET 的临时许可证？
可在 [purchase page](https://purchase.aspose.com/temporary-license/) 获取 Aspose.GIS 的临时许可证。  
### 在哪里可以寻求 Aspose.GIS for .NET 的帮助或支持？
您可以访问 Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) 提出问题、讨论或获取支持。

## 常见问题
**Q: 限制精度会影响原始 shapefile 吗？**  
A: 不会。精度仅在读取几何体时应用，源文件保持不变。  

**Q: 我可以为 X 和 Y 坐标使用不同的精度模型吗？**  
A: Aspose.GIS 目前对两个轴使用相同的 `XYPrecisionModel`。  

**Q: 是否可以设置自定义的四舍五入函数？**  
A: API 仅支持内置的 `PrecisionModel.Rounding(int)` 方法。如需自定义逻辑，需在读取后对坐标进行后处理。

---

**最后更新：** 2025-12-20  
**测试环境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
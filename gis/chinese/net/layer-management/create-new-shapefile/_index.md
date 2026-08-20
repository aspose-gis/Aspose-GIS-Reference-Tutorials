---
date: 2026-06-30
description: 了解如何使用 Aspose.GIS for .NET 创建 shapefile。此分步指南展示了如何定义矢量图层、添加日期属性以及高效管理空间数据。
keywords:
- how to create shapefile
- temporal gis shapefile
- Aspose.GIS vector layer
- GIS data automation
linktitle: 创建新 Shapefile
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create shapefile using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to define a vector layer, add a date attribute, and manage
    spatial data efficiently.
  headline: How to Create Shapefile with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS primarily supports .NET, but there are versions available for
      Java as well.
    question: Can I use Aspose.GIS with other programming languages?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I find support for Aspose.GIS?
  - answer: Get your temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license?
  - answer: You can buy the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 创建 Shapefile
url: /zh/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建新的 Shapefile

## 介绍
如果您正在使用 .NET 深入地理信息系统（GIS）开发，Aspose.GIS 是您用于 **如何创建 shapefile** 的首选解决方案。该库让您完全控制矢量图层、属性模式和文件格式合规性，从而可以在几分钟内自动化数据管道或生成测试数据集。

## 快速答案
- **本教程教授什么？** 如何创建新的 shapefile，定义矢量图层，并添加属性（包括日期字段）。  
- **需要哪个库？** Aspose.GIS for .NET。  
- **我需要许可证吗？** 免费试用可用于学习；生产环境需要商业许可证。  
- **应该使用哪个 IDE？** Visual Studio（任何近期版本）。  
- **实现需要多长时间？** 基本示例大约需要 10‑15 分钟。

## 如何使用 Aspose.GIS for .NET 创建 shapefile？
加载 Aspose.GIS 库，设置输出文件夹，创建 `VectorLayer`，定义属性并添加要素——整个工作流可以用不到 30 行 C# 代码实现。该库自动处理几何创建、属性类型和文件写入，您无需自行管理低层次的 Shapefile 规范。

## 先决条件
在开始教程之前，请确保您已具备以下先决条件：
- 对 C# 编程语言的基本了解。  
- 机器上已安装 Visual Studio。  
- Aspose.GIS for .NET 库。您可以在[此处](https://releases.aspose.com/gis/net/)下载。

## 导入命名空间
首先导入必要的命名空间以利用 Aspose.GIS 的功能：

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 步骤 1：设置项目
在 Visual Studio 中创建一个新的 C# 项目并引用 Aspose.GIS 库。

## 步骤 2：定义文档目录
```csharp
string dataDir = "Your Document Directory";
```
将 *Your Document Directory* 替换为您希望保存新 shapefile 的实际路径。

## 步骤 3：创建 VectorLayer
`VectorLayer` 类表示存储几何和属性数据的单个 shapefile 图层。  
在此步骤中，我们定义一个矢量图层并声明三个属性：文本字段（`name`）、整数字段（`age`）和日期时间字段（`dob`）。添加日期属性对于 **时空 GIS shapefile** 分析至关重要。

```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```

## 步骤 4：添加要素
### 案例 1：逐个设置值
`SetValues` 方法按照属性定义的顺序为要素分配属性值。  
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
这里我们创建两个点，分别设置每个属性，并将要素添加到图层中。

### 案例 2：一次性设置所有属性的值
或者，您可以使用 `SetValues` 并传入对象数组一次性提供所有属性值。  
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
在此方法中，我们使用对象数组一次性填充所有属性值——当属性众多时非常方便。

## 为什么这很重要？
以编程方式创建 shapefile 可让您自动化数据管道、生成测试数据集，或将 GIS 输出直接嵌入 Web 服务。Aspose.GIS 支持 **30 多种矢量和栅格格式**，并且能够在不将整个文件加载到内存的情况下写入数百页的 shapefile，提供速度和可扩展性。

## 常见陷阱与技巧
- **路径分隔符：** 使用 `Path.Combine` 以实现跨平台兼容性，而不是字符串拼接。  
- **属性顺序：** `SetValues` 中的值顺序必须与您添加属性的顺序相匹配。  
- **日期处理：** 如果您的 GIS 数据将在不同时区共享，请始终使用 `DateTimeKind.Utc`。

## 结论
恭喜！您已成功使用 Aspose.GIS for .NET 创建了新的 shapefile。本教程涵盖了设置项目、定义矢量图层和添加要素（包括日期属性）的基础知识。进一步探索时，请参考[文档](https://reference.aspose.com/gis/net/)以了解高级功能和特性。

## 常见问题
**Q: 我可以在其他编程语言中使用 Aspose.GIS 吗？**  
A: Aspose.GIS 主要支持 .NET，但也提供了 Java 版本。  

**Q: 是否提供免费试用？**  
A: 是的，您可以在[此处](https://releases.aspose.com/)获取免费试用。  

**Q: 我在哪里可以找到 Aspose.GIS 的支持？**  
A: 请访问[Aspose.GIS 论坛](https://forum.aspose.com/c/gis/33)获取社区支持和讨论。  

**Q: 我如何获取临时许可证？**  
A: 您可以在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。  

**Q: 我在哪里可以购买 Aspose.GIS for .NET？**  
A: 您可以在[此处](https://purchase.aspose.com/buy)购买该库。  

---

**Last Updated:** 2026-06-30  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## 相关教程

- [获取图层属性 – 使用 Aspose.GIS for .NET 检索图层属性信息](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [创建矢量图层并设置图层空间参考系统](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [在 File GDB 中创建矢量图层 – Aspose.GIS .NET 教程](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
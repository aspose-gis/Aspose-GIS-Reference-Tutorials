---
date: 2026-01-13
description: 学习如何使用 Aspose.GIS for .NET 创建新的 shapefile。本分步指南向您展示如何定义矢量图层、添加日期属性以及管理空间数据。
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
title: 创建新 Shapefile
url: /zh/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建新 Shapefile

## 介绍
如果您正在使用 .NET 进行地理信息系统（GIS）开发，Aspose.GIS 是您的首选解决方案。该强大的库使开发者能够轻松处理空间数据，在本教程中，我们将指导您如何使用 Aspose.GIS for .NET **创建新 shapefile**。您将了解为何定义矢量图层并添加日期属性是构建稳健 GIS 项目的关键步骤。

## 快速回答
- **本教程教什么？** 如何创建新 shapefile、定义矢量图层以及添加属性（包括日期字段）。  
- **需要哪个库？** Aspose.GIS for .NET。  
- **需要许可证吗？** 免费试用可用于学习；生产环境需商业许可证。  
- **使用哪种 IDE？** Visual Studio（任意近期版本）。  
- **实现大约需要多长时间？** 基本示例约 10‑15 分钟。

## 前置条件
在开始教程之前，请确保具备以下前置条件：
- 对 C# 编程语言有基本了解。  
- 机器上已安装 Visual Studio。  
- 已获取 Aspose.GIS for .NET 库。您可以在[此处](https://releases.aspose.com/gis/net/)下载。

## 导入命名空间
首先导入必要的命名空间，以利用 Aspose.GIS 的功能：

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
在 Visual Studio 中创建一个新的 C# 项目，并引用 Aspose.GIS 库。

## 步骤 2：定义文档目录
```csharp
string dataDir = "Your Document Directory";
```
将 *Your Document Directory* 替换为您希望保存新 shapefile 的实际路径。

## 步骤 3：创建 VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
此代码段 **定义了一个矢量图层**，并声明了三个属性：文本字段 (`name`)、整数字段 (`age`) 和日期时间字段 (`dob`)。添加日期属性对于时空 GIS 分析至关重要。

## 步骤 4：添加要素
### 情形 1：逐个设置值
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
在这里我们创建两个点，分别为每个属性赋值，并将要素添加到图层。

### 情形 2：一次性为所有属性设置新值
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
此方式使用对象数组一次性填充所有属性值——当属性众多时非常方便。

## 为什么这很重要
以编程方式创建 shapefile 可以让您自动化数据管道、生成测试数据集，或将 GIS 输出直接集成到 Web 服务中。掌握使用 Aspose.GIS **创建 shapefile** 的方法，您即可全面控制要素几何、属性模式以及文件格式合规性。

## 常见陷阱与技巧
- **路径分隔符：** 使用 `Path.Combine` 以实现跨平台兼容性，而不是字符串拼接。  
- **属性顺序：** `SetValues` 中值的顺序必须与添加属性的顺序保持一致。  
- **日期处理：** 若 GIS 数据将在不同时区共享，请始终使用 `DateTimeKind.Utc`。

## 结论
恭喜！您已成功使用 Aspose.GIS for .NET 创建了新 shapefile。本教程涵盖了项目设置、矢量图层定义以及要素添加（包括日期属性）的基础内容。进一步探索时，请参考[文档](https://reference.aspose.com/gis/net/)获取高级功能和特性。

## 常见问题
### 问：我可以在其他编程语言中使用 Aspose.GIS 吗？
Aspose.GIS 主要支持 .NET，但也提供 Java 版本。

### 问：是否有免费试用？
是的，您可以在[此处](https://releases.aspose.com/)获取免费试用。

### 问：在哪里可以获得 Aspose.GIS 的支持？
访问[Aspose.GIS 论坛](https://forum.aspose.com/c/gis/33)获取社区支持和讨论。

### 问：如何获取临时许可证？
在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

### 问：在哪里可以购买 Aspose.GIS for .NET？
您可以在[此处](https://purchase.aspose.com/buy)购买该库。

---

**最后更新：** 2026-01-13  
**测试版本：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
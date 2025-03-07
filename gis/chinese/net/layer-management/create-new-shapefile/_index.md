---
title: 创建新的形状文件
linktitle: 创建新的形状文件
second_title: Aspose.GIS .NET API
description: 了解如何使用 Aspose.GIS for .NET 创建新的 shapefile。遵循我们的分步指南并释放空间数据操作的力量。
weight: 12
url: /zh/net/layer-management/create-new-shapefile/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建新的形状文件

## 介绍
如果您正在研究使用 .NET 进行地理信息系统 (GIS) 开发，Aspose.GIS 是您的首选解决方案。这个强大的库使开发人员能够无缝地处理空间数据，在本教程中，我们将指导您完成使用 Aspose.GIS for .NET 创建新 shapefile 的过程。
## 先决条件
在我们开始学习本教程之前，请确保您具备以下先决条件：
- 对 C# 编程语言有基本了解。
- Visual Studio 安装在您的计算机上。
-  Aspose.GIS for .NET 库。你可以下载它[这里](https://releases.aspose.com/gis/net/).
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
## 第 1 步：设置您的项目
首先在 Visual Studio 中创建一个新的 C# 项目并包含 Aspose.GIS 库。
## 第 2 步：定义文档目录
```csharp
string dataDir = "Your Document Directory";
```
将“您的文档目录”替换为您要保存新 shapefile 的实际路径。
## 第 3 步：创建矢量层
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //在添加特征之前添加属性
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
此代码段设置矢量图层并定义要素的属性。
## 第 4 步：添加功能
### 情况 1：单独设置值
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
### 情况 2：为所有属性设置新值
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## 结论
恭喜！您已使用 Aspose.GIS for .NET 成功创建了一个新的 shapefile。本教程涵盖了设置项目、定义属性和添加功能的基础知识。当您进一步探索时，请参阅[文档](https://reference.aspose.com/gis/net/)以获得高级特性和功能。
## 经常问的问题
### 问：我可以将 Aspose.GIS 与其他编程语言一起使用吗？
Aspose.GIS 主要支持 .NET，但也有适用于 Java 的版本。
### 问：有免费试用吗？
是的，您可以免费试用[这里](https://releases.aspose.com/).
### 问：在哪里可以找到对 Aspose.GIS 的支持？
参观[Aspose.GIS论坛](https://forum.aspose.com/c/gis/33)以获得社区支持和讨论。
### 问：如何获得临时许可证？
获取您的临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 问：哪里可以购买 Aspose.GIS for .NET？
你可以购买图书馆[这里](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

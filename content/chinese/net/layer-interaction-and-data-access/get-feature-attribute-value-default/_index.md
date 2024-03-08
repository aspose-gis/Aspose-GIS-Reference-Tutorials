---
title: 获取特征属性值（默认）
linktitle: 获取特征属性值（默认）
second_title: Aspose.GIS .NET API
description: 释放 Aspose.GIS for .NET 的强大功能！使用此分步指南轻松检索和操作要素属性值。立即下载试用版！
type: docs
weight: 14
url: /zh/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---
## 介绍
欢迎来到 Aspose.GIS for .NET 的世界！在本综合指南中，我们将深入探讨使用 Aspose.GIS 的强大功能检索要素属性值的复杂性。无论您是经验丰富的开发人员还是刚刚入门，本教程都将为您提供分步演练，确保您充分利用这个出色工具的潜力。
## 先决条件
在我们开始这次编码冒险之前，请确保您具备以下先决条件：
- 具备 C# 和 .NET 框架的应用知识。
- 已安装 Aspose.GIS for .NET。如果没有，请从以下位置下载[这里](https://releases.aspose.com/gis/net/).
- 代码编辑器（例如 Visual Studio）可无缝执行。
## 导入命名空间
在您的 C# 项目中，确保包含必要的命名空间：
```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
现在，让我们将每个示例分解为一系列易于遵循的步骤。
## 获取特征属性值（默认）
### 第 1 步：设置环境
首先定义文档目录的路径：
```csharp
string dataDir = "Your Document Directory";
```
### 第2步：创建GeoJson层
创建一个 GeoJson 图层并定义一个具有默认值的属性：
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### 第 3 步：构建特征
使用定义的属性构造一个特征：
```csharp
    Feature feature = layer.ConstructFeature();
```
### 第 4 步：检索值
检索各种场景的属性值：
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); //值==空
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); //值==10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); //值==10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## 设置默认值
### 第 1 步：创建另一个 GeoJson 层
使用不同的 GeoJson 层和双属性重复该过程：
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### 第 2 步：（再次）构建特征
```csharp
    Feature feature = layer.ConstructFeature();
```
### 第 3 步：检索并设置值
检索和设置属性值，显示默认值：
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); //值==100
    var defValue2 = feature.GetValueOrDefault("attribute"); //值==100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); //值==50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
恭喜！您已成功利用 Aspose.GIS for .NET 的强大功能来检索和操作要素属性值。
## 结论
在本教程中，我们探讨了使用 Aspose.GIS for .NET 检索要素属性值的细微差别。凭借其直观的 API 和强大的功能，Aspose.GIS 为 .NET 环境中的 GIS 开发开辟了一个充满可能性的世界。
## 经常问的问题
### Aspose.GIS 与 .NET Core 兼容吗？
是的，Aspose.GIS与.NET Core完全兼容，提供跨平台支持。
### 我可以将 Aspose.GIS 用于商业项目吗？
绝对地！ Aspose.GIS 附带商业许可证，允许您在商业应用程序中不受任何限制地使用它。
### 我在哪里可以找到额外的支持和资源？
参观[Aspose.GIS论坛](https://forum.aspose.com/c/gis/33)寻求社区支持并探索[文档](https://reference.aspose.com/gis/net/)以获得深入的信息。
### 有免费试用吗？
是的，您可以通过免费试用来探索 Aspose.GIS。下载它[这里](https://releases.aspose.com/).
### 如何获得用于测试目的的临时许可证？
如需临时许可证，请访问[这里](https://purchase.aspose.com/temporary-license/).
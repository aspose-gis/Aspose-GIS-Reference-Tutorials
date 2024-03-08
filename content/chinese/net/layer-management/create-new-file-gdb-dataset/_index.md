---
title: 创建新文件 GDB 数据集
linktitle: 创建新文件 GDB 数据集
second_title: Aspose.GIS .NET API
description: 探索 Aspose.GIS for .NET 以轻松创建和管理 GIS 数据集。立即下载以进行无缝地理空间开发。 #Aspose #GIS
type: docs
weight: 10
url: /zh/net/layer-management/create-new-file-gdb-dataset/
---
## 介绍
在地理空间开发领域，Aspose.GIS for .NET 作为管理和操作地理信息系统 (GIS) 数据的强大工具包脱颖而出。无论您是经验丰富的开发人员还是刚刚开始 GIS 之旅，本教程都将引导您完成使用 Aspose.GIS for .NET 创建新文件地理数据库 (GDB) 数据集的过程。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
-  Aspose.GIS for .NET：确保您已安装 Aspose.GIS for .NET 库。您可以从[Aspose.GIS for .NET 下载页面](https://releases.aspose.com/gis/net/).
- 开发环境：使用兼容的 IDE（例如 Visual Studio）设置开发环境，并对 .NET 编程有基本的了解。
- 文档目录：将代码片段中的“您的文档目录”替换为您想要存储 GDB 数据集的适当路径。
- 熟悉 C#：本教程假设您熟悉 C# 编程语言。
## 导入命名空间
在初始步骤中，导入必要的命名空间以在 .NET 应用程序中利用 Aspose.GIS 功能：
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## 第1步：创建一个新的文件GDB数据集
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); //输出：0
    //继续后续步骤...
}
```
说明：在这一步中，我们使用以下命令创建一个新的 GDB 数据集：`Dataset.Create`方法。我们指定路径和驱动程序 (FileGdb) 来创建文件地理数据库。控制台输出显示初始层数，此时为零。
## 第 2 步：创建并填充 Layer_1
```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```
说明：此步骤涉及在数据集中创建一个名为“layer_1”的图层。它定义了一个名为“value”的整数类型属性，并用十个要素填充图层，每个要素都有一个点几何图形。
## 第 3 步：创建并填充 Layer_2
```csharp
using (var layer = dataset.CreateLayer("layer_2"))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
说明：在这里，我们创建名为“layer_2”的第二层，并添加具有线串几何形状的单个要素。
## 步骤 4：检查更新的层数
```csharp
Console.WriteLine(dataset.LayersCount); //输出：2
```
解释：最后，我们检查添加两层后更新的层数。在这种情况下，输出应该是 2。
## 结论
恭喜！您已成功创建了一个新的文件 GDB 数据集，并使用 Aspose.GIS for .NET 用图层填充了它。本教程提供了在 .NET 环境中使用地理空间数据的基本了解。
## 经常问的问题
### 问：我可以将 Aspose.GIS for .NET 与其他 GIS 库一起使用吗？
Aspose.GIS for .NET 是一个独立的工具包；但是，您可以将其与其他 .NET 库集成以增强功能。
### 问：是否有支持 Aspose.GIS 的社区论坛？
是的，您可以在以下位置找到支持和讨论：[Aspose.GIS论坛](https://forum.aspose.com/c/gis/33).
### 问：如何获得 Aspose.GIS 的临时许可证？
参观[临时牌照](https://purchase.aspose.com/temporary-license/)有关获得临时许可证的信息页面。
### 问：是否有其他可用的示例和文档？
探索[Aspose.GIS 文档](https://reference.aspose.com/gis/net/)了解更多示例和详细信息。
### 问：哪里可以购买 Aspose.GIS for .NET？
您可以在以下位置购买 Aspose.GIS for .NET[购买页面](https://purchase.aspose.com/buy).
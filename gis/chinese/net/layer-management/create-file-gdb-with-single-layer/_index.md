---
title: 创建单层文件 GDB
linktitle: 创建单层文件 GDB
second_title: Aspose.GIS .NET API
description: 使用 Aspose.GIS 释放 .NET 中地理空间数据管理的潜力。了解如何逐步创建文件地理数据库和图层。现在下载！
weight: 11
url: /zh/net/layer-management/create-file-gdb-with-single-layer/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建单层文件 GDB

## 介绍
您准备好使用强大的文件地理数据库和图层来提升您的地理空间应用程序了吗？ Aspose.GIS for .NET 就是您的最佳选择。在本教程中，我们将引导您完成使用 Aspose.GIS for .NET 创建单层文件地理数据库 (GDB) 的过程。轻松利用 .NET 应用程序中空间数据管理和可视化的强大功能。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
1.  Aspose.GIS for .NET：确保您已安装 Aspose.GIS 库。您可以从[Aspose.GIS for .NET 下载页面](https://releases.aspose.com/gis/net/).
2. 开发环境：在您的计算机上设置有效的 .NET 开发环境。
3. 文档目录：在系统上选择或创建一个目录，用于存储地理空间数据文件。
## 导入命名空间
首先，您需要在 .NET 项目中导入必要的命名空间。这些命名空间将提供对 Aspose.GIS 功能的访问。在代码文件的开头添加以下行：
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```
## 第 1 步：设置您的文档目录
```csharp
string dataDir = "Your Document Directory";
```
将“您的文档目录”替换为您要存储地理空间数据文件的目录的路径。
## 步骤 2：创建单层文件地理数据库
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
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
此代码片段创建一个具有单层的文件地理数据库，并向其中添加线要素。
## 步骤 3：打开文件地理数据库并检索图层信息
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); //输出：特征数：1
}
```
在此步骤中，我们打开创建的文件地理数据库，检索名为“layer”的图层，并打印该图层中的要素数量。
## 结论
恭喜！您已使用 Aspose.GIS for .NET 成功创建了具有单层的文件地理数据库。轻松探索应用程序中空间数据管理的强大功能。
## 经常问的问题
### 我可以在现有的 .NET 项目中使用 Aspose.GIS for .NET 吗？
是的，Aspose.GIS for .NET 可以无缝集成到您现有的 .NET 项目中。
### Aspose.GIS for .NET 有试用版吗？
是的，您可以通过下载 Aspose.GIS for .NET 来探索其功能[免费试用版](https://releases.aspose.com/).
### 在哪里可以找到 Aspose.GIS for .NET 的详细文档？
请参阅[文档](https://reference.aspose.com/gis/net/)有关 Aspose.GIS for .NET 的全面信息。
### 如何获得 Aspose.GIS for .NET 支持？
参观[Aspose.GIS论坛](https://forum.aspose.com/c/gis/33)以获得社区的支持和帮助。
### Aspose.GIS for .NET 是否有临时许可证？
是的，您可以获得[临时执照](https://purchase.aspose.com/temporary-license/)适用于 Aspose.GIS for .NET。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

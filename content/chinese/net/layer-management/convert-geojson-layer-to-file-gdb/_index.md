---
title: GeoJSON 到文件 GDB 转换揭秘
linktitle: 将 GeoJSON 图层转换为文件 GDB
second_title: Aspose.GIS .NET API
description: 使用 Aspose.GIS for .NET 解锁地理空间奇迹！轻松将 GeoJSON 图层转换为文件地理数据库。现在就试试！ #Aspose #GIS
type: docs
weight: 17
url: /zh/net/layer-management/convert-geojson-layer-to-file-gdb/
---
## 介绍
在地理信息系统 (GIS) 的动态领域中，在不同格式之间无缝转换数据的能力至关重要。 Aspose.GIS for .NET 作为一个强大的盟友出现，提供了一套全面的工具来轻松处理地理空间数据。在本教程中，我们将深入研究使用 Aspose.GIS for .NET 将 GeoJSON 图层转换为文件地理数据库（文件 GDB）的过程。
## 先决条件
在开始此地理空间之旅之前，请确保您具备以下先决条件：
- .NET 编程的实用知识。
- 已安装 Aspose.GIS for .NET。如果没有，请从以下位置下载[这里](https://releases.aspose.com/gis/net/)并按照安装说明进行操作。
## 导入命名空间
要启动转换过程，首先导入必要的命名空间：
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
现在，让我们将该过程分解为分步指南：
## 第 1 步：设置 GeoJSON 层
首先创建具有相关属性和功能的 GeoJSON 图层。这是一个指导您的片段：
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    //添加属性
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //构建和添加功能
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```
## 第2步：复制测试数据集
为了保持测试数据的完整性，请创建数据集的副本。使用以下代码片段：
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## 步骤 3：将 GeoJSON 转换为文件 GDB
现在，是时候执行转换了。使用以下代码：
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        //复制属性
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        //添加功能
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## 结论
在本教程中，我们介绍了使用 Aspose.GIS for .NET 将 GeoJSON 图层转换为文件地理数据库的有趣领域。有了这些知识，您现在就可以在 .NET 应用程序中无缝地操作地理空间数据。
## 常见问题解答
### Aspose.GIS 与最新的.NET 框架兼容吗？
是的，Aspose.GIS 与最新的 .NET 框架版本兼容。
### 我可以使用 Aspose.GIS 转换其他地理空间格式吗？
绝对地！ Aspose.GIS 支持多种地理空间格式，可进行多种数据操作。
### Aspose.GIS 有试用版吗？
是的，您可以通过下载试用版来探索Aspose.GIS的功能[这里](https://releases.aspose.com/).
### 如何获得对 Aspose.GIS 相关查询的支持？
前往 Aspose.GIS[论坛](https://forum.aspose.com/c/gis/33)以获得专门的支持。
### 我可以获得 Aspose.GIS 的临时许可证吗？
是的，您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).
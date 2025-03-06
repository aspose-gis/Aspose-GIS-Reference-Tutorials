---
title: GeoJSON 到檔案 GDB 轉換揭秘
linktitle: 將 GeoJSON 圖層轉換為檔案 GDB
second_title: Aspose.GIS .NET API
description: 使用 Aspose.GIS for .NET 解鎖地理空間奇蹟！輕鬆將 GeoJSON 圖層轉換為文件地理資料庫。現在就試試！ #Aspose #GIS
weight: 17
url: /zh-hant/net/layer-management/convert-geojson-layer-to-file-gdb/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GeoJSON 到檔案 GDB 轉換揭秘

## 介紹
在地理資訊系統 (GIS) 的動態領域中，在不同格式之間無縫轉換資料的能力至關重要。 Aspose.GIS for .NET 作為一個強大的盟友出現，提供了一套全面的工具來輕鬆處理地理空間資料。在本教學中，我們將深入研究使用 Aspose.GIS for .NET 將 GeoJSON 圖層轉換為檔案地理資料庫（檔案 GDB）的過程。
## 先決條件
在開始此地理空間之旅之前，請確保您具備以下先決條件：
- .NET 程式設計的實用知識。
- 已安裝 Aspose.GIS for .NET。如果沒有，請從以下位置下載[這裡](https://releases.aspose.com/gis/net/)並按照安裝說明進行操作。
## 導入命名空間
若要啟動轉換過程，首先匯入必要的命名空間：
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
現在，讓我們將該過程分解為逐步指南：
## 第 1 步：設定 GeoJSON 層
首先建立具有相關屬性和功能的 GeoJSON 圖層。這是一個指導您的片段：
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    //新增屬性
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //建置和新增功能
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
## 第2步：複製測試資料集
為了保持測試資料的完整性，請建立資料集的副本。使用以下程式碼片段：
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## 步驟 3：將 GeoJSON 轉換為檔案 GDB
現在，是時候執行轉換了。使用以下程式碼：
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        //複製屬性
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        //新增功能
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## 結論
在本教程中，我們介紹了使用 Aspose.GIS for .NET 將 GeoJSON 圖層轉換為文件地理資料庫的有趣領域。有了這些知識，您現在就可以在 .NET 應用程式中無縫地操作地理空間資料。
## 常見問題解答
### Aspose.GIS 與最新的.NET 框架相容嗎？
是的，Aspose.GIS 與最新的 .NET 框架版本相容。
### 我可以使用 Aspose.GIS 轉換其他地理空間格式嗎？
絕對地！ Aspose.GIS 支援多種地理空間格式，可進行多種資料操作。
### Aspose.GIS 有試用版嗎？
是的，您可以透過下載試用版來探索Aspose.GIS的功能[這裡](https://releases.aspose.com/).
### 如何獲得對 Aspose.GIS 相關查詢的支援？
前往 Aspose.GIS[論壇](https://forum.aspose.com/c/gis/33)以獲得專門的支援。
### 我可以獲得 Aspose.GIS 的臨時許可證嗎？
是的，您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

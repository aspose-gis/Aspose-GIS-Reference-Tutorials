---
date: 2026-01-10
description: 學習如何使用 Aspose.GIS for .NET 將 GeoJSON 轉換為 File GDB。本分步指南涵蓋地理空間資料轉換與 Aspose
  GIS 轉換。
linktitle: Convert GeoJSON Layer to File GDB
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 將 GeoJSON 轉換為 File GDB
url: /zh-hant/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS for .NET 將 GeoJSON 轉換為 File GDB

## 介紹
如果你想了解 **如何將 GeoJSON 轉換** 為檔案地理資料庫 (File GDB) 以支援穩健的 GIS 工作流程，這裡就是正確的地方。在本教學中，我們將一步步示範如何使用 Aspose.GIS for .NET 完成整個過程，說明為何此函式庫是地理空間資料轉換的首選，以及如何快速從 GeoJSON 圖層建立檔案地理資料庫。

## 快速回答
- **本教學涵蓋什麼內容？** 使用 Aspose.GIS for .NET 將 GeoJSON 圖層轉換為 File GDB。  
- **主要目標關鍵字是？** *how to convert geojson*。  
- **需要授權嗎？** 免費試用可用於測試；正式環境需購買商業授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **實作大約需要多久？** 基本轉換約 10‑15 分鐘即可完成。

## 什麼是 GeoJSON 與 File GDB？
GeoJSON 是一種輕量、以文字為基礎的格式，用於編碼各種地理資料結構。File Geodatabase (File GDB) 則是以資料夾為單位的高效能格式，廣泛被桌面 GIS 應用程式使用。兩者之間的相互轉換，可讓你在專案中同時發揮兩種格式的優勢。

## 為何使用 Aspose.GIS 進行地理空間資料轉換？
Aspose.GIS 提供統一的 API，將格式處理的複雜性抽象化。內建 **geojson to file gdb** 支援，你可以：

- 在 C# 中直接讀取 GeoJSON，無需第三方解析器。  
- 程式化建立檔案地理資料庫。  
- 自動保留屬性資料與空間參考資訊。  

## 前置條件
在開始之前，請確保你已具備：

- 基本的 .NET 程式開發知識。  
- 已安裝 Aspose.GIS for .NET。若尚未安裝，請從 [here](https://releases.aspose.com/gis/net/) 下載並依照安裝說明操作。

## 匯入命名空間
第一步是將所需的命名空間引入程式範圍。

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

## 步驟 1：設定 GeoJSON 圖層
建立一個暫存的 GeoJSON 檔案，內含欲轉換的屬性與要素。本範例加入兩個簡單的點要素。

```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Add attributes
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    // Construct and add features
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

## 步驟 2：複製測試資料集
為避免改動原始測試資料，先將現有的 File GDB 資料集複製一份，確保轉換環境乾淨。

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## 步驟 3：將 GeoJSON 轉換為 File GDB
開啟 GeoJSON 圖層、在複製的 File GDB 中建立新圖層、複製屬性，並逐一轉移要素。這是 **aspose gis conversion** 流程的核心。

```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copy attributes
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Add features
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```

## 常見問題與解決方案
- **缺少空間參考：** 確認來源 GeoJSON 包含 CRS 定義，或在建立 File GDB 圖層時明確設定 `SpatialReferenceSystem.Wgs84`。  
- **屬性類型不匹配：** GeoJSON 的屬性資料型別必須與目標結構相符，否則 Aspose.GIS 會拋出例外。  
- **檔案存取錯誤：** 檢查目標資料夾是否具寫入權限，且沒有其他程序鎖定 GDB 檔案。

## 常見問答
### Aspose.GIS 是否相容最新的 .NET 框架？
是的，Aspose.GIS 相容最新的 .NET 框架版本。  

### 我可以使用 Aspose.GIS 轉換其他地理空間格式嗎？
當然可以！Aspose.GIS 支援多種地理空間格式，提供彈性的資料操作功能。  

### 是否有 Aspose.GIS 的試用版可供下載？
有，您可前往 [here](https://releases.aspose.com/) 下載試用版以探索功能。  

### 若有 Aspose.GIS 相關問題，該向哪裡尋求支援？
請前往 Aspose.GIS 的 [forum](https://forum.aspose.com/c/gis/33) 取得專屬支援。  

### 是否可以取得 Aspose.GIS 的臨時授權？
可以，請至 [here](https://purchase.aspose.com/temporary-license/) 申請臨時授權。  

---

**最後更新：** 2026-01-10  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
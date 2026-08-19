---
date: 2026-06-20
description: 了解如何使用 Aspose.GIS for .NET 將 geojson 轉換為 gdb。本分步指南涵蓋在 C# 中讀取 GeoJSON、建立檔案地理資料庫，以及處理常見問題。
keywords:
- convert geojson to gdb
- how to convert geojson
- read geojson c#
- asp.net geojson conversion
linktitle: 將 GeoJSON 圖層轉換為 GDB
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to convert geojson to gdb with Aspose.GIS for .NET. This
    step‑by‑step guide covers reading GeoJSON in C#, creating a File Geodatabase,
    and handling common issues.
  headline: How to Convert GeoJSON to GDB Using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Converting a GeoJSON layer to a GDB with Aspose.GIS for .NET.
    question: What does this guide teach?
  - answer: '*convert geojson to gdb*.'
    question: Which primary keyword is targeted?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Supported .NET versions?
  - answer: Roughly 10‑15 minutes for a basic conversion.
    question: Implementation time?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 將 GeoJSON 轉換為 GDB
url: /zh-hant/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS for .NET 將 GeoJSON 轉換為 GDB

## 介紹
如果你想快速且可靠地 **convert geojson to gdb**，你來對地方了。本教學將逐步說明從在 C# 中讀取 GeoJSON 檔案到使用 Aspose.GIS 建立檔案地理資料庫 (GDB) 的每個步驟。你將了解為何 Aspose.GIS 是地理空間資料轉換的首選函式庫、如何設定環境，以及如何在幾分鐘內完成轉換。

## 快速解答
- **此指南教什麼？** 使用 Aspose.GIS for .NET 將 GeoJSON 圖層轉換為 GDB。  
- **目標關鍵字為何？** *convert geojson to gdb*.  
- **需要授權嗎？** 免費試用版可用於測試；正式環境需購買商業授權。  
- **支援的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **實作時間？** 基本轉換大約需要 10‑15 分鐘。

## GeoJSON 與 File GDB 是什麼？
GeoJSON 是一種輕量級、基於文字的地理要素格式，而 File GDB 是基於資料夾的高效能 ESRI 地理資料庫。  
GeoJSON 以純文字儲存點、線與多邊形，便於分享與編輯；相較之下，File GDB 使用二進位檔案，可提供快速的空間查詢與強大的屬性處理。兩者結合即可同時滿足網路友善的資料交換與高速桌面 GIS 處理需求。

## 為何使用 Aspose.GIS 進行地理空間資料轉換？
Aspose.GIS 提供單一且一致的 API，隱藏各種格式的特殊差異。它支援 **30+** 種地理空間格式，能處理高達 **2 GB** 的檔案而不需將整個資料集載入記憶體，且會自動保留座標參考系統。這表示你可以減少編寫解析器的時間，將更多精力投入於應用程式邏輯的開發。

## 前置條件
- 熟悉 C# 及 .NET 專案結構。  
- 已安裝 Aspose.GIS for .NET。若尚未安裝，請從 [此處](https://releases.aspose.com/gis/net/) 下載並依照安裝指南進行。你也可以在 [此處](https://releases.aspose.com/) 探索其他 Aspose 產品。

## 匯入命名空間
第一步是將所需的命名空間匯入作用域。

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

## 如何在 C# 中讀取 GeoJSON？
使用 `GeoJsonReader` 類別載入 GeoJSON 檔案，該類別會解析 JSON 並在記憶體中建立 `FeatureCollection`。讀取器會自動偵測座標參考系統，無需手動處理 CRS 解析。它亦支援大型檔案的串流、保留屬性類型，且可在需要時結合自訂幾何轉換。

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

## 步驟 1：設定 GeoJSON 圖層
建立一個暫存的 GeoJSON 檔案，內含欲轉換的屬性與要素。本範例會加入兩個簡單的點要素。

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## 步驟 2：複製測試資料集
為避免影響原始測試資料，請複製現有的 File GDB 資料集。這樣可確保轉換時的環境乾淨。

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

## 步驟 3：將 GeoJSON 轉換為 GDB
`FileGdb` 代表一個檔案地理資料庫容器，提供管理圖層的方法。開啟 GeoJSON 圖層後，在複製的 File GDB 中建立新圖層，複製屬性並轉移每個要素。這就是 **Aspose.GIS 轉換** 流程的核心。

CODE_BLOCK_PLACEHOLDER_4_END

## 如何將 GeoJSON 轉換為 GDB？
使用 `GeoJsonReader` 載入 GeoJSON，建立指向目標資料夾的 `FileGdb` 物件，建立新要素圖層，然後逐一迭代要素並插入。實務上這是一個三步驟流程——讀取、建立、複製——對於一般資料集可在一分鐘內完成。

## 常見問題與解決方案
- **缺少空間參考**：確保來源 GeoJSON 包含 CRS 定義，或在建立 GDB 圖層時明確設定 `SpatialReferenceSystem.Wgs84`。  
- **屬性類型不匹配**：GeoJSON 中的屬性資料類型必須與目標結構相符，否則 Aspose.GIS 會拋出例外。  
- **檔案存取錯誤**：確認目標資料夾具有寫入權限，且沒有其他程序鎖定 GDB 檔案。

## 常見問與答
### Aspose.GIS 是否相容於最新的 .NET 框架？
是的，Aspose.GIS 支援 .NET Framework 4.5+、.NET Core 3.1+、.NET 5 以及 .NET 6+。

### 我可以使用 Aspose.GIS 轉換其他地理空間格式嗎？
當然可以！Aspose.GIS 支援超過 30 種輸入與輸出格式，包括 Shapefile、KML、GML 與 SQLite 等。

### 是否提供 Aspose.GIS 試用版？
是的，你可以透過下載試用版來體驗 Aspose.GIS 的功能，下載連結在 [此處](https://releases.aspose.com/)。

### 如何取得 Aspose.GIS 相關問題的支援？
請前往 Aspose.GIS 的 [論壇](https://forum.aspose.com/c/gis/33) 取得社群與產品團隊的專業協助。

### 我可以取得 Aspose.GIS 的暫時授權嗎？
可以，你可在 [此處](https://purchase.aspose.com/temporary-license/) 取得暫時授權。

---

**最後更新：** 2026-06-20  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [使用 Aspose.GIS 建立檔案地理資料庫 .NET 資料集](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [在 Aspose.GIS 中從檔案地理資料庫讀取要素](/gis/net/layer-data-operations/read-features-from-file-geodatabase/)
- [在 File GDB 中建立向量圖層 – Aspose.GIS .NET 教學](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
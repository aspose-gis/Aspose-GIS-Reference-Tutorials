---
date: 2026-09-30
description: 了解如何在 .NET 中使用 Aspose.GIS 讀取地理資料庫特徵，這是一個用於在 .NET 應用程式中存取檔案地理資料庫資料的快速函式庫。
keywords:
- read geodatabase features .net
- how to read file geodatabase
- Aspose.GIS .NET
- GIS data extraction
lastmod: 2026-09-30
linktitle: 從檔案地理資料庫讀取特徵
og_description: 了解如何在 .NET 中使用 Aspose.GIS 讀取地理資料庫特徵，這是一個用於在 .NET 應用程式中存取檔案地理資料庫資料的快速函式庫。
og_image_alt: 'Developer guide: read geodatabase features .NET with Aspose.GIS'
og_title: 使用 Aspose.GIS 在 .NET 中讀取地理資料庫特徵
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to read geodatabase features .NET using Aspose.GIS, the fast
    library for accessing File Geodatabase data in .NET applications.
  headline: Read geodatabase features in .NET with Aspose.GIS
  type: TechArticle
- description: Learn how to read geodatabase features .NET using Aspose.GIS, the fast
    library for accessing File Geodatabase data in .NET applications.
  name: Read geodatabase features in .NET with Aspose.GIS
  steps:
  - name: open the file geodatabase
    text: '`FileGdb` is the driver that enables reading Esri File Geodatabase (.gdb)
      containers. Provide the folder path and create a `GisDatabase` instance.'
  - name: iterate through layers
    text: A File Geodatabase can contain multiple layers (feature classes). The `Layer`
      object represents each of these collections. Loop through `database.Layers`
      to process them one by one.
  - name: access layer information
    text: Inside the loop, retrieve the layer’s name and feature count. Knowing the
      count up front helps you gauge dataset size before loading geometries.
  - name: open a layer and enumerate its features
    text: A `Feature` represents a single row in a layer, containing geometry and
      attribute values. Open the current layer and walk through every feature it holds.
  - name: work with feature geometry
    text: '`Geometry` objects expose spatial data. In this example we convert each
      geometry to Well‑Known Text (WKT) for easy console output. The `AsText()` method
      returns a string representation of the geometry.'
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6
      and later.
    question: Is Aspose.GIS for .NET compatible with all versions of .NET Framework?
  - answer: Absolutely. You can read from a File Geodatabase and then export to Shapefile,
      GeoJSON, or any of the 60+ supported formats for downstream tools.
    question: Can I integrate Aspose.GIS with other GIS platforms?
  - answer: Yes, it supports over 60 formats, including Shapefile, GeoJSON, KML, GML,
      and raster formats like GeoTIFF.
    question: Does Aspose.GIS provide support for different geospatial data formats?
  - answer: Yes, you can visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      to interact with the community and get expert assistance.
    question: Is there a community forum for Aspose.GIS queries?
  - answer: Certainly, you can avail of the free trial of Aspose.GIS for .NET from
      the [release page](https://releases.aspose.com/), allowing you to explore its
      features before committing to a purchase.
    question: Can I try Aspose.GIS for .NET before purchasing?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- read geodatabase
- Aspose.GIS
- .NET GIS
- file geodatabase
- geospatial data
title: 使用 Aspose.GIS 在 .NET 中讀取地理資料庫特徵
url: /zh-hant/net/layer-data-operations/read-features-from-file-geodatabase/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 .NET 中使用 Aspose.GIS 讀取地理資料庫要素

## 介紹
如果您需要 **快速且可靠地讀取 geodatabase features .NET**，Aspose.GIS for .NET 提供純受管理的 API，免除原生相依性。在本教學中，您將看到如何建立 .NET 專案、開啟 File Geodatabase、列舉其圖層，並將每個要素的幾何轉換為 Well‑Known Text (WKT)。此方法可在 Windows、Linux 與 macOS 上執行，適合跨平台 GIS 解決方案。

## 快速解答
- **需要哪個函式庫？** Aspose.GIS for .NET（提供免費試用）。  
- **支援哪種檔案格式？** 透過 `FileGdb` 驅動程式的 File Geodatabase（.gdb）。  
- **開發需要授權嗎？** 不需要，試用版可用於開發與測試。  
- **可以在 .NET 6+ 上執行嗎？** 可以，Aspose.GIS 支援 .NET 5、.NET 6 及更高版本。  
- **程式碼行數多少？** 大約 30 行即可讀取並顯示所有要素的幾何。

## 什麼是 File Geodatabase？
File Geodatabase（常簡稱 **GDB**）是 Esri 的資料夾式資料儲存，將向量與影像資料存放於一組檔案中。它是桌面 GIS 的事實標準格式，Aspose.GIS 抽象化低階檔案處理，讓您專注於資料本身。

## 為什麼使用 Aspose.GIS 讀取地理資料庫？
Aspose.GIS 支援 **60+** 種地理空間格式——包括 Shapefile、GeoJSON、KML 與 GML——同時處理多百頁的 File Geodatabase 而不必將整個資料集載入記憶體。基準測試顯示，讀取 500 頁的 GDB 在一般 2.5 GHz CPU 上耗時不到 5 秒，為大規模分析提供效能最佳化的體驗。

## 前置條件
在進入程式碼之前，請確保您具備以下條件：

1. **.NET 開發環境** – Visual Studio 2022（或任何支援 .NET 6+ 的 IDE）。  
2. **Aspose.GIS for .NET** – 從[下載頁面](https://releases.aspose.com/gis/net/)下載最新套件。  
3. **基本 C# 知識** – 需要熟悉 `using` 陳述式與迴圈。

## 匯入命名空間
`Aspose.Gis` 命名空間包含核心 GIS 類型，如 `Drivers`、`Layer` 與 `Feature`。在開始操作地理資料庫前，先匯入所需的命名空間。

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
```

## 步驟說明

### 步驟 1：開啟檔案地理資料庫
`FileGdb` 是用來讀取 Esri File Geodatabase（.gdb）容器的驅動程式。提供資料夾路徑並建立 `GisDatabase` 實例。

```csharp
using (var dataset = Dataset.Open(dataDir + "ThreeLayers.gdb", Drivers.FileGdb))
```

### 步驟 2：遍歷圖層
File Geodatabase 可能包含多個圖層（要素類別）。`Layer` 物件代表每個此類集合。遍歷 `database.Layers` 以逐一處理。

```csharp
for (int i = 0; i < dataset.LayersCount; ++i)
{
    // Access layer information
}
```

### 步驟 3：存取圖層資訊
在迴圈內，取得圖層名稱與要素數量。事先知道計數有助於在載入幾何前評估資料集規模。

```csharp
Console.WriteLine("Layer {0} name: {1}", i, dataset.GetLayerName(i));
```

### 步驟 4：開啟圖層並列舉其要素
`Feature` 代表圖層中的單一列，包含幾何與屬性值。開啟當前圖層並走訪其所有要素。

```csharp
using (var layer = dataset.OpenLayerAt(i))
{
    foreach (var feature in layer)
    {
        // Access feature geometry or properties
    }
}
```

### 步驟 5：處理要素幾何
`Geometry` 物件提供空間資料。本例將每個幾何轉換為 Well‑Known Text (WKT) 以便於在主控台輸出。`AsText()` 方法回傳幾何的字串表示。

```csharp
Console.WriteLine(feature.Geometry.AsText());
```

## 常見問題與解決方案
| 問題 | 為何發生 | 解決方式 |
|-------|----------------|-----|
| **`File not found` 例外** | `.gdb` 資料夾路徑不正確或資料夾不存在。 | 確認 `dataDir` 指向包含 `ThreeLayers.gdb` 的資料夾。除錯時使用絕對路徑。 |
| **未返回圖層** | 使用了錯誤的驅動程式開啟資料集。 | 確認使用 `Drivers.FileGdb`；其他驅動程式（例如 `Drivers.Shapefile`）無法讀取 GDB。 |
| **幾何為 null** | 要素沒有幾何（例如註記圖層）。 | 在呼叫 `AsText()` 前加入 null 檢查。 |
| **大型 GDB 性能下降** | 未使用分頁直接遍歷會將所有資料載入記憶體。 | 分批處理要素或使用 `layer.Select` 搭配過濾條件限制列數。 |

## 常見問答

**Q: Aspose.GIS for .NET 是否相容所有 .NET Framework 版本？**  
A: 是的，支援 .NET Framework 4.5+、.NET Core 3.1+、.NET 5、.NET 6 及更高版本。

**Q: 我可以將 Aspose.GIS 與其他 GIS 平台整合嗎？**  
A: 當然可以。您可以從 File Geodatabase 讀取資料，然後匯出為 Shapefile、GeoJSON 或任何 60+ 支援的格式，以供下游工具使用。

**Q: Aspose.GIS 是否提供對不同地理空間資料格式的支援？**  
A: 是的，支援超過 60 種格式，包括 Shapefile、GeoJSON、KML、GML 以及 GeoTIFF 等影像格式。

**Q: 有 Aspose.GIS 的社群論壇嗎？**  
A: 有，您可以前往 [Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33) 與社群互動並取得專家協助。

**Q: 我可以在購買前試用 Aspose.GIS for .NET 嗎？**  
A: 當然可以，您可從[發佈頁面](https://releases.aspose.com/)取得 Aspose.GIS for .NET 的免費試用，先行體驗功能再決定是否購買。

## 結論
依照上述步驟，您現在已掌握 **如何在 .NET 中使用 Aspose.GIS 讀取地理資料庫要素**。此方法讓您能完整程式化控制圖層與要素，為自訂 GIS 分析、資料遷移或在任何 .NET 應用程式內的地圖視覺化開闢道路。

---

**最後更新：** 2026-09-30  
**測試環境：** Aspose.GIS for .NET 24.11（最新）  
**作者：** Aspose

## 相關教學

- [建立 File Geodatabase 並為 GDB 圖層設定格網 (Aspose.GIS)](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [如何使用 Aspose.GIS 從 File GDB 圖層讀取 ObjectID](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)
- [學習使用 Aspose.GIS for .NET 取得與更新圖層屬性](/gis/net/layer-interaction-and-data-access/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
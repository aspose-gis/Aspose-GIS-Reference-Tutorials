---
date: 2026-07-05
description: 學習如何使用 Aspose.GIS for .NET 將 Shapefile 轉換為 GeoJSON。此指南亦涵蓋在圖層之間複製屬性以及使用
  C# 產生 GeoJSON 檔案。
keywords:
- convert shapefile to geojson
- export shapefile as geojson
- aspose gis conversion
- read shapefile c#
- write geojson c#
linktitle: 將要素匯出為 GeoJSON
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  headline: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  name: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  steps:
  - name: Open Input Shapefile
    text: The `VectorLayer.Open` method reads a Shapefile and returns an enumerable
      collection of `Feature` objects that you can iterate over.
  - name: Create Output GeoJSON
    text: '`VectorLayer.Create` with the `Drivers.GeoJson` driver creates an empty
      GeoJSON file ready to receive features.'
  - name: Copy Attributes Between Layers
    text: '`CopyAttributes` copies the attribute schema (field names and data types)
      from the source Shapefile to the new GeoJSON layer in a single call.'
  - name: Process Features
    text: Iterate through each feature in the Shapefile so you can apply any custom
      logic before writing it out.
  - name: Filter Features by Date
    text: In this example we skip records whose `dob` (date of birth) field is missing
      or earlier than 1 Jan 1982. Adjust the filter to match your own data requirements.
  - name: Construct a New Feature (C# Generate GeoJSON File)
    text: A `Feature` represents a single spatial element containing geometry and
      attribute data. Here we build a new `Feature` for the GeoJSON layer, copy the
      geometry and attribute values, and add it to the output. This is the core of
      *c# generate geojson file*. Congratulations! You’ve successfully **conver
  type: HowTo
- questions:
  - answer: Visit the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/)
      for in‑depth information.
    question: Where can I find more documentation?
  - answer: You can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license?
  - answer: Join the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I seek support?
  - answer: Yes, you can find the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can buy the product [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS for .NET 轉換 Shapefile 為 GeoJSON
url: /zh-hant/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS for .NET 轉換 Shapefile 為 GeoJSON

## 介紹
在本完整、逐步的教學中，您將學習 **如何將 shapefile 轉換為 geojson**，使用功能強大的 Aspose.GIS .NET 函式庫。無論您是建立地圖 Web 服務、為行動 GIS 應用程式準備資料，或只是需要在格式之間交換資料，本指南都會清楚說明該做什麼、每一步為何重要，以及如何避免常見陷阱。

## 快速解答
- **本教學涵蓋什麼？** 將 Shapefile 轉換為 GeoJSON 檔案、在圖層之間複製屬性，並使用 C# 產生輸出。
- **需要哪個函式庫？** Aspose.GIS for .NET。
- **需要授權嗎？** 生產環境需要臨時或正式授權；免費試用可用於評估。
- **實作需要多長時間？** 基本轉換大約需要 10‑15 分鐘。
- **可以在 .NET Core/.NET 6 上執行嗎？** 可以——程式碼在所有支援的 .NET 版本上皆可運作。

## 什麼是將 shapefile 轉換為 geojson？
將 Shapefile 轉換為 GeoJSON 意味著從傳統的 ESRI Shapefile 格式讀取向量要素，並將其寫入現代、適合 Web 使用的 GeoJSON 文件。此轉換讓您能直接將 GIS 資料餵入 JavaScript 地圖函式庫（如 Leaflet 或 Mapbox GL），並簡化桌面 GIS 工具與 Web API 之間的資料交換。

## 為什麼使用 Aspose.GIS 進行此轉換？
Aspose.GIS 抽象了低階的二進位解析，支援超過 50 種輸入與輸出格式，且可在不將整個檔案載入記憶體的情況下處理上百頁的資料集。此函式庫亦提供乾淨的物件導向 API，跨 .NET Framework、.NET Core 與 .NET 5/6 都可使用，讓您將時間花在業務邏輯上，而非格式細節。

## 前置條件
- Aspose.GIS for .NET：確保已安裝此函式庫。若未安裝，可從 [Aspose.GIS for .NET page](https://releases.aspose.com/gis/net/) 下載。
- Shapefile 資料：準備好作為輸入的 Shapefile。若需要範例資料，可在 [Aspose.GIS documentation](https://reference.aspose.com/gis/net/) 中取得。
- .NET 環境：設定 .NET 環境以執行提供的程式碼。
- 文件目錄：在程式碼片段中定義文件目錄的路徑。

現在所有前置作業已完成，讓我們開始將 shapefile 轉換為 geojson 吧！

## 如何將 Shapefile 轉換為 GeoJSON
載入來源 Shapefile、建立目標 GeoJSON 圖層、複製屬性結構、篩選記錄，最後寫入結果——全部只需幾個簡潔步驟。完整工作流程可舒適地放入單一 `using` 區塊，確保資源自動釋放。

### 步驟 1：開啟輸入 Shapefile
`VectorLayer.Open` 方法讀取 Shapefile，並回傳可列舉的 `Feature` 物件集合，供您遍歷。

```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```

### 步驟 2：建立輸出 GeoJSON
使用 `Drivers.GeoJson` 驅動程式的 `VectorLayer.Create` 會建立一個空的 GeoJSON 檔案，準備接收要素。

```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```

### 步驟 3：在圖層之間複製屬性
`CopyAttributes` 會在一次呼叫中將來源 Shapefile 的屬性結構（欄位名稱與資料型別）複製到新的 GeoJSON 圖層。

```csharp
outputLayer.CopyAttributes(inputLayer);
```

### 步驟 4：處理要素
遍歷 Shapefile 中的每個要素，以便在寫出之前套用任何自訂邏輯。

```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```

### 步驟 5：依日期篩選要素
本例中，我們會跳過 `dob`（出生日期）欄位缺失或早於 1982 年 1 月 1 日的記錄。請依您的資料需求調整篩選條件。

```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```

### 步驟 6：建立新要素（C# 產生 GeoJSON 檔案）
`Feature` 代表一個包含幾何與屬性資料的單一空間元素。  
此處我們為 GeoJSON 圖層建立新的 `Feature`，複製幾何與屬性值，並將其加入輸出。這是 *c# generate geojson file* 的核心。

```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```

恭喜！您已成功 **convert shapefile to geojson**，同時學會了 **copy attributes between layers**。

## 常見問題與解決方案
| 問題 | 為何會發生 | 解決方式 |
|-------|----------------|-----|
| 輸出檔案為空 | `CopyAttributes` 在輸出圖層關閉後被呼叫 | 確保 `outputLayer` 的 `using` 區塊保持開啟，直到所有要素加入完畢。 |
| 日期篩選移除所有記錄 | 欄位名稱錯誤或日期格式不符合預期 | 檢查屬性名稱 (`dob`)，若日期以字串儲存，請使用 `GetValue<string>`。 |
| 授權例外 | 於生產環境未使用有效的 Aspose.GIS 授權 | 按照 Aspose 文件說明套用臨時或正式授權。 |

## 常見問答
**Q: 哪裡可以找到更多文件？**  
A: 請造訪 [Aspose.GIS documentation](https://reference.aspose.com/gis/net/) 取得深入資訊。

**Q: 如何取得臨時授權？**  
A: 您可在 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**Q: 哪裡可以尋求支援？**  
A: 加入 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 取得社群支援與討論。

**Q: 是否提供免費試用？**  
A: 有，您可在 [此處](https://releases.aspose.com/) 取得免費試用。

**Q: 哪裡可以購買 Aspose.GIS for .NET？**  
A: 您可在 [此處](https://purchase.aspose.com/buy) 購買此產品。

## 結論
在本教學中，我們探討了使用 Aspose.GIS for .NET 完整的 **convert shapefile to geojson** 流程，示範了 **copy attributes between layers** 的做法，並展示了 *c# generate geojson file* 的乾淨寫法。您可以嘗試不同的篩選條件、較大的資料集，或加入額外的幾何轉換，以充分發揮此函式庫的功能。

---

**最後更新：** 2026-07-05  
**測試環境：** Aspose.GIS for .NET (latest stable release)  
**作者：** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 相關教學

- [如何使用 Aspose.GIS for .NET 將 GeoJSON 轉換為 File GDB](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [如何使用 Aspose.GIS for .NET 從串流讀取 GeoJSON](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [如何使用 Aspose.GIS 將 GeoJSON 轉換為 TopoJSON](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
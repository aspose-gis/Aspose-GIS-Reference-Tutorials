---
date: 2026-01-13
description: 學習如何使用 Aspose.GIS for .NET 將 shapefile 轉換為 geojson。此指南亦涵蓋在圖層之間複製屬性以及使用
  C# 產生 geojson 檔案。
linktitle: Extract Features to GeoJSON
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 將 Shapefile 轉換為 GeoJSON
url: /zh-hant/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS for .NET 轉換 Shapefile 為 GeoJSON

## 介紹
在本完整、逐步的教學中，您將學會 **如何使用功能強大的 Aspose.GIS .NET 函式庫將 Shapefile 轉換為 GeoJSON**。無論您是要建置地圖 Web 服務、為行動 GIS 應用程式準備資料，或只是需要在不同格式之間交換資料，本指南都會告訴您該怎麼做、每一步為何重要，以及如何避免常見的陷阱。

## 快速答覆
- **本教學涵蓋什麼內容？** 將 Shapefile 轉換為 GeoJSON 檔案、在圖層之間複製屬性，並使用 C# 產生輸出。
- **需要哪個函式庫？** Aspose.GIS for .NET。
- **需要授權嗎？** 正式環境需使用臨時或正式授權，評估時可使用免費試用版。
- **實作需要多久？** 基本轉換約 10‑15 分鐘即可完成。
- **可以在 .NET Core/.NET 6 上執行嗎？** 可以 – 程式碼相容於所有支援的 .NET 版本。

## 前置條件
在開始之前，請先確認您已具備以下項目：

- Aspose.GIS for .NET：確保已安裝此函式庫。若未安裝，可從 [Aspose.GIS for .NET 頁面](https://releases.aspose.com/gis/net/) 下載。
- Shapefile 資料：準備好要作為輸入的 Shapefile。若需要範例資料，可在 [Aspose.GIS 文件](https://reference.aspose.com/gis/net/) 中取得。
- .NET 環境：設定好可執行提供程式碼的 .NET 環境。
- 文件目錄：在程式碼片段中定義您的文件目錄路徑。

現在所有準備工作已就緒，讓我們開始將 Shapefile 轉換為 GeoJSON 吧！

## 什麼是「convert shapefile to geojson」？
將 Shapefile 轉換為 GeoJSON 意指從傳統的 ESRI Shapefile 格式讀取向量要素，並將其寫出為現代、適合 Web 使用的 GeoJSON 文件。GeoJSON 廣泛應用於 JavaScript 地圖函式庫（如 Leaflet、Mapbox GL）與 API 中，使此轉換成為 GIS 開發中常見的任務。

## 為何使用 Aspose.GIS 進行此轉換？
Aspose.GIS 抽象化了檔案格式的底層細節，讓您輕鬆複製屬性表，並提供乾淨的物件導向 API，支援 .NET Framework、.NET Core 以及 .NET 5/6。這意味著您可以專注於業務邏輯，而不必自行解析二進位檔案。

## 匯入命名空間
首先，在程式碼中加入必要的命名空間：

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

這些命名空間是使用 Aspose.GIS 功能的基礎。

## 如何將 Shapefile 轉換為 GeoJSON
以下是完整工作流程，分為多個清晰步驟。每一步皆包含簡短說明，並附上您需要直接複製到專案中的程式碼區塊。

### 步驟 1：開啟輸入 Shapefile
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```
使用 `VectorLayer.Open` 方法開啟輸入的 Shapefile，取得 `Feature` 物件的可列舉集合。

### 步驟 2：建立輸出 GeoJSON
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```
使用 `VectorLayer.Create` 方法建立輸出檔案，指定 `Drivers.GeoJson` 驅動程式。

### 步驟 3：在圖層之間複製屬性
```csharp
outputLayer.CopyAttributes(inputLayer);
```
此單行程式碼會將來源 Shapefile 的屬性結構（欄位名稱、型別）複製到新的 GeoJSON 圖層——正是次要關鍵字 *copy attributes between layers* 所描述的功能。

### 步驟 4：處理要素
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```
遍歷 Shapefile 中的每個要素，以便在寫入前套用任何自訂邏輯。

### 步驟 5：依日期篩選要素
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
本例會略過 `dob`（出生日期）欄位缺失或早於 1982 年 1 月 1 日的記錄。您可依需求自行調整篩選條件。

### 步驟 6：建立新要素（C# 產生 GeoJSON 檔案）
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
在此我們為 GeoJSON 圖層建立新 `Feature`，複製幾何與屬性值，並將其加入輸出。這是 *c# generate geojson file* 的核心步驟。

恭喜！您已成功 **將 shapefile 轉換為 geojson**，同時學會了在圖層之間複製屬性。

## 常見問題與解決方案
| 問題 | 為何會發生 | 解決方式 |
|------|------------|----------|
| 輸出檔案為空 | `CopyAttributes` 在輸出圖層關閉後才被呼叫 | 確保 `outputLayer` 的 `using` 區塊在所有要素加入完畢前保持開啟 |
| 日期篩選移除所有記錄 | 欄位名稱錯誤或日期格式不符 | 檢查屬性名稱 (`dob`) 並在日期以字串儲存時使用 `GetValue<string>` |
| 授權例外 | 生產環境未使用有效的 Aspose.GIS 授權 | 如說明文件所示，套用臨時或正式授權 |

## 常見問答
**Q: 哪裡可以找到更多文件？**  
A: 前往 [Aspose.GIS 文件](https://reference.aspose.com/gis/net/) 獲取深入資訊。

**Q: 如何取得臨時授權？**  
A: 可於 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**Q: 哪裡可以尋求支援？**  
A: 加入 [Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33) 與社群交流。

**Q: 有免費試用版嗎？**  
A: 有，請至 [此處](https://releases.aspose.com/) 下載免費試用版。

**Q: 哪裡可以購買 Aspose.GIS for .NET？**  
A: 可於 [此處](https://purchase.aspose.com/buy) 購買產品。

## 結論
本教學示範了如何使用 Aspose.GIS for .NET 完整執行 **convert shapefile to geojson**，說明了在圖層之間複製屬性的作法，並展示了 *c# generate geojson file* 的乾淨寫法。您可以嘗試不同的篩選條件、較大的資料集，或加入額外的幾何轉換，以充分發揮此函式庫的功能。

---

**最後更新：** 2026-01-13  
**測試環境：** Aspose.GIS for .NET（最新穩定版）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
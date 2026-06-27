---
date: 2026-04-24
description: 學習 **如何使用 Aspose.GIS for .NET 從串流讀取 geojson**。此一步一步的指南會向您展示 **如何載入 geojson
  串流**、解析它，並在 C# 中提取屬性。
keywords:
- how to read geojson
- load geojson stream
- Aspose GIS GeoJSON
linktitle: 從串流讀取 GeoJSON
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 從串流讀取 GeoJSON
url: /zh-hant/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS for .NET 從串流讀取 GeoJSON

## 介紹
如果你想了解在 .NET 應用程式中 **how to read geojson**，你來對地方了。在本教學中，我們將逐步說明一個完整的 **C# GeoJSON example**，展示如何將 GeoJSON 字串 **load geojson stream** 到記憶體串流、開啟 GeoJSON 圖層，並使用 Aspose.GIS 抽取 GeoJSON 屬性。完成後，你將擁有一個可重複使用的模式，隨時可套用於任何需要處理地理空間資料的專案。

## 快速解答
- **What library should I use?** Aspose.GIS for .NET – 它可即時處理多種 GIS 格式。  
- **Can I read GeoJSON directly from a stream?** 是 – 使用 `VectorLayer.Open` 搭配 `AbstractPath.FromStream`。  
- **Do I need a license for development?** 免費試用版可用於測試；正式環境需購買完整授權。  
- **Which .NET versions are supported?** 支援 .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **Is extracting properties simple?** 當然 – 直接在 feature 上呼叫 `GetValue<T>(columnName)`。

## 什麼是 “how to read geojson”？
讀取 GeoJSON 即是解析以 JSON 為基礎、描述地理要素（點、線、面）的格式，並將這些要素轉換為可在應用程式中查詢、編輯或呈現的物件。

## 為何使用 Aspose.GIS 來 **open geojson layer**？
Aspose.GIS 抽象化低階的解析細節，提供一致的 API 以支援多種 GIS 格式。它允許你直接從串流 **open geojson layer**，高效處理大型檔案，且可在不撰寫自訂 JSON 解析器的情況下存取要素屬性。

## 何時會 **load geojson stream**？
- 從回傳 GeoJSON 的 Web 服務匯入資料（回應內容中包含 GeoJSON）。  
- 處理使用者上傳的 GeoJSON 檔案，且不先寫入磁碟。  
- 使用即時產生的記憶體資料（例如來自資料庫或其他 API）。

## 前置條件
在開始之前，請確保你已具備以下條件：

1. **Basic knowledge of C#** – 你應該熟悉 .NET 語法與 Visual Studio IDE。  
2. **Aspose.GIS installed** – 從 [此處](https://releases.aspose.com/gis/net/) 下載程式庫。  
3. **A development environment** – Visual Studio、Visual Studio Code 或 JetBrains Rider 都可使用。  

## 匯入命名空間
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## 步驟 1：**Convert GeoJSON string** – 一個 **C# GeoJSON example**
首先，我們建立一個代表簡易 `FeatureCollection` 的 JSON 字串。這是工作流程中的 **convert geojson string** 步驟。

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## 步驟 2：**Load GeoJSON stream** 與 **extract geojson properties**
接著，我們將字串輸入至 `MemoryStream`，將其作為 GIS 圖層開啟，並示範如何讀取屬性值（即 **extract geojson properties** 步驟）。

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **專業提示：** 當傳入 `Drivers.GeoJson` 時，`VectorLayer.Open` 會自動偵測 GeoJSON 格式。你也可以直接提供檔案路徑而非串流來開啟檔案。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **Invalid JSON format** | 確認 GeoJSON 字串格式正確；可使用 JSON 驗證工具。 |
| **Encoding problems** | 確保串流使用 UTF-8（`Encoding.UTF8.GetBytes`）。 |
| **Missing properties** | 檢查屬性名稱拼寫是否正確（範例中的 `"name"`）。 |
| **License exception** | 測試時使用試用授權；正式環境請套用永久授權。 |

## 常見問答
### Aspose.GIS 是否相容其他 GIS 格式？
是的，Aspose.GIS 支援 GeoJSON、Shapefile、KML、GML 等多種格式。

### 我可以在購買前試用 Aspose.GIS 嗎？
可以，你可從 [此處](https://releases.aspose.com/) 下載 Aspose.GIS 的免費試用版。

### 我在哪裡可以找到 Aspose.GIS 的文件？
你可於 [此處](https://reference.aspose.com/gis/net/) 取得 Aspose.GIS 的文件。

### 我如何取得 Aspose.GIS 的支援？
你可在 Aspose 論壇的 [此處](https://forum.aspose.com/c/gis/33) 獲得 Aspose.GIS 的支援。

### 使用 Aspose.GIS 是否需要臨時授權？
你可從 [此處](https://purchase.aspose.com/temporary-license/) 取得 Aspose.GIS 的臨時授權。

## 結論
本指南說明了如何使用 Aspose.GIS for .NET 從記憶體串流 **how to read geojson**，示範了一個 **C# read geojson** 工作流程，並展示如何從已開啟的圖層 **extract geojson properties**。透過這些步驟，你可以在任何 .NET 應用程式中無縫整合地理空間資料處理。

---

**最後更新：** 2026-04-24  
**測試版本：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
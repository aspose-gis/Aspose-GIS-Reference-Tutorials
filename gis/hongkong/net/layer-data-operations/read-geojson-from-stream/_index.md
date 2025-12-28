---
date: 2025-12-28
description: 學習如何使用 Aspose.GIS for .NET 從串流讀取 GeoJSON。此 C# 讀取 GeoJSON 指南提供逐步範例，協助整合地理空間資料。
linktitle: Read GeoJSON from Stream
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
如果你想了解在 .NET 應用程式中 **如何讀取 geojson**，你來對地方了。在本教學中，我們將逐步說明一個完整的 **c# geojson 範例**，展示如何轉換 GeoJSON 字串、從記憶體串流開啟 GeoJSON 圖層，以及使用 Aspose.GIS 抽取 GeoJSON 屬性。完成後，你將擁有一個可重用的模式，能夠套用到任何需要處理地理空間資料的專案中。

## 快速解答
- **我應該使用哪個函式庫？** Aspose.GIS for .NET  
- **我可以直接從串流讀取 GeoJSON 嗎？** 是 – 使用 `VectorLayer.Open` 搭配 `AbstractPath.FromStream`。  
- **開發時需要授權嗎？** 測試時使用免費試用版即可；正式環境需購買授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **抽取屬性是否簡單？** 是 – 在要素上呼叫 `GetValue<T>(columnName)`。

## 什麼是「how to read geojson」？
讀取 GeoJSON 意味著解析這種以 JSON 為基礎、描述地理要素（點、線、多邊形）的格式，並將這些要素以物件形式提供，讓你可以在應用程式中查詢、編輯或呈現它們。

## 為什麼使用 Aspose.GIS **開啟 geojson 圖層**？
Aspose.GIS 抽象化了低層次的解析細節，提供一致的 API 以支援多種 GIS 格式。它讓你能夠 **開啟 geojson 圖層** 直接從串流讀取，高效處理大型檔案，且無需自行編寫 JSON 解析器即可存取要素屬性。

## 前置條件
1. **具備 C# 基礎知識** – 你應該熟悉 .NET 語法與 Visual Studio 開發環境。  
2. **已安裝 Aspose.GIS** – 從 [here](https://releases.aspose.com/gis/net/) 下載函式庫。  
3. **開發環境** – Visual Studio、Visual Studio Code 或 JetBrains Rider 都可使用。  

## 匯入命名空間
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## 步驟 1：**轉換 GeoJSON 字串** – 一個 **c# geojson 範例**
首先，我們建立一個代表簡易 `FeatureCollection` 的 JSON 字串。這就是工作流程中的 **convert geojson string** 部分。

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## 步驟 2：**從串流開啟 GeoJSON 圖層** 並 **抽取 geojson 屬性**
現在，我們將字串寫入 `MemoryStream`，將其作為 GIS 圖層開啟，並示範如何讀取屬性值（即 **extract geojson properties** 步驟）。

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **小技巧：** 當你傳入 `Drivers.GeoJson` 時，`VectorLayer.Open` 會自動偵測 GeoJSON 格式。你也可以直接提供檔案路徑來開啟檔案，而非使用串流。

## 常見問題與解決方案
| 問題 | 解決方案 |
|------|----------|
| **JSON 格式無效** | 驗證 GeoJSON 字串是否符合結構；使用 JSON 驗證工具。 |
| **編碼問題** | 確認串流使用 UTF‑8（`Encoding.UTF8.GetBytes`）。 |
| **缺少屬性** | 檢查屬性名稱拼寫是否正確（範例中的 `"name"`）。 |
| **授權例外** | 測試時使用試用授權；正式環境則套用永久授權。 |

## 常見問答
### Aspose.GIS 是否相容其他 GIS 格式？
是的，Aspose.GIS 支援 GeoJSON、Shapefile、KML、GML 等多種格式。

### 我可以在購買前試用 Aspose.GIS 嗎？
可以，你可以從 [here](https://releases.aspose.com/) 下載 Aspose.GIS 的免費試用版。

### 我在哪裡可以找到 Aspose.GIS 的文件？
你可以在 [here](https://reference.aspose.com/gis/net/) 找到 Aspose.GIS 的文件。

### 我該如何取得 Aspose.GIS 的支援？
你可以在 Aspose 論壇的 [here](https://forum.aspose.com/c/gis/33) 獲得支援。

### 使用 Aspose.GIS 是否需要臨時授權？
你可以從 [here](https://purchase.aspose.com/temporary-license/) 取得 Aspose.GIS 的臨時授權。

## 結論
在本指南中，我們說明了如何使用 Aspose.GIS for .NET 從記憶體串流 **讀取 geojson**，展示了 **c# 讀取 geojson** 的工作流程，並示範了如何從已開啟的圖層 **抽取 geojson 屬性**。透過這些步驟，你可以無縫地將地理空間資料處理整合到任何 .NET 應用程式中。

---

**最後更新：** 2025-12-28  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
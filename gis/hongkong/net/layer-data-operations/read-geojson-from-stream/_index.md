---
date: 2026-10-05
description: 了解如何使用 Aspose.GIS for .NET 從串流讀取 geojson。本分步指南將示範如何載入 geojson 串流、解析它，並在
  C# 中提取屬性。
keywords:
- how to read geojson
- load geojson stream
- parse geojson c#
- open geojson layer
- extract geojson properties
lastmod: 2026-10-05
linktitle: 從串流讀取 GeoJSON
og_description: 了解如何使用 Aspose.GIS for .NET 從串流讀取 geojson，包括解析、開啟 geojson 圖層，以及在 C#
  中提取屬性。
og_image_alt: Tutorial guide showing how to read geojson from a stream with Aspose.GIS
  in C#
og_title: 使用 Aspose.GIS for .NET 從串流讀取 geojson 的方法
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to read geojson from a stream using Aspose.GIS for .NET.
    This step‑by‑step guide shows you how to load geojson stream, parse it, and extract
    properties in C#.
  headline: How to read geojson from a stream with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to read geojson from a stream using Aspose.GIS for .NET.
    This step‑by‑step guide shows you how to load geojson stream, parse it, and extract
    properties in C#.
  name: How to read geojson from a stream with Aspose.GIS for .NET
  steps:
  - name: '**Basic knowledge of C#** – you should be comfortable with .NET syntax
      and the Visual Studio IDE.'
    text: '**Basic knowledge of C#** – you should be comfortable with .NET syntax
      and the Visual Studio IDE.'
  - name: '**Aspose.GIS installed** – download the library from [Aspose.GIS .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS installed** – download the library from [Aspose.GIS .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A development environment** – Visual Studio, Visual Studio Code, or JetBrains
      Rider will work fine.'
    text: '**A development environment** – Visual Studio, Visual Studio Code, or JetBrains
      Rider will work fine.'
  type: HowTo
- questions:
  - answer: Aspose.GIS for .NET – it handles 30+ GIS formats out of the box.
    question: What library should I use?
  - answer: Yes – call `VectorLayer.Open` with `AbstractPath.FromStream`.
    question: Can I read GeoJSON directly from a stream?
  - answer: A free trial works for testing; a full license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Which .NET versions are supported?
  - answer: Absolutely – use `GetValue<T>(columnName)` on a feature.
    question: Is extracting properties simple?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET GIS
- C# geospatial
title: 使用 Aspose.GIS for .NET 從串流讀取 geojson 的方法
url: /zh-hant/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS for .NET 從串流讀取 GeoJSON

## 簡介
如果你想了解在 .NET 應用程式中 **如何讀取 geojson**，你來對地方了。在本教學中，我們將逐步說明一個完整的 **C# GeoJSON 範例**，展示如何將 GeoJSON 字串 **載入 geojson 串流** 到記憶體串流，開啟 GeoJSON 圖層，並使用 Aspose.GIS 取得 GeoJSON 屬性。完成後，你將擁有一個可重複使用的模式，能直接套用於任何需要處理地理空間資料的專案。

## 快速解答
- **應該使用哪個函式庫？** Aspose.GIS for .NET – 它內建支援超過 30 種 GIS 格式。  
- **我可以直接從串流讀取 GeoJSON 嗎？** 是的 – 呼叫 `VectorLayer.Open` 並傳入 `AbstractPath.FromStream`。  
- **開發時需要授權嗎？** 免費試用版可用於測試；正式環境需購買正式授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **提取屬性是否簡單？** 絕對簡單 – 在特徵上使用 `GetValue<T>(columnName)`。

**VectorLayer.Open** 會從檔案或串流等資料來源開啟 GIS 圖層。**AbstractPath.FromStream** 會建立一個抽象路徑物件，以代表提供給 GIS 驅動程式的串流。**GetValue<T>(columnName)** 會讀取特徵中指定屬性的值，並以 T 型別回傳。

## 什麼是「如何讀取 geojson」？
讀取 geojson 是將 GeoJSON 格式的字串或串流轉換為記憶體中的地理要素物件的過程。此格式使用 JSON 編碼點、線與多邊形，便於在 Web 服務、資料庫與客戶端應用程式之間交換空間資料。解析後，你可以使用任何支援 GIS 的 .NET 函式庫（例如 Aspose.GIS）來查詢、編輯或呈現這些要素。

## 為什麼使用 Aspose.GIS 開啟 geojson 圖層？
Aspose.GIS 允許直接從串流開啟 GeoJSON 圖層，省去暫存檔案的需求並降低 I/O 開銷。此函式庫支援超過 30 種 GIS 格式，且可處理高達 2 GB 的檔案而不必將整個文件載入記憶體，非常適合大型資料集。它亦會自動正規化座標參考系統，讓你專注於業務邏輯，而不必處理低階的解析工作。

## 何時會載入 geojson 串流？
當你從 API 接收空間資料、需要處理使用者上傳的檔案而不將其寫入磁碟，或從資料庫查詢即時產生 GeoJSON 時，會使用載入 GeoJSON 串流的方式。串流可避免不必要的磁碟寫入，在高吞吐量情境下提升效能，且保持應用程式無狀態，這在雲端原生微服務中尤為重要。

## 前置條件
在開始之前，請確保你已具備以下條件：

1. **基本的 C# 知識** – 你應該熟悉 .NET 語法與 Visual Studio IDE。  
2. **已安裝 Aspose.GIS** – 從 [Aspose.GIS .NET 下載頁面](https://releases.aspose.com/gis/net/) 下載函式庫。  
3. **開發環境** – Visual Studio、Visual Studio Code 或 JetBrains Rider 都可使用。  

## 匯入命名空間
`Aspose.GIS` 命名空間提供核心 GIS 類別。`System.IO` 提供 `MemoryStream`，`System.Text` 則提供 UTF‑8 編碼工具。匯入這些命名空間可使後續程式碼更簡潔易讀。

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## 步驟 1：轉換 geojson 字串 – C# GeoJSON 範例
首先，我們建立一個代表簡單 `FeatureCollection` 的 JSON 字串。這是工作流程中 **convert geojson string** 的部分。

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## 步驟 2：載入 geojson 串流並提取 geojson 屬性
現在，我們將字串寫入 `MemoryStream`，將其作為 GIS 圖層開啟，並示範如何讀取屬性值（即 **extract geojson properties** 步驟）。

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
| **JSON 格式無效** | 確認 GeoJSON 字串格式正確；使用 JSON 驗證工具。 |
| **編碼問題** | 確保串流使用 UTF‑8（`Encoding.UTF8.GetBytes`）。 |
| **缺少屬性** | 檢查屬性名稱拼寫正確（範例中的 `"name"`）。 |
| **授權例外** | 測試時使用試用授權；正式環境請套用永久授權。 |

## 常見問答
### Aspose.GIS 是否相容其他 GIS 格式？
是的，Aspose.GIS 支援 GeoJSON、Shapefile、KML、GML 以及超過 20 種其他格式，讓你在不同資料來源間切換而無需修改程式碼。

### 購買前可以試用 Aspose.GIS 嗎？
你可以從 [Aspose.GIS 免費試用下載頁面](https://releases.aspose.com/) 下載 Aspose.GIS 的免費試用版。

### 哪裡可以找到 Aspose.GIS 的文件？
你可以在 [Aspose.GIS .NET API 參考文件](https://reference.aspose.com/gis/net/) 中找到 Aspose.GIS 的文件。

### 如何取得 Aspose.GIS 的支援？
你可以在 Aspose GIS 論壇 [Aspose GIS 論壇](https://forum.aspose.com/c/gis/33) 獲得支援。

### 使用 Aspose.GIS 是否需要臨時授權？
你可以從 [臨時授權申請頁面](https://purchase.aspose.com/temporary-license/) 取得 Aspose.GIS 的臨時授權。

## 結論
在本指南中，我們說明了如何使用 Aspose.GIS for .NET 從記憶體串流 **讀取 geojson**，展示了 **C# 讀取 geojson** 的工作流程，並示範了如何從已開啟的圖層 **提取 geojson 屬性**。透過這些步驟，你可以無縫地將地理空間資料處理整合到任何 .NET 應用程式中。

---

**最後更新：** 2026-10-05  
**測試版本：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [如何使用 Aspose.GIS for .NET 將 GeoJSON 寫入串流](/gis/net/layer-data-operations/write-geojson-to-stream/)
- [如何使用 Aspose.GIS for .NET 將 GeoJSON 轉換為 GDB](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [使用 Aspose.GIS for .NET 將 Shapefile 轉換為 GeoJSON](/gis/net/layer-management/extract-features-to-geojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
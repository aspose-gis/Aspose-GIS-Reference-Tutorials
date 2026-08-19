---
date: 2026-06-15
description: 學習如何在 C# 中使用 Aspose.GIS for .NET 讀取 Shapefile 屬性值，檢索每個要素的屬性，並高效地匯出屬性。
keywords:
- read shapefile attribute values
- Aspose.GIS attribute extraction
- C# GIS tutorial
linktitle: 取得所有要素屬性值
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to read shapefile attribute values in C# using Aspose.GIS
    for .NET, retrieve every feature attribute, and dump attributes efficiently.
  headline: Read Shapefile Attribute Values in C# – Get All Feature Attribute Values
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS fully supports .NET Core, enabling cross‑platform GIS
      solutions on Windows, Linux, and macOS.
    question: Is Aspose.GIS compatible with .NET Core?
  - answer: Absolutely. The library handles Shapefile, GeoJSON, KML, GML, CSV, and
      over 30 other formats without additional plugins.
    question: Can I work with different GIS file formats using Aspose.GIS?
  - answer: You can acquire a temporary license for evaluation [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for testing?
  - answer: The comprehensive reference is available [here](https://reference.aspose.com/gis/net/).
    question: Where is the official documentation for Aspose.GIS?
  - answer: Use `GetValues` with a single‑element array and pass the column index
      of “Name”, or simply call `feature["Name"]` for direct access.
    question: How do I retrieve only the “Name” attribute from each feature?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 在 C# 中讀取 Shapefile 屬性值 – 取得所有要素屬性值
url: /zh-hant/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 取得所有要素屬性值

## 介紹
在本教學中，您將學會 **如何在 C# 中使用 Aspose.GIS for .NET 讀取 Shapefile 屬性值**。無論您是要建立即時地圖應用程式、執行大量空間分析，或只是需要匯出屬性表，從 Shapefile 中擷取每個欄位都是基本技能。我們將完整示範工作流程，從設定資料目錄到匯出屬性集合，並提供最佳實踐技巧，讓您的程式碼保持乾淨且效能優異。

## 快速回答
- **此程式碼的功能是什麼？** 它會開啟 Shapefile，遍歷每個要素，並取得每個屬性值或選取的子集。  
- **需要哪個函式庫？** Aspose.GIS for .NET（支援 .NET Framework、.NET Core、.NET 5/6）。  
- **需要授權嗎？** 測試時臨時授權即可；正式上線必須使用正式授權。  
- **可以讀取其他格式嗎？** 可以——相同的 API 可讀取 GeoJSON、KML、GML、CSV 以及超過 30 種其他 GIS 格式。  
- **如何匯出屬性？** 呼叫 `feature.GetValuesDump()` 取得可序列化或直接檢查的 object 陣列。

## 什麼是「在 C# 中讀取 Shapefile」？
在 C# 中讀取 Shapefile 意指使用 GIS 函式庫開啟 `.shp` 檔案，遍歷其向量要素，並存取伴隨的 `.dbf` 檔案中儲存的屬性資料。Aspose.GIS 抽象化了底層檔案處理，讓您只需幾行程式碼即可擷取屬性值。

## 為何使用 Aspose.GIS 讀取屬性？
Aspose.GIS 提供高效能、跨平台的 API，簡化從 Shapefile 提取屬性的流程。它支援 **30+ GIS 格式**，在標準 4 核心伺服器上每秒可處理高達 **500 000 個要素**，並提供直觀的 `GetValues` 與 `GetValuesDump` 方法，免除手動 DBF 解析。當您需要可靠、測試時免授權、且在 Windows、Linux、macOS 上皆無需額外外掛的程式碼時，請使用它。

## 前置條件
- **Aspose.GIS for .NET** – 從 [Aspose.GIS for .NET 下載頁面](https://releases.aspose.com/gis/net/) 下載。  
- **開發環境** – Visual Studio 2022、Rider，或任何支援 .NET 6+ 的 IDE。  
- **範例 Shapefile** – 將 `InputShapeFile.shp` 等檔案放置於電腦上已知的資料夾中。  

## 匯入命名空間
`Aspose.Gis` 命名空間包含核心 GIS 類型，如 `VectorLayer` 與 `Feature`。  
`VectorLayer` 代表向量資料集（例如 Shapefile），而 `Feature` 代表單一空間記錄。  
```csharp
using System;
using Aspose.Gis;
```

## 步驟 1：設定文件目錄
定義保存 Shapefile 的資料夾，讓 API 能找到 `.shp`、`.shx` 與 `.dbf` 檔案。  
```csharp
string dataDir = "Your Document Directory";
```
將「Your Document Directory」替換為實際的 Shapefile 所在路徑。

## 步驟 2：開啟 VectorLayer
`VectorLayer` 代表向量資料集（Shapefile、GeoJSON 等）。開啟它會載入結構資訊而不讀取全部幾何資料，降低記憶體使用。  
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
此步驟指定檔案路徑與格式（Shapefile）。

## 步驟 3：取得所有要素屬性值
`GetValues` 會將原始屬性值填入預先分配的陣列。當您需要確定且固定大小的結果集時，此方式最為理想。  
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
此程式碼示範如何將 **每個** 要素的屬性讀入固定大小的陣列。

## 步驟 4：取得多個要素屬性值
若僅需部份欄位，可傳入較小的陣列或使用欄位索引限制傳輸資料，從而減少記憶體開銷並加速處理。  
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
此範例示範讀取特定屬性值（例如「Name」與「Population」）。

## 步驟 5：以物件陣列匯出屬性值
`GetValuesDump` 會回傳 `object[]`，其中包含要素的全部屬性值，且符合要素的結構。即使事先不清楚欄位順序或型別，也能遍歷欄位。  
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
最後一步展示一種彈性、與結構無關的方式，方便除錯或序列化時匯出屬性。

## 常見問題與解決方案
- **陣列大小不匹配** – 確保傳入 `GetValues` 的陣列大小與預期的屬性數量相符，否則會得到 `null` 項目。  
- **找不到檔案** – 檢查 `dataDir` 是否指向正確的資料夾，且 Shapefile 名稱拼寫完整，包括 `.shp` 副檔名。  
- **授權例外** – 若出現授權錯誤，請在呼叫任何 API 方法前套用臨時或正式授權。

## 常見問答
**Q: Aspose.GIS 是否相容 .NET Core？**  
A: 是的，Aspose.GIS 完全支援 .NET Core，能在 Windows、Linux、macOS 上提供跨平台 GIS 解決方案。

**Q: 可以使用 Aspose.GIS 處理不同的 GIS 檔案格式嗎？**  
A: 當然可以。此函式庫可處理 Shapefile、GeoJSON、KML、GML、CSV 以及超過 30 種其他格式，無需額外外掛。

**Q: 如何取得測試用的臨時授權？**  
A: 您可於 [此處](https://purchase.aspose.com/temporary-license/) 取得評估用的臨時授權。

**Q: Aspose.GIS 的官方文件在哪裡？**  
A: 完整的參考文件可在 [此處](https://reference.aspose.com/gis/net/) 獲得。

**Q: 如何只取得每個要素的「Name」屬性？**  
A: 使用單元素陣列呼叫 `GetValues` 並傳入「Name」的欄位索引，或直接使用 `feature["Name"]` 取得。

**Q: `GetValues` 與 `GetValuesDump` 有何差異？**  
A: `GetValues` 會將原始值填入預先分配的陣列；`GetValuesDump` 則回傳 `object[]`，可在不事先了解結構的情況下遍歷。

**Q: 若遇到問題該向哪裡求助？**  
A: 請前往 Aspose GIS [支援論壇](https://forum.aspose.com/c/gis/33) 取得社群協助與官方支援。

---

**最後更新：** 2026-06-15  
**測試環境：** Aspose.GIS for .NET (latest release)  
**作者：** Aspose

## 相關教學

- [取得圖層屬性 – 使用 Aspose.GIS for .NET 取得圖層屬性資訊](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [如何取得屬性值（預設）使用 Aspose.GIS for .NET](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [讀取 Shapefile C# – 使用 Aspose.GIS 依屬性篩選要素](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
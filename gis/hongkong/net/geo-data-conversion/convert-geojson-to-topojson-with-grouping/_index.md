---
date: 2025-12-06
description: 學習如何使用 Aspose.GIS for .NET 將 GeoJSON 轉換為 TopoJSON（含分組），設定物件名稱屬性，並對 GeoJSON
  要素進行分組。
language: zh-hant
linktitle: How to Convert GeoJSON to TopoJSON with Grouping using Aspose.GIS
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS 將 GeoJSON 轉換為 TopoJSON 並進行分組
url: /net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS 將 GeoJSON 轉換為 TopoJSON 並進行分組

## 介紹

在本分步教學中，您將學習 **如何將 GeoJSON** 檔案轉換為 TopoJSON，同時根據選定的屬性對要素進行分組。使用 Aspose.GIS .NET API 可讓轉換快速、可靠，且可完全在 C# 程式碼中掌控。無論您是建立 ASP.NET GeoJSON 轉換服務，或是桌面 GIS 工具，本指南都會告訴您所需的每一步。

## 快速回答
- **哪個函式庫負責轉換？** Aspose.GIS for .NET  
- **實作需要多久？** 基本設定通常 5‑10 分鐘即可完成  
- **正式環境需要授權嗎？** 是，需要商業授權（提供免費試用）  
- **可以依任意屬性分組要素嗎？** 可以 – 將 `ObjectNameAttribute` 設為您想分組的欄位  
- **支援 .NET Core 嗎？** 當然 – API 可在 .NET Core、.NET 5/6 以及傳統 .NET Framework 上運作  

## 什麼是 GeoJSON 與 TopoJSON？

GeoJSON 是一種廣泛使用的 JSON 格式，用於編碼點、線、面等地理要素。TopoJSON 在 GeoJSON 基礎上加入拓撲資訊（共用線段），可減少檔案大小並提升複雜地圖的渲染效能。當您需要為 Web 可視化提供緊湊的地圖資料時，兩者之間的轉換是一個常見步驟。

## 為什麼要分組 GeoJSON 要素？

分組（`group geojson features`）可讓您在產生的 TopoJSON 中，將相關的幾何圖形組織在同一個具名物件下。此功能在以下情況特別有用：
- 您想為不同的行政區域建立獨立圖層。  
- 前端地圖函式庫需要具名物件以便樣式或互動。  
- 想透過共享相鄰要素的邊界來減少重複資料。

## 前置條件

在開始之前，請確保您已具備以下條件：

1. **Aspose.GIS for .NET** – 從官方網站[此處](https://releases.aspose.com/gis/net/)下載並安裝。  
2. **開發環境** – Visual Studio、Visual Studio Code，或任何支援 C# 的 IDE。  
3. **範例 GeoJSON 檔案** – 包含您欲轉換之要素的檔案。  

## 匯入命名空間

首先，在專案中加入必要的命名空間：

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```

## 步驟指南

### 步驟 1：定義檔案路徑

指定來源 GeoJSON 的位置以及 TopoJSON 要寫入的路徑：

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

> **小技巧：** 若目標為 .NET Core，請使用 `Path.Combine` 以建立跨平台的路徑。

### 步驟 2：設定轉換選項（設定物件名稱屬性）

建立 `ConversionOptions` 實例，告訴 Aspose.GIS 如何分組要素：

```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // Specify the attribute in GeoJSON layer by which we are going to group into objects
        ObjectNameAttribute = "group",
        // Specify the default object name for features with unknown attribute values
        DefaultObjectName = "unnamed",
    }
};
```

將 `"group"` 替換為您在 GeoJSON 中實際用於 **geojson feature grouping** 的屬性名稱。`DefaultObjectName` 可確保即使屬性缺失，所有要素仍會被放入 TopoJSON 物件中。

### 步驟 3：執行轉換（將 GeoJSON 轉為 TopoJSON）

只需一次 API 呼叫即可完成轉換：

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

執行完畢後，`convertedSampleWithGrouping_out.topojson` 會包含 TopoJSON 表示，且要素已依您指定的屬性完成分組。

## 常見問題與除錯

| 症狀 | 可能原因 | 解決方式 |
|------|----------|----------|
| **所有要素都出現在 “unnamed”** | `ObjectNameAttribute` 與 GeoJSON 中的屬性不匹配 | 核對屬性名稱（區分大小寫），並更新選項 |
| **輸出檔案為空** | 檔案路徑不正確或缺少讀寫權限 | 使用絕對路徑或確保程式具備檔案系統存取權限 |
| **轉換拋出 `NotSupportedException`** | 嘗試轉換含有不支援的幾何類型（如 GeometryCollection） | 簡化來源資料或升級至最新的 Aspose.GIS 版本 |

## 常見問答

**Q: 可以依多個屬性分組要素嗎？**  
A: 可以，您可以將多個欄位串接成單一虛擬屬性，或針對不同的 `ObjectNameAttribute` 值分別執行多次轉換。

**Q: Aspose.GIS 與 ASP.NET Core 相容嗎？**  
A: 完全相容 – 此函式庫支援 ASP.NET Core、.NET 5、.NET 6 以及傳統 .NET Framework。

**Q: 除了 GeoJSON，還能轉換其他地理格式嗎？**  
A: 可以，Aspose.GIS 支援 Shapefile、KML、GML、CSV 等多種格式的匯入與匯出。

**Q: Aspose.GIS 有提供免費試用嗎？**  
A: 有，您可從[此處](https://releases.aspose.com/)取得免費試用版。

**Q: 哪裡可以取得 Aspose.GIS 的支援？**  
A: 您可於 Aspose.GIS 社群論壇[此處](https://forum.aspose.com/c/gis/33)取得協助。

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**最後更新：** 2025-12-06  
**測試環境：** Aspose.GIS for .NET（最新發行版）  
**作者：** Aspose  

---
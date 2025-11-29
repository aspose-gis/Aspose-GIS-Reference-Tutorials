---
date: 2025-11-29
description: 學習如何使用 Aspose.GIS for .NET 將 GeoJSON 轉換為具有特定物件名稱的 TopoJSON。本分步指南精確展示如何高效地將
  GeoJSON 轉換為 TopoJSON。
language: zh-hant
linktitle: Convert GeoJSON to TopoJSON with Specific Object Name
second_title: Aspose.GIS .NET API
title: 將 GeoJSON 轉換為 TopoJSON 並指定物件名稱
url: /net/geo-data-conversion/convert-geojson-to-topojson-with-specific-object-name/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將 GeoJSON 轉換為 TopoJSON 並指定物件名稱

## 簡介
如果您需要在**將 GeoJSON 轉換為 TopoJSON**的同時控制輸出物件的名稱，Aspose.GIS for .NET 讓這件事變得輕而易舉。在本教學中，您將看到如何將 GeoJSON 轉換為 TopoJSON、為何可能需要自訂物件名稱，以及在現有 .NET 專案中如何插入相關程式碼。

## 快速解答
- **轉換的作用是什麼？** 它會將 GeoJSON 特徵重新寫入 TopoJSON 拓撲結構，並可選擇重新命名根物件。  
- **實作需要多長時間？** 安裝 Aspose.GIS 後大約 5‑10 分鐘即可完成。  
- **需要授權嗎？** 免費試用可用於測試；正式上線需購買商業授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **可以指定物件名稱嗎？** 可以 – 在 `TopoJsonOptions` 中使用 `DefaultObjectName`。

## 什麼是「將 GeoJSON 轉換為 TopoJSON」？
`convert geojson to topojson` 是將 GeoJSON 檔案（地理特徵的純 JSON 表示）轉換為 TopoJSON 的過程，TopoJSON 是一種更緊湊的格式，會將共用的線段儲存為弧線。此方式可減少檔案大小，提升網頁地圖的渲染效能。

## 為何使用 Aspose.GIS for .NET 來將 GeoJSON 轉換為 TopoJSON？
- **完整 .NET 整合** – 無需外部 CLI 工具。  
- **細緻的控制** – 可設定輸出物件名稱、座標精度等。  
- **跨平台** – 可於 Windows、Linux、macOS 搭配 .NET Core/.NET 5+ 執行。  
- **健全的錯誤處理** – 內建輸入 GeoJSON 的驗證與詳細例外資訊。

## 先決條件
在開始轉換之前，請先確保您具備以下項目：

1. **Aspose.GIS for .NET** – 從[官方下載頁面](https://releases.aspose.com/gis/net/)下載最新版本。  
2. **.NET 開發環境** – Visual Studio、Rider，或安裝 C# 擴充功能的 VS Code。  
3. **來源 GeoJSON 檔案** – 任意您想轉換為 TopoJSON 的有效 GeoJSON 檔案。

## 匯入命名空間
首先，將所需的命名空間引入範圍：

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 逐步指南

### 步驟 1：定義檔案路徑
告訴 API 您的來源 GeoJSON 位於何處，以及轉換後的 TopoJSON 要儲存到哪裡。

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithObjectName_out.topojson";
```

> **小技巧：** 使用 `Path.Combine` 以建立跨平台的路徑。

### 步驟 2：設定轉換選項（如何在將 GeoJSON 轉換為 TopoJSON 時使用自訂物件名稱）
建立 `ConversionOptions` 實例，並透過 `TopoJsonOptions.DefaultObjectName` 指定欲使用的物件名稱。

```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // specify the name of the object where features should be written
        DefaultObjectName = "name_of_the_object",
    }
};
```

這會指示 Aspose.GIS 將所有特徵寫入結果 TopoJSON 檔案中名為 `"name_of_the_object"` 的節點下。

### 步驟 3：執行轉換
最後，呼叫 `VectorLayer` 的靜態 `Convert` 方法。該方法會讀取 GeoJSON、套用選項，並寫入 TopoJSON。

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

若轉換成功，您會在 `outputFilePath` 看到一個已使用自訂物件名稱的緊湊 TopoJSON 檔案。

## 常見問題與解決方案

| 問題 | 發生原因 | 解決方法 |
|-------|----------------|-----|
| **找不到檔案** | 路徑不正確或缺少檔案副檔名。 | 使用 `File.Exists` 檢查 `sampleGeoJsonPath`。 |
| **GeoJSON 無效** | 輸入檔案不符合 GeoJSON 規範。 | 在轉換前使用 `GeoJsonReader` 進行驗證。 |
| **物件名稱被忽略** | 使用較舊的 Aspose.GIS 版本，未支援 `DefaultObjectName`。 | 升級至最新的 Aspose.GIS 版本。 |
| **權限被拒絕** | 輸出目錄為唯讀。 | 以適當的檔案系統權限執行應用程式。 |

## 結論
現在您已了解如何使用 Aspose.GIS for .NET **將 GeoJSON 轉換為 TopoJSON** 並指定特定的物件名稱。此方法讓您完全掌控輸出拓撲、減少檔案大小，且能無縫整合至任何基於 .NET 的 GIS 工作流程。

## 常見問答

### 我可以在商業專案中使用 Aspose.GIS for .NET 嗎？
可以，您可在商業與個人專案中皆使用 Aspose.GIS for .NET。

### 是否提供 Aspose.GIS for .NET 的免費試用？
可以，請從[此處](https://releases.aspose.com/)取得免費試用。

### 哪裡可以取得 Aspose.GIS for .NET 的支援？
您可於 [Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33)取得支援。

### 如何購買 Aspose.GIS for .NET 的授權？
請從[此處](https://purchase.aspose.com/buy)購買授權。

### 評估時是否需要臨時授權？
需要，您可從[此處](https://purchase.aspose.com/temporary-license/)取得臨時授權。

## 常見問題

**Q: TopoJSON 相較於 GeoJSON 最大的優勢是什麼？**  
A: TopoJSON 只儲存一次共用的線段，能大幅減少複雜地圖的檔案大小。

**Q: 我可以轉換大型（數百 MB）GeoJSON 檔案嗎？**  
A: 可以。Aspose.GIS 以串流方式處理資料，記憶體使用量保持低；只需確保有足夠的磁碟空間儲存輸出檔案。

**Q: 在轉換過程中可以設定座標精度嗎？**  
A: 當然可以。使用 `TopoJsonOptions.Precision` 以四捨五入至指定的小數位數。

**Q: 轉換會保留所有 GeoJSON 的屬性嗎？**  
A: 所有特徵屬性會原樣複製到 TopoJSON 輸出中。

**Q: 如何在 JavaScript 中讀取產生的 TopoJSON？**  
A: 可使用如 `topojson-client` 等函式庫解析檔案，並可引用您設定的自訂物件名稱（`name_of_the_object`）。

---

**最後更新：** 2025-11-29  
**測試環境：** Aspose.GIS for .NET 24.11（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
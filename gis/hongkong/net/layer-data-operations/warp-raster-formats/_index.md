---
date: 2026-01-02
description: 學習如何使用 Aspose.GIS for .NET 進行光柵扭曲。此逐步指南向您展示如何扭曲光柵格式、提取元數據以及處理光柵波段。
linktitle: How to Warp Raster Formats
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 變形光柵格式
url: /zh-hant/net/layer-data-operations/warp-raster-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何扭曲光柵格式

## 介紹
在本教學中，您將了解 **如何扭曲光柵** 資料，使用 Aspose.GIS for .NET。無論您需要重新投影 GeoTIFF、變更解析度，或僅僅探索光柵的內部細節，以下步驟將帶您完成整個流程——從載入檔案到檢查每個波段的統計資訊。讓我們開始吧！

## 快速回答
- **「扭曲光柵」是什麼意思？** 它是將光柵資料重新投影並重新取樣至新的空間參考系統或解析度的過程。  
- **哪個函式庫負責扭曲？** Aspose.GIS for .NET 在光柵圖層上提供 `Warp` 方法。  
- **我需要授權嗎？** 免費試用可用於開發；商業授權則需於正式環境使用。  
- **支援的輸入格式？** 範例使用 GeoTIFF，但 Aspose.GIS 支援多種光柵格式。  
- **一般執行時間？** 扭曲一個 40 × 40 的小光柵在現代電腦上不到一秒。

## 什麼是光柵扭曲？
光柵扭曲（或重新投影）是將光柵格點從一個座標系統轉換至另一個座標系統，同時可選擇調整像素大小。當您合併使用不同空間參考的圖層，或需要符合特定地圖比例的光柵時，這是必須的。

## 為什麼使用 Aspose.GIS 進行光柵扭曲？
- **純 .NET API** – 無原生相依，支援 Windows、Linux 與 macOS。  
- **功能完整** – 支援 GeoTIFF、JPEG2000、PNG 等多種格式。  
- **精確重新取樣** – 支援最近鄰、雙線性與立方體插值（預設為雙線性）。  
- **易於整合** – 可於 ASP.NET、主控台應用程式或任何 .NET 服務中使用。

## 前置條件
在進入程式碼之前，請確保您已具備以下條件：

- 已安裝 Aspose.GIS for .NET。從官方下載頁面 **[here](https://releases.aspose.com/gis/net/)** 取得最新套件。  
- 在您的機器上建立一個資料夾，用於存放範例 GeoTIFF (`raster_float32.tif`)。  
- 已安裝 .NET 6（或更新版本）SDK。

## 匯入命名空間
首先，將所需的 .NET 命名空間匯入程式碼範圍內：

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Raster;
using Aspose.Gis.SpatialReferencing;
```

## 步驟 1：初始化路徑
設定指向包含光柵檔案之目錄的路徑。

```csharp
string dataDir = "Your Document Directory";
```

## 步驟 2：開啟光柵圖層
開啟 GeoTIFF 光柵圖層。此步驟會為後續操作做好準備。

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(dataDir, "raster_float32.tif")))
```

## 步驟 3：扭曲光柵
套用扭曲操作。此範例請求在 WGS‑84 座標系統下產生 40 × 40 的光柵。

```csharp
using (var warped = layer.Warp(new WarpOptions(){Height = 40, Width = 40, TargetSpatialReferenceSystem = SpatialReferenceSystem.Wgs84}))
```

## 步驟 4：提取光柵資訊
從扭曲後的光柵中提取有用的中繼資料。

```csharp
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
var bandCount = warped.BandCount;
```

## 步驟 5：列印光柵細節
將提取的資訊輸出至主控台。

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
Console.WriteLine($"bandCount: {bandCount}");
```

## 步驟 6：探索光柵波段
遍歷每個波段，檢視其資料類型、統計資訊與 NoData 處理方式。

```csharp
for (int i = 0; i < warped.BandCount; i++)
{
    var dataType = warped.GetBand(i).DataType;
    var hasNoData = !warped.NoDataValues.IsNull();
    var statistics = warped.GetStatistics(i);
    Console.WriteLine();
    Console.WriteLine($"Band: {i}");
    Console.WriteLine($"dataType: {dataType}");
    Console.WriteLine($"statistics: {statistics}");
    Console.WriteLine($"hasNoData: {hasNoData}");
    if (hasNoData)
        Console.WriteLine($"noData: {warped.NoDataValues[i]}");
}
```

## 常見問題與解決方案
| 問題 | 發生原因 | 解決方式 |
|------|----------|----------|
| **輸出光柵為空** | 目標 SRS 未被識別 | 驗證 EPSG 代碼（`SpatialReferenceSystem.Wgs84` = 4326）且確保來源光柵具有有效的 SRS。 |
| **NoData 值顯示為零** | `NoDataValues` 未在來源設定 | 在原始光柵上明確設定 NoData，或在扭曲後使用 `warped.NoDataValues` 處理。 |
| **大型光柵效能下降** | 預設雙線性重新取樣耗用 CPU | 使用 `WarpOptions.Interpolation = InterpolationMode.NearestNeighbour` 以獲得較快（但較不平滑）的結果。 |

## 結論
您現在已了解如何使用 Aspose.GIS for .NET **扭曲光柵** 資料、提取其中繼資料，並檢查每個波段的統計資訊。此功能為進階空間分析、製圖以及異構地理資料的無縫整合開啟了大門。

## 常見問答
### Aspose.GIS 是否相容所有光柵格式？
是的，Aspose.GIS 支援廣泛的光柵格式，提供在處理各種空間資料集時的彈性。

### 我可以對未地理參考的影像執行光柵扭曲嗎？
Aspose.GIS 設計用於處理具地理參考的資料，以確保轉換的準確性。請確保您的光柵影像具有正確的空間參考資訊。

### 我該如何為 Aspose.GIS 社群做出貢獻？
加入 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 的討論，分享您的經驗、提問並與其他開發者合作。

### 是否提供 Aspose.GIS 的免費試用？
是的，您可於 **[here](https://releases.aspose.com/)** 下載免費試用版以探索其功能。

### 是否提供 Aspose.GIS 的臨時授權？
是的，若需要臨時授權，可於 **[here](https://purchase.aspose.com/temporary-license/)** 取得。

## 常見問題

**Q: 除了 GeoTIFF，我還能扭曲哪些光柵格式？**  
A: Aspose.GIS 支援 JPEG、PNG、BMP 等多種常見光柵格式。`Warp` 方法可用於任何該函式庫能開啟的格式。

**Q: 扭曲操作會修改原始檔案嗎？**  
A: 不會。`Warp` 方法會在記憶體中建立新的光柵 (`warped`)，原始檔案保持不變。

**Q: 如何變更輸出解析度？**  
A: 在 `WarpOptions` 中調整 `Height` 與 `Width` 屬性為目標像素尺寸。

**Q: 我可以將扭曲後的光柵儲存至磁碟嗎？**  
A: 可以。扭曲完成後，使用 `warped.Save("output.tif", Drivers.GeoTiff)` 將結果寫入檔案。

**Q: 是否支援自訂座標系統？**  
A: 當然。提供具有相應 EPSG 代碼或 WKT 定義的自訂 `SpatialReferenceSystem` 實例即可。

---

**最後更新：** 2026-01-02  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
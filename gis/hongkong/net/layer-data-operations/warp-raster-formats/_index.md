---
date: 2026-05-05
description: 學習如何使用 Aspose.GIS for .NET 取得柵格像元大小以及執行柵格格式的變形，提供空間資料視覺化的逐步指南。
keywords:
- get raster cell size
- how to warp raster
- Aspose GIS raster
linktitle: Warp 光柵格式
second_title: Aspose.GIS .NET API
title: 取得光柵格元大小 – 使用 Aspose.GIS 變形光柵格式
url: /zh-hant/net/layer-data-operations/warp-raster-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 取得光柵格點大小 – 變形光柵格式

## 簡介
歡迎來到令人振奮的 Aspose.GIS for .NET 地理空間程式設計世界！在本教學中，您將在光柵變形後**取得光柵格點大小**，並一步步學習**如何變形光柵**格式。無論您是資深開發者或剛起步，請系好安全帶，我們將深入探討 GeoTIFF 操作的細節，為您的空間資料帶來全新視角。

## 快速解答
- **主要目標是什麼？** 在執行變形操作後取得光柵格點大小。  
- **使用哪個函式庫？** Aspose.GIS for .NET。  
- **需要授權嗎？** 可使用免費試用版；正式環境需購買授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **範例執行需要多久？** 在一般電腦上少於一分鐘。  

## 先決條件
在踏上這段旅程之前，請確保已具備以下先決條件：
- Aspose.GIS for .NET：如果尚未安裝，請下載並安裝 Aspose.GIS 函式庫。您可於[此處](https://releases.aspose.com/gis/net/)取得最新版本。
- 文件目錄：建立一個目錄來存放您的文件。此目錄在光柵變形過程中的檔案管理至關重要。

準備就緒後，讓我們深入程式碼。

## 匯入命名空間
首先，確保我們手頭有正確的工具。匯入必要的命名空間，以啟動您的地理空間冒險：
```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Raster;
using Aspose.Gis.SpatialReferencing;
```

## 步驟 1：初始化路徑
首先設定文件目錄的路徑。所有的魔法都將在此發生：
```csharp
string dataDir = "Your Document Directory";
```

## 步驟 2：開啟光柵圖層
開啟 GeoTiff 光柵圖層並為轉換做準備。此步驟為後續的變形操作奠定基礎：
```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(dataDir, "raster_float32.tif")))
```

## 步驟 3：變形光柵
現在，執行變形操作。指定目標尺寸與空間參考系統，為您的光柵資料注入新生命：
```csharp
using (var warped = layer.Warp(new WarpOptions(){Height = 40, Width = 40, TargetSpatialReferenceSystem = SpatialReferenceSystem.Wgs84}))
```

## 步驟 4：擷取光柵資訊
是時候揭開變形後光柵的祕密。擷取關鍵資訊，如格點大小、空間參考系統、邊界與波段數量：
```csharp
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
var bandCount = warped.BandCount;
```

## 步驟 5：列印光柵詳細資訊
讓我們列印出已發掘的詳細資訊，深入了解變形後的光柵：
```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
Console.WriteLine($"bandCount: {bandCount}");
```

## 步驟 6：探索光柵波段
深入探討光柵的各個波段，解析其資料類型、統計資訊以及 NoData 值的存在與否：
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

## 為什麼要取得光柵格點大小？
在變形後了解格點大小，可幫助您掌握產生資料集的空間解析度。當需要對齊多個圖層、執行依賴實際距離的分析，或僅僅驗證變形是否保留了預期的細節層級時，這都是必不可少的。

## 如何有效變形光柵格式
`Warp` 方法抽象化了複雜的再投影邏輯，讓您專注於目標尺寸與目標空間參考系統等輸入參數。這使得在座標系統之間轉換資料、重新取樣至不同解析度，或裁剪至特定區域變得簡單直觀。

## 常見問題與解決方案
- **格點大小值異常：** 請確認 `Height` 與 `Width` 參數符合期望的輸出解析度。  
- **缺少空間參考：** 若 `spatialRefSys` 回傳 null，請確認來源 GeoTIFF 含有正確的 CRS 中繼資料。  
- **NoData 處理：** 使用 `warped.NoDataValues.IsNull()` 來偵測缺失資料；您亦可在變形前指定自訂的 NoData 值。  

## 常見問與答

**Q: Aspose.GIS 是否相容所有光柵格式？**  
A: 是的，Aspose.GIS 支援廣泛的光柵格式，提供處理各種空間資料集的彈性。

**Q: 我可以對非地理參考的影像執行光柵變形嗎？**  
A: Aspose.GIS 旨在處理具地理參考的資料，以確保轉換的精確性。請確保您的光柵影像具備正確的空間參考資訊。

**Q: 我該如何為 Aspose.GIS 社群做出貢獻？**  
A: 前往 [Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33) 參與討論，分享經驗、提問並與其他開發者合作。

**Q: 是否提供 Aspose.GIS 的免費試用？**  
A: 是的，您可於[此處](https://releases.aspose.com/)下載免費試用版，探索 Aspose.GIS 的功能。

**Q: 是否提供 Aspose.GIS 的臨時授權？**  
A: 是的，若您需要臨時授權，可於[此處](https://purchase.aspose.com/temporary-license/)取得。

**最後更新：** 2026-05-05  
**測試環境：** Aspose.GIS for .NET (latest release)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-10-10
description: 了解如何使用 Aspose.GIS for .NET 透過 warp raster formats 取得 raster cell size
  並變更 raster resolution – 步驟教學，適用於空間資料視覺化。
keywords:
- get raster cell size
- change raster resolution
- convert geotiff .net
lastmod: 2026-10-10
linktitle: Warp raster formats
og_description: 使用 Aspose.GIS for .NET 在 warp raster 後取得 raster cell size。本教學示範如何變更
  raster resolution、轉換 GeoTIFF 檔案，並在幾個簡單步驟中擷取詳細 raster metadata。
og_image_alt: 'Developer guide: Get raster cell size and warp raster formats using
  Aspose.GIS for .NET'
og_title: 取得 raster cell size 並使用 Aspose.GIS 進行 raster warp
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to get raster cell size and change raster resolution by warping
    raster formats using Aspose.GIS for .NET – a step‑by‑step guide for spatial data
    visualization.
  headline: Get raster cell size – warp raster formats
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS supports a wide range of raster formats, providing flexibility
      in handling various spatial datasets.
    question: Is Aspose.GIS compatible with all raster formats?
  - answer: Aspose.GIS is designed to handle georeferenced data, ensuring accurate
      transformations. Ensure your raster images have proper spatial reference information.
    question: Can I perform raster warping on non‑georeferenced images?
  - answer: Join the discussion on the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      to share your experiences, ask questions, and collaborate with other developers.
    question: How can I contribute to the Aspose.GIS community?
  - answer: Yes, you can explore the capabilities of Aspose.GIS by downloading a free
      trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.GIS?
  - answer: Yes, if you need a temporary license, you can obtain one [here](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- raster processing
- Aspose.GIS
- .NET GIS
- geotiff warp
title: 取得 raster cell size – warp raster formats
url: /zh-hant/net/layer-data-operations/warp-raster-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 獲取光柵像元大小 – 變形光柵格式

## 簡介
在本教學中，您將在執行變形操作後 **獲取光柵像元大小**，並了解如何使用 Aspose.GIS for .NET 為任何 GeoTIFF **變更光柵解析度**。無論您是為 Web 地圖服務準備資料、為空間分析對齊圖層，或只是需要驗證重新投影是否保留了預期的細節，這些步驟都能讓您完整掌控光柵幾何與中繼資料。讓我們從載入光柵、提取像元大小及其他關鍵屬性，一步步完成整個流程。

## 快速回答
- **主要目標是什麼？** 在執行變形操作後取得光柵像元大小。  
- **使用哪個函式庫？** Aspose.GIS for .NET。  
- **需要授權嗎？** 提供免費試用版；正式環境需購買授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **範例執行時間多久？** 在一般電腦上少於一分鐘。

## 前置條件
在開始之前，請確保您已具備以下條件：
- Aspose.GIS for .NET：如果尚未安裝，請下載並安裝 Aspose.GIS 函式庫。您可於[此處](https://releases.aspose.com/gis/net/)找到最新版本。  
- 文件目錄：建立一個目錄用於存放您的文件，這對於光柵變形過程中的檔案管理至關重要。

準備就緒後，讓我們深入程式碼。

## 匯入命名空間
`Aspose.GIS` 命名空間提供光柵與向量操作的核心類別。匯入必要的命名空間，即可展開您的地理空間之旅。

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Raster;
using Aspose.Gis.SpatialReferencing;
```

## 步驟 1：初始化路徑
先設定文件目錄的路徑，所有後續操作都會在此進行：

```csharp
string dataDir = "Your Document Directory";
```

## 步驟 2：開啟光柵圖層
`RasterLayer` 類別代表載入記憶體中的單一光柵資料集。開啟 GeoTIFF 後，即可進行後續的轉換。

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(dataDir, "raster_float32.tif")))
```

## 步驟 3：變形光柵
`Warp` 方法會將光柵重新投影並重新取樣至新的座標參考系統與解析度。它將複雜的數學運算抽象化，讓您只需在一次呼叫中指定目標尺寸與目標空間參考系統。  
`WarpOptions` 讓您定義輸出寬度、高度以及變形操作的目標空間參考系統等參數。

```csharp
using (var warped = layer.Warp(new WarpOptions(){Height = 40, Width = 40, TargetSpatialReferenceSystem = SpatialReferenceSystem.Wgs84}))
```

## 步驟 4：提取光柵資訊
變形完成後，您可以查詢結果光柵的關鍵中繼資料，如像元大小、空間參考系統、邊界以及波段數量。這些屬性可協助您驗證轉換是否如預期執行。

```csharp
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
var bandCount = warped.BandCount;
```

## 步驟 5：列印光柵細節
將剛才取得的關鍵資訊輸出，讓您快速瀏覽變形後光柵的幾何與內容。

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
Console.WriteLine($"bandCount: {bandCount}");
```

## 步驟 6：探索光柵波段
`RasterBand` 代表光柵資料的單一波段（圖層），例如紅、綠、藍或高程值。每個波段都有獨立的資料通道，可檢查其資料類型、統計資訊與 NoData 處理方式。

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

## 為什麼要取得光柵像元大小？
在變形後取得光柵像元大小，可讓您了解每個像素代表的實際地面距離。當需要對齊多個圖層、執行基於距離的分析，或確認變形是否保留了所需的空間解析度時，此資訊相當重要。

## 如何有效變形光柵格式
`Warp` 方法將複雜的重新投影邏輯抽象化，讓您專注於輸入參數，如目標尺寸與目標空間參考系統。這使得在座標系統之間轉換資料、重新取樣至不同解析度，或裁剪至特定區域變得簡單直接。

## Aspose.GIS 的量化優勢
Aspose.GIS 支援 **超過 30 種光柵格式**，且可在不將整張影像載入記憶體的情況下處理高達 **2 GB** 的檔案，於一般伺服器硬體上提供快速且記憶體效率高的轉換。

## 常見問題與解決方案
- **像元大小異常：** 確認 `Height` 與 `Width` 參數符合期望的輸出解析度。  
- **缺少空間參考：** 若 `spatialRefSys` 回傳 null，請確認來源 GeoTIFF 含有正確的 CRS 中繼資料。  
- **NoData 處理：** 使用 `warped.NoDataValues.IsNull()` 來偵測缺失資料；亦可在變形前自行指定自訂的 NoData 值。

## 常見問答

**Q: Aspose.GIS 是否相容所有光柵格式？**  
A: 是的，Aspose.GIS 支援廣泛的光柵格式，提供彈性處理各種空間資料集。

**Q: 能否對未配定位參考的影像執行光柵變形？**  
A: Aspose.GIS 設計用於處理已配定位參考的資料，以確保轉換的準確性。請確保您的光柵影像具備正確的空間參考資訊。

**Q: 如何為 Aspose.GIS 社群做出貢獻？**  
A: 前往[Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33)參與討論，分享經驗、提問並與其他開發者合作。

**Q: 是否提供 Aspose.GIS 的免費試用？**  
A: 是的，您可於[此處](https://releases.aspose.com/)下載免費試用版，探索其功能。

**Q: 是否有臨時授權可供使用？**  
A: 有，若需臨時授權，可於[此處](https://purchase.aspose.com/temporary-license/)取得。

---

**最後更新：** 2026-10-10  
**測試環境：** Aspose.GIS for .NET（最新發行版）  
**作者：** Aspose

## 相關教學

- [Layer Data Operations](/gis/net/layer-data-operations/)
- [How to Add Layer to File GDB Dataset with spatial reference WGS84 using Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)
- [How to Create Vector Layer with SRS using Aspose.GIS for .NET](/gis/net/layer-management/create-vector-layer-with-srs/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
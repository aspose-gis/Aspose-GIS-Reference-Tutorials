---
date: 2026-01-13
description: 了解如何使用 Aspose.GIS for .NET 裁剪圖層特徵，包括如何以多邊形裁剪光柵、提取光柵像元大小以及取得光柵範圍。立即下載免費試用版。
linktitle: How to Crop Layer Features
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 裁剪圖層要素
url: /zh-hant/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何裁剪圖層特徵

## 介紹
在本教學中，您將學會使用 Aspose.GIS for .NET 來 **裁剪圖層**，這是一種強大的方法，可讓您 **以多邊形裁剪光柵**、**取得光柵格點大小**，以及 **取得光柵範圍**，以進行精確的地理空間分析。無論您是為 Web 地圖準備資料、裁切衛星影像，或是分離感興趣區域，本步驟指南都會清楚說明如何完成工作。

## 快速回答
- **「裁剪圖層」是什麼意思？** 它會將光柵或向量圖層裁減至提供的幾何形狀範圍。  
- **本範例使用哪種幾何形狀？** 使用 WKT 格式定義的多邊形。  
- **裁剪後可以取得格點大小嗎？** 可以——`CellSize` 屬性會提供此資訊。  
- **執行程式碼需要授權嗎？** 評估期間可使用臨時授權；正式上線則需正式授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 什麼是「裁剪圖層」？
裁剪圖層是指將資料集限制在特定的地理區域內，將圖層外的所有內容捨棄。這樣可減少檔案大小、加快處理速度，並將分析焦點放在您關心的區域上。

## 為什麼使用 Aspose.GIS 進行裁剪？
- **高效能光柵處理** – 適用於大型 GeoTiff 檔案。  
- **簡易 API** – 只需一行 `Crop` 呼叫即可使用任意幾何形狀。  
- **完整 .NET 相容性** – 可在桌面、伺服器與雲端應用中使用。  
- **精確的空間參考處理** – 自動保留 CRS 資訊。

## 前置條件
在深入地理空間操作的奧妙之前，請先確保您已具備以下前置條件：

- Aspose.GIS for .NET 套件：請確定已在 .NET 專案中安裝 Aspose.GIS 套件。您可從 [此處](https://releases.aspose.com/gis/net/) 下載。  
- 文件目錄：建立一個目錄來存放您的文件。將範例程式碼中的 `"Your Document Directory"` 替換為實際的文件目錄路徑。

現在，讓我們開始一步步的教學。

## 匯入命名空間
先匯入必要的命名空間，以發揮 Aspose.GIS 的全部功能：

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## 步驟 1：開啟並裁剪圖層（以多邊形裁剪光柵）
先開啟 GeoTiff 圖層，並依據已定義的多邊形進行裁剪。這樣可確保您的地理空間資料只保留在感興趣的特定區域。

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## 步驟 2：取得光柵資訊（取得格點大小與光柵範圍）
圖層裁剪完成後，提取光柵資料的關鍵資訊，例如格點大小、空間參考系統與邊界。

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## 步驟 3：顯示資訊
將提取的資訊列印出來，以了解裁剪過程對地理空間資料的影響。

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

視需求重複上述步驟，以調整並客製化您的地理空間資料，滿足特定專案需求。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **多邊形方向不正確** | 確保 WKT 多邊形遵循右手規則（外環逆時針）。 |
| **缺少空間參考** | 檢查來源 GeoTiff 是否包含 CRS；若無，請在裁剪前手動設定。 |
| **大型光柵效能下降** | 在下採樣的副本上使用 `layer.Crop`，或將光柵分割成瓦片處理。 |

## 常見問答
### Q: Aspose.GIS for .NET 有提供臨時授權嗎？
A: 有，您可以在 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

### Q: 哪裡可以找到 Aspose.GIS for .NET 的完整文件？
A: 文件可在 [此處](https://reference.aspose.com/gis/net/) 取得。

### Q: 如何取得支援或加入 Aspose.GIS for .NET 社群？
A: 請前往 [Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33) 獲取支援與交流。

### Q: 可以下載 Aspose.GIS for .NET 的免費試用版嗎？
A: 可以，請在 [此處](https://releases.aspose.com/) 下載免費試用版。

### Q: 哪裡可以購買 Aspose.GIS for .NET？
A: 您可於 [此處](https://purchase.aspose.com/buy) 購買此套件。

### Q: 能否在一次執行中裁剪多個圖層？
A: 可以——只要在迴圈中對每個圖層呼叫相同的 `Crop` 並傳入所需的幾何形狀即可。

### Q: API 是否支援其他光柵格式（例如 JPEG2000）？
A: Aspose.GIS 支援所有底層 GDAL 驅動程式所提供的格式，包括 JPEG2000、PNG 等。

## 結論
透過本指南，您已掌握如何使用 Aspose.GIS for .NET 高效地 **裁剪圖層**。您可以輕鬆 **以多邊形裁剪光柵**、**取得光柵格點大小**，以及 **取得光柵範圍**，以符合任何專案需求。進一步探索重新投影、光柵樣式與向量分析等 API，釋放您的地理空間工作流程的全部潛能。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-01-13  
**測試環境：** Aspose.GIS 24.10 for .NET  
**作者：** Aspose  

---
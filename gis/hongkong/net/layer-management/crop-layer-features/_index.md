---
date: 2026-07-05
description: 了解如何使用 Aspose.GIS for .NET 裁剪圖層特徵，包括如何使用多邊形裁剪光柵、提取光柵格點大小以及取得光柵範圍。立即下載免費試用版。
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: 如何裁剪圖層特徵
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to crop layer features with Aspose.GIS for .NET, including
    how to crop raster with polygon, extract raster cell size, and retrieve raster
    extent. Download your free trial now.
  headline: How to Crop Layer Features with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for Aspose.GIS for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find comprehensive documentation for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support
      and community engagement.
    question: How can I seek support or connect with the community for Aspose.GIS
      for .NET?
  - answer: Yes, you can download a free trial [here](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.GIS for .NET?
  - answer: You can purchase the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 裁剪圖層特徵
url: /zh-hant/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何裁剪圖層特徵

## 介紹
在本教學中，您將學習 **裁剪圖層** 特徵，使用 Aspose.GIS for .NET，這是一個強大的函式庫，可讓您 **使用多邊形裁剪光柵**、**提取光柵格元大小**，以及 **取得光柵範圍**，以進行精確的地理空間分析。無論您是為網頁地圖準備資料、裁剪衛星影像，或是分離感興趣區域，本步驟指南都會清晰說明如何快速且可靠地完成任務。

## 快速答案
- **「裁剪圖層」是什麼意思？** 它會將光柵或向量圖層裁剪至提供的幾何形狀邊界，並捨棄所有位於外部的資料。  
- **此範例使用哪種幾何形狀？** 使用以 WKT（Well‑Known Text）格式定義的多邊形。  
- **裁剪後我可以提取格元大小嗎？** 可以——`CellSize` 屬性會回傳光柵格元的寬度與高度。  
- **執行程式碼是否需要授權？** 臨時授權可用於評估；正式環境則需完整授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## 什麼是「裁剪圖層」？
**裁剪圖層指的是將資料集限制在特定的地理區域內，並捨棄區域外的所有資料。** 此操作可減少檔案大小、加快後續處理速度，並將分析焦點集中於您關注的區域。透過將資料限制於感興趣區域，亦可簡化後續的樣式設定、分析與發布工作流程，同時保留原始的座標參考系統與中繼資料。

## 為什麼使用 Aspose.GIS 進行裁剪？
**Aspose.GIS 能在不將整張影像載入記憶體的情況下處理高達 2 GB 的光柵檔案，且支援超過 30 種光柵格式，包括 GeoTIFF、JPEG2000 與 PNG。** 此函式庫提供單行 `Crop` 呼叫、自動 CRS 處理，以及多執行緒效能，能在一般伺服器上於一秒內裁剪出 500 MB 的 GeoTIFF。

## 前置條件
在深入地理空間操作的奧妙之前，請確保已具備以下前置條件：

- Aspose.GIS for .NET 函式庫：確保已在您的 .NET 專案中安裝 Aspose.GIS 函式庫。您可從 [here](https://releases.aspose.com/gis/net/) 下載。  
- 文件目錄：建立一個目錄以儲存您的文件。將提供程式碼中的 `"Your Document Directory"` 替換為實際的文件目錄路徑。

現在，讓我們深入步驟指南。

## 匯入命名空間
`Aspose.Gis` 命名空間包含處理光柵與向量的所有核心類型。匯入該命名空間即可存取 `Layer`、`Geometry` 以及相關類別。

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## 如何使用多邊形裁剪圖層？
`Crop` 是 `Layer` 類別的方法，用於提取由幾何形狀定義的光柵子集。  
載入來源光柵、定義多邊形幾何，然後呼叫 `Crop` 方法——整個操作只需一行程式碼。此方法會回傳一個僅包含多邊形內像素的新光柵，並自動保留原始空間參考。

## 步驟 1：開啟並裁剪圖層（使用多邊形裁剪光柵）
`Layer` 代表可開啟、查詢與編輯的光柵資料集。  
`Layer` 類別代表可開啟、查詢與編輯的光柵資料集。開啟 GeoTIFF 並使用多邊形進行裁剪，只需幾行程式碼即可將感興趣區域分離出來。

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## 步驟 2：取得光柵資訊（提取光柵格元大小與取得光柵範圍）
`CellSize` 提供每個光柵格元在座標單位下的寬度與高度。  
`Extent` 回傳光柵的地理邊界框。  
`CellSize` 屬性提供每個格元的寬高（以座標單位表示），而 `Extent` 屬性則回傳裁剪後光柵的地理邊界框。這兩項資訊對於後續的計算（如面積測量或再投影）皆相當重要。

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## 步驟 3：顯示資訊
列印提取的資訊，以了解裁剪過程對您的地理空間資料的影響。

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

視需要重複這些步驟，以精細調整您的地理空間資料，滿足特定專案需求。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **多邊形方向不正確** | 確保 WKT 多邊形遵循右手規則（外環為逆時針方向）。 |
| **缺少空間參考** | 確認來源 GeoTiff 含有 CRS；若無，請在裁剪前手動設定。 |
| **大型光柵效能下降** | 在下採樣的副本上使用 `layer.Crop`，或將光柵分割成瓦片處理。 |

## 常見問與答
**Q: Aspose.GIS for .NET 是否提供臨時授權？**  
A: 是的，您可在 [here](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**Q: 哪裡可以找到 Aspose.GIS for .NET 的完整文件？**  
A: 文件可於 [here](https://reference.aspose.com/gis/net/) 取得。

**Q: 如何取得支援或與 Aspose.GIS for .NET 社群聯繫？**  
A: 請前往 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 獲取支援與社群交流。

**Q: 我可以下載 Aspose.GIS for .NET 的免費試用版嗎？**  
A: 是的，您可在 [here](https://releases.aspose.com/) 下載免費試用版。

**Q: 哪裡可以購買 Aspose.GIS for .NET？**  
A: 您可於 [here](https://purchase.aspose.com/buy) 購買此函式庫。

**Q: 我可以在一次執行中裁剪多個圖層嗎？**  
A: 可以——對每個圖層迴圈，使用相同的 `Crop` 呼叫並提供所需的幾何形狀。

**Q: API 是否支援其他光柵格式（例如 JPEG2000）？**  
A: Aspose.GIS 支援底層 GDAL 驅動程式所提供的所有格式，包括 JPEG2000、PNG 等。

## 結論
透過本指南，您現在已掌握如何使用 Aspose.GIS for .NET 高效地 **裁剪圖層** 特徵。您可以輕鬆 **使用多邊形裁剪光柵**、**提取光柵格元大小**，以及 **取得光柵範圍**，以符合任何專案需求。進一步探索再投影、光柵樣式設定與向量分析等 API，發揮地理空間工作流程的全部潛力。

---

**最後更新：** 2026-07-05  
**測試環境：** Aspose.GIS 24.10 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何使用 Aspose.GIS for .NET 建立多邊形幾何](/gis/net/geometry-creation/create-polygon-geometry/)
- [取得圖層屬性 – 使用 Aspose.GIS for .NET 取得圖層屬性資訊](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [建立多邊形幾何（C#）並檢查交集 – 使用 Aspose.GIS for .NET](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
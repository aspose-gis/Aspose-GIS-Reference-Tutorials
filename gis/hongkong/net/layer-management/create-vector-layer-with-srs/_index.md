---
date: 2026-01-15
description: 探索 Aspose.GIS for .NET，建立具備空間參考系統的向量圖層。了解如何設定 SRS、建立圖層及管理 GIS 資料。立即下載！
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: 建立具備 SRS 的向量圖層
url: /zh-hant/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立向量圖層與 SRS

## 介紹
Aspose.GIS for .NET 是一套功能強大的程式庫，讓開發人員能夠 **建立向量圖層** 物件，並在 .NET 應用程式中無縫操作地理資訊系統 (GIS) 資料。在本教學中，我們將一步步說明如何使用 Aspose.GIS for .NET 建立具有空間參考系統 (SRS) 的向量圖層、為何需要設定空間參考，以及此舉對實務專案帶來的好處。完成本指南後，您將能自信地在 .NET 解決方案中整合 GIS 功能。

## 快速解答
- **本教學的主要目的為何？** 示範如何使用 Aspose.GIS for .NET 以指定的 SRS 建立向量圖層。  
- **範例中使用哪種投影？** 世界墨卡托投影 (EPSG:3395)。  
- **執行程式碼是否需要授權？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **此方式能套用於其他 GIS 格式嗎？** 可以，相同的 SRS 處理方式適用於 Shapefile、GeoJSON、KML 等。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## 什麼是向量圖層以及為何要設定其空間參考？
**向量圖層** 用於儲存幾何要素（點、線、面）以及屬性資料。指定 **空間參考** (SRS) 可讓 GIS 軟體正確解讀這些座標在地球表面的位置。正確的 SRS 可確保測量精確、圖層間正確疊合，並產生可靠的地圖視覺化效果。

## 前置條件
在開始之前，請確認您已具備：

- 基本的 C# 與 .NET 開發知識。  
- 已安裝 Aspose.GIS for .NET 程式庫。您可以在 **[此處](https://releases.aspose.com/gis/net/)** 下載。  
- 開發環境（Visual Studio、VS Code 或任何 C# IDE）。

## 匯入命名空間
確保在 C# 檔案的最上方匯入必要的命名空間：

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 如何設定空間參考 (SRS) – 步驟 1
讓我們以世界墨卡托投影為例，建立一個 **投影空間參考系統**。此範例說明了 **如何為圖層設定 SRS**。

```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```

## 如何建立圖層 – 步驟 2
接下來，我們將 **建立向量圖層**（Shapefile），並加入使用剛才定義之 SRS 的要素。此步驟回答了 **如何使用 Aspose.GIS 建立圖層**。

```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // This will throw an exception as the geometry has a different SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```

> **專業提示：** 在加入要素前，務必確認幾何的 `SpatialReferenceSystem` 與圖層的 SRS 相同。若 SRS 不匹配，會拋出 `GisException`，如上例所示。

## 驗證空間參考系統 – 步驟 3
最後，開啟圖層並確認 SRS 是否正確套用。

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

如果 `IsEquivalent` 呼叫回傳 `true`，即表示您已成功 **建立向量圖層**，且具備所需的空間參考。

## 常見問題與解決方案
| 問題 | 為何會發生 | 解決方式 |
|------|------------|----------|
| `GisException` 在加入要素時拋出 | 幾何使用的 SRS 與圖層不同 | 在加入前將 `feature.Geometry.SpatialReferenceSystem` 設為圖層的 SRS |
| 圖層在 GIS 軟體中顯示為空 | Shapefile 未產生正確的 `.prj` 檔案 | 建立圖層時務必傳入 `projectedSrs` 物件 |
| 座標值異常 | 投影參數錯誤（例如中央子午線） | 再次檢查傳入 `AddProjectionParameter` 的參數 |

## 常見問答
### Aspose.GIS 是否相容所有 GIS 檔案格式？
Aspose.GIS 支援多種 GIS 格式，包括 Shapefile、GeoJSON、KML 等。完整清單請參閱 **[文件說明](https://reference.aspose.com/gis/net/)**。

### 我可以在 Web 應用程式中使用 Aspose.GIS 嗎？
當然可以！Aspose.GIS for .NET 具備彈性，可用於 Web 應用、桌面程式，甚至行動應用。

### 我可以從哪裡取得 Aspose.GIS 的支援？
您可前往 **[Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33)** 取得社群協助，解決各種問題。

### 有提供免費試用嗎？
有，您可在 **[此處](https://releases.aspose.com/)** 取得免費試用版，探索 Aspose.GIS 的功能。

### 我要如何購買 Aspose.GIS 的授權？
請前往 **[購買頁面](https://purchase.aspose.com/buy)** 進行授權購買。

## 常見問答（額外）

**Q: 若嘗試加入使用不同 SRS 的幾何會發生什麼事？**  
A: Aspose.GIS 會拋出 `GisException`。您必須先重新投影該幾何，或確保其與圖層使用相同的 SRS。

**Q: 可以變更已存在圖層的 SRS 嗎？**  
A: 可以，您可以建立一個具有目標 SRS 的新圖層，然後將要素複製過去，必要時進行重新投影。

**Q: 能處理 3D 座標嗎？**  
A: Aspose.GIS 支援 Z 座標，只要使用接受 Z 值的幾何建構子即可。

**Q: 程式庫會自動處理基準面轉換嗎？**  
A: 在使用 `Geometry.Transform` 重新投影幾何時，Aspose.GIS 會自動執行所需的基準面位移。

**Q: 官方測試的 .NET 版本有哪些？**  
A: 程式庫已於 .NET Framework 4.5 以上、.NET Core 3.1 以上，以及 .NET 5/6/7 進行測試。

## 結論
您現在已學會如何使用 Aspose.GIS for .NET 以自訂空間參考系統 **建立向量圖層**。透過正確設定 SRS、統一處理幾何資料，並驗證圖層的中繼資料，您可以打造與任何標準 GIS 軟體互通的穩健 GIS 應用程式。

---

**最後更新：** 2026-01-15  
**測試版本：** Aspose.GIS 24.11 for .NET（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
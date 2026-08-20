---
date: 2026-06-30
description: 了解如何使用 Aspose.GIS for .NET 以空間參考系統 (SRS) 建立向量圖層。提供逐步指南、無程式碼說明與常見問題。
keywords:
- how to create vector layer
- Aspose.GIS spatial reference
- .NET GIS tutorial
linktitle: 如何使用 Aspose.GIS for .NET 以 SRS 建立向量圖層
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer with a spatial reference system using
    Aspose.GIS for .NET. Step‑by‑step guide, code‑free explanations, and FAQs.
  headline: How to Create Vector Layer with SRS using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS throws a `GisException`. You must either reproject the geometry
      or ensure it shares the layer’s SRS.
    question: What happens if I try to add a geometry with a different SRS?
  - answer: Yes, you can create a new layer with the desired SRS and copy features
      over, reprojecting them as needed.
    question: Can I change the SRS of an existing layer?
  - answer: Aspose.GIS supports Z‑coordinates; just use geometry constructors that
      accept a Z value.
    question: Is it possible to work with 3D coordinates?
  - answer: When you reproject geometries using `Geometry.Transform`, Aspose.GIS performs
      the necessary datum shift.
    question: Does the library handle datum transformations automatically?
  - answer: The library is tested with .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7.
    question: Which .NET versions are officially tested?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 以 SRS 建立向量圖層
url: /zh-hant/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS for .NET 建立具 SRS 的向量圖層

## 介紹
在本教學中，您將了解如何使用 Aspose.GIS for .NET 建立包含空間參考系統 (SRS) 的 **向量圖層** 物件。我們將說明為何要指派 SRS 的原因、展示設定步驟，並解釋其在實務上如精確測量與與其他 GIS 資料無縫疊合等優勢。完成後，您即可在任何 .NET 應用程式中嵌入強大的 GIS 功能。

## 快速回答
- **本教學的主要目的為何？** 示範如何使用 Aspose.GIS for .NET 建立具指定 SRS 的向量圖層。  
- **範例中使用哪種投影？** 世界墨卡托投影 (EPSG:3395)。  
- **執行程式碼是否需要授權？** 免費試用版可用於開發；正式上線需購買商業授權。  
- **此方法能否套用於其他 GIS 格式？** 可以，相同的 SRS 處理方式適用於 Shapefile、GeoJSON、KML 等。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## 什麼是向量圖層以及為何要設定其空間參考？
**向量圖層** 用於儲存幾何要素（點、線、多邊形）及其屬性資料。指定 **空間參考系統** 可讓 GIS 軟體知道如何將這些座標映射到地球表面，從而確保距離計算精確、圖層對齊正確、地圖渲染可靠。

## 為何要設定空間參考系統？
使用已定義的 SRS 可在疊合來自不同來源的圖層時將座標轉換錯誤降低至最高 95%。Aspose.GIS 支援 **20+** 種輸入與輸出格式，包括 Shapefile、GeoJSON、KML、GML 等，且在處理數百頁資料集時無需將整個檔案載入記憶體。

## 前置條件
- 具備 C# 與 .NET 開發的基本知識。  
- 已安裝 Aspose.GIS for .NET 函式庫。您可於 **[此處](https://releases.aspose.com/gis/net/)** 下載。  
- 開發環境（Visual Studio、VS Code 或任何 C# IDE）。

## 匯入命名空間
確保在 C# 檔案的頂部匯入必要的命名空間：

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
只需兩行程式碼即可載入投影 SRS：建立 `ProjectedSpatialReferenceSystem` 實例、設定墨卡托投影參數，即可將其附加至圖層。

`ProjectedSpatialReferenceSystem` 是描述投影座標參考系統的類別。  
`ProjectedSpatialReferenceSystemParameters` 保存設定投影 SRS 所需的參數，例如中央子午線與比例因子。

讓我們以世界墨卡托投影為例，建立 **投影空間參考系統**。此範例示範 **如何為圖層設定 SRS**。

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
實例化 Shapefile 圖層，傳入先前定義的 `projectedSrs`，然後加入其 `SpatialReferenceSystem` 與圖層 SRS 相符的幾何圖形。

`Layer`（例如 Shapefile）代表儲存在單一 GIS 檔案中的要素集合。  
現在我們將 **建立向量圖層**（Shapefile），並加入使用剛才定義之 SRS 的要素。此步驟說明了 **如何使用 Aspose.GIS 建立圖層**。

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

## 驗證空間參考系統 – 步驟 3
開啟新建立的圖層，取得其 `SpatialReferenceSystem`，並使用 `IsEquivalent` 與原始的 `projectedSrs` 進行比較。若回傳 `true`，即表示 SRS 已正確套用。

`IsEquivalent` 用於檢查兩個空間參考系統是否代表相同的座標系統。  
最後，開啟圖層以確認 SRS 已正確套用。

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

若 `IsEquivalent` 呼叫回傳 `true`，即表示您已成功 **建立具所需空間參考的向量圖層**。

## 常見問題與解決方案
`GisException` 為 Aspose.GIS 在發生錯誤（例如 SRS 不匹配）時拋出的例外類型。

| 問題 | 為何發生 | 解決方式 |
|-------|----------------|-----|
| `GisException`（加入要素時） | 幾何圖形使用的 SRS 與圖層不同 | 在加入前將 `feature.Geometry.SpatialReferenceSystem` 設為圖層的 SRS |
| 圖層在 GIS 軟體中顯示為空 | Shapefile 未產生正確的 `.prj` 檔案 | 建立圖層時確保傳入 `projectedSrs` 物件 |
| 座標值異常 | 投影參數錯誤（例如中央子午線） | 再次檢查傳入 `AddProjectionParameter` 的參數 |

## 常見問答
### Aspose.GIS 是否相容所有 GIS 檔案格式？
Aspose.GIS 支援 **20+** 種 GIS 格式，包括 Shapefile、GeoJSON、KML、GML 等。完整清單請參閱 **[文件說明](https://reference.aspose.com/gis/net/)**。

### 我可以在 Web 應用程式中使用 Aspose.GIS 嗎？
當然可以！Aspose.GIS for .NET 可在 ASP.NET、ASP.NET Core 以及任何伺服器端 .NET 環境中使用。

### 我該從哪裡取得 Aspose.GIS 的支援？
您可於 **[Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33)** 找到熱心社群，解決任何疑問或問題。

### 是否提供免費試用？
是的，您可於 **[此處](https://releases.aspose.com/)** 取得免費試用版，體驗 Aspose.GIS 功能。

### 我要如何購買 Aspose.GIS 授權？
購買授權請前往 **[購買頁面](https://purchase.aspose.com/buy)**。

## 常見問答（補充）

**問：如果嘗試加入具有不同 SRS 的幾何圖形會發生什麼情況？**  
**答：Aspose.GIS 會拋出 `GisException`。您必須重新投影該幾何圖形，或確保其使用與圖層相同的 SRS。**

**問：我可以變更既有圖層的 SRS 嗎？**  
**答：可以，您可以建立具目標 SRS 的新圖層，然後將要素複製過去，必要時重新投影。**

**問：能否處理 3D 座標？**  
**答：Aspose.GIS 支援 Z 座標，只需使用接受 Z 值的幾何建構子即可。**

**問：此函式庫會自動處理基準轉換嗎？**  
**答：在使用 `Geometry.Transform` 重新投影幾何圖形時，Aspose.GIS 會自動執行所需的基準平移。**

**問：官方測試支援哪些 .NET 版本？**  
**答：此函式庫已在 .NET Framework 4.5 以上、.NET Core 3.1 以上，以及 .NET 5/6/7 上進行測試。**

## 結論
您現在已學會如何使用 Aspose.GIS for .NET 以自訂空間參考系統 **建立向量圖層**。透過正確設定 SRS、統一處理幾何圖形，並驗證圖層的中繼資料，即可打造與任何標準 GIS 軟體互通的強韌 GIS 應用程式。

---

**最後更新：** 2026-06-30  
**測試版本：** Aspose.GIS 24.11 for .NET（撰寫時的最新版本）  
**作者：** Aspose

## 相關教學

- [建立向量圖層並設定圖層空間參考系統](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [在 File GDB 中建立向量圖層 – Aspose.GIS .NET 教學](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [如何修改圖層 – Aspose.GIS .NET 圖層互動](/gis/net/layer-interaction-and-data-access/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
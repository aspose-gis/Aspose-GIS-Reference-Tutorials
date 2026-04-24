---
date: 2026-04-24
description: 學習如何使用 Aspose.GIS for .NET 建立檔案地理資料庫，並為 File GDB 圖層設定精度格線，包括向圖層新增要素及驗證座標範圍。
keywords:
- create file geodatabase
- handle out of range
- add features layer
- configure coordinate grid
- validate coordinate range
linktitle: 為檔案 GDB 圖層定義精度格網
second_title: Aspose.GIS .NET API
title: 建立檔案地理資料庫並設定 GDB 圖層格網 (Aspose.GIS)
url: /zh-hant/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.GIS 中為 File GDB 圖層設定格網

## 介紹
在本教學中，您將 **建立檔案地理資料庫** 物件，並學習如何使用 Aspose.GIS for .NET 為 File Geodatabase (GDB) 圖層 **設定格網**。定義精度格網可讓您 **驗證座標範圍**、防止超出範圍的錯誤，並確保任何 **向圖層新增要素** 的操作能精確儲存資料。我們將逐步說明每個步驟，解釋每項設定的原因，並示範如何優雅地 **處理超出範圍** 的情況。

## 快速回答
- **「設定格網」是什麼意思？** 它定義了 GIS 圖層的座標精度和有效範圍。  
- **為什麼要使用精度格網？** 它可保護您的資料免於無效座標，並提升儲存效率。  
- **哪個函式庫提供此功能？** Aspose.GIS for .NET。  
- **我需要授權嗎？** 有提供試用版；在正式環境中需購買商業授權。  
- **可以在 .NET Core 中使用嗎？** 可以，Aspose.GIS 支援 .NET Framework 與 .NET Core。

## 什麼是精度格網以及為什麼要設定它？
精度格網是一組參數（原點、比例等），告訴 GIS 引擎如何四捨五入與儲存座標值。透過設定格網，您可以自動 **驗證座標範圍**，任何嘗試插入超出格網的點都會拋出例外——協助您在開發早期 **處理超出範圍** 的情況。

## 為什麼要在建立檔案地理資料庫時使用精度格網？
建立檔案地理資料庫可提供一個可攜帶且高效能的向量資料容器。在建立時加入精度格網可確保：

- **一致的資料品質** — 每個要素皆遵循相同的數值精度。  
- **更快的索引** — 引擎能更有效率地儲存座標。  
- **提前偵測錯誤** — 超出範圍的座標會在破壞資料集之前被捕捉。

## 前置條件
在開始之前，請確保已安裝以下項目：

1. **Visual Studio** – 任意近期版本（Community、Professional 或 Enterprise）。  
2. **Aspose.GIS for .NET** – 從[官方網站](https://releases.aspose.com/gis/net/)下載。  
3. **基本的 C# 知識** – 您應該能熟練建立 .NET 主控台專案。

## 常見使用情境
- **現場資料收集**：GPS 裝置可能產生略微超出預定範圍的座標。  
- **資料遷移**：從使用不同座標精度的舊系統搬移資料。  
- **自動化 ETL 流程**：在將資料載入 GIS 資料庫前，需要強制執行空間完整性。

## 匯入命名空間
首先，匯入使用 Aspose.GIS 所需的命名空間：

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## 如何在 File GDB 圖層中設定座標格網
以下是逐步指南，說明如何正確設定格網、建立圖層，並安全地 **向圖層新增要素**。

### 步驟 1：建立資料集
我們先建立一個新的 File Geodatabase 資料集，圖層將會存在於此。

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### 步驟 2：定義精度格網選項
在此指定格網參數。請調整原點與比例，以符合您專案的座標系統。

```csharp
var options = new FileGdbOptions
{
    CoordinatePrecisionGrid = new FileGdbCoordinatePrecisionGrid
    {
        XOrigin = -400,
        YOrigin = -400,
        XYScale = 1e10,
        MOrigin = 0,
        MScale = 1e4,
    },
    EnsureValidCoordinatesRange = true,
};
```

*`EnsureValidCoordinatesRange = true` 旗標告訴 Aspose.GIS 為您新增的每個要素 **驗證座標範圍**。*

### 步驟 3：使用格網建立圖層
現在在資料集中建立新圖層，套用剛才定義的格網選項。我們將使用 WGS84 空間參考系統。

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### 步驟 4：向圖層新增要素
我們建立兩個點要素。第一個點位於格網內部，第二個則故意位於格網外，以示範 **如何處理超出範圍** 的錯誤。

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### 步驟 5：處理新增超出範圍要素時的例外
嘗試新增第二個要素時會拋出例外，因為其 X 座標（`-410`）超出已定義的格網。我們捕捉例外並輸出清晰的訊息。

```csharp
try
{
    layer.Add(feature);
}
catch (GisException e)
{
    Console.WriteLine(e.Message); // X value -410 is out of valid range.
}
```

### 步驟 6：清理資源
`using` 陳述式會自動關閉並釋放資料集與圖層，確保所有資源皆被釋放。

## 常見問題與解決方案
| 問題 | 發生原因 | 解決方式 |
|-------|----------------|-----|
| **Exception: “X value … is out of valid range.”** | 座標超出精度格網的範圍。 | 調整 `XOrigin`、`YOrigin` 或 `XYScale` 以涵蓋您的資料，或確保輸入資料位於定義的範圍內。 |
| **Features not appearing in GIS viewer** | 圖層未儲存或空間參考錯誤。 | 確認 `SpatialReferenceSystem.Wgs84` 與檢視器的 CRS 相符，且 `Dataset.Create` 已成功執行。 |
| **M values ignored** | `MScale` 設為 0 或過低。 | 設定合理的 `MScale`（例如 `1e4`）以儲存測量值。 |

## 疑難排解技巧
- **在載入大量資料前再次確認格網範圍**；`XOrigin` 的小錯字可能導致大量列被拒絕。  
- **將例外訊息記錄**（如 try‑catch 區塊所示）至檔案，於自動匯入時使用；這有助於更容易發現超出範圍資料的模式。  
- **僅在可信任的資料來源上使用 `EnsureValidCoordinatesRange = false`** — 關閉驗證會跳過檢查，可能導致幾何圖形損壞。

## 常見問答

**Q: 我可以將 Aspose.GIS for .NET 與其他 GIS 檔案格式一起使用嗎？**  
A: 可以，Aspose.GIS 支援 Shapefile、GeoJSON、KML 等多種格式。

**Q: Aspose.GIS for .NET 是否相容於 .NET Core？**  
A: 完全相容。此函式庫支援 .NET Framework、.NET Core 以及 .NET 5/6 以上版本。

**Q: 我可以執行如緩衝或交集等空間操作嗎？**  
A: 可以，API 包含緩衝、交集以及計算距離等方法。

**Q: Aspose.GIS 是否提供座標轉換功能？**  
A: 可以，您可使用內建的再投影工具在不同空間參考系統之間轉換幾何圖形。

**Q: 是否提供試用版？**  
A: 有，您可從[官方網站](https://releases.aspose.com/gis/net/)下載免費試用版。

---

**最後更新：** 2026-04-24  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
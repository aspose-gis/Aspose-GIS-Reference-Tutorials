---
date: 2025-12-28
description: 學習如何使用 Aspose.GIS for .NET 為 File GDB 圖層設定格網，包括向圖層新增要素及驗證座標範圍。
linktitle: Define Precision Grid for File GDB Layer
second_title: Aspose.GIS .NET API
title: 如何在 Aspose.GIS 中為 File GDB 圖層設定格網
url: /zh-hant/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何為 Aspose.GIS 中的 File GDB 圖層設定格線

## 介紹
在本教學中，您將學習 **如何設定格線** 於使用 Aspose.GIS for .NET 的 File Geodatabase (GDB) 圖層。設定精度格線可協助您 **驗證座標範圍**、防止超出範圍的錯誤，並確保您 **向圖層新增要素** 的資料保持準確可靠。我們將逐步說明每個步驟、解釋設定的重要性，並示範如何處理常見的陷阱。

## 快速解答
- **「設定格線」是什麼意思？** 它定義 GIS 圖層的座標精度與有效範圍。  
- **為何要使用精度格線？** 它可保護資料免於無效座標，並提升儲存效率。  
- **哪個函式庫提供此功能？** Aspose.GIS for .NET。  
- **需要授權嗎？** 提供試用版；正式環境需購買商業授權。  
- **可以在 .NET Core 上使用嗎？** 可以，Aspose.GIS 同時支援 .NET Framework 與 .NET Core。

## 什麼是精度格線以及為何要設定它？
精度格線是一組參數（原點、比例等），告訴 GIS 引擎如何四捨五入與儲存座標值。透過設定格線，系統會自動 **驗證座標範圍**，任何嘗試插入超出格線的點都會拋出例外，讓您在開發早期即 **處理超出範圍** 的情況。

## 前置條件
在開始之前，請確保已安裝以下項目：

1. **Visual Studio** – 任一近期版本（Community、Professional 或 Enterprise）。  
2. **Aspose.GIS for .NET** – 從[網站](https://releases.aspose.com/gis/net/)下載。  
3. **基本的 C# 知識** – 您應該能熟練建立 .NET 主控台專案。

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

## 如何在 File GDB 圖層中設定格線
以下是逐步指南，說明如何配置格線、建立圖層，並安全地 **向圖層新增要素**。

### 步驟 1：建立資料集
我們先建立一個新的 File Geodatabase 資料集，圖層將儲存在此處。

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### 步驟 2：定義精度格線選項
在此指定格線參數。請依專案的座標系統調整原點與比例。

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

*`EnsureValidCoordinatesRange = true` 旗標告訴 Aspose.GIS 為您 **驗證座標範圍**，每個新增的要素都會受到檢查。*

### 步驟 3：使用格線建立圖層
現在在資料集中建立新圖層，套用剛才定義的格線選項。我們將使用 WGS84 空間參考系統。

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### 步驟 4：向圖層新增要素
我們建立兩個點要素。第一個點位於格線內，第二個則故意超出格線，以示範 **如何處理超出範圍** 的錯誤。

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### 步驟 5：處理新增超出範圍要素時的例外
嘗試新增第二個要素時會拋出例外，因為其 X 座標 (`-410`) 超出已定義的格線。我們捕捉例外並輸出清晰的訊息。

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
`using` 陳述式會自動關閉並釋放資料集與圖層，確保所有資源皆被正確釋放。

## 常見問題與解決方案
| 問題 | 為何會發生 | 解決方式 |
|------|------------|----------|
| **例外：「X 值 … 超出有效範圍。」** | 座標落在精度格線之外。 | 調整 `XOrigin`、`YOrigin` 或 `XYScale` 以涵蓋您的資料，或確保輸入資料在已定義的範圍內。 |
| **要素在 GIS 檢視器中未顯示** | 圖層未儲存或空間參考錯誤。 | 確認 `SpatialReferenceSystem.Wgs84` 與檢視器的 CRS 相符，且 `Dataset.Create` 已成功執行。 |
| **M 值被忽略** | `MScale` 設為 0 或過低。 | 為 `MScale` 設定合理值（例如 `1e4`），以儲存測量值。 |

## 常見問答

**Q: 我可以在 .NET 中使用 Aspose.GIS 處理其他 GIS 檔案格式嗎？**  
A: 可以，Aspose.GIS 支援 Shapefile、GeoJSON、KML 等多種格式。

**Q: Aspose.GIS for .NET 是否相容 .NET Core？**  
A: 完全相容。此函式庫同時支援 .NET Framework、.NET Core 以及 .NET 5/6 以上版本。

**Q: 我能執行緩衝或交集等空間運算嗎？**  
A: 可以，API 提供緩衝、交集以及距離計算等方法。

**Q: Aspose.GIS 是否提供座標轉換功能？**  
A: 有的，您可以使用內建的再投影工具在不同空間參考系統之間轉換幾何圖形。

**Q: 有提供試用版嗎？**  
A: 有，您可從[網站](https://releases.aspose.com/gis/net/)下載免費試用版。

---

**最後更新：** 2025-12-28  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
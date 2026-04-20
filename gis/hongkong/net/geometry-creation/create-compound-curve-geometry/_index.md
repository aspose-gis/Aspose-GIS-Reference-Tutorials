---
date: 2026-02-15
description: 學習如何在 .NET 中使用 Aspose.GIS 添加曲線並建立複合曲線幾何，以實現無縫的地理空間資料處理。
linktitle: How to Add Curves – Compound Curve Geometry
second_title: Aspose.GIS .NET API
title: 如何新增曲線 - 使用 Aspose.GIS 的複合曲線幾何
url: /zh-hant/net/geometry-creation/create-compound-curve-geometry/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何新增曲線：使用 Aspose.GIS 的複合曲線幾何

## 介紹
在 .NET 開發領域，學習 **如何新增曲線**（with Aspose.GIS）對於構建高階地理空間應用程式至關重要。無論您是在建立互動地圖、執行空間分析，或產生複雜的 GIS 資料集，Aspose.GIS 都能提供快速且可靠的進階幾何處理工具。本指南將一步步說明 **如何新增曲線**，並將它們組合成單一可重用的複合曲線幾何。

## 快速回答
- **主要目標是什麼？** 在 Shapefile 中新增曲線並建立複合曲線幾何。  
- **使用哪個函式庫？** Aspose.GIS for .NET。  
- **前置條件？** Visual Studio、已安裝 Aspose.GIS，以及一個基本的 C# 專案。  
- **典型實作時間？** 約 10‑15 分鐘即可完成示範。  
- **支援的輸出格式？** Shapefile（相同方法亦適用於 GeoJSON、KML 等）。

## 什麼是複合曲線？
**複合曲線** 是由多個相連的曲線元件（直線串與圓弧）組成的單一幾何圖形，這些元件連接在一起形成較為複雜的形狀。當單一簡單線條無法精確表示所需路徑（例如彎曲的道路或河流彎曲）時，此結構非常有用。

## 為何使用 Aspose.GIS 來新增曲線？
- **豐富的幾何 API：** 內建支援線串、圓弧串與複合曲線。  
- **跨平台：** 可在 .NET Framework、.NET Core 以及 .NET 5/6+ 上執行。  
- **無外部相依性：** 不需要原生 GIS 函式庫或 COM interop。  
- **輕鬆匯出：** 直接寫入 Shapefile、GeoJSON、KML 等多種格式。

## 為何這很重要
新增曲線可讓您更精確地建模現實世界特徵，提升地圖渲染的視覺品質，並在距離搜尋或網路路徑規劃等空間分析中提高精度。掌握 **如何新增曲線** 後，您即可提升任何 GIS‑驅動 .NET 解決方案的真實度。

## 常見使用情境
- **交通網路：** 建模包含平滑彎道的高速公路、鐵路或自行車道。  
- **水文學：** 表示遵循自然弧線的河流走向。  
- **都市規劃：** 繪製帶有曲線段的土地界線。  
- **自訂符號：** 為地圖圖例建立裝飾或示意形狀。

## 前置條件
- 已在工作站上安裝 **Visual Studio**。  
- 已從[下載頁面](https://releases.aspose.com/gis/net/)取得 **Aspose.GIS for .NET**。  
- 一個目標為 .NET 6（或任何支援版本）的 C# 專案。

## 匯入命名空間
在 C# 檔案的頂部匯入 Aspose.GIS 所需的命名空間：

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 建立複合曲線幾何的逐步指南

### 步驟 1：定義輸出路徑
首先告訴函式庫結果要寫入哪裡。將佔位符替換為您機器上的實際資料夾路徑。

```csharp
string path = "Your Document Directory" + "CreateCompoundCurve_out.shp";
```

### 步驟 2：建立向量圖層
`VectorLayer` 充當空間要素的容器。所有幾何操作都在此 `using` 區塊內完成，且可確保資源正確釋放。

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block for creating the compound curve geometry will be inserted here.
}
```

### 步驟 3：建構複合曲線要素
在圖層內，我們建立一個新要素與一個空的 `CompoundCurve` 物件，以便儲存各個曲線部件。

```csharp
var feature = layer.ConstructFeature();
var compoundCurve = new CompoundCurve();
```

### 步驟 4：定義組件曲線
此處我們準備五段獨立的曲線——兩條直線 `LineString`、兩條圓弧 `CircularString`，以及最後一條 `LineString`。這些部件將被串接成完整的複合曲線。

```csharp
var bottom = (ILineString)Geometry.FromText("LineString (0 0, 3 0)");
var firstArc = (ICircularString)Geometry.FromText("CircularString (3 0, 4 1, 3 2)");
var middle = (ILineString)Geometry.FromText("LineString (3 2, 1 2)");
var secondArc = (ICircularString)Geometry.FromText("CircularString (1 2, 0 3, 1 4)");
var top = (ILineString)Geometry.FromText("LineString (1 4, 4 4)");
```

### 步驟 5：將組件曲線加入複合曲線
依序將每個組件加入，確保幾何保持連續且方向正確。

```csharp
compoundCurve.AddCurve(bottom);
compoundCurve.AddCurve(firstArc);
compoundCurve.AddCurve(middle);
compoundCurve.AddCurve(secondArc);
compoundCurve.AddCurve(top);
```

### 步驟 6：將幾何指派給要素
現在，組合好的 `CompoundCurve` 成為我們即將儲存的要素的幾何。

```csharp
feature.Geometry = compoundCurve;
```

### 步驟 7：將要素加入圖層
最後，我們把要素寫入 Shapefile。`using` 區塊結束時，檔案即被關閉，可在任何 GIS 應用程式中使用。

```csharp
layer.Add(feature);
```

## 常見問題與技巧
- **座標順序：** Aspose.GIS 期待 `X Y`（經度、緯度）順序。若順序顛倒會產生倒置的幾何。  
- **CircularString 語法：** 確保 `CircularString` 的中間點位於預期弧線上，否則曲線會被壓平。  
- **檔案覆寫：** 若目標 Shapefile 已存在，`VectorLayer.Create` 會直接覆寫且不提示——開發時請使用唯一檔名。  
- **效能考量：** 大量資料集建議批次加入要素，而非在 `using` 內逐一加入。  
- **進階技巧：** 建立多個相似要素時，可重複使用同一個 `CompoundCurve` 物件；在重新填充前先以 `compoundCurve.Clear()` 清除其曲線。

## 常見問答

**Q: Aspose.GIS for .NET 能否在其他 .NET 框架上使用？**  
A: 可以，Aspose.GIS for .NET 支援 .NET Framework、.NET Core 與 .NET Standard。

**Q: Aspose.GIS 是否支援讀寫不同的地理空間檔案格式？**  
A: 當然！它支援 Shapefile、GeoJSON、KML、GML 等多種格式。

**Q: Aspose.GIS 適用於桌面與 Web 應用程式嗎？**  
A: 是的，該函式庫可在桌面、Web 以及雲端服務中使用。

**Q: 我可以使用 Aspose.GIS for .NET 進行空間分析嗎？**  
A: 可以，您可以計算距離、執行幾何運算，並執行空間查詢。

**Q: 哪裡可以取得 Aspose.GIS 的社群支援？**  
A: 前往 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 提問與分享想法。

---

**最後更新：** 2026-02-15  
**測試環境：** Aspose.GIS for .NET（最新穩定版）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
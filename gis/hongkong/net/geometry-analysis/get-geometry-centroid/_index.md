---
date: 2026-02-10
description: 學習如何使用 Aspose.GIS for .NET 計算幾何圖形的質心，取得多邊形的中心點，並計算多重多邊形的質心以進行空間分析。
linktitle: Get Geometry Centroid
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 計算幾何的質心
url: /zh-hant/net/geometry-analysis/get-geometry-centroid/
weight: 19
---

" - not needed.

Let's craft translation.

Be careful not to translate code block placeholders.

Also keep bold formatting.

Let's write final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS for .NET 計算幾何圖形的質心

## 介紹
如果你正在從事 **C# 空間分析**，且需要了解 **如何計算質心** 的任何形狀，你來對地方了。在本教學中，我們將示範使用 Aspose.GIS for .NET **計算多邊形質心**、取得該質心，並看看這小小的幾何圖形如何解鎖強大的 **整合空間分析** 情境，例如標籤放置、聚類與距離計算。

## 快速回答
- **主要方法是什麼？** `GetCentroid()` 於 `IGeometry` 物件上。  
- **哪個函式庫提供它？** Aspose.GIS for .NET。  
- **程式碼行數多少？** 總計少於 15 行（不含 using 陳述式）。  
- **需要授權嗎？** 測試可使用臨時授權；正式環境需購買正式授權。  
- **能在 .NET 6+ 上執行嗎？** 可以 — API 完全相容於 .NET Core 以及 .NET 5/6。  

## 什麼是質心以及為什麼重要？
質心是形狀的幾何中心——可視為「平衡點」。對於多邊形而言，質心（或 **多邊形中心點**）常用於放置標籤、計算平均位置，或作為空間查詢的參考點。快速掌握 **如何計算質心**，即可在不自行編寫複雜數學的情況下整合空間分析功能。

## 為什麼要計算 MultiPolygon 的質心？
當處理多個多邊形的集合（例如由多個島嶼組成的國家邊界）時，你可能需要 **計算 MultiPolygon 的質心**。Aspose.GIS 允許你在 `MultiPolygon` 上呼叫 `GetCentroid()`，直接取得合併形狀的質心，簡化批次處理與地圖視覺化工作。

## 前置條件
在開始之前，請確保你具備以下條件：

### 1. 安裝 Aspose.GIS for .NET
從 [Aspose.GIS for .NET 官方網站](https://releases.aspose.com/gis/net/) 下載函式庫，依照說明將 NuGet 套件加入專案。

### 2. 熟悉 C# 程式設計
你應該能編寫基本的 C# 程式碼。若剛接觸，可先快速複習變數、類別與主控台輸出。

### 3. 基本的地理概念認識
雖非必須，但了解點、線、面之間的差異，能讓你更容易跟上範例說明。

## 匯入命名空間
我們需要將 Aspose.GIS 類別匯入作用域。於 C# 檔案頂部加入以下 `using` 陳述式：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

這些命名空間讓你可以使用幾何類型、`GetCentroid()` 方法，以及標準 .NET 工具。

## 如何計算幾何圖形的質心
以下提供逐步說明，示範 **建立多邊形幾何**、計算其質心，並顯示結果。

### 步驟 1：定義多邊形
首先，我們 **建立多邊形幾何**，指定其頂點。此範例建立一個簡單且不自交的多邊形：

```csharp
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(1, 0),
    new Point(2, 2),
    new Point(0, 4),
    new Point(5, 5),
    new Point(6, 1),
    new Point(1, 0),
});
```

### 步驟 2：取得多邊形質心（多邊形中心點）
多邊形定義完成後，呼叫 `GetCentroid()` 以 **取得多邊形質心**：

```csharp
IPoint centroid = polygon.GetCentroid();
```

### 步驟 3：顯示質心座標
最後，輸出質心的 X 與 Y 座標。格式字串會將數值四捨五入至小數點後兩位：

```csharp
Console.WriteLine("{0:F} {1:F}", centroid.X, centroid.Y); // Output: 3.33 2.58
```

執行程式後，主控台會印出質心座標，證明幾何已正確處理。

## 常見陷阱與專業提示
- **陷阱：** 提供自交的多邊形可能產生意外的質心。  
  **提示：** 在呼叫 `GetCentroid()` 前，使用 `IsValid`（若可用）驗證多邊形的有效性。  
- **陷阱：** 忘記閉合環（第一點與最後一點必須相同）。  
  **提示：** 建構 `LinearRing` 時，務必將第一個點再次加入作為最後一個點。  
- **專業提示：** 處理大型資料集時，可使用 `Parallel.ForEach` 平行計算質心，以提升批次處理速度。  
- **專業提示：** 針對 `MultiPolygon`，直接在集合上呼叫 `GetCentroid()`，即可 **一次計算 MultiPolygon 的質心**。

## FAQ
### Q: Aspose.GIS for .NET 是否相容所有版本的 .NET Framework？
A: Aspose.GIS for .NET 相容於 .NET Framework 4.6 及以上版本，確保在多種環境下皆可使用。

### Q: 我可以取得 Aspose.GIS for .NET 的臨時授權嗎？
A: 可以，臨時授權可用於測試目的。請前往 [temporary license page](https://purchase.aspose.com/temporary-license/) 取得。

### Q: Aspose.GIS for .NET 是否同時適用於桌面與 Web 應用程式？
A: 絕對可以！Aspose.GIS for .NET 可無縫整合於桌面與 Web 應用，提供開發彈性。

### Q: Aspose.GIS for .NET 是否提供完整的文件說明？
A: 有的，完整文件可在 [documentation page](https://reference.aspose.com/gis/net/) 找到，內容涵蓋使用方式與功能說明。

### Q: 我要如何取得支援或與社群互動，針對 Aspose.GIS for .NET 提問？
A: 任何問題、支援需求或社群交流，都可以前往 Aspose.GIS 專屬論壇 [here](https://forum.aspose.com/c/gis/33)。

## 常見問答

**Q: 我可以計算 MultiPolygon 的質心嗎？**  
A: 可以。對每個單獨的多邊形或直接在 `MultiPolygon` 物件上呼叫 `GetCentroid()`，API 會回傳合併形狀的質心。

**Q: 質心計算會考慮地球曲率嗎？**  
A: 內建的 `GetCentroid()` 於幾何的座標空間（平面）上運作。若處理測地資料，請先將其投影至適當的平面座標系統，再計算質心。

**Q: 有沒有辦法一次取得 GeometryCollection 中所有要素的質心？**  
A: 你可以遍歷集合逐一計算，或使用 `GeometryFactory` 合併幾何後，再對合併結果呼叫 `GetCentroid()`。

**Q: 質心對於非常大的多邊形精度如何？**  
A: 精度取決於座標的精確度與投影方式。對於極大或複雜的多邊形，建議先簡化幾何以提升效能與精度。

**Q: 我可以把質心輸出為 GeoJSON 格式嗎？**  
A: 可以。取得 `IPoint` 後，可使用 Aspose.GIS 的 `GeoJsonWriter` 或任意 JSON 序列化工具將其序列化為 GeoJSON。

---

**最後更新：** 2026-02-10  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
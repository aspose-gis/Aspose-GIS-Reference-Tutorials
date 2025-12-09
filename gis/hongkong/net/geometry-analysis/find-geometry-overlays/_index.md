---
date: 2025-12-07
description: 學習如何在此空間疊加教學中使用 Aspose.GIS for .NET 執行疊加操作。掌握交集、聯集、差集及對稱差集。
linktitle: Find Geometry Overlays
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 執行疊加操作
url: /zh-hant/net/geometry-analysis/find-geometry-overlays/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS for .NET 執行疊加操作

## 介紹
疊加分析是任何 **空間疊加教學** 的核心技術——它讓您能夠結合、比較並從多個地理圖層中提取洞見。在本指南中，您將學習如何使用功能強大的 Aspose.GIS for .NET 函式庫執行 **疊加操作**，包括交集 (Intersection)、聯集 (Union)、差集 (Difference) 與對稱差集 (Symmetric Difference)。完成教學後，您即可將這些方法套用於土地利用規劃、環境影響評估、路徑最佳化等實務 GIS 問題。

## 快速答案
- **什麼是疊加操作？** 一種結合兩個幾何圖形以產生新圖形（交集、聯集等）的空間方法。  
- **哪個函式庫在 .NET 中處理疊加？** Aspose.GIS for .NET。  
- **實作大約需要多久？** 基本範例約 10‑15 分鐘即可完成。  
- **需要授權嗎？** 試用版免費；正式環境需購買商業授權。  
- **可以在 .NET Core / .NET 6+ 上執行嗎？** 可以——Aspose.GIS 支援所有現代 .NET 執行階段。

## 什麼是疊加操作？
疊加操作會取得兩個幾何形狀，並根據它們的空間關係計算出新的形狀。  
- **交集** 會回傳兩個形狀共同的區域。  
- **聯集** 會將兩個形狀合併成單一幾何圖形。  
- **差集** 會從其中一個形狀中減去另一個形狀。  
- **對稱差集** 會回傳屬於任一形狀但不屬於兩者同時的部分。

## 為什麼在疊加時使用 Aspose.GIS？
Aspose.GIS 提供乾淨、全受管理的 API，將低階數學抽象化，讓您專注於業務邏輯。它跨平台、能有效處理大型資料集，且可無縫整合其他 .NET 元件。

## 先決條件
- 可正常運作的 .NET 開發環境（Visual Studio、VS Code 或 .NET CLI）。  
- Aspose.GIS for .NET 函式庫 ─ 從[官方網站](https://releases.aspose.com/gis/net/)下載最新版本。  

### 匯入命名空間
在開始使用 Aspose.GIS for .NET 前，請先將必要的命名空間匯入專案。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 如何在 .NET 中執行疊加操作
以下提供逐步說明，示範如何建立兩個多邊形並套用每種疊加方法。

### 步驟 1：建立多邊形物件
首先，我們定義兩個部分重疊的簡單正方形多邊形，作為測試資料。

```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```

### 步驟 2：執行交集操作
**交集** 會給出兩個多邊形的重疊區域。

```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Polygon
```

### 步驟 3：列印交集點
使用輔助方法 (`PrintRing`) 來顯示結果多邊形的座標。

```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```

### 步驟 4：執行聯集操作
**聯集** 會將兩個多邊形合併成覆蓋任一多邊形之全部區域的單一形狀。

```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Polygon
```

### 步驟 5：列印聯集點
輸出合併後幾何圖形的座標。

```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```

### 步驟 6：執行差集操作
**差集** 會從 `polygon1` 中減去 `polygon2`，僅保留 `polygon1` 未與 `polygon2` 重疊的部分。

```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Polygon
```

### 步驟 7：列印差集點
顯示減除後剩餘的頂點座標。

```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```

### 步驟 8：執行對稱差集操作
**對稱差集** 會回傳屬於任一多邊形但不屬於兩者同時的區域，結果為 `MultiPolygon`。

```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // MultiPolygon
```

### 步驟 9：列印對稱差集多邊形
遍歷 `MultiPolygon` 中的每個多邊形，並印出其座標點。

```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```

## 常見問題與解決方案
| 問題 | 為何會發生 | 解決方式 |
|------|------------|----------|
| `Intersection` 回傳 `null` | 多邊形實際上未重疊。 | 檢查座標或在呼叫 `Intersection` 前使用 `Intersects` 進行驗證。 |
| `SymDifference` 產生意外的 `MultiPolygon` | 對稱差集可能產生不相連的組件。 | 如範例所示，將結果轉型為 `IMultiPolygon` 後遍歷。 |
| 大型資料集執行緩慢 | 每次操作都會重新計算幾何圖形。 | 重複使用中間結果，或在疊加前使用 `Simplify()` 簡化幾何圖形。 |

## 常見問答

**Q: 我可以在商業專案中使用 Aspose.GIS for .NET 嗎？**  
A: 可以，持有有效授權後，Aspose.GIS for .NET 可用於商業與非商業專案。

**Q: 有提供 Aspose.GIS for .NET 的試用版嗎？**  
A: 有，您可從[此處](https://releases.aspose.com/)下載免費試用版。

**Q: 我要如何取得 Aspose.GIS for .NET 的支援？**  
A: 可於 Aspose.GIS 社群論壇[此處](https://forum.aspose.com/c/gis/33)取得支援。

**Q: 有臨時授權可供測試嗎？**  
A: 有，臨時授權可用於測試與評估，請至[此處](https://purchase.aspose.com/temporary-license/)申請。

**Q: 可以直接購買 Aspose.GIS for .NET 嗎？**  
A: 可以，請前往[此處](https://purchase.aspose.com/buy)購買。

---

**最後更新：** 2025-12-07  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
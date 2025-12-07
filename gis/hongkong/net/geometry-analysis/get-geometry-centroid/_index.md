---
date: 2025-12-07
description: 了解如何使用 Aspose.GIS for .NET 取得幾何圖形的中心點，並在 .NET 應用程式中計算多邊形的中心點以進行空間分析。
language: zh-hant
linktitle: Get Geometry Centroid
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 獲取幾何圖形的重心
url: /net/geometry-analysis/get-geometry-centroid/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS for .NET 獲取幾何圖形的質心

## 介紹
如果你正在從事 **c# spatial analysis**，且需要了解 **how to get centroid** 的任何形狀，你已經來對地方了。在本教學中，我們將示範如何使用 Aspose.GIS for .NET 來 **calculate polygon centroid**、取得該質心，並看看這小小的幾何圖形如何解鎖強大的 **integrate spatial analysis** 場景，例如標籤放置、分群與距離計算。

## 快速解答
- **主要方法是什麼？** `GetCentroid()` 於 `IGeometry` 物件上。  
- **哪個函式庫提供此功能？** Aspose.GIS for .NET。  
- **程式碼行數多少？** 總共少於 15 行（不含 using 陳述式）。  
- **需要授權嗎？** 測試時可使用臨時授權；正式環境需購買完整授權。  
- **能在 .NET 6 以上執行嗎？** 能——API 完全相容於 .NET Core 以及 .NET 5/6。

## 什麼是質心以及為何重要？
質心是形狀的幾何中心——可以想像成「平衡點」。對於多邊形而言，質心常用於放置標籤、計算平均位置，或作為空間查詢的參考點。快速掌握 **how to get centroid**，即可在不自行編寫複雜數學的情況下整合空間分析功能。

## 前置條件
在開始之前，請確保你具備以下條件：

### 1. 安裝 Aspose.GIS for .NET
從 [Aspose.GIS for .NET website](https://releases.aspose.com/gis/net/) 下載函式庫。依照安裝說明將 NuGet 套件加入你的專案。

### 2. 熟悉 C# 程式設計
你應該能寫出基本的 C# 程式碼。若是新手，建議先快速複習變數、類別與主控台輸出。

### 3. 基本的地理概念認識
雖非必須，但了解點、線、面之間的差異會讓你更容易跟上範例。

## 匯入命名空間
我們需要將 Aspose.GIS 類別引入作用域。請在 C# 檔案的最上方加入以下 `using` 指令：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

這些命名空間讓你可以存取幾何類型、`GetCentroid()` 方法，以及標準的 .NET 工具。

## 如何取得幾何圖形的質心
以下是一個逐步指南，說明如何 **create polygon geometry**、計算其質心，並顯示結果。

### 步驟 1：定義多邊形
首先，我們 **create polygon geometry**，透過指定頂點來建立。此範例建立一個簡單且不自交的多邊形：

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

### 步驟 2：取得多邊形質心
多邊形定義完成後，呼叫 `GetCentroid()` 以 **retrieve polygon centroid**：

```csharp
IPoint centroid = polygon.GetCentroid();
```

### 步驟 3：顯示質心座標
最後，輸出質心的 X 與 Y 座標。格式字串會將數值四捨五入至小數點後兩位：

```csharp
Console.WriteLine("{0:F} {1:F}", centroid.X, centroid.Y); // Output: 3.33 2.58
```

執行程式後，會在主控台印出質心座標，證實幾何圖形已正確處理。

## 常見陷阱與專業提示
- **Pitfall:** 提供自交的多邊形可能會產生意外的質心。  
  **Tip:** 在呼叫 `GetCentroid()` 前，先驗證多邊形（例如使用 `IsValid`，若有提供）。
- **Pitfall:** 忘記閉合環（第一個點與最後一個點必須相同）。  
  **Tip:** 建構 `LinearRing` 時，務必將第一個點再次加入為最後一個點。
- **Pro Tip:** 面對大型資料集時，可使用 `Parallel.ForEach` 平行計算質心，以加速批次處理。

## 常見問答

### Q: Aspose.GIS for .NET 是否相容於所有版本的 .NET Framework？
Aspose.GIS for .NET 相容於 .NET Framework 4.6 及以上版本，確保在各種版本間都有廣泛的相容性。

### Q: 我可以取得 Aspose.GIS for .NET 的臨時授權嗎？
可以，臨時授權可用於測試目的。你可以從 [temporary license page](https://purchase.aspose.com/temporary-license/) 取得。

### Q: Aspose.GIS for .NET 適用於桌面與 Web 應用程式嗎？
絕對適用！Aspose.GIS for .NET 可無縫整合於桌面與 Web 應用程式，提供開發彈性。

### Q: Aspose.GIS for .NET 有提供完整的文件說明嗎？
有，完整的文件說明可在 [documentation page](https://reference.aspose.com/gis/net/) 上取得，提供詳細的使用說明與功能說明。

### Q: 我要如何取得支援或與社群互動，針對 Aspose.GIS for .NET 提問？
任何問題、支援需求或社群交流，都可以前往 Aspose.GIS 專屬論壇 [here](https://forum.aspose.com/c/gis/33)。

## 常見問題

**Q: 我可以計算 MultiPolygon 的質心嗎？**  
A: 可以。對每個單獨的多邊形或對 `MultiPolygon` 物件呼叫 `GetCentroid()`，API 會回傳合併形狀的質心。

**Q: 質心計算會考慮地球曲率嗎？**  
A: 內建的 `GetCentroid()` 於幾何的座標空間（平面）中運作。若處理測地資料，請先將其重新投影至適當的平面座標參考系再計算質心。

**Q: 有沒有一次取得 GeometryCollection 中所有圖形質心的方法？**  
A: 你可以遍歷集合分別計算質心，或使用 `GeometryFactory` 合併圖形後，再對合併結果呼叫 `GetCentroid()`。

**Q: 質心對於非常大的多邊形準確度如何？**  
A: 準確度取決於座標精度與投影方式。對於極大或極複雜的多邊形，建議先簡化幾何以提升效能與精度。

**Q: 我可以將質心輸出為 GeoJSON 格式嗎？**  
A: 可以。取得 `IPoint` 後，可使用 Aspose.GIS 的 `GeoJsonWriter` 或任何你喜好的 JSON 序列化工具將其序列化為 GeoJSON。

**最後更新：** 2025-12-07  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
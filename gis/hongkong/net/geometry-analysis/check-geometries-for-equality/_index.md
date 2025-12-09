---
date: 2025-12-03
description: 了解如何使用 Aspose.GIS for .NET 比較幾何圖形，並在您的 .NET 應用程式中檢查幾何相等性。
linktitle: How to Compare Geometries for Equality
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 比較幾何圖形是否相等
url: /zh-hant/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS for .NET 比較幾何圖形是否相等

## 介紹
在本教學中，你將學會 **如何比較幾何圖形**，使用 Aspose.GIS for .NET。無論你是在建置地圖服務、執行空間分析，或僅需驗證兩個圖形是否代表相同位置，了解如何比較幾何圖形都是必備技能。我們將示範一個完整的端對端範例，教你如何在幾行 C# 程式碼內建立、修改並測試幾何相等性。

## 快速回答
- **「比較幾何圖形」是什麼意思？** 它會檢查兩個幾何物件是否佔據相同的空間，無論它們是如何建構的。  
- **使用哪個方法？** Aspose.GIS API 中的 `SpatiallyEquals`。  
- **開發需要授權嗎？** 測試可使用免費試用版；正式上線需購買商業授權。  
- **支援的 .NET 版本？** .NET Framework 4.5 以上、 .NET Core 3.1 以上、 .NET 5/6 以上。  
- **一般實作時間？** 基本相等性檢查約 5‑10 分鐘即可完成。

## 什麼是幾何相等性？
幾何相等性（亦稱空間相等）表示兩個幾何圖形在地球表面上代表完全相同的一組點。兩個圖形的建構方式可能不同——例如 MultiLineString 與單一 LineString——但仍可視為空間相等。

## 為什麼使用 Aspose.GIS 來比較幾何圖形？
Aspose.GIS 提供強大且高效能的幾何引擎，具備以下優勢：
- 支援多種向量格式（WKT、GeoJSON、Shapefile 等）。  
- 提供具備精度感知的比較方法，如 `SpatiallyEquals`。  
- 可離線使用，無需外部服務，適合安全或隔離的環境。

## 前置條件
在開始之前，請確保已具備以下項目：

- **已安裝 .NET Framework 或 .NET Core** – 任一 Aspose.GIS 支援的版本。  
- **Aspose.GIS for .NET 套件** – 可從 [Aspose.GIS 下載頁面](https://releases.aspose.com/gis/net/) 取得。  
- **開發 IDE** – Visual Studio、Rider，或安裝 C# 擴充功能的 VS Code。

## 匯入命名空間
在 .NET 專案中加入必要的 `using` 陳述式，讓編譯器知道 GIS 類別的所在位置：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 步驟 1：定義幾何圖形
首先，我們建立兩個將要比較的幾何圖形。此範例中 `geometry1` 為由兩段線段組成的 `MultiLineString`，而 `geometry2` 為一條覆蓋相同起點與終點的單一 `LineString`。

```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```

## 步驟 2：檢查幾何圖形是否相等
接著使用 `SpatiallyEquals` 方法，判斷兩個圖形在 GIS 引擎中是否被視為相等。

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

主控台會輸出 `True`，因為雖然建構方式不同，兩個幾何圖形皆覆蓋相同的線段 (0,0) 到 (2,2)。

## 步驟 3：修改其中一個幾何圖形
為說明變更如何影響相等性，我們在 `geometry2` 中加入一個額外的點。

```csharp
geometry2.AddPoint(3, 3);
```

## 步驟 4：修改後再次檢查相等性
變更後，兩個幾何圖形已不再相同，`SpatiallyEquals` 會回傳 `False`。

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

輸出 `False` 證實額外的點破壞了空間相等性。

## 常見問題與技巧
- **精度問題** – 若座標精度極高，建議先四捨五入或使用 `SpatiallyEquals` 的容差參數。  
- **不同 SRID** – 比較前務必確保兩個幾何圖形使用相同的空間參考系統識別碼 (SRID)。  
- **效能** – 大量集合時，可使用 LINQ 進行批次比較，以降低開銷。

## 常見問答
**Q: 可以在其他 .NET 框架上使用 Aspose.GIS for .NET 嗎？**  
A: 可以，Aspose.GIS 支援 .NET Framework、.NET Core 與 .NET Standard 專案。

**Q: 有免費試用版嗎？**  
A: 當然有。可從 [Aspose.GIS 釋出頁面](https://releases.aspose.com/) 下載試用版。

**Q: 完整的 API 文件在哪裡可以找到？**  
A: 詳細文件位於 [Aspose.GIS 文件頁面](https://reference.aspose.com/gis/net/)。

**Q: 若遇到問題該如何取得協助？**  
A: 可在 Aspose.GIS 社群論壇 [此處](https://forum.aspose.com/c/gis/33) 發問。

**Q: 可以購買臨時授權來評估嗎？**  
A: 可以，臨時授權可於 [購買頁面](https://purchase.aspose.com/temporary-license/) 取得。

## 結論
現在你已掌握 **如何使用 Aspose.GIS for .NET 比較幾何圖形**，從建立物件、檢查空間相等性到處理修改。此功能是進階空間分析（如拓撲驗證、重複檢測與基於幾何的篩選）的基礎。

---

**最後更新：** 2025-12-03  
**測試環境：** Aspose.GIS for .NET 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
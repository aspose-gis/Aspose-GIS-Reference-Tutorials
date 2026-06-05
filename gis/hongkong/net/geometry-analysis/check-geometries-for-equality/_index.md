---
date: 2026-06-05
description: 了解如何在 .NET 中使用 Aspose.GIS 比較幾何圖形、偵測重複的幾何圖形，並在應用程式中檢查幾何相等性。
keywords:
- how to compare geometries
- detect duplicate geometries
- Aspose.GIS geometry equality
linktitle: 如何比較幾何圖形的相等性
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to compare geometries in .NET using Aspose.GIS, detect duplicate
    geometries, and check geometry equality in your applications.
  headline: How to Compare Geometries for Equality using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard
      projects.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. Download a trial from the [Aspose.GIS releases page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Detailed docs are on the [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).
    question: Where can I find the full API documentation?
  - answer: Post your question on the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How do I get help if I run into an issue?
  - answer: Yes, temporary licenses are available on the [purchase page](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 比較幾何圖形的相等性
url: /zh-hant/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS for .NET 比較幾何圖形相等性

## 介紹
在本教學中，您將學習 **如何比較幾何圖形**，這在需要偵測重複幾何圖形、驗證空間資料或強制拓撲規則時相當重要。無論您是構建地圖服務、執行批次空間分析，或僅僅驗證兩個形狀是否佔據相同位置，本指南都會帶您一步步完成建立、修改與測試幾何相等性的乾淨、可投入生產的 C# 程式碼。

## 快速解答
- **「比較幾何圖形」是什麼意思？** 它會檢查兩個幾何物件是否佔據相同的空間，無論它們是如何建構的。  
- **使用哪個方法？** 來自 Aspose.GIS API 的 `SpatiallyEquals`。  
- **開發時需要授權嗎？** 測試可使用免費試用版；正式環境需購買商業授權。  
- **支援的 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **典型實作時間？** 基本相等性檢查約 5‑10 分鐘即可完成。

## 什麼是幾何相等性？
幾何相等性（亦稱空間相等性）指的是兩個幾何圖形在地表上代表完全相同的一組點。即使一個幾何是以 `MultiLineString` 建構，另一個是單一的 `LineString`，只要每個座標在容許的容差內相符，就視為相等。此定義讓開發者能可靠地在異構資料來源間偵測重複的幾何圖形。

## 為何使用 Aspose.GIS 來比較幾何圖形？
Aspose.GIS 提供高效能、離線的幾何引擎，無需依賴外部服務。它 **支援 30 多種向量與光柵格式**（包括 WKT、GeoJSON、Shapefile、KML、GML），且能在記憶體使用低於 50 MB 的情況下處理 **數十萬個頂點** 的檔案。庫中的 `SpatiallyEquals` 方法具備精度感知，即使在浮點座標下也能產生確定性的結果。

### 為何這對開發人員很重要
當您需要在批次處理、即時驗證管線或 GIS 資料遷移中 **偵測重複幾何圖形** 時，成熟的函式庫能消除猜測，保證在不同資料供應商之間得到一致的結果。

## 前置條件
在開始之前，請確保您具備以下條件：

- **已安裝 .NET Framework 或 .NET Core** – 任一 Aspose.GIS 支援的版本。  
- **Aspose.GIS for .NET 套件** – 從 [Aspose.GIS 下載頁面](https://releases.aspose.com/gis/net/) 取得。  
- **開發 IDE** – Visual Studio、Rider，或具 C# 擴充功能的 VS Code。

## 匯入命名空間
在您的 .NET 專案中，加入必要的 `using` 陳述式，讓編譯器知道 GIS 類別的所在位置：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 步驟 1：定義幾何圖形
`MultiLineString` 代表多條線段的集合，而 `LineString` 定義單一連續線。兩者皆繼承自基礎的 `Geometry` 類型。

首先，我們建立兩個將要比較的幾何圖形。此範例中，`geometry1` 為由兩段線段組成的 `MultiLineString`，而 `geometry2` 為跨越相同起點與終點的單一 `LineString`。

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
`SpatiallyEquals` 會評估兩個幾何圖形是否佔據相同的點集合，亦可接受容差值以因應浮點不精確性。

現在使用 `SpatiallyEquals` 方法，看看 GIS 引擎是否認為這兩個形狀相等。

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

控制台會印出 `True`，因為儘管建構方式不同，兩個幾何圖形皆覆蓋了從 (0,0) 到 (2,2) 的相同線段。

## 步驟 3：修改其中一個幾何圖形
為說明變更如何影響相等性，我們在 `geometry2` 中加入一個額外的點。

```csharp
geometry2.AddPoint(3, 3);
```

## 步驟 4：修改後重新檢查相等性
經過修改後，兩個幾何圖形已不再相同，`SpatiallyEquals` 因此回傳 `False`。

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

輸出 `False` 證實了額外的點破壞了空間相等性。

## 如何偵測重複的幾何圖形？
載入每個幾何圖形，使用適當的容差呼叫 `SpatiallyEquals`，將回傳 `True` 的項目過濾掉。此模式搭配 LINQ 可輕鬆在大型集合中找出重複形狀，亦可結合 `GroupBy` 進行聚合，降低儲存成本。

## 常見問題與技巧
- **精度問題** – 若處理極高精度的座標，請考慮四捨五入或使用 `SpatiallyEquals` 的容差重載。  
- **不同 SRID** – 比較前務必確保兩個幾何圖形使用相同的空間參考系統識別碼 (SRID)。  
- **效能** – 對於大型集合，使用 LINQ 或平行迴圈進行批次比較，可大幅降低運算開銷。

## 常見問答
**Q: 可以在其他 .NET 框架下使用 Aspose.GIS for .NET 嗎？**  
A: 可以，Aspose.GIS 支援 .NET Framework、.NET Core 與 .NET Standard 專案。

**Q: 有免費試用版嗎？**  
A: 當然有。請從 [Aspose.GIS 釋出頁面](https://releases.aspose.com/) 下載試用版。

**Q: 完整的 API 文件在哪裡可以找到？**  
A: 詳細文件位於 [Aspose.GIS 文件頁面](https://reference.aspose.com/gis/net/)。

**Q: 若遇到問題該如何取得協助？**  
A: 可在 Aspose.GIS 社群論壇 [此處](https://forum.aspose.com/c/gis/33) 發問。

**Q: 可以購買臨時授權來評估嗎？**  
A: 可以，臨時授權可於 [購買頁面](https://purchase.aspose.com/temporary-license/) 取得。

## 結論
現在您已掌握 **如何使用 Aspose.GIS for .NET 比較幾何圖形**，從建立物件、檢查空間相等性到處理修改。此能力是進階空間分析（如拓撲驗證、重複偵測與基於幾何的篩選）的基礎。

---

**最後更新：** 2026-06-05  
**測試環境：** Aspose.GIS for .NET 24.11  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [建立 Polygon Geometry C# 並使用 Aspose.GIS for .NET 檢查交集](/gis/net/geometry-analysis/check-geometries-intersection/)
- [使用 Aspose.GIS for .NET 執行幾何圖形的空間重疊分析](/gis/net/geometry-analysis/check-geometries-overlap/)
- [網路路由檢查：使用 Aspose.GIS 判斷相切幾何圖形](/gis/net/geometry-analysis/check-geometries-touching/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
date: 2026-08-03
description: 了解如何使用 Aspose.GIS for .NET 建立 linestring c#、向 linestring 新增點，並使用 covers
  方法執行點在線上檢查。
keywords:
- create linestring c#
- point on line check
- add points to linestring
- use covers method
lastmod: 2026-08-03
linktitle: 建立 linestring c# – 檢查幾何是否覆蓋另一個
og_description: 使用 Aspose.GIS covers 方法建立 linestring c# 並驗證點在線上。了解 .NET 應用程式的精確幾何檢查。(150‑160
  字元)
og_image_alt: Developer guide showing linestring creation and covers check in C# with
  Aspose.GIS
og_title: 建立 linestring c# – 檢查幾何是否覆蓋另一個 (50‑60 字元)
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  headline: Create linestring c# – Check geometry covers another
  type: TechArticle
- description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  name: Create linestring c# – Check geometry covers another
  steps:
  - name: create a linestring object
    text: The `LineString` class represents a sequence of points connected by straight
      line segments in a two‑dimensional plane. Here, we instantiate a new `LineString`
      object, which represents a sequence of connected line segments in a two‑dimensional
      space.
  - name: add points to linestring
    text: '`AddPoint` appends a coordinate pair to the end of the `LineString` collection,
      preserving the order of insertion. We **add points to linestring** using the
      `AddPoint` method. In this example, we add two points: (0, 0) and (1, 1), forming
      a simple diagonal line segment.'
  - name: create a point object
    text: The `Point` class models a single location in a two‑dimensional coordinate
      system. Instantiate a `Point` object representing a single point in a two‑dimensional
      space. Here, we create a point at coordinates (0, 0).
  - name: perform a point on line check – does the line cover the point?
    text: '`Covers` determines whether the first geometry completely contains the
      second geometry, returning true only when every point of the second geometry
      lies inside the first. Use the `Covers` method to check if the line covers the
      point. In this case, it returns `True` because the point (0, 0) lies exac'
  - name: verify the reverse relationship – is the point covered by the line?
    text: '`CoveredBy` is the inverse of `Covers`; it returns true when the invoking
      geometry is entirely inside the target geometry. Similarly, use the `CoveredBy`
      method to check if the point is covered by the line. Since the point (0, 0)
      lies on the line, it also returns `True`.'
  type: HowTo
- questions:
  - answer: Yes, you can use Aspose.GIS for .NET in both commercial and non‑commercial
      projects after obtaining the appropriate license.
    question: Can I use Aspose.GIS for .NET in my commercial projects?
  - answer: Yes, Aspose.GIS for .NET is compatible with both .NET Framework and .NET
      Core environments.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Yes, Aspose.GIS for .NET supports a wide range of GIS formats including
      Shapefile, GeoJSON, KML, and more.
    question: Does Aspose.GIS for .NET support various GIS formats?
  - answer: Aspose.GIS for .NET is a proprietary library developed by Aspose, so external
      contributions are not accepted. However, you can provide feedback and suggestions
      to improve the library.
    question: Can I contribute to the development of Aspose.GIS for .NET?
  - answer: Updates for Aspose.GIS for .NET are released regularly to introduce new
      features, enhancements, and bug fixes. Check the [website](https://releases.aspose.com/gis/net/)
      for the latest releases.
    question: How often are updates released for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create linestring
- Aspose.GIS
- C# geometry analysis
title: 建立 linestring c# – 檢查幾何是否覆蓋另一個
url: /zh-hant/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 檢查幾何圖形是否覆蓋另一個

## 簡介
在本教學中，您將學習如何使用 Aspose.GIS for .NET **建立 linestring c#**、向 linestring 添加點，並使用 `Covers` 與 `CoveredBy` 方法執行可靠的 **點在線上檢查**。無論您是在構建地圖工具、執行空間分析，或僅需驗證幾何關係，掌握這些操作都能為您的應用程式提供所需的精確度。

## 快速解答
- **「create linestring c#」是什麼意思？** 它指的是實例化一個 `LineString` 幾何物件並以座標點填充它。  
- **哪個方法可檢查點是否位於線上？** 使用 `LineString` 的 `Covers` 方法或 `Point` 的 `CoveredBy` 方法。  
- **執行範例是否需要授權？** 臨時授權可用於評估；正式環境需要完整授權。  
- **這能在 .NET Core 上使用嗎？** 可以，Aspose.GIS 支援 .NET Framework 與 .NET Core。  
- **我可以向 linestring 添加多少點？** 沒有硬性限制，您可以根據空間分析的需要添加任意數量的點。

## 什麼是 create linestring c#？
`LineString` 是由一系列依序連接的點組成、以直線段相連的幾何形狀。在 C# 中，您可透過實例化 `Aspose.Gis.Geometries` 命名空間下的 `LineString` 類別，然後使用 `AddPoint` 方法 **add points to linestring**。此物件是任何線性空間分析的基礎，例如路徑繪製或網路追蹤。

## 為什麼使用 Aspose.GIS 進行點在線上檢查？
`Covers` 是一種空間謂詞方法，當第一個幾何圖形完全包含第二個幾何圖形時回傳 true。  
Aspose.GIS 提供確定性且高精度的空間謂詞實作。它支援超過 50 種輸入與輸出 GIS 格式，能在不將整個資料集載入記憶體的情況下處理數百公里的線路網路，且可在 .NET Framework、.NET Core 以及 .NET 5/6+ 上執行。使用其 `Covers` 方法可確保考慮浮點數四捨五入誤差，於高需求的企業情境中仍能提供可靠的點在線上結果。

## 先決條件
在深入使用 Aspose.GIS for .NET 之前，請確保已完成以下先決條件：

### 1. 安裝 Visual Studio
確保您的系統已安裝 Visual Studio。Aspose.GIS for .NET 可無縫整合至 Visual Studio，提供順暢的開發體驗。

### 2. 取得 Aspose.GIS for .NET
從[網站](https://releases.aspose.com/gis/net/)下載 Aspose.GIS for .NET 程式庫。您可以直接下載程式庫，或使用 NuGet 等套件管理工具將其安裝至專案中。

### 3. 熟悉 .NET Framework
具備 .NET Framework 與 C# 程式語言的基本知識是有效使用 Aspose.GIS for .NET 的必要條件。

### 4. 取得文件與支援
請參考[文件](https://reference.aspose.com/gis/net/)以取得 Aspose.GIS API 與功能的詳細資訊。如遇問題或有疑問，請利用[Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33)尋求協助。

### 5. 可選：臨時授權
若您正在探索 Aspose.GIS for .NET，可從[臨時授權頁面](https://purchase.aspose.com/temporary-license/)取得臨時授權，以評估程式庫功能。

## 匯入命名空間
在專案中使用 Aspose.GIS for .NET 前，您需要匯入必要的命名空間：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

現在，讓我們將提供的範例分解為多個步驟，以了解如何使用 Aspose.GIS for .NET **檢查一個幾何圖形是否覆蓋另一個**。

## 如何建立 linestring c# – 步驟指南
載入您的專案，匯入所需的命名空間，然後依照以下五個簡潔步驟操作。只需幾行程式碼，即可取得 `LineString` 物件、`Point` 物件，以及兩個布林檢查，告訴您線是否覆蓋點以及點是否被線覆蓋。

### 步驟 1：建立 linestring 物件
`LineString` 類別代表在二維平面上由直線段連接的點序列。  
```csharp
var line = new LineString();
```
此處，我們實例化一個新的 `LineString` 物件，表示二維空間中連接的線段序列。

### 步驟 2：向 linestring 添加點
`AddPoint` 將座標對追加至 `LineString` 集合的末端，保留插入順序。  
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
我們使用 `AddPoint` 方法 **add points to linestring**。在此範例中，我們加入兩個點：(0, 0) 與 (1, 1)，形成簡單的對角線段。

### 步驟 3：建立 point 物件
`Point` 類別模型二維座標系統中的單一位置。  
```csharp
var point = new Point(0, 0);
```
實例化一個 `Point` 物件，代表二維空間中的單一點。此處，我們在座標 (0, 0) 建立一個點。

### 步驟 4：執行點在線上檢查 – 線是否覆蓋點？
`Covers` 判斷第一個幾何圖形是否完全包含第二個幾何圖形，僅在第二個幾何圖形的所有點皆位於第一個內部時回傳 true。  
```csharp
Console.WriteLine(line.Covers(point));    // True
```
使用 `Covers` 方法檢查線是否覆蓋點。在此例中，因點 (0, 0) 正好位於線上，故回傳 `True`。

### 步驟 5：驗證相反關係 – 點是否被線覆蓋？
`CoveredBy` 為 `Covers` 的相反；當呼叫的幾何圖形完全位於目標幾何圖形內部時回傳 true。  
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
同樣地，使用 `CoveredBy` 方法檢查點是否被線覆蓋。因點 (0, 0) 位於線上，亦回傳 `True`。

## 常見問題與解決方案
| 問題 | 為何會發生 | 解決方法 |
|------|------------|----------|
| `line.Covers(point)` 回傳 `False`，即使點看起來在直線上 | 由於浮點精度，點的座標並不完全相同。 | 在座標上使用 `Math.Round`，或以容差檢查 `line.Distance(point) < epsilon`。 |
| 缺少 `using Aspose.Gis.Geometries;` | 未匯入命名空間，導致編譯錯誤。 | 確認已加入匯入語句（請參閱 **匯入命名空間** 部分）。 |
| 執行時授權例外 | 生產環境未載入有效授權。 | 使用 `License license = new License(); license.SetLicense("Aspose.GIS.lic");` 載入臨時或完整授權。 |

## 常見問題

**Q: 我可以在商業專案中使用 Aspose.GIS for .NET 嗎？**  
A: 可以，取得相應授權後，您可在商業與非商業專案中使用 Aspose.GIS for .NET。

**Q: Aspose.GIS for .NET 是否相容於 .NET Core？**  
A: 是，Aspose.GIS for .NET 相容於 .NET Framework 與 .NET Core 環境。

**Q: Aspose.GIS for .NET 支援多種 GIS 格式嗎？**  
A: 支援，Aspose.GIS for .NET 支援包括 Shapefile、GeoJSON、KML 等多種 GIS 格式。

**Q: 我可以為 Aspose.GIS for .NET 的開發貢獻嗎？**  
A: Aspose.GIS for .NET 為 Aspose 所開發的專有程式庫，未接受外部貢獻。但您可提供回饋與建議以改進此程式庫。

**Q: Aspose.GIS for .NET 的更新頻率如何？**  
A: Aspose.GIS for .NET 會定期發布更新，加入新功能、改進與錯誤修正。請查看[網站](https://releases.aspose.com/gis/net/)以取得最新版本。

## 結論
透過上述步驟，您現在已了解如何 **create linestring c#**、**add points to linestring**，以及使用 `Covers` 與 `CoveredBy` 方法執行可靠的 **point on line check**。此功能提升了軟體的空間分析能力，並為更進階的 GIS 操作鋪路，例如路徑驗證、網路拓撲檢查與鄰近查詢。

---

**最後更新：** 2026-08-03  
**測試環境：** Aspose.GIS for .NET（最新版本）  
**作者：** Aspose

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [學習如何使用 Aspose.GIS for .NET 建立 LineString 幾何圖形](/gis/net/geometry-creation/create-linestring-geometry/)
- [如何向 LineString 添加點並將幾何圖形轉換為可編輯格式（使用 Aspose.GIS）](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [point inside polygon c# – 檢查幾何圖形是否包含另一個](/gis/net/geometry-analysis/check-geometry-contains-another/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
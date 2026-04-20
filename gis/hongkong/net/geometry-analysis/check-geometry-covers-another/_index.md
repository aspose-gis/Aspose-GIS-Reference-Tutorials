---
date: 2026-02-08
description: 學習如何使用 Aspose.GIS for .NET 在 C# 中建立線串、向線串加入點，並使用 covers 方法執行點在線上檢查。
linktitle: Create LineString C# – Check Geometry Covers Another
second_title: Aspose.GIS .NET API
title: 建立 LineString C# – 檢查幾何圖形是否覆蓋另一個
url: /zh-hant/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 檢查幾何圖形覆蓋另一個

## 介紹
在本教學中，您將學習如何使用 Aspose.GIS for .NET **建立 linestring c#**、將點加入 linestring，並使用 `Covers` 與 `CoveredBy` 方法執行可靠的 **點在線上檢查**。無論您是在開發地圖工具、執行空間分析，或僅需驗證幾何關係，掌握這些操作都能為您的應用程式提供所需的精確度。

## 快速解答
- **「create linestring c#」是什麼意思？** 代表實例化 `LineString` 幾何物件並以座標點填充它。  
- **哪個方法可檢查點是否位於線上？** 在 `LineString` 上使用 `Covers` 方法，或在 `Point` 上使用 `CoveredBy` 方法。  
- **執行範例需要授權嗎？** 評估時可使用臨時授權；正式上線則需正式授權。  
- **可以在 .NET Core 上使用嗎？** 可以，Aspose.GIS 同時支援 .NET Framework 與 .NET Core。  
- **可以在 linestring 中加入多少個點？** 沒有硬性上限，您可以依空間分析需求加入任意數量的點。

## 什麼是 **create linestring c#**？
`LineString` 是由有序點列表組成、以直線段相連的幾何形狀。在 C# 中，您可透過 `Aspose.Gis.Geometries` 命名空間的 `LineString` 類別建立，並使用 `AddPoint` 方法 **將點加入 linestring**。

## 為什麼使用 Aspose.GIS 進行點在線上檢查？
- **精確度** – 正確處理浮點運算與空間謂詞，提供 **精確的點在線上** 結果。  
- **跨平台** – 支援 .NET Framework、.NET Core 以及 .NET 5/6+。  
- **完整 API** – 提供完整的空間關係方法（`Covers`、`CoveredBy`、`Intersects` 等）。  

## 前置條件
在開始使用 Aspose.GIS for .NET 之前，請確保已完成以下設定：

### 1. 安裝 Visual Studio
確保您的系統已安裝 Visual Studio。Aspose.GIS for .NET 可無縫整合至 Visual Studio，提供順暢的開發體驗。

### 2. 取得 Aspose.GIS for .NET
從[官方網站](https://releases.aspose.com/gis/net/)下載 Aspose.GIS for .NET 程式庫。您可以直接下載程式庫，或使用 NuGet 等套件管理工具將其安裝至專案中。

### 3. 熟悉 .NET Framework
具備 .NET Framework 與 C# 程式語言的基礎知識，才能有效運用 Aspose.GIS for .NET。

### 4. 取得文件與支援
參考[文件說明](https://reference.aspose.com/gis/net/)取得 Aspose.GIS API 與功能的詳細資訊。如遇問題或有疑問，可前往[Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33)尋求協助。

### 5. 可選：臨時授權
若您正在探索 Aspose.GIS for .NET，可從[此處](https://purchase.aspose.com/temporary-license/)取得臨時授權，以評估程式庫功能。

## 匯入命名空間
在專案中使用 Aspose.GIS for .NET 前，請先匯入必要的命名空間：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

現在，讓我們將範例拆解為多個步驟，了解如何使用 Aspose.GIS for .NET **檢查一個幾何圖形是否覆蓋另一個**。

## 如何建立 linestring c# – 步驟指南

### 步驟 1：建立 LineString 物件
```csharp
var line = new LineString();
```
此處，我們實例化一個新的 `LineString` 物件，代表二維空間中一系列相連的線段。

### 步驟 2：**將點加入 LineString**
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
我們使用 `AddPoint` 方法 **將點加入 linestring**。本例中加入兩個點：(0, 0) 與 (1, 1)，形成一條簡單的對角線段。

### 步驟 3：建立 Point 物件
```csharp
var point = new Point(0, 0);
```
實例化一個 `Point` 物件，代表二維空間中的單一座標點。本例在 (0, 0) 位置建立點。

### 步驟 4：執行 **點在線上檢查** – 線段是否覆蓋該點？
```csharp
Console.WriteLine(line.Covers(point));    // True
```
使用 `Covers` 方法檢查線段是否覆蓋該點。此例會回傳 `True`，因為點 (0, 0) 正好落在線段上。

### 步驟 5：驗證相反關係 – 點是否被線段覆蓋？
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
同樣使用 `CoveredBy` 方法檢查點是否被線段覆蓋。由於點 (0, 0) 位於線段上，結果亦為 `True`。

## 常見問題與解決方案
| 問題 | 為何發生 | 解決方案 |
|------|----------|----------|
| `line.Covers(point)` 回傳 `False`，即使點看起來在直線上 | 由於浮點精度，點的座標可能不完全相同。 | 使用 `Math.Round` 處理座標，或以容差檢查 `line.Distance(point) < epsilon`。 |
| 缺少 `using Aspose.Gis.Geometries;` | 未匯入命名空間，導致編譯錯誤。 | 確認已加入匯入語句（參見 **匯入命名空間** 部分）。 |
| 執行時出現授權例外 | 未載入有效授權。 | 使用 `License license = new License(); license.SetLicense("Aspose.GIS.lic");` 載入臨時或正式授權。 |

## 常見問答

**問：我可以在商業專案中使用 Aspose.GIS for .NET 嗎？**  
答：可以，取得相應授權後，您可在商業與非商業專案中使用 Aspose.GIS for .NET。

**問：Aspose.GIS for .NET 是否相容 .NET Core？**  
答：是的，Aspose.GIS for .NET 同時相容 .NET Framework 與 .NET Core 環境。

**問：Aspose.GIS for .NET 支援哪些 GIS 格式？**  
答：支援多種 GIS 格式，包括 Shapefile、GeoJSON、KML 等。

**問：我可以為 Aspose.GIS for .NET 的開發貢獻程式碼嗎？**  
答：Aspose.GIS for .NET 為 Aspose 的專有程式庫，外部無法直接貢獻程式碼。但您可提供回饋與建議，協助改進產品。

**問：Aspose.GIS for .NET 的更新頻率為何？**  
答：會定期釋出更新，加入新功能、改進與錯誤修正。請前往[官方網站](https://releases.aspose.com/gis/net/)查看最新版本。

## 結論
透過上述步驟，您已瞭解如何 **建立 linestring c#**、**將點加入 linestring**，以及使用 `Covers` 與 `CoveredBy` 方法執行可靠的 **點在線上檢查**。此功能可提升您軟體的空間分析能力，並為更進階的 GIS 操作鋪路。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-02-08  
**測試環境：** Aspose.GIS for .NET (latest release)  
**作者：** Aspose
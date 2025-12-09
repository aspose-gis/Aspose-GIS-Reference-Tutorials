---
date: 2025-12-04
description: 了解如何使用 Aspose.GIS for .NET 檢查相接的幾何圖形，這是一個強大的函式庫，可用於處理空間資料與執行空間分析。
linktitle: How to Check Touching Geometries
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 檢查相接的幾何
url: /zh-hant/net/geometry-analysis/check-geometries-touching/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何檢查相接的幾何圖形

## 介紹
如果您需要 **如何檢查相接** 兩個空間物件之間的關係，Aspose.GIS for .NET 為您提供乾淨、型別安全的 API，讓此工作變得輕而易舉。在本教學中，您將看到如何建立線串、點，然後使用 `Touches` 方法判斷幾何圖形是否僅共享邊界。這是許多 .NET 空間分析情境中的核心操作，例如網路路徑規劃、地圖疊加驗證與鄰近性檢查。

## 快速解答
- **「相接」是什麼意思？** 兩個幾何圖形至少共享一個邊界點，但其內部不相交。  
- **哪個方法用來檢查？** `Geometry.Touches(otherGeometry)`。  
- **此功能需要授權嗎？** 試用版可用於開發；正式環境需購買永久授權。  
- **支援的 .NET 版本？** .NET Framework、 .NET Core、 .NET 5/6/7 – 均由 Aspose.GIS 支援。  
- **實作需要多久？** 基本範例約 5‑10 分鐘。

## 在空間分析中什麼是「相接」？
在 GIS 專業術語中，*相接* 描述的是兩個幾何圖形在邊緣相遇但不重疊的空間關係。它不同於 *相交*（包括內部重疊），常用於需要驗證要素僅在邊界相會的情況——例如道路段在交叉口相連卻不相互穿越。

## 為什麼在 .NET 空間分析中使用 Aspose.GIS？
Aspose.GIS 提供完整管理的 .NET 函式庫，讓您 **處理空間資料** 而無需本機 GIS 安裝。它支援多種格式（Shapefile、GeoJSON、KML 等），並提供高效能的幾何運算，如 `Touches`、`Intersects`、`Contains` 等。由於純 .NET 實作，您可直接將其嵌入 Web 服務、桌面應用或雲端函式中。

## 前置條件
在開始之前，請確保您具備以下條件：

1. **Visual Studio**（任何較新版本）已安裝於您的機器上。  
2. **Aspose.GIS for .NET** – 從[官方下載頁面](https://releases.aspose.com/gis/net/)下載最新套件。  
3. **有效授權**（或免費試用）– 從[此處](https://releases.aspose.com/)取得。

### 設定開發環境
1. 若尚未安裝 Visual Studio，請先安裝。  
2. 從上述連結下載 Aspose.GIS for .NET，並將 NuGet 套件加入您的專案。  
3. 在程式碼中套用授權檔（或使用臨時授權進行測試）。

## 匯入命名空間
要開始使用 API，請匯入所需的命名空間：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 步驟 1：建立線串（及點）
以下我們 **建立線串** 物件以及一個將用於測試相接關係的點。

```csharp
var geometry1 = new LineString();
geometry1.AddPoint(0, 0);
geometry1.AddPoint(2, 2);
var geometry2 = new LineString();
geometry2.AddPoint(2, 2);
geometry2.AddPoint(3, 3);
var geometry3 = new Point(2, 2);
var geometry4 = new LineString();
geometry4.AddPoint(1, 1);
geometry4.AddPoint(4, 4);
```

*說明*：  
- `geometry1` 與 `geometry2` 共享端點 `(2, 2)`。  
- `geometry3` 是正好位於該共享端點的點。  
- `geometry4` 穿過相同區域，但 **未** 與 `geometry1` 共享邊界。

## 步驟 2：檢查相接關係
現在我們呼叫 `Touches` 方法，查看哪些配對被視為相接。

```csharp
Console.WriteLine(geometry1.Touches(geometry2)); // True
Console.WriteLine(geometry2.Touches(geometry1)); // True
Console.WriteLine(geometry1.Touches(geometry3)); // True
Console.WriteLine(geometry1.Touches(geometry4)); // False
```

*結果*：  
- 前三個檢查返回 **True**，因為幾何圖形在單一點相接且內部不重疊。  
- 最後一個檢查返回 **False**，因為兩條線串在一段線段上相交，而不僅僅是邊界點。

## 常見問題與技巧
- **精度問題** – GIS 計算基於浮點數。若出現意外的 `False` 結果，請考慮正規化座標或使用 `Geometry.EqualsExact(other, tolerance)` 設定容差。  
- **混合幾何類型** – `Touches` 可用於點、線、面，但語意不同；請始終驗證資料模型的預期關係。  
- **效能** – 對於大型資料集，請批次檢查或使用 Aspose.GIS 提供的空間索引（如 R‑tree）以避免 O(N²) 比較。

## 常見問答

**問：Aspose.GIS 是否相容所有 .NET 框架？**  
答：是的。它支援 .NET Framework、 .NET Core、 .NET 5+、 .NET 6+，讓您在桌面、網頁與雲端專案中皆能靈活使用。

**問：購買授權前可以先試用 Aspose.GIS 嗎？**  
答：當然可以。您可從 Aspose 官方網站 [此處](https://purchase.aspose.com/temporary-license/) 取得免費試用，探索所有功能，包括 `Touches` 操作。

**問：在哪裡可以取得 Aspose.GIS 相關問題的支援？**  
答：請前往官方 [Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33) 提問、分享範例，並獲得社群與 Aspose 工程師的協助。

**問：Aspose.GIS 的更新頻率為何？**  
答：Aspose 定期發布更新，加入新格式支援、效能提升與錯誤修正，確保與最新 .NET 版本相容。

**問：我可以取得 Aspose.GIS 的臨時授權嗎？**  
答：是的，可於 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權以供評估。

---

**最後更新：** 2025-12-04  
**測試環境：** Aspose.GIS for .NET 24.11（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
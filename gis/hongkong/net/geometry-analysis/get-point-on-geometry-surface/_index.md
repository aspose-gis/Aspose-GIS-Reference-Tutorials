---
date: 2025-12-09
description: 學習如何使用 Aspose.GIS for .NET 檢查點是否位於多邊形內。一步一步的指南，教您取得表面點、使用 C# 建立多邊形，並取得多邊形上的點。
linktitle: Check Point Inside Polygon and Get Point on Surface
second_title: Aspose.GIS .NET API
title: 檢查點是否在多邊形內並取得表面上的點
url: /zh-hant/net/geometry-analysis/get-point-on-geometry-surface/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 檢查點是否在多邊形內部以及取得表面上的點

## 介紹
在本教學中，你將學習如何使用 Aspose.GIS for .NET **檢查點是否在多邊形內部**，以及 **取得幾何圖形表面上的點**。我們會示範在 C# 中建立多邊形、取得位於多邊形表面的點，並驗證該點確實位於多邊形內部。完成後，你將擁有一段可直接放入任何 .NET 地理空間應用程式的即用程式碼片段。

## 快速回答
- **「檢查點是否在多邊形內部」是什麼意思？** 它會驗證給定座標是否位於多邊形幾何的邊界之內。  
- **哪個方法會回傳多邊形內部的點？** `GetPointOnSurface()` 會回傳一個保證在多邊形內部的點。  
- **執行範例是否需要授權？** 可使用免費試用版進行評估；正式上線則需購買完整授權。  
- **支援哪些 .NET 版本？** .NET Framework、.NET Core 與 .NET Standard 均相容。  
- **實作大約需要多久？** 約 5‑10 分鐘即可完成複製、編譯與執行。

## 前置條件
在開始之前，請確保你具備以下條件：

### 環境設定
1. 安裝 Aspose.GIS for .NET：從 [此處](https://releases.aspose.com/gis/net/) 下載並安裝 Aspose.GIS for .NET 套件。  
2. 設定開發環境：確保已具備可用的 .NET 開發環境，若尚未安裝，可自行安裝 Visual Studio 或其他你偏好的 .NET 開發工具。  
3. 具備 C# 基礎知識：若尚未熟悉 C#，請先了解其基本語法。  
4. 取得文件說明：隨時參考 [文件說明](https://reference.aspose.com/gis/net/) 以便查詢相關資訊。

## 匯入命名空間
在實作之前，先匯入必要的命名空間：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

現在我們已完成環境設定與命名空間匯入，接下來把範例拆解成多個步驟，方便更深入了解。

## 如何在 C# 中建立多邊形  
首先，我們需要 **建立一個多邊形** 幾何。透過指定頂點座標來定義多邊形的外環。

```csharp
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(0, 0),
});
```

## 如何取得表面上的點  
接著，使用 `GetPointOnSurface()` 方法取得多邊形表面上的點。這就是 **取得表面點** 的步驟。

```csharp
IPoint pointOnSurface = polygon.GetPointOnSurface();
```

## 如何檢查點是否在多邊形內部  
我們可以利用 `SpatiallyContains()` 方法驗證先前取得的點是否位於多邊形內部。此步驟示範了 **取得多邊形點** 後再進行檢查。

```csharp
Console.WriteLine(polygon.SpatiallyContains(pointOnSurface)); // True
```

## 常見問題與解決方案
- **空的多邊形** – 請確保外環至少有三個不同的頂點，否則 `GetPointOnSurface()` 可能會回傳未定義的點。  
- **順時針 vs. 逆時針** – 環的方向不會影響包含測試，但保持一致的環向有助於其他空間運算。  
- **座標系統** – 本範例使用簡單的笛卡爾平面；若使用真實世界座標，請務必正確設定 CRS（座標參考系統）。

## 結論
在本教學中，我們學會了如何使用 Aspose.GIS for .NET **檢查點是否在多邊形內部**、取得 **表面上的點**，並驗證其包含關係。借助 Aspose.GIS，處理地理空間資料變得高效且簡單，讓開發者能打造穩健的地理空間應用程式。

## 常見問答
### Aspose.GIS 是否相容其他 .NET 框架？
是的，Aspose.GIS 支援多種 .NET 框架，包括 .NET Framework、.NET Core 與 .NET Standard。

### 我可以在購買前先試用 Aspose.GIS 嗎？
可以，你可從 [此處](https://releases.aspose.com/) 下載 Aspose.GIS 的免費試用版。

### 如何取得 Aspose.GIS 的技術支援？
可前往 Aspose.GIS 論壇 [此處](https://forum.aspose.com/c/gis/33) 尋求協助，與其他使用者與開發者交流。

### Aspose.GIS 提供臨時授權嗎？
提供，你可從 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

### 我該從哪裡購買 Aspose.GIS？
可至購買頁面 [此處](https://purchase.aspose.com/buy) 進行購買。

**其他問答**

**問：** 處理大型多邊形資料集的最佳方式是什麼？  
**答：** 採用延遲載入幾何，並重複使用單一 `GeometryFactory` 實例，以降低記憶體開銷。

**問：** 我可以取得多個表面點嗎？  
**答：** `GetPointOnSurface()` 只回傳單一內部點。若需多個點，可在多邊形的外接盒內隨機產生點，並使用 `SpatiallyContains()` 逐一測試。

**問：** 建立多邊形後能否匯出為 shapefile？  
**答：** 可以，Aspose.GIS 提供 `FeatureSet` 與 `ShapefileWriter` 類別，讓你將幾何寫入 Shapefile 格式。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2025-12-09  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

---
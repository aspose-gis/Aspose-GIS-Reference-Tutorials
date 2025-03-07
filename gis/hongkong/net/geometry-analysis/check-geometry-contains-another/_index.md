---
title: 檢查幾何體是否包含另一個幾何體
linktitle: 檢查幾何體是否包含另一個幾何體
second_title: Aspose.GIS .NET API
description: 探索 Aspose.GIS for .NET，這是一個強大的程式庫，可在 .NET 應用程式中無縫整合地理空間資料。
weight: 14
url: /zh-hant/net/geometry-analysis/check-geometry-contains-another/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 檢查幾何體是否包含另一個幾何體

## 介紹
Aspose.GIS for .NET 是一個功能強大的程式庫，可讓開發人員在其 .NET 應用程式中無縫地處理地理空間資料。無論您是建立地圖應用程式、執行地理空間分析，還是將基於位置的功能整合到您的軟體中，Aspose.GIS 都可以透過提供直覺的 API 和強大的功能來簡化流程。
## 先決條件
在深入使用 Aspose.GIS for .NET 之前，請確保您具備以下先決條件：
### 1..NET開發環境搭建
確保您的電腦上設定了有效的 .NET 開發環境。這包括正確安裝和配置 .NET SDK。
### 2.Aspose.GIS安裝
透過從發佈頁面下載資料庫來安裝 Aspose.GIS for .NET[這裡](https://releases.aspose.com/gis/net/) 。請按照文件中提供的安裝說明進行操作[這裡](https://reference.aspose.com/gis/net/)將 Aspose.GIS 整合到您的專案中。
### 3.C#的基本理解
熟悉 C# 程式語言，因為 Aspose.GIS for .NET 主要與 C# 搭配使用。

## 導入命名空間
在您的 C# 專案中，匯入必要的命名空間以利用 Aspose.GIS 功能：
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 第 1 步：定義幾何對象
首先，使用 Aspose.GIS 類別定義幾何物件：
```csharp
var geometry1 = new Polygon();
geometry1.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 4),
    new Point(4, 4),
    new Point(4, 0),
    new Point(0, 0),
});
geometry1.AddInteriorRing(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 3),
    new Point(3, 3),
    new Point(3, 1),
    new Point(1, 1),
}));
var geometry2 = new Point(2, 2);
```
## 第 2 步：檢查空間遏制
接下來，檢查一個幾何圖形是否包含另一個幾何圖形：
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry2)); //錯誤的
```
## 第 3 步：定義另一個幾何圖形
定義另一個幾何物件：
```csharp
var geometry3 = new Point(0.5, 0.5);
```
## 第 4 步：再次檢視空間遏制
檢查新定義的幾何圖形是否包含在第一個幾何圖形中：
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry3)); //真的
```
## 第 5 步：等效功能
明白`a.SpatiallyContains(b)`相當於`b.Within(a)`:
```csharp
Console.WriteLine(geometry3.Within(geometry1)); //真的
```

## 結論
總之，Aspose.GIS for .NET 提供了強大的工具來處理 .NET 應用程式中的地理空間資料。透過遵循本指南並利用提供的範例，您可以有效地執行空間包含檢查並利用專案中的其他地理空間功能。
## 常見問題解答
### Q1：Aspose.GIS 與.NET Core 相容嗎？
答：是的，Aspose.GIS完全支援.NET Core，讓您可以跨不同平台開發地理空間應用程式。
### Q2：我可以使用 Aspose.GIS 執行地理空間分析嗎？
答：當然，Aspose.GIS 提供了各種地理空間分析功能，包括空間查詢、距離計算和幾何操作。
### Q3：Aspose.GIS 的更新頻率如何？
答：Aspose.GIS 定期發布更新以提高效能、新增功能並解決任何報告的問題。您可以透過造訪發布頁面來了解最新情況。
### Q4：有 Aspose.GIS 使用者的社群論壇嗎？
答：是的，您可以加入 Aspose.GIS 社群論壇[這裡](https://forum.aspose.com/c/gis/33)與其他用戶聯繫、提出問題並分享您的經驗。
### Q5：我可以在購買前試用Aspose.GIS嗎？
答：當然，您可以透過下載免費試用版來探索 Aspose.GIS[這裡](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: 檢查幾何形狀是否相等
linktitle: 檢查幾何形狀是否相等
second_title: Aspose.GIS .NET API
description: 透過這個綜合教程，了解如何使用 Aspose.GIS for .NET 檢查 .NET 應用程式中的幾何圖形是否相等。
weight: 10
url: /zh-hant/net/geometry-analysis/check-geometries-for-equality/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 檢查幾何形狀是否相等

## 介紹
Aspose.GIS for .NET 是一個功能強大的程式庫，使開發人員能夠在其 .NET 應用程式中有效地處理地理空間資料。無論您是建立地圖應用程式、空間分析工具，還是將地理空間功能整合到現有軟體中，Aspose.GIS 都能提供完成工作所需的工具。
## 先決條件
在深入使用 Aspose.GIS for .NET 之前，請確保您符合以下先決條件：
### 安裝.NET框架
確保您的系統上安裝了 .NET Framework。您可以從 Microsoft 網站下載它。
### Aspose.GIS for .NET 函式庫
從下列位置下載並安裝 Aspose.GIS for .NET 程式庫[下載頁面](https://releases.aspose.com/gis/net/)。請按照文件中提供的安裝說明進行操作。
### 開發環境
為 .NET 開發設定您的首選開發環境，例如 Visual Studio。

## 導入命名空間
在您的 .NET 應用程式中，匯入必要的命名空間以使用 Aspose.GIS 功能：
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 第 1 步：定義幾何形狀
首先，定義要比較的幾何形狀。在此範例中，我們有兩個幾何圖形：`geometry1`和`geometry2`.
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
## 第 2 步：檢查幾何形狀是否相等
現在，使用以下命令檢查幾何圖形在空間上是否相等`SpatiallyEquals`Aspose.GIS提供的方法。
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); //真的
```
這將列印`True`到控制台，因為`geometry1`和`geometry2`空間上是相等的。
## 第 3 步：修改幾何圖形
接下來我們來修改一下`geometry2`透過新增一個新點。
```csharp
geometry2.AddPoint(3, 3);
```
## 第 4 步：重新檢視平等性
現在，重新檢查修改後幾何圖形的相等性。
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); //錯誤的
```
這次，輸出將是`False`因為由於進行了修改，幾何形狀在空間上不再相等`geometry2`.

## 結論
總之，Aspose.GIS for .NET 提供了在 .NET 應用程式中處理地理空間資料的強大工具。遵循此逐步指南，您可以使用 Aspose.GIS 方法輕鬆檢查幾何圖形是否相等。
## 常見問題解答
### 我可以將 Aspose.GIS for .NET 與其他 .NET 框架一起使用嗎？
是的，Aspose.GIS for .NET 與各種 .NET 框架相容，包括 .NET Core 和 .NET Standard。
### Aspose.GIS for .NET 是否有免費試用版？
是的，您可以從以下位置下載免費試用版：[發布頁面](https://releases.aspose.com/).
### 在哪裡可以找到 Aspose.GIS for .NET 的文件？
您可以在以下位置找到詳細文檔[Aspose.GIS 文件頁面](https://reference.aspose.com/gis/net/).
### 如何獲得 Aspose.GIS for .NET 支援？
您可以從 Aspose.GIS 社群論壇獲得支持[這裡](https://forum.aspose.com/c/gis/33).
### 我可以購買 Aspose.GIS for .NET 的臨時授權嗎？
是的，您可以從[購買頁面](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

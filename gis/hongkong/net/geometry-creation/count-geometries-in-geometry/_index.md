---
title: 使用 Aspose.GIS 計算幾何圖形
linktitle: 計算幾何中的幾何
second_title: Aspose.GIS .NET API
description: 了解如何使用 Aspose.GIS for .NET 計算幾何圖形中的幾何圖形。為開發人員提供帶有程式碼範例的逐步教學。
type: docs
weight: 23
url: /zh-hant/net/geometry-creation/count-geometries-in-geometry/
---
## 介紹
Aspose.GIS for .NET 對於尋求將地理空間功能合併到 .NET 應用程式中的開發人員來說是一個強大的工具。無論您是建立地圖軟體、基於位置的服務還是空間分析工具，Aspose.GIS 都提供了一套全面的功能來滿足您的需求。在本教程中，我們將探索如何使用 Aspose.GIS for .NET 對幾何體中的幾何體進行計數。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1. Visual Studio：確保您的系統上安裝了 Visual Studio。
2. Aspose.GIS for .NET：從下列位置下載並安裝 Aspose.GIS for .NET[下載頁面](https://releases.aspose.com/gis/net/).
3. C# 基礎知識：熟悉 C# 程式語言基礎。

## 導入命名空間
在開始編碼之前，您需要匯入必要的命名空間以存取 Aspose.GIS 功能。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 第 2 步：建立點幾何圖形
```csharp
Point point = new Point(40.7128, -74.006);
```
在這裡，我們創建一個`Point`緯度 40.7128 和經度 -74.006 的幾何圖形。
## 第 3 步：建立線串幾何圖形
```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```
此步驟建立一個`LineString`幾何體並向其添加兩個點。
## 第 4 步：建立幾何集合
```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```
然後我們創建一個`GeometryCollection`並將先前建立的點和線幾何圖形添加到其中。
## 第 5 步：計算幾何圖形
```csharp
int geometriesCount = geometryCollection.Count;
```
此步驟計算幾何圖形的數量`GeometryCollection`.
## 第 6 步：顯示計數
```csharp
Console.WriteLine(geometriesCount); // 2
```
最後，我們列印出幾何圖形的數量，在本例中是`2`.

## 結論
在本教程中，我們學習如何使用 Aspose.GIS for .NET 對幾何體中的幾何體進行計數。透過執行這些步驟，您可以輕鬆地將地理空間功能合併到您的 .NET 應用程式中。
## 常見問題解答
### Aspose.GIS for .NET 是否適用於桌面和 Web 應用程式？
是的，Aspose.GIS for .NET 可以在桌面和 Web 應用程式中無縫使用。
### 我可以使用 Aspose.GIS for .NET 執行空間查詢嗎？
當然，Aspose.GIS for .NET 為幾何圖形執行空間查詢提供了強大的支援。
### Aspose.GIS for .NET 支援各種 GIS 檔案格式嗎？
是的，Aspose.GIS for .NET 支援多種 GIS 檔案格式，包括 SHP、KML 和 GeoJSON。
### Aspose.GIS for .NET 是否有免費試用版？
是的，您可以從以下位置下載免費試用版：[網站](https://releases.aspose.com/).
### 在哪裡可以找到對 Aspose.GIS for .NET 的支援？
您可以在以下位置找到支持[Aspose.GIS論壇](https://forum.aspose.com/c/gis/33).
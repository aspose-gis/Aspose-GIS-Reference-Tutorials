---
title: 使用 Aspose.GIS for .NET 掌握幾何疊加
linktitle: 尋找幾何疊加
second_title: Aspose.GIS .NET API
description: 了解如何使用 Aspose.GIS for .NET 執行幾何疊加操作。掌握交、並、差和對稱差運算。
weight: 16
url: /zh-hant/net/geometry-analysis/find-geometry-overlays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS for .NET 掌握幾何疊加

## 介紹
在地理資訊系統 (GIS) 領域，疊加操作是空間分析的基礎。它們可以比較和組合不同的空間資料集，以獲得有價值的見解。 Aspose.GIS for .NET 提供了強大的功能來有效地執行幾何疊加。在本教程中，我們將使用 Aspose.GIS for .NET 深入研究各種疊加操作，例如交集、並集、差集和對稱差集。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
### 1..NET開發環境
確保您的電腦上設定了 .NET 開發環境。您可以從 .NET 網站下載並安裝 .NET SDK。
### 2.Aspose.GIS for .NET函式庫
從下列位置下載並安裝 Aspose.GIS for .NET 程式庫[網站](https://releases.aspose.com/gis/net/).
## 導入命名空間
在開始使用 Aspose.GIS for .NET 之前，您需要將必要的命名空間匯入到您的專案中。
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 第 1 步：建立多邊形對象
首先，我們將定義兩個表示空間區域的多邊形物件。
```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```
## 步驟2：執行相交操作
接下來，讓我們找出兩個多邊形的交點。
```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); //多邊形
```
## 第 3 步：列印交點
我們將列印相交多邊形的點。
```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```
## 步驟4：執行聯合操作
現在，讓我們找到兩個多邊形的並集。
```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); //多邊形
```
## 第 5 步：列印聯合點
列印聯合多邊形的點。
```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```
## 第6步：執行差分運算
接下來，讓我們找出兩個多邊形之間的差異。
```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); //多邊形
```
## 步驟7：列印差異點
列印差異多邊形的點。
```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```
## 步驟8：執行對稱差分運算
最後，讓我們找出兩個多邊形之間的對稱差。
```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); //多重多邊形
```
## 第9步：列印對稱差異多邊形
列印對稱差中每個多邊形的點。
```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```
## 結論
掌握幾何疊加對於空間分析至關重要，Aspose.GIS for .NET 提供了一套全面的工具來有效地執行這些操作。透過學習本教學課程，您已經了解如何利用 Aspose.GIS for .NET 對幾何形狀執行交集、並集、差值和對稱差值運算。
## 常見問題解答
### Q：我可以在我的商業專案中使用 Aspose.GIS for .NET 嗎？
是的，Aspose.GIS for .NET 可用於商業和非商業專案。
### Q：Aspose.GIS for .NET 有試用版嗎？
是的，您可以從以下位置下載免費試用版[這裡](https://releases.aspose.com/).
### Q：如何獲得 Aspose.GIS for .NET 支援？
您可以從 Aspose.GIS 社群論壇獲得支持[這裡](https://forum.aspose.com/c/gis/33).
### Q：Aspose.GIS for .NET 是否有可用的臨時授權？
是的，臨時許可證可用於測試和評估目的。您可以從以下位置獲取它們：[這裡](https://purchase.aspose.com/temporary-license/).
### Q：我可以直接購買 Aspose.GIS for .NET 嗎？
是的，您可以從網站購買 Aspose.GIS for .NET[這裡](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

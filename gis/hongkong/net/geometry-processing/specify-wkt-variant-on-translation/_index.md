---
title: 使用 Aspose.GIS 指定翻譯時的 WKT 變體
linktitle: 指定翻譯時的 WKT 變體
second_title: Aspose.GIS .NET API
description: 了解如何在 Aspose.GIS for .NET 中指定 WKT 變體，以有效控制空間資料表示格式和精確度。
weight: 19
url: /zh-hant/net/geometry-processing/specify-wkt-variant-on-translation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS 指定翻譯時的 WKT 變體

## 介紹
Aspose.GIS for .NET 是一個功能強大的程式庫，可讓開發人員在其 .NET 應用程式中輕鬆使用地理資訊系統 (GIS) 資料。 Aspose.GIS 提供的基本功能之一是能夠在翻譯過程中指定眾所周知的文字 (WKT) 變體，使用戶能夠控制空間資料表示的格式和精確度。在本教程中，我們將探索如何使用 Aspose.GIS for .NET 逐步指定 WKT 變體。
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
1. Aspose.GIS for .NET：從下列位置下載並安裝 Aspose.GIS for .NET[下載頁面](https://releases.aspose.com/gis/net/).
2. 開發環境：確保您已設定 .NET 開發環境。
3. 基礎知識：熟悉C#程式語言和.NET架構。

## 導入命名空間
在程式碼中使用 Aspose.GIS 功能之前，請匯入必要的命名空間：
```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```
## 第 1 步：建立點對象
首先，創建一個`Point`具有緯度、經度和可選度量 (M) 值的物件：
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## 步驟 2：設定空間參考系統 (SRS)
將空間參考系統 (SRS) 指派給點物件。在本例中，我們使用 WGS84 空間參考系統：
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## 第 3 步：指定 WKT 變體
現在，指定要翻譯的 WKT 變體。 Aspose.GIS 支援各種 WKT 變體，包括`Iso`, `SimpleFeatureAccessOutdated`， 和`ExtendedPostGis`。根據您的要求選擇合適的變體：
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // M 點 (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); //點 (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```
## 第 4 步：控制數字格式
您可以控制 WKT 表示形式中座標的數字格式。 Aspose.GIS 提供了指定小數精度的選項：
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); //點 M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // M 點 (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // M 點 (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // M 點 (23.573 25.342 40.3)
```

## 結論
在本教程中，我們學習如何使用 Aspose.GIS for .NET 指定翻譯時的 WKT 變體。透過遵循上述步驟，開發人員可以有效控制.NET應用程式中空間資料表示的格式和精確度，從而增強地理資訊系統的靈活性和可用性。
## 常見問題解答
### Aspose.GIS 是否與所有版本的.NET 相容？
是的，Aspose.GIS 支援 .NET Framework 4.0 及更高版本。
### 我可以將 Aspose.GIS 用於商業專案嗎？
是的，Aspose.GIS 可用於個人和商業專案。
### Aspose.GIS是否提供其他空間資料格式的支援？
是的，Aspose.GIS 支援多種空間資料格式，包括 ESRI Shapefile、GeoJSON 和 KML。
### Aspose.GIS 是否有免費試用版？
是的，您可以從以下位置下載 Aspose.GIS 的免費試用版：[這裡](https://releases.aspose.com/).
### 我可以在哪裡獲得 Aspose.GIS 的協助或支援？
您可以在 Aspose.GIS 社群發佈您的問題或尋求協助：[論壇](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

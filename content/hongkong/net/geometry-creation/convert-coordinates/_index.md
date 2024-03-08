---
title: 使用 Aspose.GIS 進行座標轉換
linktitle: 轉換座標
second_title: Aspose.GIS .NET API
description: 了解如何使用 Aspose.GIS for .NET 轉換座標。提供逐步指南、先決條件和常見問題。
type: docs
weight: 25
url: /zh-hant/net/geometry-creation/convert-coordinates/
---
## 介紹
在本教程中，我們將使用強大的 .NET 版 Aspose.GIS 函式庫深入研究地理資訊系統 (GIS) 的世界。 Aspose.GIS 是一個綜合工具包，使開發人員能夠輕鬆處理空間資料。無論您是經驗豐富的開發人員還是新手，本教學都將引導您完成利用 Aspose.GIS 有效轉換座標的過程。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1. C# 基礎知識：熟悉 C# 程式語言對於理解和實作所提供的程式碼範例至關重要。
  
2.  Aspose.GIS的安裝：確保您已經下載並安裝了.NET的Aspose.GIS函式庫。您可以從[Aspose.GIS網站](https://releases.aspose.com/gis/net/).

## 導入命名空間
在開始之前，讓我們先匯入必要的命名空間來存取 Aspose.GIS 的功能：
```csharp
using System;
using Aspose.Gis;
```

為了清楚地理解，讓我們將提供的範例分解為多個步驟：
## 第 1 步：開始轉換過程
```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```
該行僅顯示一則訊息，指示座標轉換過程的開始。
## 第 2 步：轉換為十進制度
```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```
在這裡，我們使用以下函數將座標 (25.5, 45.5) 轉換為十進制度格式`AsPointText`方法與`PointFormats.DecimalDegrees`範圍。然後將結果列印到控制台。
## 步驟 3：轉換為十進制度分
```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```
此步驟將座標轉換為十進制分格式並列印結果。
## 步驟 4：轉換為度分秒
```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```
同樣，我們將座標轉換為度分秒格式並顯示輸出。
## 第 5 步：轉換為 GeoRef
```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```
最後，我們將座標轉換為 GeoRef 格式並列印結果。

## 結論
在本教程中，我們探索了使用 Aspose.GIS for .NET 轉換座標的過程。透過遵循逐步指南並利用 Aspose.GIS 程式庫，您可以在 .NET 應用程式中有效地操作空間資料。
## 常見問題解答
### Aspose.GIS 與其他程式語言相容嗎？
Aspose.GIS 主要針對 .NET 開發人員，但它透過 Aspose.GIS for Java 提供與 Java 的互通性。
### 我可以在購買前試用 Aspose.GIS 嗎？
是的，您可以從以下位置存取 Aspose.GIS 的免費試用版：[網站](https://releases.aspose.com/).
### 我如何獲得 Aspose.GIS 的支援？
您可以向 Aspose.GIS 社群論壇尋求協助[這裡](https://forum.aspose.com/c/gis/33).
### Aspose.GIS 是否有臨時許可證？
是的，可以從以下機構獲得臨時許可證[臨時許可證頁面](https://purchase.aspose.com/temporary-license/).
### 哪裡可以購買 Aspose.GIS？
您可以從以下位置購買 Aspose.GIS[購買頁面](https://purchase.aspose.com/buy).
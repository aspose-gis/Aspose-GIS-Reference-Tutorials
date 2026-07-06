---
date: 2026-04-09
description: 了解如何在 .NET 應用程式中使用 Aspose.GIS for .NET 以 C# 建立點時指派空間參考並設定小數精度。
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: 在翻譯時指定 WKT 變體
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS 指派空間參考與設定 WKT 變體
url: /zh-hant/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 指派空間參考並使用 Aspose.GIS 設定 WKT 變體

## 簡介
在本教學中，您將學習如何 **指派空間參考** 給幾何圖形，並使用 Aspose.GIS for .NET 控制精確的 WKT 輸出格式。無論您是需要 **建立 C# 點** 物件以進行製圖、分析或資料交換，能夠選擇正確的 WKT 變體與數值精度，都能使您的空間資料具備互通性且易於閱讀。讓我們一步一步地完成此流程。

## 快速解答
- **「指派空間參考」是什麼意思？** 它將幾何圖形綁定到特定的座標系統，例如 WGS‑84。  
- **支援哪些 WKT 變體？** Iso、SimpleFeatureAccessOutdated 與 ExtendedPostGis。  
- **如何控制小數精度？** 使用 `NumericFormat` 選項，如 `General`、`RoundTrip` 或 `Flat`。  
- **我需要授權嗎？** 可取得免費試用版；正式環境需購買商業授權。  
- **相容的 .NET 版本有哪些？** .NET Framework 4.0 以上與 .NET Core/5/6+。

## 什麼是「指派空間參考」？
指派空間參考（或稱空間參考系統，SRS）告訴 GIS 軟體如何解讀幾何圖形的座標值。若沒有 SRS，點的緯度‑經度數值將沒有實際意義。

## 為何要控制 WKT 變體與數值格式？
不同的 GIS 工具對 WKT 語法的細節略有差異。選擇正確的變體可確保資料交換順暢，而設定小數精度則可避免四捨五入誤差或過長的數字，防止日誌與檔案被雜訊佔滿。

## 先決條件
1. Aspose.GIS for .NET – 從 [download page](https://releases.aspose.com/gis/net/) 下載。  
2. .NET 開發環境（Visual Studio、VS Code 或 Rider）。  
3. 具備 C# 與 .NET 框架的基本知識。

## 匯入命名空間
在使用任何 Aspose.GIS 類別之前，先匯入所需的命名空間：

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

## 步驟 1：建立點物件（create point C#）
我們先建立一個 `Point`，包含緯度、經度，以及可選的測量（M）值：

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## 步驟 2：指派空間參考系統（SRS）
現在我們 **指派空間參考** 給此點。此處使用廣泛支援的 WGS‑84 系統（SRID 4326）：

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## 步驟 3：指定所需的 WKT 變體
選擇符合下游應用程式的 WKT 變體：

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## 步驟 4：設定 WKT 輸出的十進位精度
使用 `NumericFormat` 來控制最終字串出現的位數：

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### 常見陷阱與技巧
- **陷阱：** 若在呼叫 `AsText` 前未設定 SRS，可能導致 SRID 資訊遺失。  
- **技巧：** 需要座標無損往返時，請使用 `NumericFormat.RoundTrip`。  
- **技巧：** `Iso` 變體最具可移植性；僅在需要嵌入 SRID 時才選擇 `ExtendedPostGis`。

## 結論
您現在已了解如何 **指派空間參考**、選擇適當的 WKT 變體，並在 **建立 C# 點** 物件時 **設定十進位精度**，使用 Aspose.GIS。這些控制項讓您能彈性滿足任何 GIS 工作流程的精確需求，從簡單的視覺化到高精度的空間分析。

## 常見問題

**Q:** Aspose.GIS 是否相容所有 .NET 版本？  
**A:** 是的，Aspose.GIS 支援 .NET Framework 4.0 以上，以及 .NET Core/5/6。

**Q:** 我可以在商業專案中使用 Aspose.GIS 嗎？  
**A:** 當然可以。正式使用需購買商業授權，但可取得免費試用版以供評估。

**Q:** Aspose.GIS 是否支援其他空間資料格式？  
**A:** 是的，它支援 ESRI Shapefile、GeoJSON、KML 以及其他多種格式。

**Q:** 我可以從哪裡下載免費試用版？  
**A:** 您可從 [here](https://releases.aspose.com/) 下載 Aspose.GIS 的免費試用版。

**Q:** 若遇到問題，我該如何取得協助？  
**A:** 可在 Aspose.GIS 社群 [forum](https://forum.aspose.com/c/gis/33) 發問，Aspose 工作人員與社群成員皆會提供協助。

---

**最後更新：** 2026-04-09  
**測試環境：** Aspose.GIS for .NET (latest release)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
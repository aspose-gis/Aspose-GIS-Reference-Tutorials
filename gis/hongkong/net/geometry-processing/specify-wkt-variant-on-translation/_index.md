---
date: 2026-09-15
description: 了解如何在 C# 中使用 Aspose.GIS for .NET 建立 point geometry 時，指定 coordinate system、設定
  WKT variant 以及控制 decimal precision。
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: 在翻譯時指定 WKT Variant
og_description: 了解如何在 C# 中使用 Aspose.GIS for .NET 建立 point geometry 時，指定 coordinate
  system、設定 WKT variant 以及控制 decimal precision。
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: 指定 coordinate system，設定 WKT variant，使用 Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: 指定 coordinate system，設定 WKT variant，使用 Aspose.GIS
url: /zh-hant/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 指派座標系統，使用 Aspose.GIS 設定 WKT 變體

## 簡介
在本教學中，您將學習如何**assign coordinate system**、選擇正確的 WKT 變體，並在使用 C# 及 Aspose.GIS for .NET **create point geometry** 時控制小數精度。無論您是構建地圖服務、執行空間分析，或在 GIS 平台之間交換資料，這些設定都能確保您的輸出具備互通性且易於閱讀。讓我們一步一步地完成整個流程。

## 快速回答
- **What does “assign coordinate system” mean?** 它將幾何圖形綁定到特定的座標參考系統，例如 WGS‑84。  
- **Which WKT variants are supported?** Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.  
- **How can I control decimal precision?** 使用 `NumericFormat` 列舉 (`General`, `RoundTrip`, `Flat`).  
- **Do I need a license for Aspose.GIS?** 提供免費試用版；商業授權在正式使用時是必需的。  
- **What .NET versions are compatible?** .NET Framework 4.0+ and .NET Core/5/6+.  

## 什麼是「assign coordinate system」？
指派空間參考（或稱空間參考系統，SRS）告訴 GIS 軟件如何解讀幾何圖形的座標值，將這些數字與真實世界的座標系統（如 WGS‑84）相連結。若沒有 SRS，點的緯度‑經度數值將沒有實際意義。

## 為何要控制 WKT 變體與數值格式？
超過 30 種 GIS 工具要求特定的 WKT 語法，因此選擇正確的變體可避免匯入錯誤。設定數值格式可減少四捨五入噪音，讓輸出更為簡潔，這在程式自動解析日誌或檔案時尤為重要。

## 先決條件
1. Aspose.GIS for .NET – 從 [download page](https://releases.aspose.com/gis/net/) 下載。  
2. .NET 開發環境（Visual Studio、VS Code 或 Rider）。  
3. 具備 C# 及 .NET 框架的基本知識。

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

## 如何為點指派座標系統？
載入 `Point` 實例，然後使用 `SpatialReference` 類別附加空間參考系統 (SRS)。此兩步驟模式確保幾何圖形在匯出時攜帶座標系統的中繼資料，讓下游工具能正確解讀座標。`Point` 類別代表由 X（經度）和 Y（緯度）座標定義的單一位置。

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## 步驟 2：指派空間參考系統 (SRS)
現在我們**指派空間參考**給點。`SpatialReference` 代表以 SRID 識別的座標參考系統。此處使用廣泛支援的 WGS‑84 系統（SRID 4326）：

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

## 如何設定 WKT 輸出的十進位精度？
使用 `NumericFormat` 列舉控制最終字串中顯示的位數，該列舉定義了如 `General`、`RoundTrip` 或 `Flat` 等格式規則。選擇 `RoundTrip` 可在往返傳輸情境中保留完整座標精度，而 `General` 則提供適合大多數視覺化任務的簡潔表示。`NumericFormat` 列舉決定座標數字在 WKT 輸出中的格式化方式。

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### 常見陷阱與技巧
- **Pitfall:** 忘記在呼叫 `AsText` 之前設定 SRS 可能導致缺少 SRID 資訊。  
- **Tip:** 需要座標無損往返時，使用 `NumericFormat.RoundTrip`。  
- **Tip:** `Iso` 變體最具可移植性；僅在需要嵌入 SRID 時才選擇 `ExtendedPostGis`。

## 結論
您現在已了解如何**assign coordinate system**、選擇適當的 WKT 變體，以及在使用 Aspose.GIS **create point geometry** 時**set decimal precision**。這些控制項讓您能靈活滿足任何 GIS 工作流程的精確需求，從簡單的視覺化到高精度的空間分析皆可應對。

## 常見問題

**Q:** Aspose.GIS 是否相容於所有 .NET 版本？  
**A:** 是的，Aspose.GIS 支援 .NET Framework 4.0 及以上版本，同時也支援 .NET Core/5/6。

**Q:** 我可以在商業專案中使用 Aspose.GIS 嗎？  
**A:** 當然可以。正式使用時需要商業授權，但可取得免費試用版以供評估。

**Q:** Aspose.GIS 是否支援其他空間資料格式？  
**A:** 是的，它支援超過 30 種格式，包括 ESRI Shapefile、GeoJSON、KML、CSV 等等。

**Q:** 我可以從哪裡下載免費試用版？  
**A:** 您可從 [Aspose.GIS free trial download page](https://releases.aspose.com/) 下載 Aspose.GIS 的免費試用版。

**Q:** 若遇到問題，我該如何取得協助？  
**A:** 可在 Aspose.GIS 社群 [forum](https://forum.aspose.com/c/gis/33) 發問，Aspose 工作人員與社群成員皆會提供協助。

---

**最後更新:** 2026-09-15  
**測試環境:** Aspose.GIS for .NET (latest release)  
**作者:** Aspose

## 相關教學

- [建立向量圖層並設定其空間參考系統](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [如何使用 Aspose.GIS for .NET 將幾何轉換為 WKT](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [如何限制寫入幾何的精度（使用 Aspose.GIS）](/gis/net/geometry-processing/limit-precision-writing-geometries/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
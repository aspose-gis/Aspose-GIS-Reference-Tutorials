---
date: 2025-12-23
description: 學習如何使用 Aspose.GIS for .NET 將幾何圖形轉換為 WKT，並可選擇不同的選項、設定數字格式及調整小數位精度。
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS 將幾何轉換為 WKT 變體選項
url: /zh-hant/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS 轉換幾何圖形為 WKT 變體選項

## 簡介
在現代 .NET 應用程式中，**將幾何圖形轉換為 WKT** 是在需要與其他系統交換空間資料或以文字格式儲存時的常見步驟。Aspose.GIS for .NET 讓此轉換變得輕鬆，同時讓您完整掌控 WKT 變體、數值格式與小數精度。  
在本教學中，您將學習如何將幾何圖形轉換為 WKT、選擇正確的變體，並微調輸出以符合專案的精確需求。

## 快速解答
- **「將幾何圖形轉換為 WKT」是什麼意思？** 它將幾何物件（點、線、面）轉換為 Well‑Known Text（WKT）表示法。  
- **支援哪些 WKT 變體？** `Iso`, `SimpleFeatureAccessOutdated`, 和 `ExtendedPostGis`。  
- **如何控制小數精度？** 使用 `NumericFormat` 選項，如 `General`, `RoundTrip`, 或 `Flat`。  
- **生產環境是否需要授權？** 是，非試用使用需取得商業授權。  
- **相容的 .NET 版本為何？** .NET Framework 4.0+ 以及 .NET 5/6/7。

## 什麼是「將幾何圖形轉換為 WKT」？
將幾何圖形轉換為 WKT 會產生可供人類閱讀的字串，用以描述空間物件。此格式被 GIS 工具、資料庫與 Web 服務廣泛接受，因而成為資料交換的理想選擇。

## 為何在此轉換中使用 Aspose.GIS？
- **精度控制** – 選擇輸出的小數位數。  
- **變體彈性** – 符合下游系統所需的精確 WKT 方言。  
- **無外部相依性** – 純 .NET 函式庫，無原生二進位檔案。

## 先決條件
在開始之前，請確保您已具備以下項目：

1. **Aspose.GIS for .NET** – 從[下載頁面](https://releases.aspose.com/gis/net/)下載並安裝。  
2. **開發環境** – 任何近期版本的 Visual Studio 或搭配 .NET SDK 的 VS Code。  
3. **基本 C# 知識** – 熟悉類別、物件與 .NET 框架。

## 匯入命名空間
首先，將所需的命名空間匯入作用域：

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

## 步驟 1：建立 Point 物件
建立一個稍後會 **將幾何圖形轉換為 WKT** 的 `Point`。此點包含緯度、經度，以及可選的量測 (M) 值：

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## 步驟 2：設定空間參考系統 (SRS)
指派空間參考系統，使 WKT 輸出知道參考哪個座標系統。此處使用常見的 WGS84 系統：

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## 步驟 3：指定 WKT 變體
在 **將幾何圖形轉換為 WKT** 時選擇適當的 WKT 變體。每種變體的輸出格式略有不同：

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## 步驟 4：控制數值格式（設定數值格式與調整小數精度）
微調座標的數值表示方式。`NumericFormat` 類別讓您 **設定數值格式** 並 **調整小數精度** 以符合需求：

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## 常見問題與提示
- **缺少 M 值** – 若不需要量測，請省略 `M` 屬性；ISO 變體會自動省去它。  
- **非預期的精度** – 再次確認您使用了正確的 `NumericFormat`；`General` 保留完整的 double 精度，而 `Flat` 會四捨五入至指定的小數位數。  
- **未顯示 SRID** – 僅 `ExtendedPostGis` 變體會在輸出前加上 `SRID=`。當目標系統需要 SRID 時，請選擇此變體。

## 結論
透過上述步驟，您現在已了解如何 **將幾何圖形轉換為 WKT**、選擇正確的變體，並精確控制數值輸出。這讓您能彈性地將 Aspose.GIS 整合至任何使用 WKT 的 GIS 工作流程、資料庫或 Web 服務中。

## 常見問答
### Aspose.GIS 是否相容所有 .NET 版本？
是，Aspose.GIS 支援 .NET Framework 4.0 及以上版本。

### 我可以在商業專案中使用 Aspose.GIS 嗎？
可以，Aspose.GIS 可用於個人與商業專案。

### Aspose.GIS 是否支援其他空間資料格式？
是，Aspose.GIS 支援多種空間資料格式，包括 ESRI Shapefile、GeoJSON 與 KML。

### 是否提供 Aspose.GIS 的免費試用？
是，您可從[此處](https://releases.aspose.com/)下載 Aspose.GIS 的免費試用版。

### 我可以從哪裡取得 Aspose.GIS 的協助或支援？
您可以在 [論壇](https://forum.aspose.com/c/gis/33) 發表問題或尋求 Aspose.GIS 社群的協助。

## 常見問題
**Q: 如何將 Geometry 集合匯出為單一 WKT 字串？**  
A: 遍歷集合中的每個 geometry，將其 `AsText` 結果串接起來，必要時可使用逗號或換行符號分隔。

**Q: 我可以在不更改座標的情況下變更 SRID 嗎？**  
A: 可以，將 `SpatialReferenceSystem` 屬性設定為目標 SRID；座標值保持不變。

**Q: 如果使用不支援的 WKT 變體會發生什麼情況？**  
A: Aspose.GIS 會拋出 `ArgumentException`。請務必將變體與 `WktVariant` 列舉值進行驗證。

---

**最後更新：** 2025-12-23  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-09-05
description: 了解如何使用 Aspose.GIS for .NET 建立帶孔的多邊形內環。本指南將示範如何在多邊形中加入孔洞以及如何處理資料。
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: 建立帶孔的多邊形幾何
og_description: 了解如何使用 Aspose.GIS for .NET 建立帶孔的多邊形內環。本指南將示範如何在多邊形中加入孔洞以及如何處理資料。
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: 使用 Aspose.GIS 建立帶孔的多邊形內環
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: 使用 Aspose.GIS 建立帶孔的多邊形內環
url: /zh-hant/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS 建立具有孔洞的多邊形內部環

## 簡介
在本教學中，您將學習如何 **建立多邊形內部環**，此環包含一個孔洞，使用 Aspose.GIS for .NET。無論您是開發地圖應用程式、執行空間分析，或是為 GIS 服務準備資料，在多邊形內嵌入孔洞都是核心技能。我們將從設定開發環境開始，完整說明工作流程，最終產生可儲存為任何支援的地理空間格式的有效多邊形物件。

## 快速解答
- **「建立具有孔洞的多邊形」是什麼意思？** 它指的是建立一個多邊形，內部包含一個或多個內部環（孔洞），這些區域會從總面積中扣除。  
- **哪個函式庫處理此功能？** Aspose.GIS for .NET 提供對外部環與內部環的完整支援。  
- **我需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **需要多久時間？** 通常在 10 分鐘內即可完成實作與測試。

## 如何使用 Aspose.GIS 為多邊形添加孔洞
載入您的 GIS 環境，定義外部環，然後附加一個或多個內部環。Aspose.GIS 會自動調整環的方向並驗證幾何形狀，讓您專注於表示空洞的座標。

## 什麼是多邊形內部環？
**polygon interior ring** 是一條內部邊界，會從多邊形的外部形狀中減除面積。  
您可以透過定義一系列封閉的點序列，讓 Aspose.GIS 將其視為孔洞，計算面積或渲染形狀時會自動排除。

## 為什麼要使用 Aspose.GIS 建立多邊形內部環？
Aspose.GIS 能在 5 ms 內驗證並校正典型 200 點多邊形的環向，省去自行撰寫驗證程式碼的需求。它亦支援 **30+ geospatial file formats**（Shapefile、GeoJSON、GML、KML 等），且可在不將整個檔案載入記憶體的情況下處理多達 10,000 點的多邊形，提供高速與可擴充性。

## 實務情境：具有孔洞的多邊形
1. **內部有湖泊的土地分割** – 湖泊被建模為孔洞，因而不計入土地面積。  
2. **帶有庭院的建築外形** – 庭院被排除在建築外形之外。  
3. **大型保護區內的受保護區域** – 可在不建立獨立圖層的情況下排除受限制區段。

## 先決條件
在開始之前，請確保您具備以下條件：
1. Aspose.GIS for .NET 函式庫：您可以從 **Aspose.GIS for .NET 下載頁面**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)) 下載。  
2. 開發環境：請確保已安裝 Visual Studio 或其他 .NET IDE，並完成開發環境的設定。

## 匯入命名空間
`Aspose.Gis` 命名空間包含您所需的所有幾何類型，包括 `Polygon`、`LinearRing` 以及驗證的輔助方法。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

現在，讓我們繼續使用 Aspose.GIS for .NET 建立帶孔洞的多邊形幾何。

## 步驟 1：建立多邊形物件
`Polygon` 是 Aspose.GIS 的幾何類型，代表一個平面多邊形，可選擇性包含內部環。我們先實例化一個空的 `Polygon` 物件，稍後再加入外部環與內部環。

```csharp
Polygon polygon = new Polygon();
```

## 步驟 2：定義外部環
`LinearRing` 是用於外部與內部邊界的類別。外部環定義多邊形的外部邊界。請以順時針順序加入點，以形成封閉形狀。

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## 步驟 3：定義內部環（孔洞）
`LinearRing` 亦可表示內部環。內部環即 **hole**，會從多邊形的面積中扣除。點通常以逆時針順序加入，但 Aspose.GIS 會自動處理方向。

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## 步驟 4：指派外部環並將內部環加入多邊形
`AddInteriorRing` 方法會將一個或多個內部環附加至 `Polygon`。在設定 `ExteriorRing` 屬性之後呼叫此方法；如需多個孔洞，可重複呼叫。

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## 提示與最佳實踐
- **Orientation matters for readability** – 雖然 Aspose.GIS 會自動校正方向，保持外部環順時針、內部環逆時針，可讓 GIS 檢視器更易於檢查幾何。  
- **Close each ring** – 必須將第一個座標重複為最後一個點，以保證環為有效的封閉形狀。  
- **Validate after creation** – 可呼叫 `polygon.IsValid` 以確保幾何符合 OGC 標準，然後再儲存。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| GIS 檢視器中未顯示孔洞 | 內部環方向相反 | 確保點的加入方向與外部環相反（逆時針）。 |
| 多邊形無效錯誤 | 環未閉合（首點 ≠ 末點） | 在每個環的最後重複第一個點（如上所示）。 |
| 出現空的幾何物件 | 未先設定 `ExteriorRing` 就加入內部環 | 先設定 `polygon.ExteriorRing`，再呼叫 `AddInteriorRing`。 |

## 常見問答
### 1. 什麼是 Aspose.GIS？
Aspose.GIS 是一套 .NET 函式庫，讓開發者能處理地理空間資料，支援建立、讀取與操作各種地理空間檔案格式。

### 2. 我可以在商業專案中使用 Aspose.GIS 嗎？
可以，您可透過購買授權在個人或商業專案中使用 Aspose.GIS。請前往 **Aspose.GIS purchase page**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)) 了解更多細節。

### 3. 是否提供 Aspose.GIS 的免費試用？
可以，您可從 **Aspose.GIS free trial download page**([https://releases.aspose.com/](https://releases.aspose.com/)) 取得免費試用版。

### 4. 我可以在哪裡取得 Aspose.GIS 的支援？
您可於 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 取得支援。

### 5. 我如何取得 Aspose.GIS 的臨時授權？
您可從 **Aspose.GIS temporary license page**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)) 取得臨時授權。

---

**最後更新：** 2026-09-05  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [如何使用 Aspose.GIS for .NET 建立多邊形幾何](/gis/net/geometry-creation/create-polygon-geometry/)
- [學習如何使用 Aspose.GIS 建立 MultiPolygon 幾何](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [將多邊形轉換為線段（使用 Aspose.GIS for .NET）](/gis/net/geometry-processing/replace-polygons-with-lines/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
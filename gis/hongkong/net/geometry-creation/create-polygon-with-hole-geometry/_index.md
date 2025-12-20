---
date: 2025-12-20
description: 學習如何使用 Aspose.GIS for .NET 建立帶孔的多邊形幾何。此指南將向您展示如何在多邊形中創建孔洞以及如何處理地理空間資料。
linktitle: Create Polygon with Hole Geometry
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS 創建帶孔洞的多邊形幾何
url: /zh-hant/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS 建立帶孔多邊形幾何

## Introduction
在本教學中，您將 **建立帶孔多邊形** 幾何，使用 Aspose.GIS for .NET。無論您是在建構地圖應用程式、執行空間分析，或是為 GIS 服務準備資料，了解如何在多邊形內嵌入孔洞都是必備技能。我們將一步一步說明整個流程，從環境設定到產生最終的多邊形物件。

## Quick Answers
- **「建立帶孔多邊形」是什麼意思？** 指的是建立一個多邊形，內含一個或多個內環（孔洞），這些區域不計入多邊形的面積。
- **哪個函式庫支援此功能？** Aspose.GIS for .NET 完整支援外環與內環。
- **需要授權嗎？** 免費試用版可用於開發；正式環境需購買商業授權。
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。
- **需要多久時間？** 通常在 10 分鐘內即可完成實作與測試。

## What is “create polygon with hole”?
建立帶孔多邊形是指定義一個 **外環** 來描繪外部邊界，並加入一個或多個 **內環** 以挖出空洞。內環常被稱為 *孔洞*，因為它們代表不屬於多邊形表面的區域。

## Why create hole in polygon using Aspose.GIS?
- **精確的空間建模：** 真實世界中，如土地分割內的湖泊或建築內的庭院等，都需要使用孔洞。
- **相容性：** Shapefile、GeoJSON、GML 等格式原生支援內環；Aspose.GIS 能完整保留。
- **效能：** 函式庫會自動處理幾何有效性，您無需自行撰寫驗證程式。

## Prerequisites
在開始之前，請確保具備以下前置條件：

1. Aspose.GIS for .NET 函式庫：可從 [here](https://releases.aspose.com/gis/net/) 下載。
2. 開發環境：請確保已安裝 Visual Studio 或其他 .NET IDE，並完成設定。

## Import Namespaces
首先，您需要匯入使用 Aspose.GIS 功能所需的命名空間。以下示範如何操作：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

現在，我們開始使用 Aspose.GIS for .NET 建立帶孔多邊形幾何。

## Step 1: Create Polygon Object
## 步驟 1：建立 Polygon 物件

我們先建立一個空的 `Polygon` 物件，之後會放入外環與內環。

```csharp
Polygon polygon = new Polygon();
```

## Step 2: Define Exterior Ring
## 步驟 2：定義外環

外環用來定義多邊形的外部邊界。請以順時針方向加入點，以形成封閉形狀。

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Step 3: Define Interior Ring (Hole)
## 步驟 3：定義內環（孔洞）

接下來，我們建立內環——即會從多邊形面積中排除的 **孔洞**。點通常以逆時針方向加入，但 Aspose.GIS 會自動處理方向。

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Step 4: Assign Exterior Ring and Add Interior Ring to Polygon
## 步驟 4：指派外環並將內環加入 Polygon

最後，將外環指派給多邊形，接著加入內環（孔洞）。若需要多個孔洞，可多次呼叫 `AddInteriorRing` 方法。

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Common Issues and Solutions
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| GIS 檢視器中未顯示孔洞 | 內環方向相反 | 請確保點的加入方向與外環相反（逆時針）。 |
| Polygon 無效錯誤 | 環未閉合（首點 ≠ 末點） | 在每個環的最後重複首點（如上所示）。 |
| 意外的空幾何 | 在加入內環前未指派 `ExteriorRing` | 先設定 `polygon.ExteriorRing`，再呼叫 `AddInteriorRing`。 |

## Conclusion
## 結論

恭喜！您已成功學會如何使用 Aspose.GIS for .NET **建立帶孔多邊形** 幾何。此技巧在許多需要以內部空洞表示複雜形狀的地理空間情境中相當重要。

## Frequently Asked Questions
### 1. What is Aspose.GIS?
### 1. 什麼是 Aspose.GIS？

Aspose.GIS 是一套 .NET 函式庫，讓開發者能處理地理空間資料，具備建立、讀取與操作各種地理空間檔案格式的功能。

### 2. Can I use Aspose.GIS for commercial projects?
### 2. 我可以在商業專案中使用 Aspose.GIS 嗎？

可以，您只要購買授權，即可在個人或商業專案中使用 Aspose.GIS。詳情請見 [here](https://purchase.aspose.com/buy)。

### 3. Is there a free trial available for Aspose.GIS?
### 3. Aspose.GIS 有提供免費試用嗎？

有，您可從 [here](https://releases.aspose.com/) 取得 Aspose.GIS 的免費試用版。

### 4. Where can I find support for Aspose.GIS?
### 4. 我可以在哪裡取得 Aspose.GIS 的支援？

您可於 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 獲得支援。

### 5. How can I obtain a temporary license for Aspose.GIS?
### 5. 如何取得 Aspose.GIS 的臨時授權？

您可從 [here](https://purchase.aspose.com/temporary-license/) 取得 Aspose.GIS 的臨時授權。

---

**最後更新：** 2025-12-20  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
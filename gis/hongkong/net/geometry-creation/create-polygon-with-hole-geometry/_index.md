---
date: 2026-04-03
description: 學習如何使用 Aspose.GIS for .NET 建立帶洞的多邊形幾何。此指南將向您展示如何在多邊形中創建洞以及如何處理地理空間資料。
keywords:
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
linktitle: 建立帶洞多邊形幾何
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS 建立帶洞的多邊形幾何
url: /zh-hant/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS 建立帶洞多邊形幾何

## 簡介
在本教學中，您將 **建立帶洞多邊形** 幾何，使用 Aspose.GIS for .NET。無論您是開發地圖應用程式、執行空間分析，或是為 GIS 服務準備資料，了解如何在多邊形內嵌入洞是必備技能。我們將一步一步說明整個流程，從環境設置到產生最終的多邊形物件。

## 快速解答
- **「create polygon with hole」是什麼意思？** 它表示建立一個多邊形，其中包含一個或多個內環（洞），這些區域不計入面積。  
- **哪個函式庫負責此功能？** Aspose.GIS for .NET 提供對外環與內環的完整支援。  
- **我需要授權嗎？** 免費試用版可用於開發；正式環境需購買商業授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **需要多長時間？** 通常在 10 分鐘內即可完成實作與測試。

## 如何使用 Aspose.GIS 為多邊形加入洞
加入洞只是定義一個 **interior ring** 並將其附加到多邊形的問題。函式庫會處理方向與有效性，讓您只需關注代表空洞的座標。

## 什麼是「create polygon with hole」？
建立帶洞的多邊形涉及定義一個 **exterior ring** 以描繪外部邊界，及一個或多個 **interior rings** 以挖出空白區域。內環通常稱為 *holes*，因為它們代表不屬於多邊形表面的區域。

## 為什麼使用 Aspose.GIS 在多邊形中建立洞？
- **精確的空間建模：** 真實世界的特徵，例如土地分割內的湖泊或建築物內的庭院，需要使用洞。  
- **相容性：** Shapefile、GeoJSON、GML 等格式原生支援內環；Aspose.GIS 能保留它們。  
- **效能：** 函式庫管理幾何有效性，您無需自行編寫驗證程式碼。

## 帶洞多邊形的實務情境
1. **內部有湖泊的土地分割** – 將湖泊建模為洞，使其不計入土地面積。  
2. **建築外形圖含庭院** – 庭院被排除在建築外形圖之外。  
3. **大型保護區內的受保護區域** – 可將受限制區段排除，而不必建立獨立圖層。

## 先決條件
在開始之前，請確保您具備以下先決條件：
1. Aspose.GIS for .NET 函式庫：您可從 [here](https://releases.aspose.com/gis/net/) 下載。  
2. 開發環境：確保已安裝 Visual Studio 或其他 .NET IDE，並完成環境設定。

## 匯入命名空間
首先，您需要匯入必要的命名空間以使用 Aspose.GIS 功能。以下是做法：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

現在，讓我們繼續使用 Aspose.GIS for .NET 建立帶洞多邊形幾何。

## 步驟 1：建立 Polygon 物件
我們先建立一個空的 `Polygon` 物件，之後會放入外環與內環。

```csharp
Polygon polygon = new Polygon();
```

## 步驟 2：定義外環
外環定義多邊形的外部邊界。請以順時針順序加入點，以形成封閉形狀。

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## 步驟 3：定義內環（洞）
接著，我們建立內環——這就是將從多邊形面積中排除的 **hole**。點通常以逆時針順序加入，但 Aspose.GIS 會自動處理方向。

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## 步驟 4：指派外環並將內環加入 Polygon
最後，將外環附加到 Polygon，然後加入內環（即洞）。若需要多個洞，可多次呼叫 `AddInteriorRing` 方法。

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## 提示與最佳實踐
- **方向影響可讀性** – 雖然 Aspose.GIS 會自動校正方向，保持外環順時針、內環逆時針，可讓 GIS 檢視器更易於檢查幾何。  
- **關閉每個環** – 必須將第一個座標重複為最後一個點，以確保環為有效的封閉形狀。  
- **建立後驗證** – 可呼叫 `polygon.IsValid` 以確保幾何符合 OGC 標準，再進行儲存。

## 常見問題與解決方案
| Issue | Reason | Fix |
|-------|--------|-----|
| GIS 檢視器未顯示洞 | 內環方向相反 | 確保點的加入方向與外環相反（逆時針）。 |
| Polygon 無效錯誤 | 環未封閉（首點 ≠ 末點） | 在每個環中將第一個點重複為最後一個點（如上所示）。 |
| 意外的空幾何 | 在加入內環前忘記指派 `ExteriorRing` | 先設定 `polygon.ExteriorRing`，再呼叫 `AddInteriorRing`。 |

## 常見問答
### 1. 什麼是 Aspose.GIS？
Aspose.GIS 是一個 .NET 函式庫，讓開發人員能處理地理空間資料，並能建立、讀取與操作各種地理空間檔案格式。

### 2. 我可以在商業專案中使用 Aspose.GIS 嗎？
是的，您可透過購買授權，在個人與商業專案中使用 Aspose.GIS。詳情請參閱 [here](https://purchase.aspose.com/buy)。

### 3. 是否提供 Aspose.GIS 的免費試用？
是的，您可從 [here](https://releases.aspose.com/) 取得 Aspose.GIS 的免費試用版。

### 4. 我可以在哪裡取得 Aspose.GIS 的支援？
您可於 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 獲得支援。

### 5. 如何取得 Aspose.GIS 的臨時授權？
您可從 [here](https://purchase.aspose.com/temporary-license/) 取得 Aspose.GIS 的臨時授權。

---

**最後更新：** 2026-04-03  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
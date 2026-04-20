---
date: 2026-02-08
description: 學習如何使用 Aspose.GIS for .NET 進行幾何緩衝，並執行空間分析緩衝，包括安裝、命名空間匯入及包含性檢查。
linktitle: How to Create Buffer Using Aspose.GIS for .NET
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 進行幾何緩衝
url: /zh-hant/net/geometry-analysis/create-geometry-buffer/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS for .NET 緩衝幾何圖形

## 介紹
如果你在 .NET 環境中處理地理空間資料，了解 **如何緩衝幾何圖形** 對於鄰近分析、分區以及要素概化都是必備技能。在本教學中，我們將一步步示範如何使用 Aspose.GIS for .NET——從安裝、匯入必要的命名空間、為線與多邊形幾何圖形產生緩衝區，最後檢查空間包含關係。完成後，你將能在自己的應用程式中自如地運用 **空間分析緩衝**。

## 快速回答
- **什麼是幾何緩衝區？** 一個多邊形，包圍來源幾何圖形一定距離內的所有點。  
- **為什麼使用 Aspose.GIS 來緩衝？** 它提供簡潔且高效能的 API，支援 .NET Framework、.NET Core 以及 .NET 5/6+。  
- **如何安裝 Aspose.GIS？** 從官方網站下載程式庫，並在 Visual Studio 中加入參考。  
- **如何檢查包含關係？** 使用 `SpatiallyContains` 方法測試點是否位於產生的緩衝區內。  
- **我可以執行緩衝以外的空間分析嗎？** 可以——交集、聯集與距離計算等操作亦受支援。

## 什麼是幾何緩衝區？
幾何緩衝區會在要素（點、線或多邊形）周圍依使用者自訂的距離建立一個區域。此區域可用於辨識鄰近要素、建立影響範圍，或簡化複雜形狀。

## 使用 Aspose.GIS 進行空間分析緩衝的方式
### 為什麼選擇 Aspose.GIS 來做空間分析緩衝？
- **跨平台支援：** 可在 Windows、Linux 與 macOS 上執行。  
- **零外部相依性：** 不需要原生 GIS 函式庫。  
- **功能豐富的 API：** 包含緩衝、空間謂詞與座標系統轉換。  
- **效能優化：** 能有效處理大型資料集，適合重度空間分析緩衝。

## 前置條件
在開始之前，請確保你已具備以下環境：

- **Visual Studio 2019 或更新版本**（或任何相容的 .NET IDE）。  
- **.NET 6 SDK**（或 .NET Core 3.1 以上）。  
- **Aspose.GIS for .NET 程式庫**——請參考下方安裝步驟。

### 如何安裝 Aspose.GIS for .NET
1. 從 [下載連結](https://releases.aspose.com/gis/net/) 下載 Aspose.GIS for .NET 程式庫。  
2. 在 Visual Studio 中，右鍵點擊專案 → **Add** → **Reference…** → 瀏覽至下載的 DLL 並加入。  
3. 從 [Aspose](https://purchase.aspose.com/buy) 取得授權，或使用 [臨時授權](https://purchase.aspose.com/temporary-license/) 進行評估。

## 匯入命名空間
要開始使用 API，請在 C# 檔案中匯入必要的命名空間。

### 如何匯入 Aspose.GIS
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

現在讓我們一步步說明緩衝區的建立流程。

## 步驟說明

### 步驟 1：建立幾何緩衝區
首先，我們定義一個簡單的 `LineString` 幾何圖形，作為緩衝的來源。

```csharp
// Define a LineString geometry
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(3, 3);
```

在此程式碼片段中，我們建立一個 `LineString`，並加入兩個點，形成從 (0,0) 到 (3,3) 的對角線。

### 步驟 2：為 LineString 產生緩衝區
接著，我們以 **正向距離** 1 單位為線條產生緩衝區。

```csharp
// Generate a buffer for the LineString with a positive distance
var lineBuffer = line.GetBuffer(distance: 1);
```

`GetBuffer` 方法會回傳一個多邊形，包含原始線條 1 單位內的所有點。

### 步驟 3：檢查空間包含關係
現在示範 **如何檢查包含**，測試特定點是否落在緩衝區內。

```csharp
// Check spatial containment of points within the buffer
Console.WriteLine(lineBuffer.SpatiallyContains(new Point(1, 2)));     // True
Console.WriteLine(lineBuffer.SpatiallyContains(new Point(3.1, 3.1))); // True
```

`SpatiallyContains` 謂詞若點位於緩衝多邊形內則回傳 `true`。

### 步驟 4：定義多邊形幾何圖形
我們也會建立一個 `Polygon` 幾何圖形，以說明 **負向距離** 緩衝，會使形狀縮小。

```csharp
// Define a Polygon geometry
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 3),
    new Point(3, 3),
    new Point(3, 0),
    new Point(0, 0),
});
```

此多邊形為一個正方形，頂點座標為 (0,0)、(0,3)、(3,3) 與 (3,0)。

### 步驟 5：為多邊形產生緩衝區
使用 -1 單位的負向距離，將多邊形向內收縮。

```csharp
// Generate a buffer for the Polygon with a negative distance
var polygonBuffer = (IPolygon)polygon.GetBuffer(distance: -1);
```

產生的 `polygonBuffer` 為較小的正方形，可用於建立內部區域。

### 步驟 6：存取緩衝區外環點座標
最後，我們取得並顯示緩衝區外環的座標。

```csharp
// Access points of the exterior ring of the buffer Polygon
var ring = polygonBuffer.ExteriorRing;
for (int i = 0; i < ring.Count; ++i)
{
    Console.WriteLine("[{0}] = ({1} {2})", i, ring[i].X, ring[i].Y);
}
```

此迴圈會列印收縮後多邊形的每個頂點，驗證緩衝幾何圖形。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **緩衝返回 `null`** | 確認距離值對於該幾何圖形的座標系統是否適當。 |
| **`SpatiallyContains` 總是返回 `false`** | 檢查兩個幾何圖形是否使用相同的空間參考系統（CRS）。 |
| **大型資料集效能下降** | 將幾何圖形分批處理，並重複使用同一個 `GeometryFactory` 實例。 |

## 常見問答

**Q: Aspose.GIS for .NET 是否相容其他 .NET 框架？**  
A: 是的，支援 .NET Framework、.NET Core、.NET 5 以及 .NET 6。

**Q: 我可以使用 Aspose.GIS for .NET 進行空間分析嗎？**  
A: 當然可以。程式庫支援緩衝、交集、距離計算等功能。

**Q: 資料集大小有沒有上限？**  
A: API 已針對大型資料集進行最佳化，但記憶體使用量仍取決於載入的幾何圖形大小。

**Q: Aspose.GIS 是否支援不同的空間參考系統？**  
A: 支援廣泛的座標系統，並可即時執行轉換。

**Q: 我該向哪裡取得技術支援？**  
A: 前往 Aspose.GIS 社群論壇 [https://forum.aspose.com/c/gis/33](https://forum.aspose.com/c/gis/33) 取得協助。

---

**最後更新：** 2026-02-08  
**測試環境：** Aspose.GIS for .NET（最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
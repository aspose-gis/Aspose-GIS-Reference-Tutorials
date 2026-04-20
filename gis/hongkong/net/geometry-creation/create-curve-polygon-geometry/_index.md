---
date: 2026-02-15
description: 學習如何使用 Aspose.GIS for .NET 建立向量圖層與曲線多邊形幾何，並包含內環的圓弧串幾何。
linktitle: Create Curve Polygon Geometry
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS 建立向量圖層與曲線多邊形
url: /zh-hant/net/geometry-creation/create-curve-polygon-geometry/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS 建立向量圖層與曲線多邊形

## 簡介
在地理資訊系統（GIS）開發領域，**Aspose.GIS for .NET** 脫穎而出，成為一個功能強大的函式庫，可用於建立、編輯與操作空間資料。在本教學中，您將一步一步學習如何**create vector layer** 與 **create curve polygon** 幾何，讓您能直接在 GIS 應用程式中嵌入複雜形狀。完成本指南後，您將擁有一個可直接使用的 Shapefile，內含具有外環與內環的曲線多邊形。

## 快速解答
- **使用的函式庫是什麼？** Aspose.GIS for .NET  
- **主要任務？** Create a curve polygon geometry, save it as a Shapefile, and **create vector layer** for the data  
- **一般實作時間？** 5–10 minutes for a basic shape  
- **先決條件？** .NET development environment and Aspose.GIS NuGet package  
- **可以檢視結果嗎？** Yes – any GIS viewer that supports Shapefile (e.g., QGIS, ArcGIS)

## 什麼是曲線多邊形？
「*曲線多邊形*」是一種其邊緣可以由曲線段（例如圓弧）組成，而非僅直線的多邊形。這使得對湖泊、島嶼或任何需要平滑邊界的自然特徵進行更真實的建模成為可能。

## 為什麼要使用 Aspose.GIS 建立曲線多邊形幾何？
- **Precision** – 曲線邊緣以數學方式儲存，保留精確的幾何形狀。  
- **Interoperability** – 產生的 Shapefile 可在所有主要 GIS 平台上使用。  
- **Productivity** – 定義複雜形狀只需極少程式碼，提升開發效率。  
- **Flexibility** – 您可以即時 **create vector layer** 物件，並附加任何所需的幾何。

## 先決條件
在開始之前，請確保您已具備以下條件：

1. **Aspose.GIS for .NET** 已安裝。從 [Aspose.GIS for .NET releases page](https://releases.aspose.com/gis/net/) 下載。  
2. 具備 C# 及 .NET 生態系統的實務知識。  
3. 使用 Visual Studio（任何近期版本）或 Visual Studio Code 等 IDE。

## 匯入命名空間
在此步驟中，我們將匯入必要的命名空間，以在程式碼中使用 Aspose.GIS 功能。

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 步驟說明

### 步驟 1：定義檔案路徑
首先，指定產生的曲線多邊形 Shapefile 要儲存的位置。

```csharp
string path = "Your Document Directory" + "CreateCurvePolygon_out.shp";
```

將 `"Your Document Directory"` 替換為您機器上的實際資料夾路徑。

### 步驟 2：建立向量圖層
使用 Shapefile 驅動程式實例化新的向量圖層。這就是 **create vector layer** 步驟，用於為我們的幾何建立容器。

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Your code for creating the Curve Polygon Geometry will go here
}
```

`using` 陳述式可確保資源正確釋放。

### 步驟 3：建構要素
建立一個要素物件，用於保存幾何與任何屬性資料。

```csharp
var feature = layer.ConstructFeature();
```

### 步驟 4：建立曲線多邊形幾何
現在我們將建立一個空的 `CurvePolygon` 物件。

```csharp
var curvePolygon = new CurvePolygon();
```

### 步驟 5：定義外環
加入一個圓形串列，形成多邊形的外部邊界。

```csharp
var exterior = new CircularString();
exterior.AddPoint(-2, 0);
exterior.AddPoint(0, 2);
exterior.AddPoint(2, 0);
exterior.AddPoint(0, -2);
exterior.AddPoint(-2, 0);
curvePolygon.ExteriorRing = exterior;
```

上述座標會產生類似環形的形狀。

### 步驟 6：定義內環（可選）
如果需要在多邊形內部留孔，可將其定義為另一個圓形串列。此範例示範如何使用 **circular string geometry** 新增 **interior ring polygon**。

```csharp
var interior = new CircularString();
interior.AddPoint(-1, 0);
interior.AddPoint(0, 1);
interior.AddPoint(1, 0);
interior.AddPoint(0, -1);
interior.AddPoint(-1, 0);
curvePolygon.AddInteriorRing(interior);
```

### 步驟 7：將幾何指派給要素
將曲線多邊形連結至先前建立的要素。

```csharp
feature.Geometry = curvePolygon;
```

### 步驟 8：將要素加入圖層
最後，將要素加入向量圖層，使其成為資料集的一部份。

```csharp
layer.Add(feature);
```

當 `using` 區塊結束時，Shapefile 會寫入磁碟。

## 常見問題與解決方案
| 問題 | 發生原因 | 解決方法 |
|-------|----------------|-----|
| **檔案未建立** | 路徑不正確或缺少寫入權限 | 確認目錄存在且應用程式具有寫入權限。 |
| **曲線邊緣在某些檢視器中顯示為直線** | 檢視器不支援 circular strings | 使用完整支援 Shapefile 規範的 GIS 應用程式（例如 QGIS 3.28+）。 |
| **在 `AddPoint` 上拋出 `ArgumentException`** | 點超出所選坐標參考系統的有效座標範圍 | 確保座標位於您計畫使用的坐標參考系統之內。 |

## 常見問與答

**Q: Aspose.GIS for .NET 是否相容於其他 GIS 函式庫？**  
A: 是的，Aspose.GIS for .NET 支援與多種流行 GIS 格式的互操作性，讓您能與如 GDAL/OGR 或 Proj.NET 等函式庫交換資料。

**Q: 我可以在 GIS 軟體中視覺化產生的曲線多邊形幾何嗎？**  
A: 當然可以！產生的 Shapefile 可在 QGIS、ArcGIS 或任何支援 Shapefile 格式的 GIS 工具中開啟。

**Q: Aspose.GIS for .NET 是否提供空間分析功能？**  
A: 有的，它包含空間查詢、緩衝、交集等功能，讓您能直接在 .NET 中執行進階分析。

**Q: 我可以在哪裡尋求協助或與其他使用者討論想法？**  
A: 前往 Aspose.GIS 社群論壇 [here](https://forum.aspose.com/c/gis/33) 與其他開發者交流。

**Q: 購買前是否提供免費試用？**  
A: 當然！您可從 [releases page](https://releases.aspose.com/) 下載免費試用版，評估全部功能。

## 結論
您現在已學會如何使用 Aspose.GIS for .NET **create vector layer** 與 **create curve polygon** 幾何，將其儲存為 Shapefile，並了解常見的陷阱與常見問答。歡迎嘗試不同的座標組、加入屬性資料，或將圖層整合至更大的 GIS 工作流程中。

---

**最後更新：** 2026-02-15  
**測試環境：** Aspose.GIS for .NET 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
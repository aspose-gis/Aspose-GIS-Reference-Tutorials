---
date: 2025-12-31
description: 學習如何使用 Aspose.GIS for .NET 建立向量圖層並設定圖層的空間參考系統。掌握定義空間參考、加入點要素以及取得 EPSG
  代碼的技巧。
linktitle: Set Layer Spatial Reference System
second_title: Aspose.GIS .NET API
title: 建立向量圖層並設定圖層空間參考系統
url: /zh-hant/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 Vector Layer 並設定圖層空間參考系統

## Introduction
在廣闊的地理資訊系統 (GIS) 領域中，**Aspose.GIS for .NET** 脫穎而出，成為開發人員的強大且多功能工具。在本教學中，您將 **create vector layer**，定義其空間參考，新增點要素，並取得 EPSG 代碼——全部提供清晰、一步一步的指引。無論您是資深 GIS 工程師或剛入門，這些技巧都能協助您正確設定 shapefile 的座標系統，提升空間資料工作流程的可靠性。

## Quick Answers
- **「create vector layer」是什麼意思？** It creates a new GIS layer (e.g., a Shapefile) that can store geometries such as points, lines, or polygons.  
- **範例中使用的 EPSG 代碼是什麼？** EPSG 26918 (NAD83 / UTM zone 18N).  
- **建立圖層後，我可以新增點要素嗎？** Yes—use `ConstructFeature()` and assign a `Point` geometry.  
- **如何取得圖層的 CRS？** Read `layer.SpatialReferenceSystem.EpsgCode` or `.Name`.  
- **是否需要 Aspose.GIS 授權？** A free trial is available; a license is required for production use.  

## Prerequisites
- 具備 .NET 程式設計的實務知識。  
- 系統已安裝 Visual Studio。  
- Aspose.GIS for .NET 函式庫，可從 [here](https://releases.aspose.com/gis/net/) 下載。  
- 具備 GIS 中空間參考系統的基本概念。  

## Import Namespaces
在您的 .NET 專案中，首先匯入必要的命名空間，以存取 Aspose.GIS 所提供的功能。使用以下程式碼片段：

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Step 1: Specify the Document Directory
首先指定文件目錄的路徑。此路徑將用於儲存您的空間資料檔案。

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Define Spatial Reference and Set Shapefile Coordinate System
定義 Shapefile 的路徑，並使用 EPSG 代碼（本例為 26918）**定義空間參考**。此步驟會為圖層**設定 shapefile 座標系統**。

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Step 3: Create Vector Layer
現在使用指定的 Shapefile 路徑、驅動類型（Shapefile）以及剛才定義的空間參考系統**建立 vector layer**。

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

## Step 4: Add Point Feature to the Layer
建立新的要素，並透過設定其幾何形狀（座標為 60, 24 的 `Point`）**新增 point feature**。接著將該要素加入 vector layer。

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

## Step 5: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
開啟 Vector Layer，取得空間參考系統的資訊，例如 EPSG 代碼與可讀名稱。此範例示範如何**取得 EPSG 代碼**以及**設定圖層 CRS**。

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

依照您的實際需求重複上述步驟，即可熟練 **create vector layer** 的技巧，並使用 Aspose.GIS for .NET 管理空間參考。

## Common Issues and Solutions
| 問題 | 為何發生 | 解決方式 |
|------|----------|----------|
| **圖層無法開啟** | 驅動程式錯誤或檔案路徑損毀 | Verify `Drivers.Shapefile` and ensure `path` points to an existing `.shp` file. |
| **顯示的 CRS 不正確** | 使用了錯誤的 EPSG 代碼 | Double‑check the EPSG code with an authoritative source (e.g., EPSG.io). |
| **要素未儲存** | 未在 `using` 區塊內呼叫 `layer.Add(feature)` | Ensure the `Add` method is executed before the layer is disposed. |

## Frequently Asked Questions
### Aspose.GIS 是否相容於其他 GIS 函式庫？
是，Aspose.GIS 能與其他 GIS 函式庫良好整合，且可同時使用。

### 我可以同時在桌面與 Web 應用程式中使用 Aspose.GIS 嗎？
當然可以！Aspose.GIS 多功能，可用於桌面與基於 Web 的應用程式。

### Aspose.GIS 有哪些授權方案可供選擇？
有，您可在 [here](https://purchase.aspose.com/buy) 查看授權方案並購買。

### 是否提供 Aspose.GIS 的免費試用版？
當然！您可在 [here](https://releases.aspose.com/) 下載免費試用版。

### 我可以在哪裡取得 Aspose.GIS 相關問題的支援？
如需支援或詢問，請前往 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)。

## Additional Frequently Asked Questions
**問：如何變更既有 Shapefile 的 CRS？**  
**答：** 開啟圖層，使用目標 EPSG 代碼建立新的 `SpatialReferenceSystem`，並在儲存前將其指派給 `layer.SpatialReferenceSystem`。

**問：我可以使用相同方式新增其他幾何類型（例如多邊形）嗎？**  
**答：** 可以——視需求將 `new Point(x, y)` 替換為 `new Polygon(...)` 或 `new LineString(...)`。

**問：是否能有效處理大型資料集？**  
**答：** 使用串流 API（`VectorLayer.Create` 搭配 `FeatureCollection`），並及時釋放圖層以節省資源。

**問：Aspose.GIS 支援座標轉換嗎？**  
**答：** 支援——使用 `Geometry.Transform(targetSrs)` 可在不同空間參考之間重新投影幾何圖形。

**問：支援哪些 .NET 版本？**  
**答：** Aspose.GIS 相容於 .NET Framework 4.6 以上、.NET Core 3.1 以上，以及 .NET 5/6/7。

## Conclusion
在本教學中，我們探討了如何使用 Aspose.GIS for .NET **create vector layer**、定義其空間參考、**add point feature**，以及**retrieve EPSG code**。掌握這些步驟後，您即可自信地設定 shapefile 座標系統、管理圖層 CRS，並建立可靠的 GIS 應用程式。

---

**Last Updated:** 2025-12-31  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
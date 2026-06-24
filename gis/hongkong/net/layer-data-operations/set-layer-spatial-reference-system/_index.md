---
date: 2026-06-15
description: 了解如何使用 Aspose.GIS for .NET 建立向量圖層並設定圖層空間參考系統。精通定義空間參考、加入點要素以及取得 EPSG
  代碼。
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: 設定圖層空間參考系統
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 建立向量圖層並設定圖層空間參考系統
url: /zh-hant/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立向量圖層並設定圖層空間參考系統

## 簡介
在廣闊的地理資訊系統（GIS）領域中，**Aspose.GIS for .NET** 脫穎而出，作為一個穩健且高效能的函式庫，支援超過 **70+** 種向量與影像格式，且能在不將整個資料集載入記憶體的情況下處理超過 **10 GB** 的檔案。在本教學中，您將 **建立向量圖層**、定義其空間參考、**新增點要素**，並取得 EPSG 代碼——全部以清晰的逐步指引說明。無論您是構建地圖服務、資料轉換管線，或是空間分析引擎，掌握這些基礎將確保您的 shapefile 坐標系統精確，GIS 工作流程可靠。

## 快速解答
- **「建立向量圖層」是什麼意思？** 它會建立一個新的 GIS 圖層（例如 Shapefile），可儲存點、線或多邊形等幾何圖形。  
- **範例中使用的 EPSG 代碼為何？** EPSG 26918（NAD83 / UTM zone 18N）。  
- **建立圖層後可以新增點要素嗎？** 可以——使用 `ConstructFeature()` 並指派 `Point` 幾何。  
- **如何取得圖層的 CRS？** 讀取 `layer.SpatialReferenceSystem.EpsgCode` 或 `.Name`。  
- **使用 Aspose.GIS 是否需要授權？** 提供免費試用版；正式使用需購買授權。  

## 什麼是建立向量圖層？
**建立向量圖層** 操作會建立一個新的向量資料集（例如 Shapefile），可容納幾何要素與屬性資料。在 Aspose.GIS 中，這透過以驅動程式和空間參考系統實例化 `VectorLayer` 物件來完成。

## 為何要正確設定圖層座標系統 (CRS)？
設定正確的座標參考系統（CRS）可確保您儲存的每個幾何圖形與其他空間資料集對齊。使用 Aspose.GIS，您可以透過標準 EPSG 代碼定義 CRS，確保與全球 GIS 軟體的互通性。例如，EPSG 26918 定義 NAD83 / UTM zone 18N，這是美國東部常用的投影。

## 先決條件
- .NET 開發經驗（C# 或 VB.NET）。  
- Visual Studio 2022 或更新版本。  
- Aspose.GIS for .NET 函式庫 – 於 **[此處](https://releases.aspose.com/gis/net/)** 下載。  
- 具備空間參考系統（CRS/EPSG）的基本認識。  

## 匯入命名空間
`Aspose.Gis` 命名空間提供核心 GIS 類別，而 `Aspose.Gis.Geometries` 則提供如 `Point` 等幾何類型。  

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## 如何在 Aspose.GIS for .NET 中建立向量圖層？
VectorLayer 代表向量資料集（例如 Shapefile），提供建立、讀取與編輯要素的方法。  
SpatialReferenceSystem 使用 EPSG 代碼定義座標參考系統。  

載入目標資料夾，定義 EPSG 編碼的 `SpatialReferenceSystem`，然後使用 Shapefile 驅動程式呼叫 `VectorLayer.Create`。此單一呼叫會建立新的 `.shp` 檔案，寫入相應的 `.shx` 與 `.dbf` 檔案，並嵌入 CRS 中繼資料，為高效的要素插入做好準備。

### 步驟 1：指定文件目錄
首先指定文件目錄的路徑。此路徑將是儲存空間資料檔案的位置。  

```csharp
string dataDir = "Your Document Directory";
```

### 步驟 2：定義空間參考並設定 Shapefile 座標系統
SpatialReferenceSystem 代表圖層的 CRS，由 EPSG 代碼識別。  

定義 Shapefile 的路徑，並使用 EPSG 代碼（本例為 26918）**定義空間參考**。此步驟**設定圖層的 shapefile 座標系統**。  

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## 如何向向量圖層新增點要素？
`Point` 是代表單一 X/Y 座標對的幾何類型。  

建構新要素，指派帶有所需 X/Y 座標的 `Point` 幾何，並將要素加入開啟的 `VectorLayer`。此操作會在單一交易中將幾何寫入 `.shp` 檔案，屬性記錄寫入 `.dbf` 檔案。  

### 步驟 3：建立向量圖層
`ConstructFeature` 會建立可容納幾何與屬性資料的新要素物件。  

現在使用指定的 Shapefile 路徑、驅動程式類型（Shapefile）以及剛才定義的空間參考系統**建立向量圖層**。  

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### 步驟 4：將點要素加入圖層
建構新要素，透過設定其幾何（座標為 60, 24 的 `Point`）**新增點要素**。然後將要素加入向量圖層。  

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### 步驟 5：取得空間參考系統資訊（取得 EPSG 代碼）
開啟向量圖層並取得空間參考系統的資訊，例如 EPSG 代碼與可讀名稱。此示範說明如何**取得 EPSG 代碼**以及**設定圖層 CRS**。  

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## 常見問題與解決方案
| 問題 | 發生原因 | 解決方法 |
|-------|----------------|-----|
| **圖層無法開啟** | 驅動程式錯誤或檔案路徑損毀 | 確認 `Drivers.Shapefile` 並確保 `path` 指向已存在的 `.shp` 檔案。 |
| **顯示的 CRS 不正確** | 使用了錯誤的 EPSG 代碼 | 使用權威來源（例如 EPSG.io）再次確認 EPSG 代碼。 |
| **要素未儲存** | 未在 `using` 區塊內呼叫 `layer.Add(feature)` | 確保在圖層釋放前執行 `Add` 方法。 |

## 常見問與答
**Q: 如何變更現有 Shapefile 的 CRS？**  
A: 開啟圖層，使用目標 EPSG 代碼建立新的 `SpatialReferenceSystem`，指派給 `layer.SpatialReferenceSystem`，然後儲存圖層。  

**Q: 我可以使用相同方式新增其他幾何類型（例如多邊形）嗎？**  
A: 可以——視需要將 `new Point(x, y)` 替換為 `new Polygon(...)` 或 `new LineString(...)`。  

**Q: 是否能有效處理大型資料集？**  
A: 使用串流 API（`VectorLayer.Create` 搭配 `FeatureCollection`）並及時釋放圖層以節省資源。  

**Q: Aspose.GIS 是否支援座標轉換？**  
A: 支援——使用 `Geometry.Transform(targetSrs)` 在不同空間參考之間重新投影幾何。  

**Q: 支援哪些 .NET 版本？**  
A: Aspose.GIS 支援 .NET Framework 4.6 以上、.NET Core 3.1 以上、以及 .NET 5/6/7。  

---

**最後更新：** 2026-06-15  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [使用 Aspose.GIS for .NET 建立向量圖層並設定線性化容差](/gis/net/geometry-processing/set-linearization-tolerance/)
- [在 File GDB 中建立向量圖層 – Aspose.GIS .NET 教學](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [spatial reference wgs84 – 使用 Aspose.GIS 新增圖層至 GDB](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
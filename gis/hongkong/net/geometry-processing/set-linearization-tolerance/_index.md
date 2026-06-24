---
date: 2026-05-31
description: 了解如何使用 Aspose.GIS for .NET 建立 GeoJSON、設定 GeoJSON 選項，以及將要素新增至圖層。請遵循此一步一步的指南。
keywords:
- how to create geojson
- add feature to layer
- configure geojson options
linktitle: 設定線性化容差
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  headline: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  name: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  steps:
  - name: Configure GeoJSON Options (how to set tolerance)
    text: '`GeoJsonOptions` specifies the serialization settings used when writing
      GeoJSON files. `GeoJsonOptions` defines how Aspose.GIS serializes GeoJSON, including
      linearization tolerance, coordinate precision, and other output settings. We’ll
      create a `GeoJsonOptions` object and tell Aspose.GIS how close '
  - name: Define the Output Path (how to export GeoJSON)
    text: Specify the full file path where the resulting GeoJSON will be saved. Ensure
      the folder exists and the application has write permissions.
  - name: '**Create Vector Layer** with the configured options'
    text: The `VectorLayer` class represents a GIS container that can read and write
      spatial data. `Drivers.GeoJson` is the driver identifier for writing GeoJSON
      format files. Using `VectorLayer.Create` together with the `Drivers.GeoJson`
      driver and the previously configured `GeoJsonOptions` creates a new Geo
  - name: Construct a Geometry (e.g., a circular string)
    text: '`CircularString` is a curved line geometry that Aspose.GIS can linearize
      based on the tolerance you set. You can replace this with any valid WKT representation
      such as `POINT`, `LINESTRING`, or `POLYGON`.'
  - name: '**Add Feature to Layer** and save'
    text: '`Feature` is the object that couples a geometry with attribute data. After
      creating a `Feature` instance, assign the geometry, optionally add attribute
      values, and call `layer.Add(feature)` to persist it. When the `using` block
      ends, the layer is automatically written to the file defined in `path`. '
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. A commercial license removes all evaluation restrictions and
      provides full technical support.
    question: Can I use Aspose.GIS in commercial projects?
  - answer: Yes, it supports over 30 formats—including Shapefile, KML, GML, and CSV—allowing
      seamless conversion between them.
    question: Does Aspose.GIS support other GIS formats besides GeoJSON?
  - answer: You can download a free 30‑day trial from the Aspose website; it includes
      all features.
    question: Is there a trial version available?
  - answer: Use the Aspose forums, the dedicated support portal, or the “Contact Support”
      link in the product dashboard.
    question: Where can I get support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 如何在 Aspose.GIS for .NET 中使用容差建立 GeoJSON
url: /zh-hant/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用容差在 Aspose.GIS for .NET 中建立 GeoJSON

## 簡介
如果您想 **學習如何建立 GeoJSON** 檔案、控制曲線精度，並將結果匯出為可直接使用的文件，Aspose.GIS for .NET 讓這一切變得簡單。在本教學中，您將了解如何設定 GeoJSON 選項、設定線性化容差，並 **將特徵新增至圖層** 物件，同時保持程式碼乾淨且適合投入生產環境。

## 快速解答
- **What does “create vector layer” mean?** 它會建立一個新的 GIS 向量資料集（例如 GeoJSON 檔案），可儲存幾何圖形和屬性。  
- **How do I set linearization tolerance?** 在建立圖層之前，於 `GeoJsonOptions` 實例上設定 `LinearizationTolerance` 屬性。  
- **Can I export a GeoJSON file directly?** 可以 — 使用 `VectorLayer.Create` 搭配 `Drivers.GeoJson` 驅動程式以及已設定的選項。  
- **Do I need a license?** 有效的 Aspose.GIS 授權會解鎖所有功能；臨時評估金鑰可用於測試。  
- **Which .NET versions are supported?** 支援 .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 「create vector layer」是什麼？
建立向量圖層表示初始化一個新的 GIS 容器（例如 GeoJSON 檔案），可容納點、線、面以及相關的屬性資料。此圖層成為您所建構的任何幾何圖形和所附加屬性的目標。

## 為什麼要設定 GeoJSON 選項？
設定 GeoJSON 選項——尤其是 **linearization tolerance**——可確保曲線幾何（例如 `CircularString`）以符合應用程式精度需求的方式近似。適當的設定可減少檔案大小，同時保留視覺忠實度，這在 GeoJSON 被網頁地圖或空間分析工具使用時尤為重要。

## 前置條件
1. **Visual Studio**（任何較新版本）。  
2. **Aspose.GIS license**（或臨時評估金鑰）。  
3. 在專案中參考 **Aspose.GIS for .NET** 程式庫。  
4. 基本熟悉 **C#**。

## 匯入命名空間
首先，匯入所需的命名空間，讓編譯器知道 GIS 類別的所在位置：

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 步驟指南

### 步驟 1：設定 GeoJSON 選項（如何設定容差）
`GeoJsonOptions` 指定寫入 GeoJSON 檔案時使用的序列化設定。  
`GeoJsonOptions` 定義 Aspose.GIS 如何序列化 GeoJSON，包括線性化容差、座標精度以及其他輸出設定。  
我們將建立一個 `GeoJsonOptions` 物件，告訴 Aspose.GIS 線性化後的幾何圖形需與原始曲線多接近。

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### 步驟 2：定義輸出路徑（如何匯出 GeoJSON）
指定最終 GeoJSON 檔案要儲存的完整路徑。確保資料夾已存在且應用程式具有寫入權限。

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### 步驟 3：使用已設定的選項 **Create Vector Layer**
`VectorLayer` 類別代表可讀寫空間資料的 GIS 容器。  
`Drivers.GeoJson` 是寫入 GeoJSON 格式檔案的驅動程式識別碼。  
結合 `VectorLayer.Create`、`Drivers.GeoJson` 驅動程式以及先前設定的 `GeoJsonOptions`，即可建立一個可供新增特徵的全新 GeoJSON 檔案。

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### 步驟 4：建構幾何（例如 circular string）
`CircularString` 是一種曲線線段幾何，Aspose.GIS 可根據您設定的容差將其線性化。您可以將其替換為任何有效的 WKT 表示，例如 `POINT`、`LINESTRING` 或 `POLYGON`。

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### 步驟 5：**Add Feature to Layer** 並儲存
`Feature` 是將幾何圖形與屬性資料結合的物件。建立 `Feature` 實例後，指派幾何圖形，必要時加入屬性值，然後呼叫 `layer.Add(feature)` 以將其寫入。當 `using` 區塊結束時，圖層會自動寫入 `path` 所定義的檔案。

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

當 `using` 區塊結束時，圖層會自動寫入 `path` 所定義的檔案，為您提供可直接使用的 GeoJSON 檔案。

## 常見問題與技巧
- **Incorrect path** – 確認目錄已存在且您具有寫入權限。  
- **Tolerance too low** – 將 `LinearizationTolerance` 設為極小值會大幅增加檔案大小；通常 0.001 的容差能在精度與大小之間取得平衡。  
- **License errors** – 若看到授權警告，請確保在任何 Aspose.GIS 呼叫之前已載入授權檔案。  
- **Performance note** – 由於採用串流架構，Aspose.GIS 支援處理高達 2 GB 的檔案，而無需將整個文件載入記憶體。

## 常見問答

**Q: Aspose.GIS for .NET 是否相容於其他 .NET 框架？**  
A: 是的，它支援 .NET Framework 4.5+、.NET Core 3.1+ 以及 .NET 5/6/7。

**Q: 我可以在商業專案中使用 Aspose.GIS 嗎？**  
A: 當然可以。商業授權會移除所有評估限制，並提供完整的技術支援。

**Q: Aspose.GIS 是否支援除 GeoJSON 之外的其他 GIS 格式？**  
A: 是的，它支援超過 30 種格式，包括 Shapefile、KML、GML 與 CSV，能夠在它們之間無縫轉換。

**Q: 是否提供試用版？**  
A: 您可從 Aspose 官方網站下載免費 30 天試用版，內含所有功能。

**Q: 我該向哪裡取得支援？**  
A: 可使用 Aspose 論壇、專屬支援入口，或在產品儀表板中的「Contact Support」連結。

## 結論
透過上述步驟，您現在已了解 **如何建立 GeoJSON**、設定線性化容差，並 **將特徵新增至圖層** 以順利匯出 GeoJSON。探索更多幾何類型、屬性處理與批次處理情境，充分發揮 Aspose.GIS 在 .NET GIS 專案中的威力。

---

**最後更新：** 2026-05-31  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何轉換 GeoJSON – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [建立向量圖層，限制精度 – Aspose.GIS for .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [在 File GDB 中建立向量圖層 – Aspose.GIS .NET 教學](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
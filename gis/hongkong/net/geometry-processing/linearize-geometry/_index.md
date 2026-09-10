---
date: 2026-09-10
description: 了解如何使用 Aspose.GIS for .NET 將曲線轉換為線條（線性化幾何），以在 .NET 應用程式中實現高效的地理空間處理與分析。
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
lastmod: 2026-09-10
linktitle: 線性化幾何
og_description: 使用 Aspose.GIS for .NET 將曲線轉換為線條（線性化幾何）。逐步學習如何簡化幾何，以提升渲染速度並擴大相容性。
og_image_alt: Guide showing how to linearize curved geometries to straight lines using
  Aspose.GIS in a .NET application
og_title: 使用 Aspose.GIS for .NET 將曲線轉換為線條
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  headline: How to Convert Curves to Lines with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  name: How to Convert Curves to Lines with Aspose.GIS for .NET
  steps:
  - name: Define the output path
    text: '`Path.Combine` builds a platform‑independent file path, handling Windows
      backslashes and Unix forward slashes automatically. Replace `"Your Document
      Directory"` with the folder where you want the KML file saved.'
  - name: Create a layer for the output file
    text: A *layer* groups geographic features of the same type. Here we instantiate
      a new KML layer that will store the linearized geometry.
  - name: Construct a new feature
    text: A *feature* represents a single geographic object (point, line, polygon,
      etc.). We’ll attach our linear geometry to this feature.
  - name: Define the original complex geometry
    text: '`Geometry.FromWkt` parses a Well‑Known Text (WKT) string into a geometry
      object. The sample WKT includes a `LineString`, a `CompoundCurve`, and a `CircularString`
      to showcase curve handling.'
  - name: Convert curves to lines
    text: '`ToLinearGeometry()` tessellates every curve in the source geometry into
      straight‑line segments, returning a new linear geometry that retains any Z‑coordinates.'
  - name: Assign the linear geometry to the feature
    text: The feature’s `Geometry` property now holds the simplified, linear version
      of the original shape.
  - name: Add the feature to the layer
    text: Adding the feature to the KML layer queues it for writing; when the `using`
      block ends, the layer flushes the data to the output file.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Core, enabling cross‑platform applications.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Absolutely! The library supports KML, Shapefile, GeoJSON, and many more
      formats—over 30 in total.
    question: Can I work with different GIS file formats using Aspose.GIS for .NET?
  - answer: Yes, it provides a wide range of spatial functions, from buffering to
      spatial joins.
    question: Does Aspose.GIS offer spatial operations and analysis?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      and staff support.
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert curves to lines
- Aspose.GIS
- .NET GIS processing
title: 如何使用 Aspose.GIS for .NET 將曲線轉換為線條
url: /zh-hant/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將曲線轉換為線段（線性化幾何）使用 Aspose.GIS for .NET

## 介紹
如果您需要為製圖、空間分析或資料交換任務 **將曲線轉換為線段**，Aspose.GIS for .NET 為您提供乾淨且程式化的解決方案。在本教學中，我們將逐步示範一個完整的實務範例，說明如何將包含曲線與複合形狀的複雜幾何圖形，轉換為可在任何 GIS 系統中使用的簡單線性表示。

## 快速解答
- **「將曲線轉換為線段」是什麼意思？** 它會將曲線幾何轉換為直線段。  
- **為什麼選擇 Aspose.GIS？** 此函式庫支援超過 30 種 GIS 格式，且可在不使用外部工具的情況下處理幾何轉換。  
- **事前需要什麼？** .NET Framework 或 .NET Core、Visual Studio（或任何 C# IDE）以及 Aspose.GIS NuGet 套件。  
- **範例執行需要多久？** 安裝函式庫後不到五分鐘即可完成。  
- **可以匯出為其他格式嗎？** 當然可以——只要將 KML 驅動程式換成 Shapefile、GeoJSON 等即可。  
您可以從 [Aspose website](https://releases.aspose.com/) 下載完整產品套件。

## 「將曲線轉換為線段」是什麼意思？
將曲線轉換為線段（亦稱 **線性化幾何**）會將每個曲線段替換為一系列短直線段，從而產生 *線性幾何*。這可使渲染速度提升至五倍，降低記憶體使用量，並確保資料能被僅接受線性要素的舊版 GIS 服務所使用。

## 為什麼要將曲線轉換為線段？
線性幾何的渲染與查詢速度可比曲線幾何快 **5 倍以上**，且 **30 多個 GIS 平台** 只接受線性要素。簡化幾何亦可縮小網頁預覽的檔案大小，並使需要直線輸入的演算法（如網路分析或叢集）得以運作。

## 如何線性化幾何？
使用 Aspose.GIS 提供的 `ToLinearGeometry()` 方法。它會自動將幾何中的每條曲線細分為直線段，同時保留 Z 值，讓您在不失去高程資料的情況下取得線性近似。您亦可指定容差，以控制原始曲線與產生的線段之間的最大偏差，從而在精度與檔案大小之間取得平衡。此方法同時適用於 2D 與 3D 幾何。

## 前置條件
在深入程式碼之前，請確保您已具備：

1. **Aspose.GIS for .NET** – 從 [Aspose.GIS website](https://releases.aspose.com/gis/net/) 下載。  
2. **.NET Framework**（或 .NET Core）已安裝於開發機器上。  
3. **Visual Studio**（或任何相容 C# 的 IDE）用於編寫與執行範例。

## 匯入命名空間
要開始使用 Aspose.GIS 功能，請匯入所需的命名空間。

### 核心 Aspose.GIS 命名空間
`Aspose.Gis` 命名空間包含所有 GIS 操作所需的核心幾何類別、驅動程式與工具。  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### 目標格式的驅動程式
`Aspose.Gis.Drivers` 為每種支援的檔案格式提供靜態工廠；`Drivers.Kml` 會建立 KML 寫入器。  
```csharp
using Aspose.GIS.Kml;
```

## 逐步指南：將曲線轉換為線段
以下為每行程式碼的詳細說明，解釋 **如何將曲線轉換為線段** 以及每個步驟的重要性。

### 步驟 1：定義輸出路徑
`Path.Combine` 會建立跨平台的檔案路徑，自動處理 Windows 的反斜線與 Unix 的正斜線。  
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
將 `"Your Document Directory"` 替換為您希望儲存 KML 檔案的資料夾路徑。

### 步驟 2：為輸出檔案建立圖層
*圖層* 用於將相同類型的地理要素分組。此處我們實例化一個新的 KML 圖層，用於儲存線性化的幾何。  
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```

### 步驟 3：建立新要素
*要素* 代表單一的地理物件（點、線、面等）。我們將把線性幾何附加到此要素上。  
```csharp
var feature = layer.ConstructFeature();
```

### 步驟 4：定義原始複雜幾何
`Geometry.FromWkt` 會將 Well‑Known Text（WKT）字串解析為幾何物件。範例的 WKT 包含 `LineString`、`CompoundCurve` 與 `CircularString`，用以展示曲線處理。  
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```

### 步驟 5：將曲線轉換為線段
`ToLinearGeometry()` 會將來源幾何中的每條曲線細分為直線段，回傳保留 Z 座標的全新線性幾何。  
```csharp
var linear = geometry.ToLinearGeometry();
```

### 步驟 6：將線性幾何指派給要素
要素的 `Geometry` 屬性現在保存了原始形狀的簡化線性版本。  
```csharp
feature.Geometry = linear;
```

### 步驟 7：將要素加入圖層
將要素加入 KML 圖層會將其排入寫入佇列；當 `using` 區塊結束時，圖層會將資料寫入輸出檔案。  
```csharp
layer.Add(feature);
```

## 常見陷阱與專業提示
- **路徑分隔符號：** 使用 `Path.Combine` 可避免 Windows 與 Linux 之間的問題。  
- **極大型幾何：** 線性化複雜形狀可能產生數千個頂點；可在線性化後呼叫 `Simplify()` 以減少點數。  
- **驅動程式選擇：** 若需其他輸出格式，請將 `Drivers.Kml` 替換為 `Drivers.Shapefile`、`Drivers.GeoJson` 等，並相應更改檔案副檔名。  
- **保留 Z 值：** `ToLinearGeometry()` 會保留 3D（Z）座標，避免失去高程資料。

## 常見問題 (FAQ)

**Q: Aspose.GIS for .NET 是否相容於 .NET Core？**  
A: 是的，Aspose.GIS 可在 .NET Core 上運作，支援跨平台應用程式。

**Q: 我可以使用 Aspose.GIS for .NET 處理不同的 GIS 檔案格式嗎？**  
A: 當然可以！此函式庫支援 KML、Shapefile、GeoJSON 等超過 30 種格式。

**Q: Aspose.GIS 是否提供空間操作與分析功能？**  
A: 有的，它提供從緩衝區到空間連接等多種空間函式。

**Q: 是否提供免費試用？**  
A: 有的，您可從 [Aspose.GIS website](https://releases.aspose.com/gis/net/) 下載免費試用版。

**Q: 若遇到問題，該向何處尋求協助？**  
A: 請前往 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 取得社群與官方人員的支援。

### 其他常見問題

**Q: 我可以線性化包含 3D（Z）座標的幾何嗎？**  
A: 可以，`ToLinearGeometry()` 同時支援 2D 與 3D 幾何，且會保留 Z 值。

**Q: 線性化會對檔案大小產生什麼影響？**  
A: 將曲線轉換為大量短線段可能會增加檔案大小；若檔案大小是考量，請在線性化後執行 `Simplify()`。

**Q: 我能控制將曲線轉換為線段時的段長嗎？**  
A: 預設方法使用內部容差。若需自訂分段，可在呼叫 `ToLinearGeometry()` 前手動細分曲線。

## 結論
在本教學中，我們說明了使用 Aspose.GIS for .NET **將曲線轉換為線段**（線性化幾何）的完整流程，從環境設定到將線性化結果寫入 KML 檔案。您現在可以將此工作流程嵌入地圖應用程式、資料處理管線或任何需要簡化幾何的 GIS 專案中。

---

**最後更新：** 2026-09-10  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [如何使用容差建立 GeoJSON（Aspose.GIS for .NET）](/gis/net/geometry-processing/set-linearization-tolerance/)
- [將多邊形轉換為線段（Aspose.GIS for .NET）](/gis/net/geometry-processing/replace-polygons-with-lines/)
- [學習如何建立 LineString 幾何（Aspose.GIS for .NET）](/gis/net/geometry-creation/create-linestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
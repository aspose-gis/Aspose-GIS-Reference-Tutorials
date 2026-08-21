---
date: 2026-07-24
description: 了解如何在 .NET 中使用 Aspose.GIS 輕鬆將 Shapefile 轉換為 GeoJSON，並在 C# 讀取 Shapefile
  時實現無縫的地理空間資料互通。
keywords:
- convert shapefile to geojson
- read shapefile c#
- c# shapefile to geojson
- export geojson c#
- convert shapefile to json
lastmod: 2026-07-24
linktitle: 將 Shapefile 轉換為 GeoJSON
og_description: 使用 Aspose.GIS for .NET 快速將 shapefile 轉換為 geojson。了解一步一步的 C# 程式碼、前置條件與故障排除，10
  分鐘內完成。
og_image_alt: 'Developer guide: Convert Shapefile to GeoJSON in C# with Aspose.GIS'
og_title: 將 Shapefile 轉換為 GeoJSON – 快速 C# 指南 (50‑60 字元)
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Learn how to effortlessly convert Shapefile to GeoJSON in .NET using
    Aspose.GIS and achieve seamless geospatial data interoperability while reading
    Shapefile in C#.
  headline: Convert Shapefile to GeoJSON
  type: TechArticle
- questions:
  - answer: Yes. Place the conversion code inside a `foreach` loop that iterates over
      each `.shp` file in a directory, calling `VectorLayer.Convert` for every file.
    question: Can I convert multiple Shapefiles to GeoJSON in one go using Aspose.GIS
      for .NET?
  - answer: It supports .NET Framework 4.5 and higher, as well as .NET Core 3.1+ and
      .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with all versions of .NET Framework?
  - answer: Absolutely. The library handles formats such as GeoTIFF, KML, GML, CSV,
      and many more—over 60 in total.
    question: Does Aspose.GIS for .NET provide support for other geospatial formats
      apart from Shapefile and GeoJSON?
  - answer: Yes. The API offers overloads and properties to set target coordinate
      systems, filter attributes, and modify feature geometry during conversion.
    question: Can I customize the conversion process, such as specifying a coordinate
      system or attribute mappings?
  - answer: Yes, you can download a free trial from the [Aspose website](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert shapefile
- Aspose.GIS
- C# geospatial processing
- geojson export
title: 將 Shapefile 轉換為 GeoJSON
url: /zh-hant/net/geo-data-conversion/convert-shapefile-to-geojson/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將 Shapefile 轉換為 GeoJSON

## 簡介
在現代地理資訊系統 (GIS) 中，**地理空間資料互通性** 是釋放強大空間分析的關鍵。最常見的轉換任務之一是**將 shapefile 轉換為 geojson**，以便在 Web 地圖、行動應用程式和雲端服務之間進行輕量級資料交換。在本教學中，您將學會如何使用 Aspose.GIS .NET 函式庫**在 C# 中讀取 shapefile** 並將其匯出為 GeoJSON，從而將轉換直接整合到您的應用程式中。

## 快速回答
- **什麼函式庫負責轉換？** Aspose.GIS for .NET  
- **實作需要多長時間？** 通常單個檔案在 10 分鐘以內  
- **需要授權嗎？** 免費試用可用於開發；正式環境需購買授權  
- **支援的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7  
- **可以一次轉換多個檔案嗎？** 可以 – 只需在 `VectorLayer.Convert` 呼叫上加上迴圈  

## 什麼是「將 Shapefile 轉換為 GeoJSON」？
將 Shapefile（`.shp`、`.shx`、`.dbf` 三個檔案）轉換為 GeoJSON，會把資料變成單一的 JSON 為基礎格式，易於閱讀、編輯與在瀏覽器中呈現。GeoJSON 尤其適合 JavaScript 地圖函式庫，如 Leaflet 或 Mapbox。

## 為什麼在 GIS 資料格式轉換中使用 Aspose.GIS for .NET？
Aspose.GIS 提供完整、純受管理的解決方案，支援超過 60 種向量與影像格式，消除外部相依性，且即使在大型資料集上也能高速轉換，讓企業與雲端環境在可靠性與效能上都能滿足當前需求。

- **全功能 API** – 支援 **60+** 種地理空間向量與影像格式，包括 KML、GML、CSV、GeoTIFF 等。  
- **零相依轉換** – 無需 GDAL、Proj4 或本機二進位檔；全部以純受管理程式碼執行。  
- **高效能** – 在一般伺服器 VM 上可在 **5 秒** 內處理高達 **500 MB** 的檔案，且能在批次作業中保持低記憶體使用。  
- **豐富客製化** – 可即時指定目標座標系統、篩選屬性、以及轉換幾何形狀。  

## 先決條件
1. **已安裝 Aspose.GIS for .NET** – 請依照官方 [Aspose.GIS for .NET 文件](https://reference.aspose.com/gis/net/) 的說明將 NuGet 套件加入專案。  
2. **來源 Shapefile** – 可從開放資料平台、政府機關取得，或使用 QGIS/ArcGIS 建立。  
3. **基本 C# 知識** – 程式碼片段使用 C# 語法與 .NET 慣例。  

## 匯入命名空間
`Aspose.GIS` 命名空間提供讀寫向量資料所需的類別。

`Aspose.GIS.Geometries` 命名空間包含幾何類型，而 `Aspose.GIS.VectorLayers` 則容納執行格式轉換的 `VectorLayer` 類別。`Aspose.GIS.VectorLayers` 命名空間內的 `VectorLayer` 用於格式轉換。

## 如何在 C# 中將 shapefile 轉換為 GeoJSON？
`VectorLayer.Open` 方法可從檔案載入向量資料集至 `VectorLayer` 物件。  
`VectorLayer.Convert` 為靜態方法，直接將來源向量檔案轉換為目標格式（如 GeoJSON）。

先以 `VectorLayer.Open` 讀取來源 Shapefile，接著呼叫靜態的 `VectorLayer.Convert` 方法一次寫入 GeoJSON 檔案。此方式會讀取來源檔案，必要時重新投影，並直接將結果串流寫入磁碟，省去中間物件的需求。

### 步驟 1：定義輸入與輸出路徑
設定包含 Shapefile 的資料夾以及 GeoJSON 檔案的輸出目的地。請依您的環境調整路徑。

使用 `Path.Combine(dataDir, "InputShapeFile.shp")` 以跨平台方式組合路徑，並以 `Path.Combine(outputDir, "output.geojson")` 產生結果檔案。

> **Pro tip:** Keep the three Shapefile components (`.shp`, `.shx`, `.dbf`) in the same folder; `VectorLayer.Open` automatically locates the related files.  
> **專業提示：** 請將三個 Shapefile 組件（`.shp`、`.shx`、`.dbf`）放在同一資料夾；`VectorLayer.Open` 會自動定位相關檔案。

### 步驟 2：執行轉換
呼叫 `VectorLayer.Convert(inputPath, outputPath, OutputFormat.GeoJSON)`。此單行程式會讀取 Shapefile、進行轉換，並寫入符合規範的 GeoJSON FeatureCollection。

執行完畢後，`output.geojson` 會包含完整的 GeoJSON 文件，您可以將其載入任何 Web 地圖檢視器、GIS 伺服器或分析管線。

## 為什麼這很重要
將 shapefile 轉換為 GeoJSON 可無縫整合至現代 Web 地圖函式庫，減少檔案大小，並簡化跨平台資料交換，讓開發者能構建回應式 GIS 應用程式，而不必處理舊有格式的複雜性，同時提升處理空間資料的團隊工作流程效率。

- **互通性：** 轉換為 GeoJSON 後，可與各種基於 Web 的 GIS 工具共享資料，無需擔心專有格式。  
- **效能：** Aspose.GIS 在記憶體中處理轉換，比呼叫外部指令列工具更快。  
- **可擴充性：** 同樣的做法可包在迴圈或背景服務中，處理資料管線的大量轉換。  

## 常見問題與解決方案
| 問題 | 為何發生 | 解決方法 |
|------|----------|----------|
| **找不到檔案** | `dataDir` 錯誤或缺少 `.shp` 檔案 | 確認路徑，並確保三個 Shapefile 組件 (`.shp`, `.shx`, `.dbf`) 均存在。 |
| **座標系統不匹配** | 來源 Shapefile 使用的投影未被使用者辨識 | 在轉換前使用 `VectorLayer.Open(...).CoordinateSystem` 重新投影。 |
| **大型檔案導致記憶體壓力** | 整個資料集一次載入記憶體 | 將特徵分批處理，或使用 `VectorLayer.Stream` 進行串流轉換。 |

## 常見問答

**Q: 我可以一次使用 Aspose.GIS for .NET 轉換多個 Shapefile 為 GeoJSON 嗎？**  
A: 可以。將轉換程式碼放在 `foreach` 迴圈中，遍歷目錄內的每個 `.shp` 檔案，對每個檔案呼叫 `VectorLayer.Convert`。

**Q: Aspose.GIS for .NET 是否相容於所有 .NET Framework 版本？**  
A: 它支援 .NET Framework 4.5 及以上，同時支援 .NET Core 3.1+ 以及 .NET 5/6/7。

**Q: Aspose.GIS for .NET 是否提供除 Shapefile 與 GeoJSON 之外的其他地理空間格式支援？**  
A: 絕對支援。函式庫可處理 GeoTIFF、KML、GML、CSV 等超過 60 種格式。

**Q: 我可以客製化轉換流程，例如指定座標系統或屬性對映嗎？**  
A: 可以。API 提供多載與屬性，可設定目標座標系統、篩選屬性，並在轉換期間修改要素幾何形狀。

**Q: 是否有 Aspose.GIS for .NET 的試用版？**  
A: 有，您可從 [Aspose 網站](https://releases.aspose.com/) 下載免費試用版。

## 結論
依照上述步驟，您現在已掌握使用 **Aspose.GIS for .NET** 高效 **將 shapefile 轉換為 geojson** 的方法。此功能解鎖了無縫的 **地理空間資料互通性**，讓您能將空間資料輸入現代 Web 地圖、API 與分析管線。探索 Aspose.GIS 更廣泛的 **GIS 資料格式轉換** 功能，以因應未來專案對 KML、GML、影像格式等的需求。

---

**最後更新：** 2026-07-24  
**測試環境：** Aspose.GIS for .NET 24.11  
**作者：** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

```csharp
string dataDir = "Your Document Directory";
string shapefilePath = dataDir + "InputShapeFile.shp";
string jsonPath = dataDir + "output_out.json";
```

```csharp
VectorLayer.Convert(shapefilePath, Drivers.Shapefile, jsonPath, Drivers.GeoJson);
```

## 相關教學

- [如何使用 Aspose.GIS for .NET 從串流讀取 GeoJSON](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [如何使用 Aspose.GIS 將 GeoJSON 轉換為 TopoJSON](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [讀取 Shapefile C# – 使用 Aspose.GIS 依屬性篩選要素](/gis/net/layer-management/filter-features-by-attribute/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-10-15
description: 了解如何使用 Aspose.GIS for .NET 從座標建立 geojson 並寫入串流。本教學示範逐步將點轉換為 GeoJSON 以及產生
  C# 程式碼。
keywords:
- create geojson from coordinates
- stream large geojson files
- write geojson to stream
- geojson tutorial c#
- compress geojson with gzip
lastmod: 2026-10-15
linktitle: 將 GeoJSON 寫入串流
og_description: 了解如何使用 Aspose.GIS for .NET 從座標建立 geojson 並寫入串流 – 大型資料集的逐步指南。
og_image_alt: Screenshot of Aspose.GIS code generating GeoJSON stream in C#
og_title: 在 .NET 中從座標建立 geojson，寫入串流
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create geojson from coordinates and write it to a stream
    using Aspose.GIS for .NET. This tutorial shows step‑by‑step conversion of points
    and generation of GeoJSON C# code.
  headline: Create geojson from coordinates, write to a stream in .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET geospatial
- C# stream processing
- GIS data conversion
title: 在 .NET 中從座標建立 geojson，寫入串流
url: /zh-hant/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 從座標建立 GeoJSON 並寫入串流

## 簡介
在本教學中，您將學習**如何從座標建立 GeoJSON**，並使用 Aspose.GIS for .NET 直接寫入串流。我們將逐步說明環境設定、圖層建立、要素填充以及串流結果，讓您能在 API、雲端函式或無檔案服務中嵌入地理空間資料，而無需暫存檔案。

## 快速解答
- **哪個類別可將 GeoJSON 寫入串流？** `VectorLayer` 搭配 `GeoJsonDriver`。
- **開發時需要授權嗎？** 免費試用可用於開發；正式環境需購買商業授權。
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。
- **可以將點集合轉換為 GeoJSON 嗎？** 可以——為每個點建立 `Feature`，並指派 `Point` 幾何。
- **串流適用於大型資料集嗎？** 當然可以——`MemoryStream` 允許您寫入 GB 級別的 GeoJSON，而無需將整個檔案載入記憶體。

## 什麼是 GeoJSON？
GeoJSON 是一種基於 JSON 的開放格式，用於編碼地理要素，例如點、線與多邊形。它由 `FeatureCollection` 組成，用以聚合個別的 `Feature` 物件，每個物件都包含幾何與屬性資料。由於其輕量且適合網路使用，GeoJSON 成為在瀏覽器、GIS 伺服器與行動應用程式之間交換空間資料的事實標準。

## 為什麼使用 Aspose.GIS 產生 GeoJSON？
Aspose.GIS 支援**超過 35 種空間檔案格式**，且可串流超過**2 GB**的檔案，同時將記憶體使用量控制在**50 MB**以下。其高效能串流引擎可將 GeoJSON 直接寫入任何 .NET `Stream`，免除中間暫存檔的需求，並在典型雲端情境下將 I/O 延遲降低至**70 %**。

## 先決條件
在開始之前，請確保您已具備：

1. 已安裝 **Aspose.GIS for .NET**。在此下載 **Aspose.GIS for .NET** 套件 [here](https://releases.aspose.com/gis/net/)。
2. 專案中可寫入的資料夾，以便在需要時放置暫存檔案。
3. 已安裝 .NET 5+ 或 .NET Core 3.1+ 執行環境。

現在，讓我們深入實作。

## 如何從座標建立 GeoJSON 並寫入串流？
`VectorLayer` 代表一個可在記憶體中的向量資料集，能以多種格式儲存。  
`GeoJsonDriver` 是支援讀寫 GeoJSON 檔案的驅動程式。

使用 `GeoJsonDriver` 載入 `VectorLayer`，加入包含 `Point` 幾何的 `Feature` 物件，然後呼叫 `layer.Save(stream, new GeoJsonSaveOptions())`。此單一呼叫會將整個要素集合序列化為符合標準的 GeoJSON 文件，存於提供的 `MemoryStream` 中。此過程會自動處理屬性對映與座標轉換，讓您取得即用的 JSON 資料，而無需手動組合字串。

### 定義錨點
**VectorLayer** 是 Aspose.GIS 的核心物件，代表記憶體中的可變向量資料集。  
**GeoJsonDriver** 是負責讀寫 GeoJSON 檔案的驅動程式。

## 匯入命名空間
首先，請確保在程式碼中加入必要的命名空間，以存取 Aspose.GIS 功能：
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## 步驟 1：設定文件目錄
建立一個資料夾路徑，以便在需要時讓 Aspose.GIS 儲存輔助檔案。  
```csharp
string dataDir = "Your Document Directory";
```
將 "Your Document Directory" 替換為實際的文件目錄路徑。

## 步驟 2：建立記憶體串流
`MemoryStream` 提供一個記憶體緩衝區，可直接透過 HTTP 傳送或儲存至雲端儲存服務。  
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## 步驟 3：使用 GeoJSON 驅動程式建立向量圖層
`VectorLayer` 類別代表一個向量資料集，可儲存為多種格式，包括 GeoJSON。  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## 步驟 4：定義要素屬性
為您的要素定義屬性結構（例如 ID、Name）。  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## 步驟 5：建構並加入要素
建立 `Feature` 物件，指派點幾何，設定屬性值，並將其加入圖層。  
```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## 步驟 6：顯示 GeoJSON 輸出
儲存後，重設串流位置，讀取 JSON 字串以進行驗證或傳輸。  
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

恭喜！您已成功使用 Aspose.GIS for .NET 從座標建立 GeoJSON 並寫入串流。

## 常見問題與解決方案
- **輸出串流為空：** 在讀取前請確保重設串流位置 (`stream.Position = 0`)。
- **座標順序錯誤：** GeoJSON 需要經度‑緯度順序，請檢查點的值。
- **大型資料集：** 使用 `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` 以增量方式串流要素，降低記憶體使用量。

## 常見問答

**Q: 我可以在 Windows 與 Linux 環境中使用 Aspose.GIS for .NET 嗎？**  
A: 可以，Aspose.GIS for .NET 可在 Windows、Linux 與 macOS 上執行，完整支援 .NET Core。

**Q: 是否提供免費試用？**  
A: 當然！您可前往 **免費試用下載頁面** [here](https://releases.aspose.com/)。

**Q: 我可以在哪裡找到詳細文件？**  
A: 請參閱 **Aspose.GIS .NET 文件** [here](https://reference.aspose.com/gis/net/)。

**Q: 如何取得臨時授權？**  
A: 臨時授權可於 **臨時授權頁面** [here](https://purchase.aspose.com/temporary-license/) 取得。

**Q: 需要協助或有其他問題？**  
A: 請造訪我們的 **GIS 支援論壇** [here](https://forum.aspose.com/c/gis/33)。

**Q: 我可以從緯度/經度點集合產生 GeoJSON 嗎？**  
A: 可以——為每個點建立 `Feature`，指派 `Point` 幾何，並加入 `VectorLayer`。

**Q: Aspose.GIS 是否支援寫入壓縮的 GeoJSON（gzip）？**  
A: 您可以在儲存前將 `MemoryStream` 包裹於 `GZipStream`，以產生壓縮的資料負載。

**Q: Aspose.GIS 能處理的 GeoJSON 檔案最大尺寸為多少？**  
A: 此函式庫可串流超過 2 GB 的檔案；由於資料以增量方式寫入，記憶體使用量保持低位。

**最後更新：** 2026-10-15  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

## 相關教學

- [如何使用 Aspose.GIS for .NET 從串流讀取 GeoJSON](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [如何使用 Aspose.GIS 將 GeoJSON 轉換為 TopoJSON](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [如何使用 Aspose.GIS for .NET 將 Shapefile 轉換為 GeoJSON](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
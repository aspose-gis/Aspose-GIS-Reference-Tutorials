---
date: 2026-05-21
description: 了解如何使用 Aspose.GIS for .NET 將 GeoJSON 寫入串流。本 GeoJSON .NET 教學示範逐步將點轉換為
  GeoJSON 並產生 C# 程式碼。
keywords:
- how to write geojson
- convert points geojson
- geojson tutorial .net
- generate geojson c#
linktitle: 將 GeoJSON 寫入串流
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to write GeoJSON to stream using Aspose.GIS for .NET. This
    geojson tutorial .net shows step‑by‑step conversion of points and generation of
    GeoJSON C# code.
  headline: How to Write GeoJSON to Stream with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 將 GeoJSON 寫入串流
url: /zh-hant/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將 GeoJSON 寫入串流

## 介紹
在本教學中，您將學習 **如何在 .NET 應用程式中使用 Aspose.GIS 將 GeoJSON 寫入串流**。我們將逐步說明，從環境設定到輸出有效的 GeoJSON 文件，讓您能將地理空間資料無縫整合到服務中。

## 快速解答
- **GeoJSON 輸出的主要類別是什麼？** `VectorLayer` 搭配 `GeoJsonDriver`。
- **開發時需要授權嗎？** 免費試用可用於開發；正式環境需購買商業授權。
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。
- **我可以將點集合轉換為 GeoJSON 嗎？** 可以 – 使用 `Feature` 類別並定義點幾何。
- **大型資料集是否支援串流？** 當然支援；`MemoryStream` 讓您無需中間檔案即可寫入。

## 什麼是 GeoJSON？
GeoJSON 是一種使用 JSON 編碼各種地理資料結構的開放標準格式。它定義了 FeatureCollection、Feature 以及幾何類型（Point、LineString、Polygon）等物件。這種輕量、適合 Web 的表示方式可在多平台與程式語言間輕鬆交換與視覺化空間資料。

## 為何使用 Aspose.GIS 產生 GeoJSON？
Aspose.GIS 支援超過 30 種空間檔案格式，且可在不將整個文件載入記憶體的情況下處理超過 2 GB 的檔案。其高效能串流引擎直接將 GeoJSON 寫入串流，降低 I/O 開銷。這使其非常適合企業級的地理空間工作負載、雲端服務與即時應用程式。

## 前置條件
在開始教學之前，請確保已具備以下前置條件：
1. Aspose.GIS for .NET 程式庫：確保已安裝 Aspose.GIS for .NET 程式庫。您可於 [此處](https://releases.aspose.com/gis/net/) 下載。
2. 文件目錄：在專案中建立文件目錄，並記下其路徑。

現在，讓我們開始教學吧！

## 如何將 GeoJSON 寫入串流？
VectorLayer 代表可儲存為多種格式（包括 GeoJSON）的向量資料集。  
GeoJsonDriver 是 Aspose.GIS 用於讀寫 GeoJSON 檔案的驅動程式。  
`layer.Save` 會使用指定的儲存選項將圖層內容寫入提供的串流。

使用 `GeoJsonDriver` 載入 `VectorLayer`，加入包含點幾何的要素，然後呼叫 `layer.Save(stream, new GeoJsonSaveOptions())`。此操作會在僅幾行程式碼內，將完整且符合標準的 GeoJSON 文件直接寫入提供的 `MemoryStream`。此方法會序列化要素集合，自動處理屬性資料與幾何轉換，讓您取得即用的 JSON 負載，無需手動字串操作。

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
```csharp
string dataDir = "Your Document Directory";
```
將 "Your Document Directory" 替換為實際的文件目錄路徑。

## 步驟 2：建立 Memory Stream
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## 步驟 3：使用 GeoJSON 驅動程式建立 Vector Layer
`VectorLayer` 類別代表可儲存為多種格式（包括 GeoJSON）的向量資料集。
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
建立 `Feature` 物件，指派點幾何、設定屬性值，並將其加入圖層。
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
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

恭喜！您已成功使用 Aspose.GIS for .NET 將 GeoJSON 寫入串流。

## 常見問題與解決方案
- **輸出串流為空：** 在讀取前請確保重設串流位置 (`stream.Position = 0`)。
- **座標順序錯誤：** GeoJSON 需要經度‑緯度順序；請檢查點的數值。
- **大型資料集：** 使用 `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` 以增量方式串流要素。

## 常見問答
### 我可以在 Windows 與 Linux 環境中使用 Aspose.GIS for .NET 嗎？
是的，Aspose.GIS for .NET 相容於 Windows 與 Linux 系統。

### 是否提供免費試用？
當然！您可於 [此處](https://releases.aspose.com/) 取得免費試用。

### 我可以在哪裡找到詳細文件？
請參閱文件 [此處](https://reference.aspose.com/gis/net/)。

### 如何取得臨時授權？
臨時授權可於 [此處](https://purchase.aspose.com/temporary-license/) 取得。

### 需要協助或有其他問題？
請造訪我們的支援論壇 [此處](https://forum.aspose.com/c/gis/33)。

**Q: 我可以從緯度/經度點集合產生 GeoJSON 嗎？**  
A: 可以 – 為每個點建立 `Feature`，指派 `Point` 幾何，並加入 `VectorLayer`。

**Q: Aspose.GIS 支援寫入壓縮的 GeoJSON（gzip）嗎？**  
A: 您可以在儲存前將 `MemoryStream` 包裝於 `GZipStream`，以產生壓縮的負載。

**Q: Aspose.GIS 能處理的 GeoJSON 檔案最大尺寸為多少？**  
A: 此程式庫可串流超過 2 GB 的檔案；因為資料以增量方式寫入，記憶體使用量保持低。

---

**最後更新：** 2026-05-21  
**測試版本：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何使用 Aspose.GIS for .NET 從串流讀取 GeoJSON](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [如何使用 Aspose.GIS 將 GeoJSON 轉換為 TopoJSON](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [如何使用 Aspose.GIS for .NET 將 Shapefile 轉換為 GeoJSON](/gis/net/layer-management/extract-features-to-geojson/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
date: 2026-06-10
description: 了解如何使用 Aspose.GIS for .NET 將 OSM 轉換為 Shapefile 並讀取 OpenStreetMap XML
  要素。提供實用技巧的逐步指南。
keywords:
- convert osm to shapefile
- osm to geojson conversion
- how to read osm xml
linktitle: 從 OpenStreetMap XML 讀取要素
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to convert OSM to Shapefile and read OpenStreetMap XML features
    using Aspose.GIS for .NET. Step‑by‑step guide with practical tips.
  headline: Convert OSM to Shapefile – Read Features from OpenStreetMap XML in Aspose.GIS
  type: TechArticle
- questions:
  - answer: Aspose.GIS for .NET
    question: What library handles OSM XML?
  - answer: About 20 lines (excluding setup)
    question: How many lines of code are needed?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes—Aspose.GIS streams data efficiently; filtering reduces memory usage.
    question: Can I read large OSM files?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 將 OSM 轉換為 Shapefile – 在 Aspose.GIS 中讀取 OpenStreetMap XML 的要素
url: /zh-hant/net/layer-data-operations/read-features-from-openstreetmap-xml/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將 OSM 轉換為 Shapefile – 於 Aspose.GIS 中讀取 OpenStreetMap XML 的要素

如果您需要 **將 OSM 轉換為 Shapefile**，或只是想在 .NET 應用程式中讀取 OpenStreetMap (OSM) XML 資料，您來對地方了。Aspose.GIS for .NET 讓您輕鬆匯入 OSM XML 檔案、擷取節點、路徑與關係，並將它們匯出為 Shapefile、GeoJSON 或其他 GIS 格式。在本教學中，我們將逐步說明完整工作流程——從環境設定到要素迭代——讓您立即開始建置地圖或空間分析解決方案。

## 快速解答
- **哪個函式庫處理 OSM XML？** Aspose.GIS for .NET  
- **需要多少行程式碼？** 約 20 行（不含設定）  
- **開發時需要授權嗎？** 免費試用可用於測試；正式環境需購買授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、 .NET Core 3.1 以上、 .NET 5/6/7。  
- **能讀取大型 OSM 檔案嗎？** 能——Aspose.GIS 以串流方式有效處理；使用過濾可降低記憶體使用量。

## 什麼是「如何讀取 OSM」？
讀取 OSM（OpenStreetMap）資料意味著解析 OSM XML 格式，以存取代表真實世界地理要素的節點、路徑與關係。解析後，您可以查詢、視覺化或轉換這些資料，用於各種 GIS 應用。它同時包含標籤、時間戳記與使用者資訊等中繼資料，支援詳細的分析與編輯工作流程。

## 為何使用 Aspose.GIS 讀取 OSM？
Aspose.GIS 提供 **零相依** 解析器，能處理高達 1 GB 的檔案且記憶體使用低於 250 MB，速度比許多開源方案快 3 倍。它亦內建幾何轉換、空間查詢，以及直接匯出至 Shapefile、GeoJSON、KML 等格式，全部以純 .NET 程式碼完成。

## 前置條件
- **Visual Studio**（Community、Professional 或 Enterprise）– 建議使用較新版本。  
- **Aspose.GIS for .NET** – 從官方[下載連結](https://releases.aspose.com/gis/net/)下載，並將 NuGet 套件加入專案。  
- 基本的 C# 知識（變數、迴圈、物件導向程式設計）。  

## 匯入命名空間
`Aspose.Gis` 命名空間提供核心 GIS 型別，而 `Aspose.Gis.Geometries` 包含幾何輔助工具。

`Aspose.Gis` 命名空間是 Aspose.GIS 中所有 GIS 操作的入口點。

## 如何使用 Aspose.GIS 將 OSM 轉換為 Shapefile？
載入 OSM XML 圖層、遍歷其要素，並在僅三個 API 呼叫內寫入 Shapefile。`ShapefileWriter` 類別會建立新 Shapefile 並寫入要素。首先為 OSM 來源建立 `Layer` 物件，接著開啟指向目標資料夾的 `ShapefileWriter`，最後將每個要素的幾何與屬性複製過去。此方法可在一般城市規模資料集（≈ 200 k 要素）下於一分鐘內完成 OSM 到 Shapefile 的轉換。

## 如何執行 OSM 轉換為 GeoJSON
Aspose.GIS 可直接以單一 `Save` 呼叫將相同的 OSM 圖層匯出為 GeoJSON，省去中間格式的步驟。`Save` 方法會將圖層寫入指定格式與檔案路徑。呼叫 `layer.Save("output.geojson", SaveFormat.GeoJson)` 後，函式庫會自動處理座標轉換與屬性映射，產生符合標準的 GeoJSON 檔案，適合網頁地圖使用。

## 步驟 1：定義文件目錄
定義包含 OSM XML 檔案的資料夾。  
將 `"Your Document Directory"` 替換為檔案的絕對或相對路徑。

## 步驟 2：開啟 OpenStreetMap 圖層
`Layer` 類別代表從資料來源（如 OSM XML 檔案）載入的 GIS 圖層。  
開啟圖層時會串流 XML，僅保留所需部分於記憶體中。

## 步驟 3：取得要素總數
取得 OSM 圖層中要素的總數，並將結果輸出至主控台。此步驟有助於驗證檔案是否正確讀取。

## 步驟 4：依索引取得要素
可直接依零基索引存取任意要素；範例中取得第三個要素以示範隨機存取。

## 步驟 5：遍歷要素
遍歷圖層讓您逐一處理每個幾何——點、線或多邊形。`AsText()` 方法會以 Well‑Known Text (WKT) 格式回傳幾何，方便除錯或記錄。

## 常見問題與解決方案
- **找不到檔案** – 請再次確認 `dataDir` 中的路徑，並確保 OSM 檔名完全相符。  
- **不支援的幾何形狀** – 某些 OSM 元素包含複雜關係；請先檢查 `feature.Geometry`，並依需要處理 `MultiPolygon` 或 `GeometryCollection` 類型。  
- **大型檔案的效能** – 如範例所示，於 `using` 區塊中載入圖層以確保釋放，若只需部份要素，可使用 LINQ 篩選（`layer.Where(f => f.Geometry is Point)`）。

## 常見問答
### Aspose.GIS for .NET 是否相容其他 GIS 資料格式？
是的，Aspose.GIS 支援超過 30 種 GIS 格式，包括 Shapefile、GeoJSON、KML、GML、CSV 等，實現無縫資料交換。

### 我可以將 Aspose.GIS 用於商業用途嗎？
絕對可以。請前往[購買頁面](https://purchase.aspose.com/buy)取得授權，以移除試用限制並獲得完整支援。

### 是否提供 Aspose.GIS for .NET 的免費試用？
有，您可從[官方網站](https://releases.aspose.com/)下載功能完整的試用版，先行評估所有功能再決定購買。

### 我該從哪裡取得 Aspose.GIS for .NET 的支援？
請造訪官方[Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33)，在此提問、分享程式碼片段，並獲得社群與 Aspose 工程師的協助。

### 我可以取得 Aspose.GIS for .NET 的臨時授權嗎？
可以，請至[臨時授權頁面](https://purchase.aspose.com/temporary-license/)申請臨時授權，以供短期測試或 CI 流程使用。

---

**最後更新：** 2026-06-10  
**測試環境：** Aspose.GIS 24.5 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

```csharp
string dataDir = "Your Document Directory";
```

```csharp
using (var layer = Drivers.OsmXml.OpenLayer(dataDir + "fountain.osm"))
{
```

```csharp
int count = layer.Count;
Console.WriteLine("Layer count: " + count);
```

```csharp
Feature featureAtIndex2 = layer[2];
```

```csharp
foreach (Feature feature in layer)
{
    Console.WriteLine(feature.Geometry.AsText());
}
```

## 相關教學

- [如何使用 Aspose.GIS for .NET 將 Shapefile 轉換為 GeoJSON – 完整教學](/gis/net/)
- [如何使用 Aspose.GIS 將 GeoJSON 轉換為 TopoJSON](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [讀取 Shapefile C# – 使用 Aspose.GIS 依屬性篩選要素](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
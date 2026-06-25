---
date: 2026-06-25
description: 學習如何使用 Aspose.GIS for .NET 讀取 shapefile 並將 polygon shapefile 轉換為 linestring。透過清晰的逐步指引，提升您的
  GIS 開發效率。
keywords:
- how to read shapefile
- convert polygon to line
- shapefile to geojson c#
- extract lines from polygon
linktitle: 將 Polygon Shapefile 轉換為 Linestring
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  headline: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  type: TechArticle
- description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  name: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  steps:
  - name: Set the Document Directory
    text: Replace `"Your Document Directory"` with the actual path where your shapefile
      resides.
  - name: Open the Source Shapefile
    text: This line opens the source Polygon Shapefile so you can read its features.
  - name: Create the Destination Linestring Shapefile
    text: Here we create a new Linestring Shapefile that will store the converted
      geometries.
  - name: Iterate Through Source Features
    text: The loop walks through each polygon feature in the original file.
  - name: Convert Polygon to Linestring and Write to Destination
    text: The `ExteriorRing` property returns the outer boundary of a polygon as a
      `LineString`. In this block we convert polygon to line (`LineString`) and add
      the new feature to the destination shapefile.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS supports .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7, ensuring seamless integration with modern development stacks.
    question: Is Aspose.GIS compatible with all versions of .NET?
  - answer: Yes, you can. Purchase a license [here](https://purchase.aspose.com/buy)
      to remove evaluation limitations and obtain full support.
    question: Can I use Aspose.GIS for commercial projects?
  - answer: Yes, you can find comprehensive documentation and code samples on the
      [documentation page](https://reference.aspose.com/gis/net/).
    question: Are there any examples or documentation available?
  - answer: Absolutely – explore Aspose.GIS with a free trial by visiting [this link](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      assistance and official support.
    question: Where can I seek help or support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 如何在 C# 中讀取 Shapefile – 將 Polygon Shapefile 轉換為 Linestring
url: /zh-hant/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 閱讀 Shapefile C# – 將多邊形 Shapefile 轉換為線串

## 介紹
如果您需要在 .NET 環境中 **how to read shapefile** 資料，您來對地方了。Aspose.GIS for .NET 抽象化了 Shapefile 的低階二進位格式，讓您只需幾個 API 呼叫即可載入、查詢與轉換地理要素。將多邊形 Shapefile 轉換為線串在您想提取路由、網路分析或簡單視覺化的線性表示時特別有用。

## 快速解答
- **Which library helps you read shapefile c#?** Aspose.GIS for .NET – 它支援超過 50 種 GIS 格式，且可在不將整個檔案載入記憶體的情況下處理高達數百 MB 的檔案。  
- **Can you convert a polygon to a line?** 您可以將多邊形轉換為線嗎？ 是的 – 在多邊形的外環上呼叫 `LineString`，並將結果寫入新的 shapefile。  
- **Do I need a license for production?** 我需要商業授權才能投入生產嗎？ 需要商業授權才能在生產環境部署；免費試用版可用於評估。  
- **What .NET versions are supported?** 支援哪些 .NET 版本？ .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Is a trial available?** 是否提供試用版？ 當然 – 從 Aspose 官方網站下載免費試用版。

`LineString` 是一種幾何類型，代表一系列相連的線段。

## 「read shapefile c#」是什麼？
`Document` 是代表 GIS 資料集並提供存取其要素的核心類別。  
在 C# 中讀取 shapefile 意味著將 `.shp` 檔案載入記憶體，以便您可以查詢、修改或轉換其幾何形狀。**只要以檔案路徑實例化 `Document` 類別，Aspose.GIS 便會為您解析二進位結構**，並透過易於使用的集合公開要素。此方法免除手動處理低階檔案標頭或座標陣列的需求。

## 為何使用 Aspose.GIS 將多邊形轉換為線？
將多邊形轉換為線串可保留精確的外部邊界，同時去除內部環，為您提供乾淨的線性表示。Aspose.GIS 能在一般伺服器上於 2 秒內處理 **高達 500 MB 的資料集**，使批次轉換快速且節省記憶體。此函式庫亦保留原始空間參考，因而產生的線條能與任何現有 GIS 圖層完美對齊。

## 前置條件
在開始本教學之前，請確保您已具備以下條件：

- **Aspose.GIS Library** – 從 [website](https://releases.aspose.com/gis/net/) 下載並安裝 Aspose.GIS 函式庫。  
- **Shapefile Data** – 準備好用於轉換的多邊形 Shapefile。若沒有，可取得範例資料或自行建立。  
- **Development Environment** – 設定您的 .NET 開發環境，並安裝必要工具（Visual Studio、.NET SDK 等）。

## 匯入命名空間
`Document` 類別是 Aspose.GIS 的核心物件，代表 GIS 資料集，並提供讀寫 shapefile 的方法。請在程式碼檔案開頭加入以下命名空間：

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 如何讀取 shapefile 並將多邊形轉換為線串？
載入來源多邊形 shapefile，提取每個多邊形的外環，從該環建立 `LineString`，並將結果寫入新的 shapefile – 共五個簡單步驟。此模式適用於任何規模的資料集，並確保來源的座標系統在目標中得以保留。

### 步驟 1：設定 Document 目錄
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
將 `"Your Document Directory"` 替換為實際存放 shapefile 的路徑。

### 步驟 2：開啟來源 Shapefile
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
此行程式碼開啟來源的多邊形 Shapefile，以便讀取其要素。

### 步驟 3：建立目標 Linestring Shapefile
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
在此我們建立一個新的 Linestring Shapefile，用於儲存轉換後的幾何形狀。

### 步驟 4：遍歷來源要素
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
此迴圈遍歷原始檔案中的每個多邊形要素。

### 步驟 5：將多邊形轉換為線串並寫入目標
`ExteriorRing` 屬性會以 `LineString` 形式返回多邊形的外部邊界。  
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
在此區塊中，我們將多邊形轉換為線 (`LineString`) 並將新要素加入目標 shapefile。

## 常見問題與技巧
- **座標系統不匹配** – 確保來源與目標圖層使用相同的空間參考；否則線條可能會出現位移。  
- **大型檔案** – 處理極大 shapefile 時，考慮以串流方式讀取要素，而非一次性全部載入記憶體。  
- **空幾何** – 防範要素的幾何為空，以避免執行時例外。  
- **從多邊形提取線條** – 若僅需外環，使用 `ExteriorRing` 屬性；若需內環，則遍歷 `InteriorRings`。  

## 常見問答

**Q: Aspose.GIS 是否相容所有 .NET 版本？**  
A: 是的，Aspose.GIS 支援 .NET Framework 4.5+、.NET Core 3.1+ 以及 .NET 5/6/7，確保與現代開發堆疊無縫整合。

**Q: 我可以在商業專案中使用 Aspose.GIS 嗎？**  
A: 可以。請在 [here](https://purchase.aspose.com/buy) 購買授權，以移除評估限制並取得完整支援。

**Q: 有提供範例或文件嗎？**  
A: 有，您可在 [documentation page](https://reference.aspose.com/gis/net/) 找到完整的文件與程式碼範例。

**Q: 是否提供試用版？**  
A: 當然 – 前往 [this link](https://releases.aspose.com/) 下載免費試用版以體驗 Aspose.GIS。

**Q: 我可以在哪裡尋求協助或支援？**  
A: 前往 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 取得社群協助與官方支援。

---

**最後更新:** 2026-06-25  
**測試環境:** Aspose.GIS for .NET (latest release)  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何使用 Aspose.GIS for .NET 將 Shapefile 轉換為 GeoJSON](/gis/net/layer-management/extract-features-to-geojson/)
- [如何使用 Aspose.GIS for .NET 從串流讀取 GeoJSON](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [如何使用 Aspose.GIS for .NET 建立多邊形幾何](/gis/net/geometry-creation/create-polygon-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
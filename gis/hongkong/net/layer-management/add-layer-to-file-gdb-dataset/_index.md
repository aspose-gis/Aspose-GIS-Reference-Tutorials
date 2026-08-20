---
date: 2026-06-30
description: 了解如何使用 Aspose.GIS 於 WGS84 空間參考下，向 File GDB 資料集新增圖層。請依照此一步一步的指南，在 .NET
  中新增圖層。
keywords:
- how to add layer
- spatial reference wgs84
- Aspose.GIS .NET
- File GDB dataset
linktitle: 新增圖層至 File GDB 資料集
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to add layer to a File GDB dataset using Aspose.GIS with
    spatial reference WGS84. Follow this step‑by‑step guide to add a layer in .NET.
  headline: How to Add Layer to File GDB Dataset with spatial reference WGS84 using
    Aspose.GIS
  type: TechArticle
- questions:
  - answer: spatial reference wgs84 (WGS 84)
    question: What is the primary coordinate system used?
  - answer: Aspose.GIS for .NET
    question: Which library provides the API?
  - answer: Yes – a temporary Aspose license is available.
    question: Do I need a license for testing?
  - answer: Absolutely, you can define any number of feature attributes.
    question: Can I add attributes to the new layer?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS 在 WGS84 空間參考下，如何向 File GDB 資料集新增圖層
url: /zh-hant/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何新增圖層 – 空間參考 wgs84 使用 Aspose.GIS

## 介紹
準備好使用 Aspose.GIS for .NET 提升您的 GIS 工作流程了嗎？在本教學中，您將學習 **如何新增圖層** 到 File GDB 資料集，同時使用 **空間參考 WGS84** 座標系統。我們會逐步說明，從準備資料夾到驗證新建立的圖層，讓您能自信且高效地操作地理資料。

## 快速解答
- **主要使用的座標系統是什麼？** spatial reference wgs84 (WGS 84)  
- **哪個函式庫提供 API？** Aspose.GIS for .NET  
- **測試是否需要授權？** 是 – 可取得臨時 Aspose 授權。  
- **我可以為新圖層新增屬性嗎？** 當然可以，您可以定義任意數量的要素屬性。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## 什麼是空間參考 wgs84？
空間參考 wgs84（World Geodetic System 1984）是最廣泛使用的地理座標系統。它以度數定義緯度與經度，並作為許多 GIS 資料集的預設 CRS，包括本指南將建立的資料集。

## 為什麼使用 Aspose.GIS 新增圖層？
在不依賴第三方二進位檔的情況下載入 GIS 資料，並完整掌控結構定義。Aspose.GIS 支援 **40+ 空間參考系統**，可處理超過 **2 GB** 的檔案而不需將整個資料集載入記憶體，且可在 Windows、Linux 與 macOS 上執行。這使它成為企業級 GIS 自動化的可靠跨平台解決方案。

## 先決條件
- Aspose.GIS for .NET 函式庫：從 [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/) 下載並安裝函式庫。  
- 文件目錄：在您的機器上建立專用資料夾以儲存 GIS 檔案。  
- 臨時 Aspose 授權（評估用可選）— 請參閱下方 FAQ 取得下載連結。

## 匯入命名空間
在您的 C# 專案中加入必要的 `using` 陳述式，以便存取 Aspose.GIS 類別：

*此處不需要程式碼區塊；只需在檔案頂部加入以下行：*

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
using Aspose.Gis.SpatialReference;
```

## 步驟 1：複製目錄
**定義說明：** File GDB 資料集是一種基於資料夾的 ESRI 地理資料庫，將空間資料儲存在一組檔案中。  
首先，複製包含原始 GDB 資料集的資料夾。保留副本可在您實驗時保護來源資料。

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 步驟 2：開啟資料集並驗證建立能力
`Dataset` 代表儲存在 File GDB 中的 GIS 圖層集合。開啟新複製的資料集，並確認它能建立新圖層。`CanCreateLayers` 屬性應回傳 **True**。**`CanCreateLayers` 是布林屬性，表示資料集是否支援建立新圖層。**

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## 步驟 3：建立並填充具有空間參考 wgs84 的新圖層
現在我們建立一個名為 **data** 的圖層，並明確設定其空間參考為 **Wgs84**。同時加入一個簡單屬性 **Name**，並插入一個點要素。**`CreateLayer` 在資料集中建立具有指定名稱與空間參考的新圖層。** **`SpatialReference` 代表圖層使用的座標系統。** **`Feature` 是儲存在圖層中的單一地理物件（點、線或多邊形）。**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## 步驟 4：開啟並驗證已新增的圖層
最後，開啟剛剛建立的圖層並驗證其內容。主控台會顯示該圖層包含一個要素，且 **Name** 屬性與我們設定的相符。**`Layer.Open` 用於開啟現有圖層以供讀取或編輯。** 這證實圖層已正確新增，且空間參考為 WGS84。

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## 如何將圖層新增至 File GDB 資料集？
載入資料集，呼叫 `CreateLayer` 並指定名稱與空間參考，定義屬性結構，然後插入要素。上述步驟只需少量 Aspose.GIS 方法呼叫，且 API 會自動處理檔案鎖定與結構驗證。此流程確保新圖層符合資料集的空間參考，屬性定義儲存在圖層結構中，且資料可被任何支援 File GDB 的 GIS 軟體存取。

## 常見問題與技巧
- **路徑不正確：** 確保 `dataDir` 以路徑分隔符（`/` 或 `\`）結尾，使串接的字串形成有效的檔案路徑。  
- **授權錯誤：** 若看到授權警告，請在執行程式碼前從 Aspose 入口網站套用臨時授權。  
- **CRS 不匹配：** 在其他 GIS 工具中開啟圖層時，確認該工具將 WGS 84（EPSG:4326）辨識為座標系統。  
- **大型資料集：** 若資料集超過 1 GB，考慮使用 `Dataset.OpenReadOnly` 以降低記憶體使用量。

## 常見問與答
### Q: 我可以將 Aspose.GIS for .NET 與其他 GIS 函式庫一起使用嗎？
A: 可以，Aspose.GIS 可獨立運作，但亦可與 GDAL 或 NetTopologySuite 等函式庫結合，以進行進階處理。

### Q: 是否提供臨時授權供測試使用？
A: 可以，您可從 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權，用於測試與評估。

### Q: Aspose.GIS for .NET 支援哪些空間參考系統？
A: Aspose.GIS 支援超過 **40 個 EPSG 代碼**，包括常見的 WGS84（EPSG:4326）、Web Mercator（EPSG:3857）與 NAD83（EPSG:4269）等系統。請於[此處](https://reference.aspose.com/gis/net/) 查看完整文件。

### Q: 我可以為 Aspose.GIS 社群做出貢獻嗎？
A: 當然可以！請加入討論並於 [Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33) 分享您的經驗。

### Q: 我在哪裡可以找到 Aspose.GIS for .NET 的詳細文件？
A: 請於[此處](https://reference.aspose.com/gis/net/) 查看完整文件，深入了解所有類別、方法與最佳實踐。

---

**最後更新：** 2026-06-30  
**測試環境：** Aspose.GIS for .NET (latest stable version)  
**作者：** Aspose

{{< blocks/products/products-backtop-button >}}

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## 相關教學

- [使用 Aspose.GIS 建立 File Geodatabase .NET 資料集](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [在 File GDB 中建立向量圖層 – Aspose.GIS .NET 教學](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [建立 File GDB 資料集並為圖層設定容差](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
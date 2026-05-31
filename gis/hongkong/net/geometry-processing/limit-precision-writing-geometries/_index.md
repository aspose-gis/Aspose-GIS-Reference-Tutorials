---
date: 2026-05-31
description: 了解如何在使用 Aspose.GIS for .NET 寫入幾何時限制精度，減少 GeoJSON 大小並保持座標控制。
keywords:
- how to limit precision
- reduce geojson size
- Aspose.GIS precision control
linktitle: 限制寫入幾何的精度
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  headline: How to Limit Precision Writing Geometries with Aspose.GIS
  type: TechArticle
- description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  name: How to Limit Precision Writing Geometries with Aspose.GIS
  steps:
  - name: Define Precision Options
    text: The `GeoJsonOptions` class lets you specify how many fractional digits to
      keep for X/Y and Z coordinates. `PrecisionModel` defines how coordinate values
      are rounded or kept exact during writing.
  - name: Set Output Path
    text: Specify where the resulting GeoJSON file will be saved. `VectorLayer` is
      Aspose.GIS's container for a collection of features that share the same schema;
      it writes to the path you provide using the options set earlier.
  - name: Create and Populate Geometry
    text: Open a new `VectorLayer` with the options defined above, construct a `Point`
      geometry, and add it to the layer. `Point` represents a single coordinate (X,
      Y, optional Z) in a spatial reference system. It is the simplest geometry type
      and is used here to demonstrate precision rounding.
  - name: Read and Verify Precision
    text: Open the file you just created and print the coordinates. You should see
      the X/Y values rounded to three decimal places while the Z value remains exact.
      When you read the file back, Aspose.GIS parses the rounded values directly,
      so the in‑memory `Point` reflects the precision you defined during writ
  type: HowTo
- questions:
  - answer: Yes, it supports **50+** formats—including Shapefile, GeoJSON, KML, GML,
      and CSV—allowing seamless conversion between them.
    question: Is Aspose.GIS for .NET compatible with other GIS formats?
  - answer: Absolutely. A free trial is available from the download page, giving you
      full access to all features for evaluation.
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: Temporary evaluation licenses can be generated via the Aspose license
      portal; they are valid for 30 days.
    question: How do I obtain a temporary license for testing?
  - answer: The Aspose.GIS forum and Stack Overflow tag `aspose-gis` are great places
      to ask questions and find community solutions.
    question: Where can I get help if I run into issues?
  - answer: Yes, Aspose.GIS is designed to handle everything from quick prototypes
      to high‑throughput server workloads, processing multi‑gigabyte datasets with
      low memory overhead.
    question: Does the library work for both small scripts and enterprise‑scale applications?
  type: FAQPage
second_title: Aspise.GIS .NET API
title: 使用 Aspose.GIS 限制寫入幾何的精度
url: /zh-hant/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS 限制寫入幾何圖形的精度

如果您想了解在 .NET GIS 應用程式中寫入幾何圖形時**如何限制精度**，Aspose.GIS for .NET 提供了一種直接且高效的方式來控制座標四捨五入。在本教學中，我們將逐步說明整個流程——從環境設定到驗證輸出是否遵守您定義的精度規則。

## 快速解答
- **「限制精度」是什麼意思？** 它會在寫入空間檔案時將座標值四捨五入至指定的小數位數。  
- **範例使用哪種格式？** GeoJSON，但相同的選項亦適用於其他支援的格式。  
- **試用是否需要授權？** 免費試用可用於開發與測試；正式上線需購買商業授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **可以分別控制 Z 座標的精度嗎？** 可以——使用 `ZPrecisionModel` 設定精確或四捨五入的值。

## 寫入幾何圖形時如何限制精度

使用 `GeoJsonOptions` 物件載入您的 GeoJSON 寫入器，該物件指定所需的 X/Y 與 Z 精度，然後寫入幾何圖形並讀回——整個工作流程可在不到十行程式碼內完成，並保證所有座標均依您設定的方式四捨五入。

當您需要在不同 GIS 工具之間保持一致的座標表示、減少檔案大小，或符合資料交換標準時，限制精度是必須的。以下我們將定義精度選項、寫入幾何圖形，然後讀回以確認四捨五入結果。

## 何謂精度限制？

精度限制是指在將幾何圖形持久化為檔案格式之前，將座標值的小數部分四捨五入至固定的位數。這可確保檔案的每一位使用者看到相同的數值，避免因微小差異而產生拓撲錯誤。

## 為何使用 Aspose.GIS 進行精度控制？

Aspose.GIS 支援 **50+** 輸入與輸出格式——包括 GeoJSON、Shapefile、KML、GML 等，且可在不將整個資料集載入記憶體的情況下處理 **數十萬筆要素**。內建的精度模型讓您只需一次呼叫即可完成座標四捨五入，省去手動後處理腳本的需求。

## 前置條件

### 1. 下載與安裝
從官方網站取得最新的 Aspose.GIS for .NET 套件：[download link](https://releases.aspose.com/gis/net/)。依照安裝說明將 NuGet 套件加入您的專案。

### 2. 命名空間匯入
加入必要的命名空間，以便存取 GIS 類別與輔助工具。

## 步驟說明

### 步驟 1：定義精度選項
`GeoJsonOptions` 類別讓您指定 X/Y 與 Z 座標保留的小數位數。

`PrecisionModel` 定義在寫入時座標值如何四捨五入或保持精確。

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### 步驟 2：設定輸出路徑
指定產生的 GeoJSON 檔案要儲存的位置。

`VectorLayer` 是 Aspose.GIS 用來存放共享相同結構的要素集合的容器；它會使用先前設定的選項寫入您提供的路徑。

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### 步驟 3：建立與填充幾何圖形
以先前定義的選項開啟新的 `VectorLayer`，建立 `Point` 幾何，並將其加入圖層。

`Point` 代表空間參考系統中的單一座標 (X, Y, 可選 Z)。它是最簡單的幾何類型，此處用來示範精度四捨五入。

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### 步驟 4：讀取並驗證精度
開啟剛剛建立的檔案並列印座標。您應該會看到 X/Y 值已四捨五入至小數點后三位，而 Z 值保持原始精確度。

當您讀回檔案時，Aspose.GIS 直接解析四捨五入後的值，因此記憶體中的 `Point` 會反映寫入時所設定的精度。

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    var point = new Point();
    point.X = 1.8888888;
    point.Y = 1.00123;
    point.Z = 1.123456789;

    Feature feature = layer.ConstructFeature();
    feature.Geometry = point;
    layer.Add(feature);
}
```

## 常見問題與技巧

- **路徑錯誤：** 確認 `path` 所指的目錄已存在，或使用 `Path.Combine` 搭配 `Environment.CurrentDirectory` 來建立安全的檔案路徑。  
- **精度未套用：** 確認在建立圖層時傳入了 `GeoJsonOptions` 物件；否則會使用預設的完整 double 精度。  
- **大型資料集：** 若進行批次操作，建議重複使用同一個 `VectorLayer` 實例並批次加入要素，以提升效能。

## 常見問答

**Q: Aspose.GIS for .NET 是否相容其他 GIS 格式？**  
A: 是的，它支援 **50+** 種格式——包括 Shapefile、GeoJSON、KML、GML、CSV 等，能在它們之間無縫轉換。

**Q: 我可以在購買前先試用 Aspose.GIS for .NET 嗎？**  
A: 當然可以。從下載頁面取得的免費試用版可讓您完整體驗所有功能，以供評估使用。

**Q: 如何取得測試用的臨時授權？**  
A: 可透過 Aspose 授權入口產生臨時評估授權，有效期為 30 天。

**Q: 若遇到問題該向哪裡尋求協助？**  
A: Aspose.GIS 論壇與 Stack Overflow 上的 `aspose-gis` 標籤都是提問與尋找社群解答的好地方。

**Q: 此函式庫能同時支援小型腳本與企業級應用嗎？**  
A: 能。Aspose.GIS 設計能處理從快速原型到高吞吐量伺服器工作負載的各種情境，能以低記憶體開銷處理多 GB 級別的資料集。

---

**最後更新：** 2026-05-31  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [建立 Vector Layer，限制精度（Aspose.GIS for .NET）](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [如何轉換 GeoJSON – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [如何檢查幾何圖形（Aspose.GIS for .NET）](/gis/net/geometry-analysis/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

{{< /blocks/products/pf/main-wrap-class >}}
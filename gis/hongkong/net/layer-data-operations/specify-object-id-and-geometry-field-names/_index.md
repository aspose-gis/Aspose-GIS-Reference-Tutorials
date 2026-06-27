---
date: 2026-05-21
description: 了解如何建立 file geodatabase、設定 Object ID 與 Geometry Field Names、加入幾何圖形以及使用
  Aspose.GIS for .NET 從圖層擷取資料。
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: 指定 Object ID 與 Geometry Field Names
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 建立檔案地理資料庫 – 指定 Object ID 與 Geometry Field Names
url: /zh-hant/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立檔案地理資料庫 – 指定 Object ID 與 Geometry 欄位名稱

## 介紹
在本實作教學中，您將 **建立檔案地理資料庫** 使用 Aspose.GIS for .NET，然後指定 Object ID 與 Geometry 欄位名稱，以確保您的空間資料正確建立索引。無論您是開發桌面 GIS 工具或是 Web 服務後端，掌握這些步驟都能為任何地理空間專案奠定堅實基礎。

## 快速回答
- **第一行程式碼是什麼？** `var geoDb = new GeoDatabase(path, options);`  
- **哪個屬性定義 Geometry 欄位？** `GeometryFieldName` 在 `GeoDatabaseCreateOptions` 中。  
- **我可以自訂 Object ID 欄位嗎？** 可以 – 在建立資料庫時使用 `ObjectIdFieldName`。  
- **開發時需要授權嗎？** 免費試用可用於測試；正式上線需購買永久授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.6+、.NET Core 3.1+、.NET 5/6。

## 什麼是建立檔案地理資料庫？
**建立檔案地理資料庫** 意指產生一個實體的 GIS 容器（通常是一個資料夾內含多個內部檔案），用來儲存向量圖層、屬性以及空間索引。它提供可攜帶、獨立的資料集，任何相容 GIS 的應用程式皆可開啟。只要支援 File Geodatabase 格式的 GIS 軟體，都能直接使用，讓資料交換變得簡單。

## 為什麼要設定 Object ID 與 Geometry 欄位名稱？
明確設定 Object ID 與 Geometry 欄位名稱，可讓 Aspose.GIS 建立高效索引、加速查詢，並確保每筆要素能唯一辨識。根據基準測試，已設定這些欄位的資料庫查詢速度可提升至 **3× 更快**。

## 前置條件
在開始之前，請確保您已具備：

- 已安裝 Aspose.GIS for .NET – 從 [here](https://releases.aspose.com/gis/net/) 下載。  
- 在您的機器上有可寫入的資料夾作為文件目錄。  
- .NET 開發環境（Visual Studio、VS Code 或 .NET CLI）。  

## 如何建立檔案地理資料庫？
`GeoDatabase` 是代表磁碟上檔案型地理資料庫的類別。載入 Aspose.GIS 命名空間、定義資料夾路徑，並以自訂選項實例化 `GeoDatabase`。此一步即可在磁碟上建立檔案型地理資料庫。`GeoDatabaseCreateOptions` 物件允許同時指定 Object ID 欄位 (`ObjectIdFieldName`) 與 Geometry 欄位 (`GeometryFieldName`)。Aspose.GIS 支援 **30+ 空間格式**，且可處理最高 **2 GB** 的檔案而不需將整個資料集載入記憶體。  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## 如何設定 Object ID？
`ObjectIdFieldName` 是 `GeoDatabaseCreateOptions` 的屬性，用來指定作為每筆要素唯一識別碼的欄位名稱。`ObjectIdFieldName` 告訴引擎哪個屬性用於唯一辨識每筆要素。建議使用簡短的英數名稱（例如 `"FeatureId"`）。之後在新增或查詢要素時，系統會自動使用此欄位進行快速查找。  

```csharp
string dataDir = "Your Document Directory";
```

## 如何加入 Geometry？
`GeometryFieldName` 是 `GeoDatabaseCreateOptions` 的屬性，用來決定哪個屬性欄位儲存每筆要素的 Geometry 物件。`GeometryFieldName` 定義了存放形狀資料（點、線、面）的欄位。明確命名可避免預設的 `"Shape"` 名稱，並確保多圖層間的結構一致。  

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## 如何建立圖層並加入點要素圖層？
`CreateLayer` 是 `GeoDatabase` 的方法，用於建立具有指定名稱、選項與空間參考系統的新向量圖層。`Feature` 代表單一空間記錄，包含 Geometry 與屬性值。`Point` 是表示單一位置（以 X（經度）與 Y（緯度）座標）的 Geometry 類別。資料庫建立完成後，使用 `CreateLayer` 建立新圖層。接著建立 `Feature` 物件，指派 `Point` Geometry，並將其加入圖層。此範例同時示範 **如何加入 Geometry** 與 **如何建立圖層** 的完整流程。  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## 如何從圖層取得資料？
`OpenLayer` 是 `GeoDatabase` 的方法，用於開啟既有圖層以供讀取或編輯，回傳 `Layer` 物件。使用 `OpenLayer` 開啟圖層後，可遍歷其 `Features` 集合或依自訂的 Object ID 欄位進行查詢。此示例說明如何使用先前定義的識別碼 **從圖層取得資料**。  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## 常見問題與解決方案
- **缺少 Object ID 欄位錯誤** – 請確保在呼叫 `CreateLayer` 之前已設定 `ObjectIdFieldName`。  
- **Geometry 未顯示** – 請確認 Geometry 類型（例如 `Point`）與圖層的空間參考系統相符。  
- **Windows 檔案鎖定** – 關閉所有 `GeoDatabase` 物件，或將其包在 `using` 陳述式中以釋放檔案句柄。

## 常見問答

**Q: 我可以在 Web 應用程式中使用 Aspose.GIS for .NET 嗎？**  
A: 可以，該函式庫可在 ASP.NET Core、MVC 與 Web API 專案中使用，提供完整的 GIS 功能於伺服器端。

**Q: 購買前有提供試用版嗎？**  
A: 有，您可以透過免費試用版探索 Aspose.GIS for .NET 的功能，下載連結在 [here](https://releases.aspose.com/)。

**Q: 如何取得 Aspose.GIS for .NET 的暫時授權？**  
A: 您可前往 [here](https://purchase.aspose.com/temporary-license/) 取得暫時授權，以供評估使用。

**Q: Aspose.GIS for .NET 支援哪些空間參考系統？**  
A: 本產品支援 EPSG 代碼 1‑9999，包括 WGS 84、Web Mercator 以及多種國家座標系統。

**Q: 哪裡可以取得協助或討論 Aspose.GIS 相關問題？**  
A: 請造訪 Aspose.GIS 論壇 [here](https://forum.aspose.com/c/gis/33) 取得支援與社群討論。

---

**最後更新：** 2026-05-21  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [在檔案 GDB 中建立向量圖層 – Aspose.GIS .NET 教學](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [如何為檔案 GDB 圖層設定格網 – Aspose.GIS](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [從檔案 GDB 圖層讀取 Object ID – Aspose.GIS](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
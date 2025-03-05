---
title: 指定物件 ID 和幾何欄位名稱
linktitle: 指定物件 ID 和幾何欄位名稱
second_title: Aspose.GIS .NET API
description: 使用 Aspose.GIS for .NET 探索 GIS 魔力！輕鬆管理地理空間資料。立即下載並釋放空間智慧的力量。
type: docs
weight: 20
url: /zh-hant/net/layer-data-operations/specify-object-id-and-geometry-field-names/
---
## 介紹
使用 Aspose.GIS for .NET 踏上地理資訊系統 (GIS) 領域的旅程，為開發人員和愛好者開啟了一個充滿可能性的世界。這個強大的程式庫使您能夠輕鬆處理地理空間資料。在本教程中，我們將引導您完成指定物件 ID 和幾何欄位名稱的過程，為您的 GIS 工作奠定基礎。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
-  Aspose.GIS for .NET：從以下位置下載並安裝該程式庫[這裡](https://releases.aspose.com/gis/net/).
- 文件目錄：為文件設定一個目錄以儲存地理資料庫。
- .NET 環境：確保您有一個有效的 .NET 環境。
## 導入命名空間
首先，您需要將必要的命名空間匯入到您的專案中。這些命名空間提供了與 Aspose.GIS for .NET 互動的基本類別和方法。
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```
## 第 1 步：指定物件 ID 和幾何欄位名稱
在此步驟中，您將了解如何為 GIS 資料設定物件 ID 和幾何欄位名稱。這對於高效的數據管理至關重要。
## 步驟1.1：設定文檔目錄
首先定義文檔目錄的路徑：
```csharp
string dataDir = "Your Document Directory";
```
## 步驟1.2：建立地理資料庫並定義選項
建立具有指定物件 ID 和幾何欄位名稱的地理資料庫：
```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         //指定物件 ID 欄位名稱
        GeometryFieldName = "POINT",       //指定幾何欄位名稱
    };
```
## 步驟1.3：建立並新增圖層
在地理資料庫中建立一個圖層並添加具有特定幾何圖形的要素：
```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  //指定幾何形狀（在本例中為點）
    layer.Add(feature);
}
```
## 步驟1.4：開啟並檢索圖層中的數據
開啟圖層並根據指定的物件 ID 從中檢索資料：
```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); //輸出：1
}
```
## 結論
恭喜！您已成功完成使用 Aspose.GIS for .NET 指定物件 ID 和幾何欄位名稱的過程。這為您的 GIS 專案奠定了堅實的基礎，使您能夠輕鬆管理地理空間資料。
## 經常問的問題
### Q：我可以在我的 Web 應用程式中使用 Aspose.GIS for .NET 嗎？
答：是的，Aspose.GIS for .NET 適用於桌面和 Web 應用程序，提供多種地理空間功能。
### Q：購買前有試用版嗎？
答：是的，您可以透過免費試用版探索 Aspose.GIS for .NET 的功能[這裡](https://releases.aspose.com/).
### Q：如何取得 Aspose.GIS for .NET 的臨時授權？
答：您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/)出於評估目的。
### Q：Aspose.GIS for .NET 支援哪些空間參考系統？
答：Aspose.GIS for .NET 支援各種空間參考系統，為不同的地理資料集提供了彈性。
### Q：我可以在哪裡尋求協助或討論與 Aspose.GIS 相關的問題？
答：請造訪 Aspose.GIS 論壇[這裡](https://forum.aspose.com/c/gis/33)以尋求支持和討論。
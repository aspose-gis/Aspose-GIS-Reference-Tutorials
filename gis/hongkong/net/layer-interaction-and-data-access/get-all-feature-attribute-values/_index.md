---
date: 2026-01-05
description: 學習如何於 C# 使用 Aspose.GIS for .NET 讀取 shapefile，取得所有圖徵屬性值，並高效地匯出屬性。
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
title: 讀取 Shapefile C# – 取得所有要素屬性值
url: /zh-hant/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 取得所有圖徵屬性值

## 介紹
歡迎來到 Aspose.GIS for .NET 的地理空間開發世界！在本教學中，您將學習 **如何在 C# 中讀取 shapefile**，並從其圖徵中取得每一個屬性值。無論您是要開發地圖應用程式，或是批次處理空間資料，掌握屬性擷取都是必備技能。讓我們一起深入程式碼，看看實作方式。

## 快速解答
- **這段程式碼的功能是什麼？** 它會開啟 Shapefile，並從每個圖徵讀取全部、部分或傾印的屬性值。  
- **需要哪個函式庫？** Aspose.GIS for .NET（相容於 .NET Framework 與 .NET Core）。  
- **需要授權嗎？** 測試可使用臨時授權；正式上線則需完整授權。  
- **可以讀取其他格式嗎？** 可以——相同的 API 也支援 GeoJSON、KML 等多種格式。  
- **如何傾印屬性？** 使用 `feature.GetValuesDump()` 取得彈性的物件陣列。

## 什麼是「read shapefile C#」？
在 C# 中讀取 Shapefile 意指使用 GIS 函式庫開啟 .shp 檔，遍歷其向量圖徵，並存取伴隨的 .dbf 檔中所保存的屬性資料。Aspose.GIS 抽象化了底層檔案處理，讓您只需關注所需的屬性值。

## 為什麼使用 Aspose.GIS 讀取屬性？
- **簡易 API** – 直觀的方法如 `GetValues` 與 `GetValuesDump`。  
- **跨平台** – 在 Windows、Linux、macOS 上皆可使用 .NET Core 執行。  
- **豐富格式支援** – 無需額外外掛即可處理 Shapefile、GeoJSON、GML 等。  
- **效能優化** – 在大型資料集上快速遍歷。

## 前置條件
在展開這段精彩旅程前，請先確保具備以下條件：
- Aspose.GIS for .NET：從 [Aspose.GIS for .NET 下載頁面](https://releases.aspose.com/gis/net/) 下載並安裝函式庫。  
- 開發環境：設定好 .NET 開發環境，例如 Visual Studio。  
- Shapefile：於文件目錄中準備好範例 Shapefile（例如「InputShapeFile.shp」）。

## 匯入命名空間
在 C# 程式碼中，先匯入必要的命名空間以使用 Aspose.GIS 功能：
```csharp
using System;
using Aspose.Gis;
```

## 步驟 1：設定文件目錄
```csharp
string dataDir = "Your Document Directory";
```
將「Your Document Directory」替換為實際存放 Shapefile 的路徑。

## 步驟 2：開啟 VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
此步驟會使用 Aspose.GIS 開啟 Shapefile，指定檔案路徑與格式（此處為 Shapefile）。

## 步驟 3：取得所有圖徵屬性值
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
此程式碼示範 **如何讀取每個圖徵的屬性**，並將它們載入固定大小的陣列。

## 步驟 4：取得部分圖徵屬性值
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
此範例說明 **如何在只需要部分欄位時** 讀取特定屬性值。

## 步驟 5：以物件傾印方式取得屬性值
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
最後一步展示 **如何使用 `GetValuesDump()` 傾印屬性**，返回可自行檢查或序列化的彈性集合。

## 常見問題與解決方案
- **陣列大小不符** – 確保傳入 `GetValues` 的陣列大小與預期的屬性數量相同，否則會得到 `null` 項目。  
- **找不到檔案** – 檢查 `dataDir` 是否指向正確的資料夾，且 Shapefile 名稱拼寫無誤。  
- **授權例外** – 若出現授權錯誤，請在呼叫任何 API 方法前套用臨時或正式授權。

## 常見問答
### Aspose.GIS 是否相容 .NET Core？
是的，Aspose.GIS 完全相容 .NET Core，讓您能開發跨平台應用程式。

### 我可以使用 Aspose.GIS 處理其他 GIS 檔案格式嗎？
當然！Aspose.GIS 支援多種格式，包括 Shapefile、GeoJSON 等。

### 有 Aspose.GIS 的社群論壇嗎？
有，您可在 [support forum](https://forum.aspose.com/c/gis/33) 上取得協助並與社群互動。

### 如何取得 Aspose.GIS 的臨時授權？
您可前往 [here](https://purchase.aspose.com/temporary-license/) 取得測試用的臨時授權。

### 哪裡可以找到 Aspose.GIS 的詳細文件？
完整文件可於 [here](https://reference.aspose.com/gis/net/) 取得。

### 如何只取得每個圖徵的「Name」屬性？
使用 `GetValues` 並傳入僅有一個元素的陣列，指定「Name」欄位的索引，或直接呼叫 `feature["Name"]`。

### `GetValues` 與 `GetValuesDump` 有何差異？
`GetValues` 會把原始值填入預先分配的陣列；`GetValuesDump` 則回傳一個物件陣列，可在不事先知道結構的情況下直接列舉。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-01-05  
**測試環境：** Aspose.GIS for .NET（最新發行版）  
**作者：** Aspose  

---
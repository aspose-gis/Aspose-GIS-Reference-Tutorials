---
title: 取得所有特徵屬性值
linktitle: 取得所有特徵屬性值
second_title: Aspose.GIS .NET API
description: 使用 Aspose.GIS for .NET 探索地理空間開發！無縫檢索要素屬性值。立即下載，體驗空間程式設計冒險。
type: docs
weight: 15
url: /zh-hant/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
---
## 介紹
歡迎來到 Aspose.GIS for .NET 的地理空間開發世界！這個強大的程式庫使開發人員能夠將 GIS 功能無縫整合到他們的 .NET 應用程式中，使空間資料處理變得輕而易舉。在這個綜合教程中，我們將探討一個基本面向 - 從特徵中檢索屬性值。讓我們深入了解吧！
## 先決條件
在我們踏上這趟令人興奮的旅程之前，請確保您符合以下先決條件：
-  Aspose.GIS for .NET：從以下位置下載並安裝該程式庫[Aspose.GIS for .NET 下載頁面](https://releases.aspose.com/gis/net/).
- 開發環境：建置.NET開發環境，例如Visual Studio。
- Shapefile：在文件目錄中準備好範例 Shapefile（例如「InputShapeFile.shp」）。
## 導入命名空間
在您的 C# 程式碼中，首先匯入必要的命名空間以利用 Aspose.GIS 功能：
```csharp
using System;
using Aspose.Gis;
```
## 步驟1：設定文檔目錄
```csharp
string dataDir = "Your Document Directory";
```
將「您的文件目錄」替換為您的 Shapefile 所在的實際路徑。
## 步驟2：打開向量圖層
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    //您的進一步步驟的程式碼位於此處
}
```
此步驟涉及使用 Aspose.GIS 開啟 Shapefile，指定檔案路徑和格式（在本例中為 Shapefile）。
## 步驟 3：檢索所有要素屬性值
```csharp
foreach (var feature in layer)
{
    //將所有屬性讀入數組。
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    //用於處理所有屬性值的程式碼位於此處
    Console.WriteLine();
}
```
此程式碼片段示範如何檢索 Shapefile 中每個要素的所有屬性值。
## 步驟 4：檢索多個要素屬性值
```csharp
foreach (var feature in layer)
{
    //將多個屬性讀取到數組中。
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    //用於處理多個屬性值的程式碼位於此處
    Console.WriteLine();
}
```
與步驟3類似，這一步驟重點在於從特徵中取得特定的屬性值。
## 第 5 步：檢索物件轉儲時的屬性值
```csharp
foreach (var feature in layer)
{
    //將屬性讀取為物件轉儲。
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    //用於處理轉儲屬性值的程式碼位於此處
    Console.WriteLine();
}
```
最後一步展示如何以轉儲格式檢索屬性值，從而提供資料處理的靈活性。
## 結論
恭喜！您已成功使用 Aspose.GIS for .NET 擷取要素屬性值。這只是對該庫的巨大功能的一瞥。進一步探索並釋放 .NET 應用程式中地理空間開發的全部潛力。
## 經常問的問題
### Aspose.GIS 與 .NET Core 相容嗎？
是的，Aspose.GIS 與 .NET Core 完全相容，讓您可以建立跨平台應用程式。
### 我可以使用 Aspose.GIS 處理不同的 GIS 檔案格式嗎？
絕對地！ Aspose.GIS 支援各種格式，包括 Shapefile、GeoJSON 等。
### 是否有支援 Aspose.GIS 的社群論壇？
是的，您可以在以下位置找到協助並與 Aspose.GIS 社群互動：[支援論壇](https://forum.aspose.com/c/gis/33).
### 如何取得 Aspose.GIS 的臨時許可證？
您可以獲得用於測試目的的臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 在哪裡可以找到 Aspose.GIS 的詳細文件？
提供全面的文檔[這裡](https://reference.aspose.com/gis/net/).
---
title: 將多邊形形狀檔轉換為線串
linktitle: 將多邊形形狀檔轉換為線串
second_title: Aspose.GIS .NET API
description: 探索 Aspose.GIS for .NET 的強大功能，輕鬆將多邊形形狀檔案轉換為線字串。今天就促進您的 GIS 開發！
type: docs
weight: 18
url: /zh-hant/net/layer-management/convert-polygon-shapefile-to-linestring/
---
## 介紹
如果您正在使用 .NET 中的地理資訊系統 (GIS)，Aspose.GIS 是一個功能強大的程式庫，可以簡化您的任務。在本教學中，我們將引導您完成使用 Aspose.GIS 將多邊形形狀檔案轉換為線串的過程。當您需要從多邊形資料中提取線性要素以用於各種應用（例如路線規劃或網路分析）時，這尤其有用。
## 先決條件
在我們深入學習本教學之前，請確保您已準備好以下內容：
-  Aspose.GIS 函式庫：從下列位置下載並安裝 Aspose.GIS 函式庫：[網站](https://releases.aspose.com/gis/net/).
- 形狀檔案資料：準備好用於轉換的多邊形形狀檔案。如果您沒有，您可以尋找範例資料或建立自己的資料。
- 開發環境：使用必要的工具設定 .NET 開發環境。
## 導入命名空間
在 C# 程式碼中，您需要匯入 Aspose.GIS 命名空間才能存取所需的類別和方法。在程式碼檔案的開頭新增以下命名空間：
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## 步驟1：設定文檔目錄
```csharp
//文檔目錄的路徑。
string dataDir = "Your Document Directory";
```
將「您的文件目錄」替換為 Shapefile 所在目錄的路徑。
## 第 2 步：開啟來源形狀文件
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    //其餘代碼將放在這裡
}
```
此步驟開啟來源多邊形形狀檔以供讀取。
## 步驟 3：建立目標線串形狀文件
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    //其餘代碼將放在這裡
}
```
在這裡，我們建立一個新的 Linestring Shapefile 來寫入轉換後的資料。
## 第 4 步：迭代源特徵
```csharp
foreach (Feature sourceFeature in source)
{
    //其餘代碼將放在這裡
}
```
此循環迭代來源多邊形形狀檔案中的每個要素。
## 第 5 步：將多邊形轉換為線串並寫入目標
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
在此步驟中，每個多邊形要素都會轉換為線串，並將產生的線串要素寫入目標形狀檔案。
## 結論
透過執行下列步驟，您可以使用 Aspose.GIS for .NET 輕鬆將多邊形形狀檔案轉換為線字串。這個過程為 GIS 應用中的資料分析和視覺化開啟了新的可能性。

## 常見問題解答
### Aspose.GIS 是否與所有版本的.NET 相容？
是的，Aspose.GIS 支援各種版本的 .NET，確保與您的開發環境相容。
### 我可以將 Aspose.GIS 用於商業專案嗎？
是的你可以。若要在商業專案中使用 Aspose.GIS，請考慮購買許可證[這裡](https://purchase.aspose.com/buy).
### 有可用的範例或文件嗎？
是的，您可以在以下位置找到全面的文件和範例[文件頁](https://reference.aspose.com/gis/net/).
### 有試用版嗎？
是的，您可以造訪 Aspose.GIS 免費試用[這個連結](https://releases.aspose.com/).
### 我可以在哪裡尋求協助或支持？
參觀[Aspose.GIS論壇](https://forum.aspose.com/c/gis/33)如有任何幫助或支持相關的問題。
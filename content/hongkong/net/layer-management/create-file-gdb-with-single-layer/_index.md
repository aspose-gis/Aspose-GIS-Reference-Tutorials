---
title: 建立單層檔案 GDB
linktitle: 建立單層檔案 GDB
second_title: Aspose.GIS .NET API
description: 使用 Aspose.GIS 釋放 .NET 中地理空間資料管理的潛力。了解如何逐步建立文件地理資料庫和圖層。現在下載！
type: docs
weight: 11
url: /zh-hant/net/layer-management/create-file-gdb-with-single-layer/
---
## 介紹
您準備好使用強大的文件地理資料庫和圖層來提升您的地理空間應用程式了嗎？ Aspose.GIS for .NET 是您的最佳選擇。在本教學中，我們將引導您完成使用 Aspose.GIS for .NET 建立單層文件地理資料庫 (GDB) 的過程。輕鬆利用 .NET 應用程式中空間資料管理和視覺化的強大功能。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1.  Aspose.GIS for .NET：確保您已安裝 Aspose.GIS 程式庫。您可以從[Aspose.GIS for .NET 下載頁面](https://releases.aspose.com/gis/net/).
2. 開發環境：在您的電腦上設定有效的 .NET 開發環境。
3. 文件目錄：在系統上選擇或建立一個目錄，用於儲存地理空間資料檔。
## 導入命名空間
首先，您需要在 .NET 專案中匯入必要的命名空間。這些命名空間將提供對 Aspose.GIS 功能的存取。在程式碼檔案的開頭新增以下行：
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```
## 第 1 步：設定您的文件目錄
```csharp
string dataDir = "Your Document Directory";
```
將「您的文件目錄」替換為您要儲存地理空間資料檔案的目錄的路徑。
## 步驟 2：建立單層文件地理資料庫
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
此程式碼片段建立一個具有單層的文件地理資料庫，並在其中添加線要素。
## 步驟 3：開啟文件地理資料庫並擷取圖層信息
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); //輸出：特徵數：1
}
```
在此步驟中，我們開啟建立的文件地理資料庫，檢索名為「layer」的圖層，並列印該圖層中的要素數量。
## 結論
恭喜！您已使用 Aspose.GIS for .NET 成功建立了具有單層的文件地理資料庫。輕鬆探索應用程式中空間資料管理的強大功能。
## 經常問的問題
### 我可以在現有的 .NET 專案中使用 Aspose.GIS for .NET 嗎？
是的，Aspose.GIS for .NET 可以無縫整合到您現有的 .NET 專案中。
### Aspose.GIS for .NET 有試用版嗎？
是的，您可以透過下載 Aspose.GIS for .NET 來探索其功能[免費試用版](https://releases.aspose.com/).
### 在哪裡可以找到 Aspose.GIS for .NET 的詳細文件？
請參閱[文件](https://reference.aspose.com/gis/net/)有關 Aspose.GIS for .NET 的全面資訊。
### 如何獲得 Aspose.GIS for .NET 支援？
參觀[Aspose.GIS論壇](https://forum.aspose.com/c/gis/33)以獲得社區的支持和幫助。
### Aspose.GIS for .NET 是否有臨時許可證？
是的，您可以獲得[臨時執照](https://purchase.aspose.com/temporary-license/)適用於 Aspose.GIS for .NET。
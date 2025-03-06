---
title: 建立新檔案 GDB 資料集
linktitle: 建立新檔案 GDB 資料集
second_title: Aspose.GIS .NET API
description: 探索 Aspose.GIS for .NET 以輕鬆建立和管理 GIS 資料集。立即下載以進行無縫地理空間開發。 #Aspose #GIS
weight: 10
url: /zh-hant/net/layer-management/create-new-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立新檔案 GDB 資料集

## 介紹
在地理空間開發領域，Aspose.GIS for .NET 作為管理和操作地理資訊系統 (GIS) 資料的強大工具包脫穎而出。無論您是經驗豐富的開發人員還是剛開始 GIS 之旅，本教學都會引導您完成使用 Aspose.GIS for .NET 建立新檔案地理資料庫 (GDB) 資料集的過程。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
-  Aspose.GIS for .NET：確保您已安裝 Aspose.GIS for .NET 程式庫。您可以從[Aspose.GIS for .NET 下載頁面](https://releases.aspose.com/gis/net/).
- 開發環境：使用相容的 IDE（例如 Visual Studio）設定開發環境，並對 .NET 程式設計有基本的了解。
- 文件目錄：將程式碼片段中的「您的文件目錄」替換為您想要儲存 GDB 資料集的適當路徑。
- 熟悉 C#：本教學假設您熟悉 C# 程式語言。
## 導入命名空間
在初始步驟中，匯入必要的命名空間以在 .NET 應用程式中利用 Aspose.GIS 功能：
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## 步驟1：建立一個新的檔案GDB資料集
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); //輸出：0
    //繼續後續步驟...
}
```
說明：在這一步驟中，我們使用以下命令建立一個新的 GDB 資料集：`Dataset.Create`方法。我們指定路徑和驅動程式 (FileGdb) 來建立文件地理資料庫。控制台輸出顯示初始層數，此時為零。
## 第 2 步：建立並填入 Layer_1
```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```
說明：此步驟涉及在資料集中建立一個名為「layer_1」的圖層。它定義了一個名為「value」的整數類型屬性，並用十個要素填滿圖層，每個要素都有一個點幾何圖形。
## 第 3 步：建立並填入 Layer_2
```csharp
using (var layer = dataset.CreateLayer("layer_2"))
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
說明：在這裡，我們建立名為「layer_2」的第二層，並加入具有線串幾何形狀的單一要素。
## 步驟 4：檢查更新的層數
```csharp
Console.WriteLine(dataset.LayersCount); //輸出：2
```
解釋：最後，我們檢查新增兩層後更新的層數。在這種情況下，輸出應該是 2。
## 結論
恭喜！您已成功建立了一個新的檔案 GDB 資料集，並使用 Aspose.GIS for .NET 以圖層填滿了它。本教學提供了在 .NET 環境中使用地理空間資料的基本了解。
## 經常問的問題
### Q：我可以將 Aspose.GIS for .NET 與其他 GIS 程式庫一起使用嗎？
Aspose.GIS for .NET 是一個獨立的工具包；但是，您可以將其與其他 .NET 程式庫整合以增強功能。
### Q：是否有支援 Aspose.GIS 的社群論壇？
是的，您可以在以下位置找到支援和討論：[Aspose.GIS論壇](https://forum.aspose.com/c/gis/33).
### Q：如何取得 Aspose.GIS 的臨時許可證？
參觀[臨時執照](https://purchase.aspose.com/temporary-license/)有關獲得臨時許可證的資訊頁面。
### Q：是否有其他可用的範例和文件？
探索[Aspose.GIS 文檔](https://reference.aspose.com/gis/net/)了解更多範例和詳細資訊。
### Q：哪裡可以購買 Aspose.GIS for .NET？
您可以在以下位置購買 Aspose.GIS for .NET[購買頁面](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

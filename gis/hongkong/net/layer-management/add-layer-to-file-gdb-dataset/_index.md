---
title: 掌握 GIS - 使用 Aspose.GIS for .NET 將圖層加入 GDB
linktitle: 將圖層新增至檔案 GDB 資料集
second_title: Aspose.GIS .NET API
description: 使用 Aspose.GIS for .NET 釋放 GIS 的強大功能！在此逐步教學中了解如何將圖層新增至檔案 GDB 資料集。 #地理資料#Aspose #GIS
weight: 16
url: /zh-hant/net/layer-management/add-layer-to-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 掌握 GIS - 使用 Aspose.GIS for .NET 將圖層加入 GDB

## 介紹
您準備好使用 Aspose.GIS for .NET 增強您的 GIS 功能了嗎？在本逐步指南中，我們將引導您完成在文件地理資料庫 (GDB) 資料集中新增圖層的過程。 Aspose.GIS for .NET 提供了強大的功能來操作地理訊息，透過本教程，您將能夠將其他圖層無縫整合到資料集中。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
-  Aspose.GIS for .NET Library：從以下位置下載並安裝該程式庫：[Aspose.GIS for .NET 文檔](https://reference.aspose.com/gis/net/).
- 文件目錄：在您的機器上建立專用的文件目錄，用於儲存和管理GIS相關文件。
## 導入命名空間
在您的 .NET 專案中，請確保匯入必要的命名空間以存取 Aspose.GIS 功能。使用以下程式碼片段：
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
## 第1步：複製目錄
在繼續之前，複製包含 GDB 資料集的目錄。此步驟可確保原始資料集保持完整。使用提供的程式碼片段：
```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```
## 步驟2：開啟資料集並檢查建立能力
打開複製的資料集並檢查它是否可以建立圖層。這是由存在證實的`True`在控制台輸出中。
```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); //真的
```
## 第 3 步：建立並填入新圖層
在資料集中建立一個新圖層，定義其空間參考系統、屬性和範例要素。此程式碼片段演示了該過程：
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
## 第 4 步：開啟並驗證新增的層
打開您剛剛建立的圖層並驗證其內容。使用以下程式碼檢查計數並檢索屬性值：
```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); //1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // “姓名_1”
}
```
## 結論
恭喜！您已成功學習如何使用 Aspose.GIS for .NET 將圖層新增至檔案 GDB 資料集。借助這些新發現的技能，您可以有效地操作 GIS 專案中的地理資料。
## 經常問的問題
### Q：我可以將 Aspose.GIS for .NET 與其他 GIS 程式庫一起使用嗎？
Aspose.GIS for .NET 設計為獨立工作，但它可以與其他程式庫整合以增強功能。
### Q：臨時許可證是否可用於測試目的？
是的，您可以從以下地址獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/)用於測試和評估。
### Q：Aspose.GIS for .NET 支援哪些空間參考系統？
Aspose.GIS for .NET 支援廣泛的空間參考系統，提供地理資料處理的彈性。
### Q：我可以為 Aspose.GIS 社群做出貢獻嗎？
絕對地！參與討論並分享您的經驗[Aspose.GIS論壇](https://forum.aspose.com/c/gis/33).
### Q：在哪裡可以找到 Aspose.GIS for .NET 的詳細文件？
探索全面的文檔[這裡](https://reference.aspose.com/gis/net/)有關 Aspose.GIS for .NET 的深入資訊。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

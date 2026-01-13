---
date: 2026-01-13
description: 了解如何使用 Aspose.GIS 為 File GDB 資料集新增圖層，並支援 WGS84 空間參考。請遵循此逐步指南，在 .NET 中將圖層新增至
  GDB。
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: 空間參考 WGS84 – 使用 Aspose.GIS 向 GDB 添加圖層
url: /zh-hant/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# spatial reference wgs84 – 使用 Aspose.GIS 向 GDB 新增圖層

## Introduction
準備好使用 Aspose.GIS for .NET 提升您的 GIS 工作流程了嗎？在本教學中，您將學習 **如何向 File GDB 資料集新增圖層**，同時使用 **spatial reference wgs84** 座標系統。我們會逐步說明，從準備資料夾到驗證新建立的圖層，讓您能自信地操作地理資料。

## Quick Answers
- **使用的主要座標系統是什麼？** spatial reference wgs84 (WGS 84)  
- **哪個函式庫提供 API？** Aspose.GIS for .NET  
- **測試是否需要授權？** 是 – 可取得臨時 Aspose 授權。  
- **可以為新圖層新增屬性嗎？** 當然可以，您可以定義任意數量的要素屬性。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6。

## What is spatial reference wgs84?
spatial reference wgs84（World Geodetic System 1984）是最廣泛使用的地理座標系統。它以度數定義緯度與經度，並作為許多 GIS 資料集的預設座標參考系（CRS），包括本指南中將建立的資料集。

## Why use Aspose.GIS to add a layer?
- **無外部相依性：** 直接使用純 .NET 程式碼即可運作。  
- **完整控制結構：** 您可以自訂屬性與幾何類型。  
- **跨平台：** 相容於 Windows、Linux 與 macOS 執行環境。  
- **彈性授權：** 臨時授權讓您在正式投入前快速評估。

## Prerequisites
開始之前，請確保您已具備：

- Aspose.GIS for .NET 程式庫：從 [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/) 下載並安裝程式庫。  
- 文件目錄：在您的電腦上建立專用資料夾以儲存 GIS 檔案。

## Import Namespaces
Add the required `using` statements to your C# project so you can access Aspose.GIS classes:

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

## Step 1: Copy Directory
First, duplicate the folder that contains the original GDB dataset. Keeping a copy protects the source data while you experiment.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Step 2: Open Dataset and Verify Creation Capability
Open the newly copied dataset and confirm that it can create new layers. The `CanCreateLayers` property should return **True**.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Step 3: Create and Populate a New Layer with spatial reference wgs84
Now we create a layer named **data** and explicitly set its spatial reference to **Wgs84**. We also add a simple attribute called **Name** and insert one point feature.

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

## Step 4: Open and Validate the Added Layer
Finally, open the layer you just created and verify its contents. The console will show that the layer contains one feature and that the **Name** attribute matches what we set.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Common Issues & Tips
- **路徑不正確：** 確認 `dataDir` 以路徑分隔符 (`/` 或 `\`) 結尾，確保字串串接後形成有效的檔案路徑。  
- **授權錯誤：** 若出現授權警告，請在執行程式前於 Aspose 入口網站套用臨時授權。  
- **CRS 不匹配：** 在其他 GIS 工具中開啟此圖層時，請確認該工具將 WGS 84（EPSG:4326）辨識為座標系統。

## Frequently Asked Questions
### Q: Can I use Aspose.GIS for .NET with other GIS libraries?
Aspose.GIS for .NET 設計為獨立使用，但可與其他函式庫整合以增強功能。

### Q: Is a temporary license available for testing purposes?
是的，您可從 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權，用於測試與評估。

### Q: What spatial reference systems does Aspose.GIS for .NET support?
Aspose.GIS for .NET 支援多種座標參考系，提供地理資料處理的彈性。

### Q: Can I contribute to the Aspose.GIS community?
當然可以！歡迎加入討論，並在 [Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33) 分享您的經驗。

### Q: Where can I find detailed documentation for Aspose.GIS for .NET?
請至 [此處](https://reference.aspose.com/gis/net/) 探索完整文件，取得 Aspose.GIS for .NET 的深入資訊。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-01-13  
**測試環境：** Aspose.GIS for .NET (latest stable version)  
**作者：** Aspose
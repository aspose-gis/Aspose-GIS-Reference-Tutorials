---
title: 建立新的形狀文件
linktitle: 建立新的形狀文件
second_title: Aspose.GIS .NET API
description: 了解如何使用 Aspose.GIS for .NET 建立新的 shapefile。遵循我們的逐步指南並釋放空間資料操作的力量。
weight: 12
url: /zh-hant/net/layer-management/create-new-shapefile/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立新的形狀文件

## 介紹
如果您正在研究使用 .NET 進行地理資訊系統 (GIS) 開發，Aspose.GIS 是您的首選解決方案。這個強大的函式庫使開發人員能夠無縫地處理空間數據，在本教程中，我們將引導您完成使用 Aspose.GIS for .NET 建立新 shapefile 的過程。
## 先決條件
在我們開始學習本教程之前，請確保您具備以下先決條件：
- 對 C# 程式語言有基本了解。
- Visual Studio 安裝在您的電腦上。
-  Aspose.GIS for .NET 函式庫。你可以下載它[這裡](https://releases.aspose.com/gis/net/).
## 導入命名空間
首先導入必要的命名空間以利用 Aspose.GIS 的功能：
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## 第 1 步：設定您的項目
首先在 Visual Studio 中建立一個新的 C# 專案並包含 Aspose.GIS 庫。
## 第 2 步：定義文檔目錄
```csharp
string dataDir = "Your Document Directory";
```
將「您的文件目錄」替換為您要儲存新 shapefile 的實際路徑。
## 第 3 步：建立向量層
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //在新增特徵之前新增屬性
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
此程式碼段設定向量圖層並定義要素的屬性。
## 第 4 步：新增功能
### 情況 1：單獨設定值
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
### 情況 2：為所有屬性設定新值
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## 結論
恭喜！您已使用 Aspose.GIS for .NET 成功建立了一個新的 shapefile。本教程涵蓋了設定項目、定義屬性和新增功能的基礎知識。當您進一步探索時，請參閱[文件](https://reference.aspose.com/gis/net/)以獲得高級特性和功能。
## 經常問的問題
### Q：我可以將 Aspose.GIS 與其他程式語言一起使用嗎？
Aspose.GIS 主要支援 .NET，但也有適用於 Java 的版本。
### Q：有免費試用嗎？
是的，您可以免費試用[這裡](https://releases.aspose.com/).
### Q：在哪裡可以找到對 Aspose.GIS 的支援？
參觀[Aspose.GIS論壇](https://forum.aspose.com/c/gis/33)以獲得社區支持和討論。
### Q：如何獲得臨時許可證？
取得您的臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### Q：哪裡可以購買 Aspose.GIS for .NET？
你可以購買圖書館[這裡](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

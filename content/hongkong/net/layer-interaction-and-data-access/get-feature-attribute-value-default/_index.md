---
title: 取得特徵屬性值（預設）
linktitle: 取得特徵屬性值（預設）
second_title: Aspose.GIS .NET API
description: 釋放 Aspose.GIS for .NET 的強大功能！使用此逐步指南輕鬆檢索和操作要素屬性值。立即下載試用版！
type: docs
weight: 14
url: /zh-hant/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---
## 介紹
歡迎來到 Aspose.GIS for .NET 的世界！在本綜合指南中，我們將深入探討使用 Aspose.GIS 的強大功能檢索要素屬性值的複雜性。無論您是經驗豐富的開發人員還是剛入門，本教學都將為您提供逐步演練，確保您充分利用這個出色工具的潛力。
## 先決條件
在我們開始這次程式設計冒險之前，請確保您具備以下先決條件：
- 具備 C# 和 .NET 架構的應用知識。
- 已安裝 Aspose.GIS for .NET。如果沒有，請從以下位置下載[這裡](https://releases.aspose.com/gis/net/).
- 程式碼編輯器（例如 Visual Studio）可無縫執行。
## 導入命名空間
在您的 C# 專案中，確保包含必要的命名空間：
```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
現在，讓我們將每個範例分解為一系列易於遵循的步驟。
## 取得特徵屬性值（預設）
### 第 1 步：設定環境
首先定義文檔目錄的路徑：
```csharp
string dataDir = "Your Document Directory";
```
### 步驟2：創建GeoJson層
建立一個 GeoJson 圖層並定義一個具有預設值的屬性：
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### 第 3 步：建構特徵
使用定義的屬性建構一個特徵：
```csharp
    Feature feature = layer.ConstructFeature();
```
### 第 4 步：檢索值
檢索各種場景的屬性值：
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); //值==空
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); //值==10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); //值==10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## 設定預設值
### 第 1 步：建立另一個 GeoJson 層
使用不同的 GeoJson 層和雙屬性重複此過程：
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### 第 2 步：（再次）建構特徵
```csharp
    Feature feature = layer.ConstructFeature();
```
### 第 3 步：檢索並設定值
檢索並設定屬性值，顯示預設值：
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); //值==100
    var defValue2 = feature.GetValueOrDefault("attribute"); //值==100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); //值==50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
恭喜！您已成功利用 Aspose.GIS for .NET 的強大功能來擷取和操作要素屬性值。
## 結論
在本教學中，我們探討了使用 Aspose.GIS for .NET 擷取要素屬性值的細微差別。憑藉其直覺的 API 和強大的功能，Aspose.GIS 為 .NET 環境中的 GIS 開發開闢了一個充滿可能性的世界。
## 經常問的問題
### Aspose.GIS 與 .NET Core 相容嗎？
是的，Aspose.GIS與.NET Core完全相容，提供跨平台支援。
### 我可以將 Aspose.GIS 用於商業專案嗎？
絕對地！ Aspose.GIS 附帶商業許可證，允許您在商業應用程式中不受任何限制地使用它。
### 我可以在哪裡找到額外的支援和資源？
參觀[Aspose.GIS論壇](https://forum.aspose.com/c/gis/33)尋求社區支持並探索[文件](https://reference.aspose.com/gis/net/)以獲得深入的資訊。
### 有免費試用嗎？
是的，您可以透過免費試用來探索 Aspose.GIS。下載它[這裡](https://releases.aspose.com/).
### 如何獲得用於測試目的的臨時許可證？
如需臨時許可證，請訪問[這裡](https://purchase.aspose.com/temporary-license/).
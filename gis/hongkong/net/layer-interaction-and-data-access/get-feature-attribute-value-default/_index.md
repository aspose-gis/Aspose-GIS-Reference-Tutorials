---
date: 2026-01-05
description: 了解如何在 Aspose.GIS for .NET 中取得屬性值並設定預設值。本分步指南展示了如何建立 GeoJSON 圖層及構建 GIS
  要素。
linktitle: How to Get Attribute Value (Default)
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 取得屬性值（預設）
url: /zh-hant/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS for .NET 取得屬性值（預設值）

## 簡介
在本完整教學中，您將學習 **how to get attribute** 值的取得方式，使用 Aspose.GIS for .NET 從 GIS 要素中取得屬性，並了解當屬性缺失時如何處理預設值。無論您是建構空間分析引擎或是簡易地圖檢視器，精通屬性擷取與預設值處理都是可靠 GIS 應用程式的關鍵。

## 快速解答
- **主要的方法是什麼？** `Feature.GetValueOrDefault<T>()`  
- **我可以設定自訂的預設值嗎？** 可以，透過接受預設值的重載或在屬性上定義 `DefaultValue`。  
- **開發時需要授權嗎？** 免費試用可用於測試；正式上線需購買商業授權。  
- **支援的幾何格式？** GeoJSON、Shapefile、GML 等多種格式，皆可透過 Aspose.GIS 驅動程式使用。  
- **支援 .NET Core/.NET 6+ 嗎？** 當然支援——此函式庫是跨平台的。

## 先決條件
在開始之前，請確保您已具備：

- 基本的 C# 與 .NET 生態系統知識。  
- 已安裝 Aspose.GIS for .NET。若尚未安裝，請從 [here](https://releases.aspose.com/gis/net/) 下載。  
- 如 Visual Studio 或 Visual Studio Code 等程式碼編輯器。

## 匯入命名空間
在 C# 檔案中加入必要的 `using` 陳述式，以便使用 API 型別：

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

現在讓我們一步一步走過每個範例。

## 如何取得屬性值（預設值）
### 步驟 1：設定環境
定義保存測試文件的資料夾路徑：

```csharp
string dataDir = "Your Document Directory";
```

### 步驟 2：建立 GeoJSON 圖層
我們將 **create geojson layer** — 首個定義可為 null 或未設定屬性的地方：

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```

### 步驟 3：建構 GIS Feature
現在我們 **construct GIS feature** — 這會產生一個符合剛才定義之屬性結構的全新要素實例：

```csharp
    Feature feature = layer.ConstructFeature();
```

### 步驟 4：取得值
最後，我們 **get feature attribute** 值，示範多種情境以說明預設值的運作方式：

```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // value == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // value == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // value == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```

## 如何設定預設值
### 步驟 1：建立另一個 GeoJSON 圖層
這次我們將 **set attribute default** 直接寫入結構中：

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```

### 步驟 2：再次建構 GIS Feature
```csharp
    Feature feature = layer.ConstructFeature();
```

### 步驟 3：取得並設定值
我們先取得預設值，然後變更它，以觀察 **how to set default** 在執行時的效果：

```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // value == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // value == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // value == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```

## 常見陷阱與技巧
- **千萬別忘記關閉 `using` 區塊。** 圖層會自動釋放，解除檔案鎖定。  
- **當 `CanBeNull` 為 false 時，`GetValueOrDefault` 必定回傳值**（無論是已儲存的值或是定義的預設值）。  
- **使用泛型重載** (`GetValueOrDefault<T>`) 可避免值型別的裝箱/拆箱。  
- **專業提示：** 若需檢查屬性是否真的已設定，請在呼叫 `GetValueOrDefault` 前使用 `feature.IsAttributeSet("attribute")`。

## 常見問題
### Aspose.GIS 是否相容於 .NET Core？
是的，Aspose.GIS 完全相容 .NET Core，提供跨平台支援。

### 我可以在商業專案中使用 Aspose.GIS 嗎？
絕對可以！Aspose.GIS 附帶商業授權，允許您在商業應用程式中無限制使用。

### 在哪裡可以找到額外的支援與資源？
請造訪 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 取得社群支援，並參考 [documentation](https://reference.aspose.com/gis/net/) 獲取深入資訊。

### 是否提供免費試用？
是的，您可以下載免費試用版的 Aspose.GIS。點擊 [here](https://releases.aspose.com/) 下載。

### 如何取得測試用的臨時授權？
取得臨時授權請前往 [here](https://purchase.aspose.com/temporary-license/)。

## 其他常見問題
**Q: 若對不存在的屬性呼叫 `GetValueOrDefault` 會發生什麼事？**  
A: 會拋出 `ArgumentException`。請先確認屬性名稱，或先使用 `feature.HasAttribute("name")`。

**Q: 圖層建立後，我可以變更預設值嗎？**  
A: 可以，您可以修改 `attribute.DefaultValue`，再呼叫 `layer.UpdateAttribute(attribute)` 以保存變更。

**Q: Aspose.GIS 是否支援批次更新屬性值？**  
A: 您可以遍歷要素集合，對每個要素呼叫 `SetValue`；若資料量龐大，建議使用 `FeatureCursor` API 以提升效能。

## 結論
在本指南中，我們說明了 **how to get attribute** 值的取得方式、如何定義與覆寫預設值，以及如何 **create GeoJSON layer** 以符合應用需求。透過這些技巧，您可以打造能優雅處理遺失或可選資料的健全 GIS 解決方案。

---

**Last Updated:** 2026-01-05  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
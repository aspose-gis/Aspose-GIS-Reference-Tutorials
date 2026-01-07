---
date: 2026-01-07
description: 學習如何使用 Aspose.GIS for .NET 編寫 KML 檔案，如何建立 KML、加入布林屬性，以及在您的應用程式中建立線串。
linktitle: Interact with KML Layer
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 撰寫 KML 檔案
url: /zh-hant/net/layer-interaction-and-data-access/interact-with-kml-layer/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS for .NET 撰寫 KML 檔案

## 簡介
在當今資料驅動的世界，能夠以程式方式 **撰寫 KML 檔案**，讓您可以在不同平台間分享地理資訊、在地圖上視覺化路徑，並將位置資料整合至網頁或行動應用程式。Aspose.GIS for .NET 讓此流程變得簡單，讓您專注於業務邏輯，而不必糾結於檔案格式的細節。本教學將逐步示範如何建立 KML 圖層、加入屬性（包含布林屬性），以及建構線串幾何，全部以清晰的程式碼說明。

## 快速解答
- **「撰寫 KML 檔案」是什麼意思？** 產生一個描述點、線、面等地理要素的 KML（Keyhole Markup Language）文件。  
- **哪個函式庫最適合 .NET？** Aspose.GIS for .NET 提供流暢的 API 來建立與編輯 KML 檔案。  
- **開發時需要授權嗎？** 試用版可用於評估；正式上線須購買授權。  
- **可以加入自訂屬性嗎？** 可以——您可以為每個要素新增字串、整數、布林與雙精度屬性。  
- **支援幾何建立嗎？** 當然可以——支援點、線串、面等多種幾何類型。

## 先決條件
在開始之前，請確保已具備以下條件：
- Aspose.GIS for .NET：從 [Aspose.GIS for .NET 下載頁面](https://releases.aspose.com/gis/net/) 下載並安裝。  
- 開發環境：設定好 Visual Studio 等開發工具，以便將 Aspose.GIS 無縫整合至您的 .NET 專案。

## 匯入命名空間
在操作 KML 圖層前，請先在專案中加入必要的命名空間，以取得地理空間資料操作所需的類別與方法。

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Drawing;
using System.Threading;
using Aspose.Gis.Formats.Kml;
using Aspose.Gis.Formats.Kml.Styles;
using Aspose.Gis.Geometries;
using Point = Aspose.Gis.Geometries.Point;
```

## 步驟 1：設定文件目錄
定義存放 KML 檔案的文件目錄路徑。

```csharp
string dataDir = "Your Document Directory";
```

## 步驟 2：建立 KML 圖層
使用 Aspose.GIS 初始化 KML 圖層，並指定 KML 檔案的路徑。

```csharp
using (var layer = Drivers.Kml.CreateLayer(dataDir + "Kml_File_out.kml"))
{
```

## 步驟 3：定義屬性（新增布林屬性）
為 KML 圖層加入不同資料型別的屬性，如字串、整數、**布林** 與雙精度。這裡即為每個要素「新增布林屬性」。

```csharp
layer.Attributes.Add(new FeatureAttribute("string_data", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("int_data", AttributeDataType.Integer));
layer.Attributes.Add(new FeatureAttribute("bool_data", AttributeDataType.Boolean));
layer.Attributes.Add(new FeatureAttribute("float_data", AttributeDataType.Double));
```

## 步驟 4：建構並填充要素（建立線串）
建立代表地理實體的要素，並為先前定義的屬性設定值。此處 **建立線串** 幾何，用以示範簡單路徑。

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("string_data", "string value");
feature.SetValue("int_data", 10);
feature.SetValue("bool_data", true);
feature.SetValue("float_data", 3.14);
feature.Geometry = new LineString(new[] { new Point(0, 0), new Point(1, 1) });
layer.Add(feature);
```

## 步驟 5：新增另一個要素
重複上述流程，加入第二筆要素，設定不同的屬性值與空的幾何（null）。

```csharp
Feature feature2 = layer.ConstructFeature();
feature2.SetValue("string_data", "string value2");
feature2.SetValue("int_data", 100);
feature2.SetValue("bool_data", false);
feature2.SetValue("float_data", 3.1415);
feature2.Geometry = Geometry.Null;
layer.Add(feature2);
```

## 如何撰寫 KML 檔案 – 完整範例
依照上述步驟操作後，您將得到一個完整的 KML 檔案，內含自訂屬性（包括布林旗標）與線串幾何。可在 Google Earth、ArcGIS 或任何支援 KML 的 GIS 檢視器中開啟 `Kml_File_out.kml`。

## 常見問題與疑難排解
- **檔案路徑錯誤** – 請確認 `dataDir` 以正確的路徑分隔符（`\` 或 `/`）結尾，符合您的作業系統。  
- **缺少授權** – 試用版僅供評估，正式寫入 KML 檔案需購買授權。  
- **空的幾何** – `Geometry.Null` 為有意為之，表示該要素無空間資料；若所有要素皆需幾何，可自行省略。

## 常見問答
### Aspose.GIS 是否相容其他 GIS 格式？
是，Aspose.GIS 支援多種 GIS 格式，包括 shapefile、GeoJSON 與 KML。

### 我能否視覺化使用 Aspose.GIS 建立的地理空間資料？
當然可以！Aspose.GIS 可與各種地圖函式庫整合，協助您視覺化資料。

### 是否提供 Aspose.GIS 的試用版？
有，您可下載 [免費試用版](https://releases.aspose.com/) 以體驗功能。

### 如何取得 Aspose.GIS 的支援？
請前往 [Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33) 取得社群支援，或在此處探索 [付費支援方案](https://purchase.aspose.com/buy)。

### 是否提供 Aspose.GIS 的臨時授權？
有，您可在此取得臨時授權 [here](https://purchase.aspose.com/temporary-license/)。

## 其他常見問答

**問：如何使用自訂樣式建立 KML 檔案？**  
答：使用 `Aspose.Gis.Formats.Kml.Styles` 命名空間，在加入要素前定義圖示、線條顏色與標籤樣式。

**問：我能有效率地寫入大型 KML 檔案嗎？**  
答：可將要素分批寫入，並定期 flush 圖層，以降低記憶體使用量。

**問：Aspose.GIS 是否支援 .NET Core 與 .NET 6 以上版本？**  
答：是，該函式庫完全相容 .NET Core、.NET 5 以及 .NET 6+。

---

**最後更新：** 2026-01-07  
**測試環境：** Aspose.GIS 24.10 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
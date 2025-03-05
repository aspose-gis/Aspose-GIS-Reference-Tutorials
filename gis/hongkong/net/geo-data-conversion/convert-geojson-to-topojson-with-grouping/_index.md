---
title: 透過分組將 GeoJSON 轉換為 TopoJSON
linktitle: 透過分組將 GeoJSON 轉換為 TopoJSON
second_title: Aspose.GIS .NET API
description: 在此綜合教程中，了解如何使用 Aspose.GIS for .NET 透過分組將 GeoJSON 轉換為 TopoJSON。
type: docs
weight: 13
url: /zh-hant/net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
---
## 介紹

歡迎使用我們的分步指南，了解如何使用 Aspose.GIS for .NET 透過分組將 GeoJSON 轉換為 TopoJSON。 Aspose.GIS 是一個功能強大的.NET API，可讓開發人員無縫地處理地理資料。在本教程中，我們將引導您完成將 GeoJSON 檔案轉換為 TopoJSON 的過程，同時根據指定的屬性將要素分組。

## 先決條件

在我們開始之前，請確保您具備以下先決條件：

1.  Aspose.GIS for .NET：請確定您已下載並安裝 Aspose.GIS for .NET 程式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/gis/net/).

2. 開發環境：您應該擁有一個使用 Visual Studio 或任何其他相容 IDE 設定的工作開發環境。

3. 範例 GeoJSON 檔案：準備要轉換的範例 GeoJSON 檔案。您可以從各種來源取得範例 GeoJSON 檔案或建立自己的檔案。

## 導入命名空間

首先，請確保在您的專案中包含必要的命名空間：

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```


現在讓我們將轉換過程分解為多個步驟：

## 第 1 步：定義檔路徑

定義輸入 GeoJSON 檔案和輸出 TopoJSON 檔案的路徑：

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

代替`"Your Document Directory"`與檔案所在的實際目錄。

## 第 2 步：配置轉換選項

配置轉換選項以指定如何執行分組。在此範例中，我們將根據特定屬性對功能進行分組。

```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        //指定 GeoJSON 圖層中我們要分組為物件的屬性
        ObjectNameAttribute = "group",
        //為具有未知屬性值的要素指定預設物件名稱
        DefaultObjectName = "unnamed",
    }
};
```

調整`ObjectNameAttribute`和`DefaultObjectName`根據您的 GeoJSON 資料的屬性。

## 第 3 步：執行轉換

使用 Aspose.GIS API 執行轉換程序：

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

此行程式碼將使用指定的分組選項將 GeoJSON 檔案轉換為 TopoJSON。

## 結論

在本教程中，我們學習如何使用 Aspose.GIS for .NET 透過分組將 GeoJSON 轉換為 TopoJSON。透過執行這些簡單的步驟，您可以在 .NET 應用程式中有效地處理地理資料格式。

## 常見問題解答

### Q1：我可以根據多個屬性對特徵進行分組嗎？
答：是的，您可以自訂轉換選項以根據多個屬性對要素進行分組。

### Q2：Aspose.GIS 與.NET Core 相容嗎？
答：是的，Aspose.GIS 支援 .NET Core 以及傳統的 .NET Framework。

### Q3：我可以使用Aspose.GIS轉換其他地理資料格式嗎？
答：是的，Aspose.GIS 提供對 GeoJSON 和 TopoJSON 以外的各種地理資料格式的支援。

### Q4：Aspose.GIS 提供免費試用嗎？
答：是的，您可以從以下位置獲得 Aspose.GIS 的免費試用版：[這裡](https://releases.aspose.com/).

### Q5：從哪裡可以獲得 Aspose.GIS 的支援？
答：您可以從 Aspose.GIS 社群論壇獲得支持[這裡](https://forum.aspose.com/c/gis/33).
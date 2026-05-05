---
date: 2026-01-18
description: 學習如何使用 Aspose.GIS for .NET 為地圖新增城市並產生 SVG 地圖，快速打造驚豔的視覺化效果。
linktitle: Render a Map
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 將城市加入地圖
url: /zh-hant/net/map-rendering/render-a-map/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS for .NET 為地圖新增城市

## 介紹
歡迎來到 Aspose.GIS for .NET 的精彩世界！在本一步一步的指南中，您將學習**如何為地圖新增城市**並產生高品質的 SVG 輸出。無論您是構建桌面儀表板還是基於網頁的 GIS 入口網站，本教學都會示範如何繪製向量圖層、設定地圖尺寸，以及輕鬆載入 GeoJSON 地圖。

## 快速答覆
- **本教學涵蓋什麼內容？** 為地圖新增城市並將其匯出為 SVG 檔案。  
- **需要哪個函式庫？** Aspose.GIS for .NET。  
- **需要授權嗎？** 提供免費試用版；正式環境需購買授權。  
- **可以在網頁應用程式中使用嗎？** 可以 — 相同程式碼可於 ASP.NET、Blazor 以及其他 .NET 網頁框架中執行。  
- **產生的輸出格式為何？** SVG 地圖，可在瀏覽器中顯示或進一步編輯。

## 前置條件
在開始本教學之前，請確保已具備以下前置條件：
- Aspose.GIS for .NET 函式庫：確保已安裝 Aspose.GIS for .NET 函式庫。您可於[此處](https://releases.aspose.com/gis/net/)下載。
- 資料檔案：準備本教學所需的 shapefile 與 GeoJSON 資料。您可在文件中找到範例資料，或使用自己的檔案。
- 開發環境：建立 .NET 開發環境，並安裝如 Visual Studio 等程式碼編輯器。

## 匯入命名空間
首先，將所需的命名空間匯入您的 .NET 專案。這些命名空間對於使用 Aspose.GIS 功能至關重要。

```csharp
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.Drawing.Text;
using System.IO;
using System.Linq;
```

## 步驟 1：設定地圖（設定地圖尺寸）
```csharp
string dataDir = "Your Document Directory";
using (var map = new Map(800, 476))
{
    // Additional code for map setup can be added here.
}
```
在此步驟中，我們會初始化一個寬度為 800 像素、高度為 476 像素的新地圖。請依設計需求調整尺寸。

## 步驟 2：新增底圖（繪製向量圖層）
```csharp
var baseMapSymbolizer = new SimpleFill { FillColor = Color.Salmon, StrokeWidth = 0.75 };
map.Add(VectorLayer.Open(dataDir + "basemap.shp", Drivers.Shapefile), baseMapSymbolizer);
```
此處，我們使用 shapefile **繪製底圖的向量圖層**。您可以自由調整 `SimpleFill` 屬性，以符合您的視覺風格。

## 步驟 3：將城市新增至地圖（新增城市、載入 GeoJSON 地圖）
```csharp
var citiesSymbolizer = new SimpleMarker() { FillColor = Color.LightBlue };
citiesSymbolizer.FeatureBasedConfiguration = (feature, symbolizer) =>
{
    // Additional configuration logic can be added here.
};
map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), citiesSymbolizer);
```
此步驟會載入包含城市點資料的 GeoJSON 檔案，並 **將城市新增至地圖**。您可以加強 `FeatureBasedConfiguration` 委派，依人口等屬性為城市設定樣式。

## 步驟 4：渲染地圖（匯出 SVG、產生 SVG 地圖）
```csharp
map.Render(dataDir + "cities_out.svg", Renderers.Svg);
```
最後，我們 **將地圖匯出為 SVG** 檔案。產生的 `cities_out.svg` 可在任何現代瀏覽器或向量圖形編輯器中開啟。

## 結論
恭喜！您已成功 **為地圖新增城市**，並使用 Aspose.GIS for .NET 產生 SVG 地圖。本教學示範了如何設定地圖尺寸、繪製向量圖層、載入 GeoJSON 資料，以及將結果匯出為可縮放的 SVG——適用於網頁與列印情境。

## 常見問題
### 我可以在網頁應用程式中使用 Aspose.GIS for .NET 嗎？
可以，Aspose.GIS for .NET 適用於桌面與網頁應用程式。

### 是否提供試用版？
可以，您可於[此處](https://releases.aspose.com/)探索免費試用版。

### 我可以在哪裡取得 Aspose.GIS for .NET 的支援？
請前往 [Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33)尋求協助或諮詢。

### 我可以為短期專案購買臨時授權嗎？
可以，臨時授權可於[此處](https://purchase.aspose.com/temporary-license/)取得。

### 是否有其他 Aspose.GIS for .NET 的教學？
有，請參閱 [文件](https://reference.aspose.com/gis/net/)以取得完整的教學與指南。

---

**最後更新：** 2026-01-18  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
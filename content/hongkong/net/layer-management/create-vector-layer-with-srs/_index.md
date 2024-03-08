---
title: 使用 SRS 建立向量圖層
linktitle: 使用 SRS 建立向量圖層
second_title: Aspose.GIS .NET API
description: 探索 Aspose.GIS for .NET - 無縫 GIS 整合的關鍵。使用指定的空間參考系統輕鬆建立向量圖層。現在下載！
type: docs
weight: 13
url: /zh-hant/net/layer-management/create-vector-layer-with-srs/
---
## 介紹
Aspose.GIS for .NET 是一個功能強大的程式庫，可讓開發人員在 .NET 應用程式中無縫地處理地理資訊系統 (GIS) 資料。在本教程中，我們將重點放在使用空間參考系統 (SRS) 建立向量圖層。閱讀本指南後，您將能夠輕鬆地將 GIS 功能整合到您的 .NET 專案中。
## 先決條件
在我們深入學習本教程之前，請確保您具備以下先決條件：
- C# 和 .NET 開發的基礎知識。
- 安裝了 Aspose.GIS for .NET 程式庫。你可以下載它[這裡](https://releases.aspose.com/gis/net/).
- 開發環境已設定並準備就緒。
## 導入命名空間
確保在 C# 檔案的開頭導入了必要的命名空間：
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## 步驟 1：設定投影空間參考系統
讓我們使用世界墨卡托投影作為範例來建立投影空間參考系統 (SRS)。按著這些次序：
```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```
## 第 2 步：建立向量圖層並新增要素
現在，讓我們建立一個 shapefile 並使用指定的 SRS 新增功能：
```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); //這將引發異常，因為幾何體有不同的 SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## 步驟 3：驗證空間參考系統
最後，我們打開圖層並驗證其空間參考系統：
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // “WGS 84 / 世界墨卡托”
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); //應該回傳 true
}
```
透過執行這些步驟，您已使用 Aspose.GIS for .NET 成功建立了具有指定空間參考系統的向量圖層。
## 結論
借助 Aspose.GIS，將 GIS 功能整合到 .NET 應用程式中從未如此簡單。憑藉輕鬆建立向量圖層和管理空間參考系統的能力，您可以透過強大的地理空間功能增強您的專案。
## 常見問題解答
### Aspose.GIS 是否與所有 GIS 檔案格式相容？
 Aspose.GIS支援各種GIS格式，包括Shapefile、GeoJSON、KML等。檢查[文件](https://reference.aspose.com/gis/net/)取得完整清單。
### 我可以在 Web 應用程式中使用 Aspose.GIS 嗎？
絕對地！ Aspose.GIS for .NET 用途廣泛，可用於 Web 應用程式、桌面應用程序，甚至行動應用程式。
### 我可以在哪裡獲得 Aspose.GIS 的支援？
您可以在以下位置找到有用的社區：[Aspose.GIS論壇](https://forum.aspose.com/c/gis/33)對於您可能遇到的任何疑問或問題。
### 有免費試用嗎？
是的，您可以透過免費試用來探索 Aspose.GIS 的功能[這裡](https://releases.aspose.com/).
### 如何購買 Aspose.GIS 許可證？
要購買許可證，請訪問[購買頁面](https://purchase.aspose.com/buy).
---
date: 2025-12-20
description: 了解如何在使用 Aspose.GIS for .NET 撰寫幾何圖形時限制精度。本一步步指南協助您以精確的座標控制管理空間資料。
linktitle: Limit Precision Writing Geometries
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS 限制寫入幾何圖形的精度
url: /zh-hant/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.GIS 中限制寫入幾何圖形的精度

如果您想了解在 .NET GIS 應用程式中 **如何限制精度**，Aspose.GIS for .NET 提供了一種簡單且高效的方式來控制座標四捨五入。在本教學中，我們將從環境設定一路走到驗證輸出是否遵守您所定義的精度規則，完整說明整個流程。

## 快速解答
- **「限制精度」是什麼意思？** 在寫入空間檔案時，將座標值四捨五入至指定的小數位數。  
- **範例使用哪種格式？** GeoJSON，但相同的選項同樣適用於其他支援的格式。  
- **試用需要授權嗎？** 免費試用可用於開發與測試；正式上線則需購買商業授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **可以分別控制 Z 座標的精度嗎？** 可以——使用 `ZPrecisionModel` 來設定精確或四捨五入的值。

## 如何在寫入幾何圖形時限制精度
當您需要在不同 GIS 工具間保持座標表現一致、減少檔案大小，或遵循資料交換標準時，限制精度是必須的。以下我們將定義精度選項、寫入幾何圖形，然後再讀回來確認四捨五入是否正確。

## 前置條件

### 1. 下載與安裝
從官方網站取得最新的 Aspose.GIS for .NET 套件：[download link](https://releases.aspose.com/gis/net/)。依照安裝說明將 NuGet 套件加入您的專案。

### 2. 匯入命名空間
加入必要的命名空間，以便存取 GIS 類別與輔助工具。

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 步驟說明

### 步驟 1：定義精度選項
建立 `GeoJsonOptions` 物件，告訴 Aspose.GIS 您希望 X/Y 與 Z 座標保留多少位小數。

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### 步驟 2：設定輸出路徑
指定產生的 GeoJSON 檔案要儲存的位置。

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### 步驟 3：建立並填充幾何圖形
以先前定義的選項開啟新的 `VectorLayer`，建立 `Point` 幾何，並將其加入圖層。

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    var point = new Point();
    point.X = 1.8888888;
    point.Y = 1.00123;
    point.Z = 1.123456789;

    Feature feature = layer.ConstructFeature();
    feature.Geometry = point;
    layer.Add(feature);
}
```

### 步驟 4：讀取並驗證精度
開啟剛才建立的檔案並印出座標。您應該會看到 X/Y 值已四捨五入至三位小數，而 Z 值保持原始精確度。

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

## 常見問題與技巧

- **路徑錯誤：** 確認 `path` 所指的目錄已存在，或使用 `Path.Combine` 搭配 `Environment.CurrentDirectory` 來建立安全的檔案路徑。  
- **精度未套用：** 確認在建立圖層時傳入了 `GeoJsonOptions` 物件；若未傳入，系統會使用預設的完整 double 精度。  
- **大型資料集：** 若需批次處理，建議重複使用同一個 `VectorLayer` 實例，並以批次方式加入要素，以提升效能。

## 常見問答

**Q: Aspose.GIS for .NET 是否相容其他 GIS 格式？**  
A: 是的，它支援 Shapefile、GeoJSON、KML、GML 等多種格式，讓您可以在不同格式之間無縫轉換。

**Q: 可以在購買前先試用 Aspose.GIS for .NET 嗎？**  
A: 當然可以。下載頁面提供免費試用，讓您完整體驗所有功能以進行評估。

**Q: 如何取得測試用的臨時授權？**  
A: 可於 Aspose 授權入口產生臨時評估授權，授權有效期為 30 天。

**Q: 若遇到問題，該向哪裡尋求協助？**  
A: Aspose.GIS 論壇與 Stack Overflow 上的 `aspose-gis` 標籤都是提問與尋找社群解答的好地方。

**Q: 此函式庫能同時支援小型腳本與企業級應用嗎？**  
A: 能。Aspose.GIS 設計能處理從快速原型到高吞吐量伺服器應用的各種需求。

## 結論
依照上述步驟，您現在已掌握 **如何在 Aspose.GIS for .NET 中限制寫入幾何圖形的精度**。控制座標四捨五入不僅能讓空間資料保持整潔、具備互操作性，亦能提升儲存效率——這些都是任何以 GIS 為核心的專案所重視的關鍵優勢。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2025-12-20  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose
---
date: 2025-12-20
description: 學習如何使用 Aspose.GIS for .NET 建立向量圖層及在讀取幾何圖形時限制精度。提供逐步指南，以實現最佳的地理空間資料處理。
linktitle: Limit Precision Reading Geometries
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS for .NET 建立向量圖層，限制精度
url: /zh-hant/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立向量圖層，限制精度（使用 Aspose.GIS for .NET）

## Introduction
在處理地理空間資料時，您常常需要 **create vector layer** 物件，並在讀取時控制保留多少數值細節。Aspose.GIS for .NET 讓限制精度變得簡單，這可在不需要超高精度的情況下提升效能並減少儲存空間。於本教學中，您將會看到如何建立向量圖層、寫入簡單的點幾何，然後以精確與截斷兩種精度讀回它。

## Quick Answers
- **「limit precision」是什麼意思？** 它會將座標值四捨五入至指定的小數位數。  
- **為什麼要先建立向量圖層？** 向量圖層是儲存點、線、面等幾何圖形的容器。  
- **有哪些精度模型可供選擇？** `PrecisionModel.Exact`（不四捨五入）與 `PrecisionModel.Rounding(n)`（四捨五入至 *n* 位小數）。  
- **試用這個功能需要授權嗎？** 可從 releases 頁面取得免費試用版。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 以及 .NET 5/6 以上。

## Prerequisites
在開始之前，請確保您已具備以下前置條件：
1. **Installation** – 必須在開發環境中安裝 Aspose.GIS for .NET 套件。若尚未安裝，可從 [releases page](https://releases.aspose.com/gis/net/) 下載。  
2. **Familiarity with .NET** – 需要具備基本的 C# 與 .NET 框架知識，以便理解與實作範例程式碼。  
3. **Development Environment** – 必須有可運作的 .NET 開發環境，例如 Visual Studio。  
4. **Document Directory** – 請先建立一個資料夾，用於存放與存取本教學產生的 shapefile。

## Import Namespaces
在實作讀取幾何時限制精度的功能之前，先確保已匯入必要的命名空間：
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## How to Create Vector Layer
第一步是 **create vector layer**，用來保存我們的幾何圖形。此圖層將以 Shapefile 格式儲存，之後可使用不同的精度設定重新開啟。
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Setting Precision Options
接下來，我們需要為讀取幾何圖形定義選項，指定所需的精度模型。我們先使用精確精度作為範例：
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Reading Geometries with Exact Precision
現在，使用先前設定的選項開啟向量圖層，以精確精度讀取幾何圖形：
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Truncating Precision
若想將精度截斷至特定的小數位數，可相應調整精度模型：
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Common Issues and Solutions
- **Unexpected coordinate values** – 請確保在開啟圖層之前就設定 `options.XYPrecisionModel`。開啟之後再更改不會生效。  
- **File not found** – 請檢查 `path` 變數指向的是有效的目錄，且前一步已成功建立 Shapefile。  
- **Incorrect geometry type** – 範例使用 `Point`。若使用其他幾何類型（例如 `LineString`），請確保轉型與實際類型相符。

## Conclusion
總結來說，讀取幾何圖形時的精度管理是地理空間資料操作中的關鍵環節。Aspose.GIS for .NET 提供了強大的功能，讓您能有效地限制精度。依循本教學的步驟，您即可順利 **create vector layer** 並依需求限制精度，確保應用程式中的資料處理達到最佳效能。

## FAQ's
### 我可以在 .NET Core 或 .NET Standard 等其他 .NET 框架上使用 Aspose.GIS for .NET 嗎？
可以，Aspose.GIS for .NET 相容於多種 .NET 框架，包括 .NET Core 與 .NET Standard。  
### Aspose.GIS for .NET 有提供試用版嗎？
有，您可從 [releases page](https://releases.aspose.com/) 取得免費試用版。  
### 哪裡可以找到 Aspose.GIS for .NET 的完整文件說明？
請參考 [documentation](https://reference.aspose.com/gis/net/) 取得詳細資訊與範例。  
### 如何取得 Aspose.GIS for .NET 的臨時授權？
可於 [purchase page](https://purchase.aspose.com/temporary-license/) 取得 Aspose.GIS 的臨時授權。  
### 若需要協助或支援，該去哪裡尋求？
您可以前往 Aspose.GIS 的 [forum](https://forum.aspose.com/c/gis/33) 提問、討論或取得支援。

## Frequently Asked Questions
**Q: 限制精度會影響原始的 shapefile 嗎？**  
A: 不會。精度只在讀取幾何時套用，來源檔案保持不變。  

**Q: 可以為 X 與 Y 座標使用不同的精度模型嗎？**  
A: 目前 Aspose.GIS 會對兩個軸使用相同的 `XYPrecisionModel`。  

**Q: 能否自訂四捨五入函式？**  
A: API 只支援內建的 `PrecisionModel.Rounding(int)` 方法。若需自訂邏輯，必須在讀取後自行處理座標。

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
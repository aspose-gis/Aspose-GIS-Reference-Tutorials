---
date: 2026-04-03
description: 學習如何使用 Aspose.GIS for .NET 建立向量圖層及在讀取幾何圖形時限制精度。一步一步的指南，助您最佳化地理空間資料處理。
keywords:
- create vector layer
- reduce shapefile size
- set precision model
linktitle: 限制精度讀取幾何圖形
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS for .NET 建立向量圖層，限制精度
url: /zh-hant/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立向量圖層，限制 Aspose.GIS for .NET 的精度

## 介紹
當處理地理空間資料時，您常常需要 **create vector layer** 物件，並決定座標細節需要保留多少位小數。限制精度不僅能加快處理速度，還能 **reduce shapefile size**，使儲存與傳輸更有效率。在本教學中，我們將示範如何建立向量圖層、寫入簡單的點幾何，然後使用精確與四捨五入的精度模型讀回。完成後，您將了解如何 **set precision model** 以符合應用程式的精度需求。

## 快速解答
- **「limit precision」是什麼意思？** 它會將座標值四捨五入到指定的小數位數。  
- **為什麼要先建立向量圖層？** 向量圖層是儲存點、線、面等幾何圖形的容器。  
- **有哪些精度模型可用？** `PrecisionModel.Exact`（不四捨五入）與 `PrecisionModel.Rounding(n)`（四捨五入至 *n* 位小數）。  
- **試用需要授權嗎？** 可從 releases 頁面取得免費試用版。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core，以及 .NET 5/6+。

## 為何限制精度以及它有何幫助？
- **效能提升** – 數字越少，解析與序列化的資料量就越少。  
- **檔案更小** – 四捨五入座標可顯著縮減 shapefile，尤其是大型資料集。  
- **足夠的精確度** – 許多 GIS 分析不需要亞毫米級精度，四捨五入至 2‑3 位小數通常已足夠。

## 前置條件
在開始之前，請確保您已具備以下條件：
1. **Installation** – 必須在開發環境中安裝 Aspose.GIS for .NET 套件。若尚未安裝，可從 [releases page](https://releases.aspose.com/gis/net/) 下載。  
2. **Familiarity with .NET** – 需要具備 C# 與 .NET 框架的基本知識，以便理解與實作提供的程式碼範例。  
3. **Development Environment** – 需要可用的 .NET 開發環境，例如 Visual Studio。  
4. **Document Directory** – 請先建立一個目錄，用於儲存與存取在過程中產生的 shapefile。

## 匯入命名空間
在實作限制讀取幾何精度的功能之前，先確保匯入必要的命名空間：
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

## 如何建立向量圖層
第一步是 **create vector layer**，用來保存我們的幾何圖形。此圖層將儲存為 Shapefile，之後可使用不同的精度設定重新開啟。
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## 設定精度選項
接下來，我們需要為讀取幾何圖形定義選項，指定所需的精度模型。我們可以先使用精確精度：
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## 以精確精度讀取幾何圖形
現在，讓我們以指定的選項開啟向量圖層，以精確精度讀取幾何圖形：
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## 截斷精度
如果想將精度截斷到特定的小數位數，可相應調整精度模型：
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## 如何為不同情境設定精度模型
您可能會想知道何時使用 `Exact` 與 `Rounding`。以下是兩個常見情境：

| 情境 | 推薦模型 | 原因 |
|----------|-------------------|--------|
| 高精度科學分析 | `PrecisionModel.Exact` | 不會遺失座標細節 |
| 網頁製圖圖磚或行動應用程式 | `PrecisionModel.Rounding(2)` | 減少檔案大小並加快渲染速度 |

選擇合適的模型是 **set precision model** 的決策過程之一，需在精確度與效能之間取得平衡。

## 常見問題與解決方案
- **Unexpected coordinate values** – 確保在開啟圖層前先設定 `options.XYPrecisionModel`，之後再變更不會生效。  
- **File not found** – 請確認 `path` 變數指向有效目錄，且前一步已成功建立 Shapefile。  
- **Incorrect geometry type** – 範例使用 `Point`。若使用其他幾何類型（例如 `LineString`），需將型別轉換為實際類型。

## 減少 Shapefile 大小的技巧
- 使用 `PrecisionModel.Rounding`，選擇最少的小數位數以滿足精度需求。  
- 在寫入圖層前移除不必要的屬性欄位。  
- 若需傳輸，可使用一般 ZIP 工具壓縮產生的 `.shp`、`.shx`、`.dbf` 檔案。

## 結論
總結來說，讀取幾何圖形時管理精度是地理空間資料操作的關鍵環節。Aspose.GIS for .NET 提供強大的功能，讓您能有效地執行此操作。依照上述步驟，您可以順利 **create vector layer** 物件、**set precision model**，並在適當時 **reduce shapefile size**，確保應用程式的資料處理最佳化。

## 常見問答
### 我可以將 Aspose.GIS for .NET 與其他 .NET 框架（如 .NET Core 或 .NET Standard）一起使用嗎？
是的，Aspose.GIS for .NET 相容於多種 .NET 框架，包括 .NET Core 與 .NET Standard。  
### 是否有 Aspose.GIS for .NET 的試用版可供下載？
是的，您可從 [releases page](https://releases.aspose.com/) 取得免費試用版。  
### 我可以在哪裡找到 Aspose.GIS for .NET 的完整文件？
請參考 [documentation](https://reference.aspose.com/gis/net/) 以取得詳細資訊與範例。  
### 如何取得 Aspose.GIS for .NET 的臨時授權？
可從 Aspose.GIS 的 [purchase page](https://purchase.aspose.com/temporary-license/) 取得臨時授權。  
### 我可以在哪裡尋求 Aspose.GIS for .NET 的協助或支援？
您可前往 Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) 提問、討論或取得支援。

## 常見問題
**Q: 限制精度會影響原始 shapefile 嗎？**  
A: 不會。精度僅在讀取幾何圖形時套用，來源檔案保持不變。  

**Q: 可以為 X 與 Y 座標使用不同的精度模型嗎？**  
A: Aspose.GIS 目前對兩軸使用相同的 `XYPrecisionModel`。  

**Q: 能否設定自訂的四捨五入函式？**  
A: API 僅支援內建的 `PrecisionModel.Rounding(int)` 方法。若需自訂邏輯，必須在讀取後自行處理座標。

---

**最後更新：** 2026-04-03  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
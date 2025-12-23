---
date: 2025-12-23
description: 學習如何使用 Aspose.GIS for .NET 將 WKT 轉換為幾何圖形以及計算點數。開發者一步一步的指南。
linktitle: Translate Geometry from WKT
second_title: Aspose.GIS .NET API
title: 如何在 .NET 中使用 Aspose.GIS 將 WKT 轉換為幾何
url: /zh-hant/net/geometry-processing/translate-geometry-from-wkt/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS 在 .NET 中將 WKT 轉換為 Geometry

## Introduction
在本教學中，您將了解 **如何將 WKT 轉換為 geometry**，並看到一個實作範例，說明 **如何計算結果形狀中的點數**。無論您是構建地圖服務、處理 GIS 資料，或僅需在 .NET 應用程式中讀取 Well‑Known Text，這些步驟都能讓您快速上手。

## Quick Answers
- **Aspose.GIS 能讀取 WKT 嗎？** 是 – `Geometry.FromText` 方法可直接解析 WKT 字串。  
- **需要多少行程式碼？** 基本的轉換與點數計算大約需要 5‑6 行。  
- **正式環境需要授權嗎？** 需要，非試用版必須購買商業授權。  
- **支援的 .NET 版本？** .NET Framework 4.6 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **點數計算是否內建？** 當然 – geometry 物件提供 `Count` 屬性。

## What is “convert WKT to geometry”?
Well‑Known Text (WKT) 是用於表示幾何物件的純文字標記。將 WKT 轉換為 geometry 意味著將該文字轉換為物件模型（例如 `ILineString`、`IPolygon`），以便以程式方式操作。

## Why use Aspose.GIS for this conversion?
- **Zero‑dependency parsing** – 無需外部函式庫。  
- **Full GIS feature set** – 支援 2D/3D 座標、SRID 處理以及多種檔案格式。  
- **High performance** – 為大型資料集與多執行緒情境進行最佳化。  

## Prerequisites
在開始之前，請確保您已具備以下項目：

1. Aspose.GIS for .NET API – 從 [here](https://releases.aspose.com/gis/net/) 下載。  
2. 具備 C# 基礎知識以及 .NET 開發環境（如 Visual Studio、VS Code 等）。

## Import Namespaces
首先，將必要的命名空間加入您的 C# 檔案：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step 1: Create a LineString from WKT
現在，我們將 **將 WKT 轉換為 geometry**，透過從包含 Z‑座標的 WKT 字串建立 `LineString` 物件：

```csharp
ILineString line = (ILineString)Geometry.FromText("LINESTRING Z (0.1 0.2 0.3, 1 2 1, 12 23 2)");
```

> *小技巧:* `FromText` 方法會自動偵測幾何類型，您可以將其轉型為相應的介面（`ILineString`、`IPolygon` 等）。

## How to count points in a LineString?
要回答次要關鍵字 **how to count points**，只需讀取 `ILineString` 實例的 `Count` 屬性：

```csharp
Console.WriteLine(line.Count); // Output: 3
```

輸出顯示該線段包含三個頂點，證實轉換成功且點數計算正確。

## Conclusion
現在您已了解 **如何將 WKT 轉換為 geometry**，以及如何透過單一屬性呼叫取得點的數量。這些基礎讓您能在任何 .NET 應用程式中整合 GIS 資料處理，無論是桌面工具還是雲端服務。

## FAQ's
### 我可以在商業專案中使用 Aspose.GIS for .NET 嗎？
可以，Aspose.GIS for .NET 採取每位開發者授權模式，允許您在商業專案中無限制使用。

### Aspose.GIS for .NET 支援除 WKT 之外的其他幾何格式嗎？
支援，Aspose.GIS for .NET 支援多種幾何格式，包括 WKB、GeoJSON 與 Shapefile。

### 是否提供 Aspose.GIS for .NET 的免費試用？
可以，您可從 [here](https://releases.aspose.com/) 取得免費試用。

### 我可以在哪裡找到 Aspose.GIS for .NET 的文件？
您可以在 [here](https://reference.aspose.com/gis/net/) 找到相關文件。

### 如何取得 Aspose.GIS for .NET 的支援？
您可在 Aspose.GIS 論壇 [here](https://forum.aspose.com/c/gis/33) 獲得支援。

## Frequently Asked Questions (Additional)

**Q: 若我的 WKT 字串語法無效，該怎麼辦？**  
A: `Geometry.FromText` 會拋出 `FormatException`。請將呼叫包在 try‑catch 區塊中，以優雅地處理格式錯誤的 WKT。

**Q: 我能一次轉換多個 WKT 字串嗎？**  
A: 可以 – 迭代您的字串清單，對每個項目呼叫 `Geometry.FromText`，並將結果存入 `List<IGeometry>`。

**Q: Aspose.GIS 在轉換時會保留 Z 值嗎？**  
A: 當然會。當 WKT 包含 Z 座標（如範例所示），轉換後的 geometry 會保留這些值。

**Q: 操作完 geometry 後，能再匯出為 WKT 嗎？**  
A: 使用任意 `IGeometry` 例項的 `ToText()` 方法即可取得 WKT 表示。

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
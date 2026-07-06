---
date: 2026-04-09
description: 學習如何使用 Aspose.GIS for .NET 減少幾何精度並四捨五入 Z 值，提升 GIS 效能並節省記憶體。
keywords:
- how to reduce geometry
- how to round z
- geometry precision .NET
linktitle: 降低幾何精度
second_title: Aspose.GIS .NET API
title: 如何在 .NET 中降低幾何精度並對 Z 進行四捨五入
url: /zh-hant/net/geometry-processing/reduce-geometry-precision/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 .NET 中降低幾何精度並四捨五入 Z 值

## 介紹
如果您正在處理大型空間資料集，您可能已注意到幾何資料中每多一位小數，都會累積成檔案大小和處理時間的增加。在本教學中，您將學習 **how to reduce geometry** 精度以及 **how to round Z** 值，使用 Aspose.GIS for .NET。完成本指南後，您將能縮小幾何檔案、加快空間運算，並保持低記憶體佔用，全部只需幾個簡單的方法呼叫。

## 快速解答
- **What does “how to round Z” mean?** 它會修剪幾何物件中 Z 座標的小數位數。  
- **Why reduce geometry precision?** 它會減少每個頂點儲存的資料量，從而加快空間查詢並降低記憶體使用量。  
- **Which library handles this?** Aspose.GIS for .NET 提供內建的 `RoundZ` 與 `RoundXY` 方法。  
- **Do I need a license?** 免費試用可用於測試；正式環境需商業授權。  
- **Can I control the number of decimal places?** 可以，您可在 `Round*` 方法中指定所需的小數位數。

## 如何在 .NET 中降低幾何精度
降低幾何精度只需對任何幾何物件呼叫 `RoundXY`。此方法接受您想保留的 X 與 Y 座標的小數位數。此操作在不需要精確到次米的分析中特別有用。

## 如何在 .NET 中四捨五入 Z 值
當資料包含 Z（高程）成分時，您可以呼叫 `RoundZ` 以限制其精度。這就是 **how to round z** 步驟，通常能為 3‑D 資料集帶來最大的檔案大小縮減，因為高程值往往有許多小數位。

## 在 GIS 中什麼是「how to round Z」？
對 Z 座標四捨五入會去除多餘的小數精度，將 3.345 之類的值變為 3.3（或您自行定義的精度）。此簡單操作可大幅縮減檔案大小並加速計算，特別是當第三維度對分析並非關鍵時。

## 為何使用 Aspose.GIS 降低幾何精度？
- **Performance boost:** 資料量減少意味著更快的空間查詢與轉換。  
- **Memory savings:** 較小的頂點表示釋放記憶體，讓更大的資料集能保留在記憶體中。  
- **Flexibility:** 您可自行決定在精度與速度之間的平衡。

## 前置條件
在開始之前，請確保您具備以下前置條件：

1. Aspose.GIS for .NET Library：從 [Aspose.GIS website](https://releases.aspose.com/gis/net/) 下載並安裝此函式庫。  
2. 基本的 C# 程式設計知識：熟悉 C# 程式語言將有助於學習。

## 匯入命名空間
首先，匯入必要的命名空間以使用 Aspose.GIS 類別與方法。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 步驟 1：建立點
讓我們先建立一個具有特定座標的點。

```csharp
Point point = new Point(1.344, 2.345, 3.345, 4.345);
```

## 步驟 2：降低 XY 精度
現在，我們將把該點的 X 與 Y 座標精度降低至小數點後兩位。

```csharp
point.RoundXY(digits: 2);
```

## 步驟 3：顯示座標
顯示點的更新後座標。

```csharp
Console.WriteLine("{0}, {1}, {2}, {3}", point.X, point.Y, point.Z, point.M);
```

## 步驟 4：降低 Z 精度 – **how to round z**
接下來，將點的 Z 座標精度降低至小數點後一位。這就是 **how to round z** 的核心。

```csharp
point.RoundZ(digits: 1);
```

## 步驟 5：顯示更新後的座標
在降低 Z 精度後，顯示點的更新座標。

```csharp
Console.WriteLine("{0}, {1}, {2}, {3}", point.X, point.Y, point.Z, point.M);
```

## 步驟 6：建立 LineString
現在，建立一個 `LineString` 並向其中加入點。

```csharp
LineString line = new LineString();
line.AddPoint(1.2, 2.3);
line.AddPoint(2.4, 3.1);
```

## 步驟 7：降低 LineString 的 XY 精度
將 `LineString` 的 X 與 Y 座標精度降低至零小數位。

```csharp
line.RoundXY(digits: 0);
```

## 步驟 8：顯示 LineString 更新後的座標
在降低 XY 精度後，顯示 `LineString` 的更新座標。

```csharp
Console.WriteLine("{0}, {1}", line[0].X, line[0].Y);
Console.WriteLine("{0}, {1}", line[1].X, line[1].Y);
```

## 常見使用情境與技巧
- **Large raster‑vector conversions:** 四捨五入 Z 可縮減中間幾何檔案的大小。  
- **Mobile GIS apps:** 降低精度可減少傳輸幾何資料時的頻寬需求。  
- **Pro tip:** 先套用 `RoundXY` 再套用 `RoundZ`，以保持工作流程的一致性。

## 常見問題

**Q: 為什麼在 GIS 中降低幾何精度很重要？**  
A: 降低幾何精度有助於優化記憶體使用並提升效能，尤其在處理大型 GIS 資料集時。

**Q: 降低幾何精度會影響準確度嗎？**  
A: 雖然會失去少量精度，但此取捨通常能在大多數空間分析中取得精度與效能的良好平衡。

**Q: 我可以自訂 Aspose.GIS for .NET 的精度降低層級嗎？**  
A: 可以，您可使用 `RoundXY` 與 `RoundZ` 方法指定 XY 與 Z 座標所需的小數位數。

**Q: 是否有可量化的效能提升？**  
A: 絕對有——每個頂點的資料量減少，意味著更快的空間查詢、降低 I/O 與記憶體消耗。

**Q: 我可以從哪裡取得 Aspose.GIS for .NET 的支援？**  
A: 您可前往 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 或存取文件說明 [here](https://reference.aspose.com/gis/net/)。

---

**最後更新：** 2026-04-09  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
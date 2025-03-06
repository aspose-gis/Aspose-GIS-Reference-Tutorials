---
title: 使用 .NET 中的 Aspose.GIS 轉換 WKT 中的幾何圖形
linktitle: 從 WKT 轉換幾何圖形
second_title: Aspose.GIS .NET API
description: 了解如何使用 Aspose.GIS for .NET 從眾所周知的文字轉換幾何圖形。無縫整合的分步教程。
weight: 21
url: /zh-hant/net/geometry-processing/translate-geometry-from-wkt/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 .NET 中的 Aspose.GIS 轉換 WKT 中的幾何圖形

## 介紹
在本教程中，我們將深入研究使用 Aspose.GIS for .NET 從眾所周知的文字 (WKT) 轉換幾何圖形的過程。 Aspose.GIS 是一個功能強大的 .NET API，可讓開發人員輕鬆處理地理空間資料。無論您是經驗豐富的開發人員還是剛開始地理空間編程，本教學都將逐步引導您完成整個過程。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
1.  Aspose.GIS for .NET API：您可以從以下位置下載：[這裡](https://releases.aspose.com/gis/net/).
2. 對 C# 程式語言有基本了解。

## 導入命名空間
首先，讓我們將必要的命名空間匯入到我們的 C# 專案中：
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## 第 1 步：從 WKT 建立 LineString
第一步是從 Well-Known Text 表示建立一個 LineString 物件：
```csharp
ILineString line = (ILineString)Geometry.FromText("LINESTRING Z (0.1 0.2 0.3, 1 2 1, 12 23 2)");
```
## 步驟 2：計算 LineString 中的點
接下來，我們來計算 LineString 中的點數：
```csharp
Console.WriteLine(line.Count); //輸出：3
```

## 結論
在本教程中，我們探索如何使用 Aspose.GIS for .NET 從眾所周知的文字轉換幾何圖形。透過執行這些簡單的步驟，您可以將地理空間資料處理無縫整合到您的 .NET 應用程式中。
## 常見問題解答
### 我可以在我的商業專案中使用 Aspose.GIS for .NET 嗎？
是的你可以。 Aspose.GIS for .NET 按開發人員授權，允許您在商業專案中使用它而不受任何限制。
### 除了 WKT 之外，Aspose.GIS for .NET 是否支援其他幾何格式？
是的，Aspose.GIS for .NET 支援各種幾何格式，包括 WKB、GeoJSON 和 Shapefile。
### Aspose.GIS for .NET 是否有免費試用版？
是的，您可以從以下位置獲得免費試用[這裡](https://releases.aspose.com/).
### 在哪裡可以找到 Aspose.GIS for .NET 的文件？
你可以找到文檔[這裡](https://reference.aspose.com/gis/net/).
### 如何獲得 Aspose.GIS for .NET 支援？
您可以從 Aspose.GIS 論壇獲得支持[這裡](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

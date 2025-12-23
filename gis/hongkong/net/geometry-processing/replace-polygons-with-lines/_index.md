---
date: 2025-12-23
description: 學習如何使用 Aspose.GIS for .NET 從多邊形建立線條，並將多邊形轉換為線條，快速掌握 GIS 資料操作。
linktitle: Replace Polygons with Lines
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 從多邊形建立線段
url: /zh-hant/net/geometry-processing/replace-polygons-with-lines/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS for .NET 從多邊形建立線段

## Introduction
如果您在 GIS 應用程式中需要 **create line from polygon**，Aspose.GIS for .NET 提供一個簡單、單行的方法來完成此轉換。將多邊形幾何轉換為線條幾何是想要視覺化邊界、執行線性分析或降低資料複雜度時的常見步驟。在本教學中，您將看到如何將多邊形替換為線條、為什麼這很重要，以及如何將此解決方案整合到您的 .NET 專案中。

## Quick Answers
- **What does “create line from polygon” mean?** 它將封閉的多邊形形狀轉換為其組成的邊界線。  
- **Which method performs the conversion?** `ReplacePolygonsByLines()` 來自 Aspose.GIS Geometry API。  
- **Do I need a license to run the code?** 免費試用可用於評估；正式生產環境需購買商業授權。  
- **What .NET versions are supported?** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **Can I use this with other GIS formats?** 可以 — 相同方法適用於 Shapefile、GeoJSON、KML 等格式。

## What is “create line from polygon”?
從多邊形建立線段即將多邊形的邊緣提取為 `LineString` 集合。此操作通常稱為 *polygon to line* 轉換，對於網路分析、地圖渲染與資料簡化等任務相當有用。

## Why use Aspose.GIS for this transformation?
- **Built‑in method** – 無需自行撰寫幾何解析程式碼。  
- **High performance** – 為大型資料集進行最佳化。  
- **Cross‑format support** – 支援多種 GIS 檔案類型。  
- **Comprehensive documentation** – 易於上手。

## Prerequisites
在開始撰寫程式碼之前，請確保已準備好以下項目：

### Installing Aspose.GIS for .NET
1. 下載 Aspose.GIS for .NET：前往 [this link](https://releases.aspose.com/gis/net/) 下載最新版本。  
2. 安裝 Aspose.GIS for .NET：依照套件內的安裝說明或參考 [documentation](https://reference.aspose.com/gis/net/) 完成設定。

## Import Namespaces
在您的 .NET 專案中匯入必要的命名空間，以便使用 Aspose.GIS 幾何類別。

```csharp
using System;
using Aspose.Gis.Geometries;
```

## Step‑by‑step guide to replace polygons with lines

### Step 1: Define source geometry
建立一個包含欲轉換多邊形的幾何集合。

```csharp
var srcGeometry = Geometry.FromText(@"GeometryCollection (POLYGON((1 2, 1 4, 3 4, 3 2)), Point (5 1))");
```

### Step 2: Convert polygon to lines
使用 `ReplacePolygonsByLines()` 方法 **convert polygon to lines**。這是 *create line from polygon* 操作的核心。

```csharp
var dstGeometry = srcGeometry.ReplacePolygonsByLines();
```

### Step 3: Display the results
列印原始幾何與轉換後的幾何，以驗證轉換結果。

```csharp
Console.WriteLine($"source: {srcGeometry.AsText()}");
Console.WriteLine($"result: {dstGeometry.AsText()}");
```

## Common pitfalls and troubleshooting
- **Empty geometry collection** – 確認來源幾何實際包含多邊形；否則 `ReplacePolygonsByLines()` 會回傳未變更的原始幾何。  
- **Mixed geometry types** – 此方法僅影響多邊形，其他類型（例如點）會原樣傳遞。  
- **Version compatibility** – 使用最新的 Aspose.GIS NuGet 套件以避免過時 API 的問題。

## Frequently Asked Questions

**Q: Can Aspose.GIS for .NET work with various GIS file formats?**  
A: Yes, Aspose.GIS for .NET supports reading and writing formats such as Shapefile, GeoJSON, KML, and more.

**Q: Is there a free trial available for Aspose.GIS for .NET?**  
A: Yes, you can access the free trial of Aspose.GIS for .NET [here](https://releases.aspose.com/).

**Q: Does Aspose.GIS for .NET offer support for developers?**  
A: Yes, developers can get support and assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).

**Q: Can I purchase a temporary license for Aspose.GIS for .NET?**  
A: Yes, you can acquire a temporary license from [here](https://purchase.aspose.com/temporary-license/).

**Q: Is Aspose.GIS for .NET suitable for both beginners and experienced developers?**  
A: Absolutely, Aspose.GIS for .NET caters to developers of all levels, offering comprehensive documentation and support.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.GIS for .NET 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
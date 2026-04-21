---
date: 2026-04-13
description: 學習如何使用 Aspose.GIS for .NET 將幾何圖形轉換為 WKT。本指南說明如何將幾何圖形轉換為 WKT 以及如何有效使用
  AsText 方法。
keywords:
- how to translate geometry
- convert geometry to wkt
- how to use astext
linktitle: 將幾何轉換為 WKT
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 將幾何圖形轉換為 WKT
url: /zh-hant/net/geometry-processing/translate-geometry-to-wkt/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS for .NET 將幾何轉換為 WKT

## 介紹
如果您在 .NET 應用程式中處理空間資料，通常需要將 **幾何轉換** 為其他系統可消費的文字表示。Well‑Known Text (WKT) 格式是事實上的標準。在本教學中，我們將示範如何使用 Aspose.GIS for .NET **將幾何轉換** 為 WKT，並展示方便的 `AsText()` 方法，使轉換只需一行程式碼。

## 快速解答
- **什麼是「幾何轉換」？** 將幾何物件（點、線、面等）轉換為文字格式，例如 WKT。  
- **哪個方法會產生 WKT？** 任何幾何物件的 `AsText()`。  
- **我需要授權嗎？** 免費試用可用於開發；正式環境需商業授權。  
- **支援的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **我可以轉換其他格式嗎？** 可以 — Aspose.GIS 亦支援 WKB、GeoJSON、Shapefile 等。

## 什麼是幾何轉換為 WKT？
將幾何轉換為 WKT 意味著以純文字字串表達空間物件的座標與形狀，例如 `POINT (23.5732 25.3421)`。此格式易於閱讀，且被 GIS 工具、資料庫與 Web 服務廣泛接受。

## 為什麼要使用 Aspose.GIS 完成此任務？
* **Zero‑dependency API** – 無需安裝原生函式庫。  
* **Consistent behavior** – 在 .NET Framework、.NET Core 與 .NET 5/6 上行為一致。  
* **Rich format support** – 除 WKT 外，還支援 WKB、GeoJSON、Shapefile 等。  
* **Thread‑safe and high‑performance** – 適用於小型腳本與大型服務。

## 前置條件
在開始之前，請確保您具備以下條件：

1. **Install Aspose.GIS for .NET** – 依照官方 [Aspose.GIS for .NET documentation](https://reference.aspose.com/gis/net/) 的說明進行安裝。  
2. **Set up a .NET development environment** – Visual Studio、Rider 或安裝 C# 擴充功能的 VS Code 都可。  
3. **Basic C# knowledge** – 範例使用簡單的 C# 語法。

## 如何使用 Aspose.GIS for .NET 將幾何轉換為 WKT
以下章節將流程拆解為清晰的編號步驟。每一步都包含簡短說明與所需的完整程式碼。

### 步驟 1：匯入必要的命名空間
首先，將 Aspose.GIS 幾何類別匯入作用域。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### 步驟 2：建立幾何物件（點範例）
建立您想要轉換的幾何物件。此處使用 `Point`，相同模式亦適用於 `LineString`、`Polygon` 等。

```csharp
Point point = new Point(23.5732, 25.3421);
```

### 步驟 3：使用 `AsText()` 將幾何轉換為 WKT
`AsText()` 擴充方法會回傳幾何的 WKT 表示。您可以將其印出至主控台或依需求儲存。

```csharp
Console.WriteLine(point.AsText()); // POINT (23.5732, 25.3421)
```

> **小技巧：** 若需要去除座標周圍的括號，可使用 `point.AsText().Replace(",", " ")`。

## 如何使用 AsText 方法
`AsText()` 是 **將幾何轉換為 WKT** 的主要方式。它適用於任何繼承自 `Geometry` 的類別，您可直接在 `LineString`、`Polygon`、`MultiPolygon` 等上呼叫，無需額外的轉換步驟。

## 常見問題與解決方案
| 問題 | 原因 | 解決方案 |
|-------|--------|-----|
| `AsText()` 回傳 `null` | 幾何物件未初始化 | 在呼叫 `AsText()` 前，確保已使用有效座標建立幾何物件。 |
| 格式不符合預期（逗號 vs 空格） | 不同 GIS 工具需要不同的分隔符 | 使用字串操作（`Replace`）或 `WktWriter` 類別自訂格式。 |
| 轉換大量集合時效能瓶頸 | 重複的 Console I/O | 批次轉換並寫入檔案或使用 `StringBuilder`，而非 `Console.WriteLine`。 |

## 結論
使用 Aspose.GIS for .NET 將幾何轉換為 WKT 非常簡單：匯入命名空間、建立幾何，然後呼叫 `AsText()`。此方式讓您在 .NET 應用程式中直接嵌入 GIS 功能，且無需外部相依。

## 常見問答
### Q: 我可以在其他 .NET 框架中使用 Aspose.GIS for .NET 嗎？
A: 可以，Aspose.GIS for .NET 相容於多種 .NET 框架，包括 .NET Core 與 .NET Framework。  

### Q: Aspose.GIS for .NET 適合大型應用程式嗎？
A: 絕對適合，Aspose.GIS for .NET 設計用於高效處理大型 GIS 應用，提供高效能與可靠性。  

### Q: Aspose.GIS for .NET 支援除 WKT 之外的其他空間格式嗎？
A: 可以，Aspose.GIS for .NET 支援多種空間格式，包括 WKB、GeoJSON、Shapefile 等。  

### Q: 我可以提出額外功能需求或回報問題給 Aspose.GIS for .NET 嗎？
A: 可以，您可前往 [Aspose.GIS for .NET forum](https://forum.aspose.com/c/gis/33) 取得支援、提出功能需求或回報問題。  

### Q: 有提供 Aspose.GIS for .NET 的試用版嗎？
A: 有，您可在此取得 Aspose.GIS for .NET 的免費試用版 [here](https://releases.aspose.com/)。  

## 常見問題
**Q: 如何有效率地將多個幾何集合轉換為 WKT？**  
**A:** 逐一遍歷集合，對每個項目呼叫 `AsText()`，將結果存入 `StringBuilder` 或直接寫入檔案，以避免 Console 輸出造成的效能損耗。  

**Q: 若需以特定 SRID 匯出 WKT，該怎麼做？**  
**A:** 使用 `AsText(Srid)` 重載，傳入欲使用的空間參考識別碼。  

**Q: `AsText()` 方法是否會受本地語系影響？**  
**A:** `AsText()` 總是使用不變文化 (Invariant Culture)，確保小數點分隔符在任何系統語系下皆一致。  

**Q: 能否將 WKT 解析回幾何物件？**  
**A:** 可以，使用 `Geometry.FromText(string wkt)` 從 WKT 字串建立幾何實例。  

**Q: Aspose.GIS 在 WKT 中是否支援 3D 座標？**  
**A:** 從 22.10 版開始，函式庫支援 WKT 中的 Z 與 M 值，例如 `POINT Z (x y z)`。  

**最後更新：** 2026-04-13  
**測試版本：** Aspose.GIS for .NET 23.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
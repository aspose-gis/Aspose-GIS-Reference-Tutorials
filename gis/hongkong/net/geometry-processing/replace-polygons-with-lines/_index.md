---
date: 2026-04-09
description: 學習如何使用 Aspose.GIS for .NET 將多邊形轉換為線條，快速指南，適合 GIS 開發人員。
keywords:
- convert polygon to line
- how to replace polygons
- transform polygons to lines
linktitle: 以線條取代多邊形
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS for .NET 將多邊形轉換為線
url: /zh-hant/net/geometry-processing/replace-polygons-with-lines/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS for .NET 將多邊形轉換為線

## 介紹
如果您在 .NET GIS 專案中需要**將多邊形轉換為線**，Aspose.GIS 讓此過程變得簡單。無論您是要簡化地圖視覺化、為路徑規劃演算法準備資料，或只是需要更乾淨的幾何表示，本教學都會一步步說明如何使用 Aspose.GIS API 將多邊形取代為線幾何。

## 快速解答
- **「將多邊形轉換為線」是什麼意思？** 它會將封閉的多邊形形狀轉換為其邊界線串。  
- **為什麼要使用 Aspose.GIS 來完成此任務？** 它提供一個單一方法（`ReplacePolygonsByLines`），能有效地執行轉換，無需手動解析幾何圖形。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上，以及 .NET 5/6 以上。  
- **開發時需要授權嗎？** 免費試用版可用於測試；正式上線則需商業授權。  
- **實作需要多長時間？** 基本轉換通常在 10 分鐘以內完成。

## 「將多邊形轉換為線」是什麼？
將多邊形轉換為線表示的是擷取多邊形的外環（即其周界），並以 `LineString` 形式呈現。轉換後的幾何圖形保留了形狀的輪廓，但會失去內部面積資訊，這在網路分析或邊緣渲染等工作中相當有用。

## 為什麼使用 Aspose.GIS 將多邊形轉換為線？
- **簡化視覺化：** 線條渲染較輕量，特別是在網頁地圖上。  
- **為路徑規劃準備資料：** 許多路徑規劃引擎需要線幾何。  
- **保持拓撲：** 線條保留原始多邊形的精確邊界，確保空間精度。  
- **一行解決方案：** `ReplacePolygonsByLines()` 方法為您完成所有繁重的工作。

## 前置條件
在開始之前，請確保您已具備以下項目：

### 安裝 Aspose.GIS for .NET
1. 下載 Aspose.GIS for .NET：前往[此連結](https://releases.aspose.com/gis/net/)以下載最新版本。  
2. 安裝 Aspose.GIS for .NET：依照套件內的安裝說明進行，或參考[文件說明](https://reference.aspose.com/gis/net/)取得詳細步驟。

## 匯入命名空間
在您的 .NET 專案中，匯入所需的命名空間，以便使用 Aspose.GIS 類別。

```csharp
using System;
using Aspose.Gis.Geometries;
```

## 步驟說明

### 步驟 1：定義來源幾何圖形
建立一個幾何集合，內含您想要轉換的一个或多個多邊形。本範例同時加入一個點，以示非多邊形元素會保持不變。

```csharp
var srcGeometry = Geometry.FromText(@"GeometryCollection (POLYGON((1 2, 1 4, 3 4, 3 2)), Point (5 1))");
```

### 步驟 2：將多邊形轉換為線
呼叫 `ReplacePolygonsByLines()` 方法。此一次呼叫會掃描集合，將每個多邊形替換為相對應的線表示，並保留其他幾何類型不變。

```csharp
var dstGeometry = srcGeometry.ReplacePolygonsByLines();
```

### 步驟 3：顯示原始與轉換後的幾何圖形
將原始與轉換後的幾何圖形同時印出至主控台，以便驗證轉換結果。

```csharp
Console.WriteLine($"source: {srcGeometry.AsText()}");
Console.WriteLine($"result: {dstGeometry.AsText()}");
```

## 常見問題與解決方案
- **缺少線輸出：** 請確認來源幾何實際包含多邊形；點或多點會直接傳遞而不變。  
- **座標順序問題：** Aspose.GIS 期望座標以 `X Y`（經度 緯度）順序提供。若順序顛倒會產生意外的形狀。  
- **大型集合：** 對於極大資料集，建議分批處理幾何圖形，以避免過高的記憶體使用量。

## 常見問與答

**Q: Aspose.GIS for .NET 能否支援各種 GIS 檔案格式？**  
A: 可以，它支援 Shapefile、GeoJSON、KML 以及許多其他常見的 GIS 格式。

**Q: 是否提供 Aspose.GIS for .NET 的免費試用？**  
A: 有，您可在此取得 Aspose.GIS for .NET 的免費試用版[此處](https://releases.aspose.com/)。

**Q: Aspose.GIS for .NET 是否提供開發者支援？**  
A: 有，開發者可從 Aspose.GIS 社群論壇取得支援與協助[此處](https://forum.aspose.com/c/gis/33)。

**Q: 我可以購買 Aspose.GIS for .NET 的臨時授權嗎？**  
A: 可以，您可從[此處](https://purchase.aspose.com/temporary-license/)取得臨時授權。

**Q: Aspose.GIS for .NET 是否適合新手與有經驗的開發者？**  
A: 當然，它提供完整的文件、程式碼範例與 API 參考，適用於各種技術層級。

## 結論
透過上述步驟，您已學會如何使用 Aspose.GIS for .NET **將多邊形轉換為線**，並有效地 **將多邊形轉為線**。此功能可讓您實現更輕量的視覺化、路徑規劃準備以及其他各種 GIS 工作流程。歡迎探索 Aspose.GIS 的其他功能，如空間查詢、重新投影與格式轉換，以擴充您的應用程式功能。

---

**最後更新：** 2026-04-09  
**測試環境：** Aspose.GIS for .NET (latest release)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
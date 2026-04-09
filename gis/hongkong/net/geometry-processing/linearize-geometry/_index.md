---
date: 2026-04-09
description: 了解如何使用 Aspose.GIS for .NET 將曲線轉換為直線（線性化幾何），從而在您的 .NET 應用程式中實現高效的地理空間處理與分析。
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
linktitle: 將幾何線性化
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 將曲線轉換為線條
url: /zh-hant/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 轉換曲線為直線（幾何線性化）使用 Aspose.GIS for .NET

## 介紹
如果您需要 **將曲線轉換為直線** 以進行製圖、空間分析或資料交換工作，Aspose.GIS for .NET 為您提供一個乾淨且程式化的解決方案。本教學將示範一個完整的實務範例，說明如何將包含曲線與複合形狀的複雜幾何，轉換為可在任何 GIS 系統中使用的簡單線性表示。

## 快速解答
- **What does “convert curves to lines” mean?** 它將曲線幾何轉換為直線段。  
- **Why choose Aspose.GIS?** 此函式庫支援數十種 GIS 格式，且可在不使用外部工具的情況下處理幾何轉換。  
- **What do I need beforehand?** .NET Framework 或 .NET Core、Visual Studio（或任何 C# IDE）以及 Aspose.GIS NuGet 套件。  
- **How long will the sample run?** 安裝函式庫後，執行樣本不超過五分鐘。  
- **Can I export to other formats?** 當然可以——將 KML driver 換成 Shapefile、GeoJSON 等即可。

## 什麼是轉換曲線為直線？
將曲線轉換為直線（亦稱 **linearizing geometry**）會將任何曲線或複合形狀分解為一系列直線段，稱為「線性幾何」。此簡化可加快渲染速度，提升與舊版 GIS 服務的相容性，並降低空間演算法的複雜度。

## 為什麼要轉換曲線為直線？
- **Performance:** 線性幾何的渲染與查詢速度更快。  
- **Compatibility:** 許多 GIS 平台（尤其是舊版服務）僅接受線性要素。  
- **Simplification:** 適用於縮圖、快速預覽，或將資料輸入需要線性輸入的演算法。

## 前置條件
在開始編寫程式碼之前，請確保您已具備以下條件：

1. **Aspose.GIS for .NET** – 從 [Aspose.GIS website](https://releases.aspose.com/gis/net/) 下載。  
2. **.NET Framework**（或 .NET Core）已安裝於開發機器上。  
3. **Visual Studio**（或任何相容 C# 的 IDE）用於編寫與執行範例。

## 匯入命名空間
要開始使用 Aspose.GIS 功能，請匯入所需的命名空間。

### 步驟 1：核心 Aspose.GIS 命名空間
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### 步驟 2：目標格式的 Driver
以下範例將結果寫入 KML 檔案：
```csharp
using Aspose.GIS.Kml;
```

## 逐步指南：轉換曲線為直線
以下是每行程式碼的詳細說明，解釋 **how to convert curves to lines** 以及每個步驟的重要性。

### 步驟 1：定義輸出路徑
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
將 `"Your Document Directory"` 替換為您希望儲存 KML 檔案的資料夾。建議使用 `Path.Combine` 以確保跨平台相容性。

### 步驟 2：為輸出檔案建立圖層
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
*圖層* 是地理要素的容器。此處我們建立一個新的 KML 圖層，用於保存線性化的幾何。

### 步驟 3：建立新要素
```csharp
var feature = layer.ConstructFeature();
```
*要素* 代表單一的地理物件（點、線、多邊形等）。我們將把線性幾何附加到此要素上。

### 步驟 4：定義原始複雜幾何
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
我們從 Well‑Known Text（WKT）字串建立幾何。此範例包含 `LineString`、`CompoundCurve` 與 `CircularString`——非常適合示範 **convert curves to lines**。

### 步驟 5：轉換曲線為直線
```csharp
var linear = geometry.ToLinearGeometry();
```
`ToLinearGeometry()` 方法會將所有曲線轉換為直線段，產生原始幾何的 *線性* 版本。

### 步驟 6：將線性幾何指派給要素
```csharp
feature.Geometry = linear;
```
現在要素持有簡化後的線性幾何。

### 步驟 7：將要素加入圖層
```csharp
layer.Add(feature);
```
最後，我們將要素加入 KML 圖層，`using` 區塊結束時會將線性幾何寫入輸出檔案。

## 常見陷阱與專業提示
- **Path separators:** 使用 `Path.Combine` 可避免 Windows 與 Linux 之間的路徑分隔符問題。  
- **Very large geometries:** 線性化複雜形狀可能產生數千個頂點；可在線性化後呼叫 `Simplify()` 以減少點數。  
- **Driver selection:** 若需不同輸出格式，將 `Drivers.Kml` 換成 `Drivers.Shapefile`、`Drivers.GeoJson` 等，並相應更改檔案副檔名。  
- **Preserving Z‑values:** `ToLinearGeometry()` 會保留 3‑D（Z）座標，避免失去高程資料。

## 常見問與答 (FAQ)

**Q: Aspose.GIS for .NET 是否相容於 .NET Core？**  
A: 是的，Aspose.GIS 可在 .NET Core 上運行，支援跨平台應用程式。

**Q: 我可以使用 Aspose.GIS for .NET 處理不同的 GIS 檔案格式嗎？**  
A: 當然可以！此函式庫支援 KML、Shapefile、GeoJSON 等多種格式。

**Q: Aspose.GIS 是否提供空間運算與分析功能？**  
A: 有，提供廣泛的空間功能，從緩衝區到空間連接等。

**Q: 是否提供免費試用？**  
A: 有，您可從 [Aspose website](https://releases.aspose.com/) 下載免費試用版。

**Q: 若遇到問題，該向何處尋求協助？**  
A: 前往 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 取得社群與官方支援。

### 其他常見問題

**Q: 我可以線性化包含 3D（Z）座標的幾何嗎？**  
A: 可以，`ToLinearGeometry()` 同時支援 2D 與 3D 幾何，Z 值會被保留。

**Q: 線性化會如何影響檔案大小？**  
A: 將曲線轉換為大量短線段可能會增加檔案大小。如需控制大小，可在線性化後使用 `Simplify()`。

**Q: 我能控制轉換曲線為直線時的段長嗎？**  
A: 預設方法使用內部容差。若需自訂分段，可在呼叫 `ToLinearGeometry()` 前手動對曲線進行細分。

## 結論
本教學說明了如何使用 Aspose.GIS for .NET **how to convert curves to lines**（幾何線性化），從環境設定到將線性化結果寫入 KML 檔案。您現在可以將此工作流程嵌入地圖應用程式、資料處理管線或任何需要簡化幾何的 GIS 專案中。

---

**最後更新：** 2026-04-09  
**測試版本：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
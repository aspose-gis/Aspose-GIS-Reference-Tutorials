---
date: 2025-12-21
description: 學習如何使用 Aspose.GIS for .NET 進行幾何線性化，從而在您的 .NET 應用程式中實現高效的地理空間資料處理、空間分析與幾何操作。
linktitle: Linearize a Geometry
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 進行幾何線性化
url: /zh-hant/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 線性化幾何

## 介紹
如果您需要**如何線性化幾何**以進行製圖、空間分析或資料交換任務，Aspose.GIS for .NET 為您提供乾淨、程式化的方式來完成。在本教學中，我們將逐步示範一個完整的實務範例，說明如何將包含曲線與複合形狀的複雜幾何，轉換為可在任何 GIS 系統中使用的簡單線性表示。

## 快速解答
- **線性化幾何是什麼意思？** 將曲線和複雜形狀轉換為直線段。  
- **為什麼使用 Aspose.GIS？** 它支援數十種 GIS 格式，且能在不使用外部工具的情況下處理幾何轉換。  
- **先決條件？** .NET Framework 或 .NET Core、Visual Studio，以及 Aspose.GIS 程式庫。  
- **範例執行需要多長時間？** 安裝程式庫後，執行時間不到五分鐘。  
- **我可以儲存為其他格式嗎？** 可以 — 只要將 KML 驅動程式換成 Shapefile、GeoJSON 等即可。

## 什麼是線性化幾何？
線性化幾何是指將任何曲線或複合形狀分解為一系列直線段（稱為「線性幾何」）。這可簡化渲染、分析，並提升與僅支援線與點的工具之間的相容性。

## 為什麼線性化幾何？
- **效能：** 線性幾何的渲染與查詢速度較快。  
- **相容性：** 許多 GIS 平台（例如舊版地圖服務）僅接受線性要素。  
- **簡化：** 適用於產生縮圖、快速預覽，或將資料輸入需要線性輸入的演算法。

## 先決條件
在深入程式碼之前，請確保您已具備以下項目：

1. **Aspose.GIS for .NET** – 從 [Aspose.GIS website](https://releases.aspose.com/gis/net/) 下載。  
2. **.NET Framework**（或 .NET Core）已安裝於您的開發機器上。  
3. **Visual Studio**（或任何相容 C# 的 IDE）用於編寫與執行範例。

## 匯入命名空間
若要開始使用 Aspose.GIS 功能，請匯入所需的命名空間。

### 步驟 1：匯入 Aspose.GIS Core 命名空間
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### 步驟 2：匯入目標格式的驅動程式
在本範例中，我們將結果寫入 KML 檔案：
```csharp
using Aspose.GIS.Kml;
```

## 如何線性化幾何 – 步驟說明指南
以下為每行程式碼的詳細說明，解釋**如何線性化幾何**以及每一步的意義。

### 步驟 1：定義輸出路徑
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
將 `"Your Document Directory"` 替換為您希望儲存 KML 檔案的資料夾路徑。

### 步驟 2：為輸出檔案建立圖層
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
*圖層* 是地理要素的容器。此處我們建立一個新的 KML 圖層，用於保存線性化的幾何。

### 步驟 3：建立新要素
```csharp
var feature = layer.ConstructFeature();
```
*要素* 代表單一的地理物件（點、線、面等）。我們將把線性幾何附加到此要素上。

### 步驟 4：定義原始複雜幾何
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
我們從 Well‑Known Text（WKT）字串建立幾何。此範例包含 `LineString`、`CompoundCurve` 與 `CircularString`，非常適合示範線性化。

### 步驟 5：線性化幾何
```csharp
var linear = geometry.ToLinearGeometry();
```
`ToLinearGeometry()` 方法會將所有曲線轉換為直線段，產生原始幾何的*線性*版本。

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

## 常見陷阱與技巧
- **路徑分隔符號：** 使用 `Path.Combine` 以建立跨平台的路徑。  
- **大型幾何：** 線性化非常複雜的形狀可能產生大量頂點；若需要較少點，可在線性化後使用 `Simplify()`。  
- **驅動程式選擇：** 若需不同的輸出格式，將 `Drivers.Kml` 換成 `Drivers.Shapefile`、`Drivers.GeoJson` 等，並相應調整檔案副檔名。

## 結論
在本教學中，我們說明了如何使用 Aspose.GIS for .NET **線性化幾何**，從環境設定到將線性化結果寫入 KML 檔案。您現在可以將此工作流程整合至製圖應用程式、資料處理管線，或任何需要簡化幾何的 GIS 專案中。

## 常見問題
### Q: Aspose.GIS for .NET 是否相容於 .NET Core？
是，Aspose.GIS for .NET 相容於 .NET Core，讓您能夠建立跨平台的應用程式。

### Q: 我可以使用 Aspose.GIS for .NET 處理不同的 GIS 檔案格式嗎？
當然可以！Aspose.GIS 支援多種 GIS 檔案格式，包括 KML、Shapefile、GeoJSON 等。

### Q: Aspose.GIS 是否提供空間運算與分析的支援？
是的，Aspose.GIS 提供廣泛的空間運算與分析功能，以處理複雜的地理空間任務。

### Q: 是否有 Aspose.GIS for .NET 的免費試用版？
有，您可從 [Aspose website](https://releases.aspose.com/) 下載免費試用版。

### Q: 我可以在哪裡取得 Aspose.GIS 的協助與支援？
您可以前往 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 向社群與 Aspose 支援人員尋求協助。

## 其他常見問題

**Q: 我可以線性化包含 3D (Z) 座標的幾何嗎？**  
A: 可以，`ToLinearGeometry()` 支援 2D 與 3D 幾何；Z 值會在產生的線段中保留。

**Q: 線性化會如何影響輸出檔案的大小？**  
A: 將曲線轉換為大量短線段可能會增加檔案大小。若檔案大小是考量，可在線性化後使用 `Simplify()`。

**Q: 線性化時能否控制線段長度？**  
A: 預設方法使用內部容差。若需自訂分段，可在呼叫 `ToLinearGeometry()` 前手動對曲線進行細分。

---

**最後更新：** 2025-12-21  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
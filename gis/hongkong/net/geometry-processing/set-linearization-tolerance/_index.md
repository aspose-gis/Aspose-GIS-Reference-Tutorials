---
date: 2025-12-21
description: 學習如何使用 Aspose.GIS for .NET 建立向量圖層、設定線性化容差，並將要素新增至圖層。請依照本逐步指南匯出 GeoJSON
  檔案。
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS for .NET 建立向量圖層並設定線性化容差
url: /zh-hant/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS for .NET 建立向量圖層並設定線性化容差

## 簡介
如果您需要 **create vector layer** 檔案、控制曲線精度，並將結果匯出為 GeoJSON 文件，Aspose.GIS for .NET 讓這一切變得簡單。在本教學中，您將學習如何設定 GeoJSON 選項、設定線性化容差，以及 **add feature to layer** 物件——同時保持程式碼乾淨且適合投入生產環境。

## 快速解答
- **What does “create vector layer” mean?** 它會建立一個新的 GIS 向量資料集（例如 GeoJSON 檔案），可儲存幾何圖形和屬性。  
- **如何設定容差？** 使用 `GeoJsonOptions` 的 `LinearizationTolerance` 屬性。  
- **我可以匯出 GeoJSON 檔案嗎？** 可以——只需使用 `Drivers.GeoJson` 驅動程式建立 `VectorLayer`。  
- **我需要授權嗎？** 有效的 Aspose.GIS 授權會解鎖所有功能；臨時授權可用於評估。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 什麼是 “create vector layer”？
建立向量圖層表示初始化一個新的 GIS 容器（例如 GeoJSON 檔案），可容納點、線、面等幾何要素。此圖層成為您所建構的任何幾何圖形以及所附加屬性的目標。

## 為什麼要設定 GeoJSON 選項？
設定 GeoJSON 選項——尤其是 **linearization tolerance**——可確保曲線幾何（例如 `CircularString`）以符合應用程式精度需求的方式近似。當您之後 **export GeoJSON file** 用於網頁地圖或空間分析時，此步驟至關重要。

## 先決條件
1. 已安裝 **Visual Studio**（任何近期版本）。  
2. **Aspose.GIS 授權**（或臨時評估金鑰）。  
3. 已下載 **Aspose.GIS for .NET** 函式庫並在專案中引用。  
4. 具備基本的 **C#** 知識。

## 匯入命名空間
首先，匯入所需的命名空間，以便編譯器知道從哪裡取得 GIS 類別：

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 逐步指南

### 步驟 1：設定 GeoJSON 選項（如何設定容差）
我們將建立一個 `GeoJsonOptions` 物件，告訴 Aspose.GIS 線性化後的幾何圖形與原始曲線的接近程度。

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### 步驟 2：定義輸出路徑（如何匯出 GeoJSON）
指定結果檔案的儲存位置。將佔位符替換為實際的資料夾路徑。

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### 步驟 3：使用已設定的選項 **Create Vector Layer**
現在我們實際使用 `VectorLayer.Create` 方法 **create vector layer**。`using` 區塊確保資源得到正確釋放。

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### 步驟 4：建構幾何圖形（例如 circular string）
此處我們建立一個範例幾何圖形——`CircularString`。您可以將其替換為任何有效的 WKT。

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### 步驟 5：**Add Feature to Layer** 並儲存
最後，我們建立一個要素，指派幾何圖形，並將其加入圖層。這就是 **add feature to layer** 操作的核心。

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

當 `using` 區塊結束時，圖層會自動寫入 `path` 中定義的檔案，為您產生可直接使用的 GeoJSON 檔案。

## 常見問題與技巧
- **Incorrect path** – 確認目錄存在且您具有寫入權限。  
- **Tolerance too low** – 設定 `LinearizationTolerance` 為非常小的值可能會大幅增加檔案大小。請根據精度需求調整。  
- **License errors** – 若看到授權警告，請確認在任何 Aspose.GIS 呼叫之前正確載入授權檔案。

## 常見問答

**Q: Aspose.GIS for .NET 是否相容於其他 .NET 框架？**  
A: 是的，它支援 .NET Framework、 .NET Core 以及 .NET 5/6/7。

**Q: 我可以在商業專案中使用 Aspose.GIS 嗎？**  
A: 當然可以。商業授權會移除所有評估限制。

**Q: Aspose.GIS 是否支援除 GeoJSON 之外的其他 GIS 格式？**  
A: 是的，它支援 Shapefile、KML、GML 等多種格式。

**Q: 是否提供試用版？**  
A: 您可從 Aspose 官方網站下載免費試用版。

**Q: 我可以從哪裡取得支援？**  
A: 使用 Aspose 論壇或資源區段中的支援連結。

## 結論
透過上述步驟，您現在已了解如何 **create vector layer**、設定線性化容差，並 **add feature to layer**，以順利完成 **export GeoJSON file** 的建立。探索更多幾何類型與屬性處理，充分發揮 Aspose.GIS 在 .NET GIS 專案中的威力。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2025-12-21  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose
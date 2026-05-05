---
date: 2026-05-05
description: 學習如何使用 Aspose.GIS for .NET 建立 TopoJSON。一步步指南，教您將要素寫入 TopoJSON 格式。
keywords:
- create topojson aspose
- Aspose.GIS TopoJSON
- .NET GIS tutorial
linktitle: 將要素寫入 TopoJSON
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 建立 TopoJSON
url: /zh-hant/net/layer-data-operations/write-features-to-topojson/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS for .NET 建立 TopoJSON

## 介紹
如果您需要直接在 .NET 應用程式中 **建立 TopoJSON** 檔案，Aspose.GIS 提供了簡潔且高效的 API 來完成此工作。在本教學中，我們將逐步說明將要素寫入 TopoJSON 文件的完整流程，從環境設定到新增屬性與幾何圖形。完成後，您即可將 TopoJSON 產生整合至任何您正在開發的 GIS 解決方案中。

## 快速解答
- **本教學涵蓋什麼內容？** 使用 Aspose.GIS for .NET 將向量要素寫入 TopoJSON 檔案。  
- **需要多長時間？** 基本實作大約需要 10‑15 分鐘。  
- **是否需要授權？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **支援的 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **可以加入自訂屬性嗎？** 可以——在加入幾何圖形前，您可以定義任意數量的要素屬性。

## 什麼是 TopoJSON 以及為什麼使用 Aspose.GIS？
TopoJSON 是 GeoJSON 的擴充，會編碼拓撲資訊，從而產生更小的檔案大小並共享線段。使用 Aspose.GIS **建立 TopoJSON** 可讓您以程式方式控制、獲得高效能，並能與 .NET 生態系統中的其他 GIS 工作流程無縫整合。

## 前置條件
在開始之前，請確保您已具備以下項目：

- 已安裝 Aspose.GIS for .NET。您可於 [此處](https://reference.aspose.com/gis/net/) 找到文件與下載程式庫。  
- .NET 開發環境（如 Visual Studio、VS Code，或您偏好的任何 IDE）。  
- 您機器上的一個資料夾，用於儲存輸出檔案——在程式碼範例中，我們會稱其為 `Your Document Directory`。

## 匯入命名空間
首先，加入所需的命名空間，以便使用 GIS 類別。

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## 步驟說明

### 步驟 1：設定文件目錄
定義用來存放產生之 TopoJSON 檔案的資料夾。

```csharp
string dataDir = "Your Document Directory";
```

將 `"Your Document Directory"` 替換為您系統上的實際路徑。

### 步驟 2：指定輸出路徑
將目錄與欲使用的檔名結合。

```csharp
var outputPath = dataDir + "sample_out.topojson";
```

### 步驟 3：使用 TopoJSON 驅動程式建立 VectorLayer
建立使用 TopoJSON 驅動程式的 `VectorLayer`。此圖層將作為您加入的所有要素的容器。

```csharp
using (VectorLayer layer = VectorLayer.Create(outputPath, Drivers.TopoJson))
```

### 步驟 4：為圖層新增屬性
在插入幾何圖形之前，先宣告屬性結構。這些屬性會與每個要素一起儲存。

```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("measurement", AttributeDataType.Double));
layer.Attributes.Add(new FeatureAttribute("id", AttributeDataType.Integer));
```

### 步驟 5：將要素加入圖層
建立個別要素、設定其屬性值、指派幾何圖形，並將其加入圖層。

```csharp
var feature0 = layer.ConstructFeature();
feature0.SetValue("name", "name_0");
feature0.SetValue("measurement", 1.03);
feature0.SetValue("id", 0);
feature0.Geometry = new Point(1.3, 2.3);
layer.Add(feature0);
var feature1 = layer.ConstructFeature();
feature1.SetValue("name", "name_1");
feature1.SetValue("measurement", 10.03);
feature1.SetValue("id", 1);
feature1.Geometry = new Point(241.32, 23.2);
layer.Add(feature1);
```

當 `using` 區塊結束時，Aspose.GIS 會自動將資料寫入 `sample_out.topojson`。

## 常見問題與技巧
- **路徑分隔符號：** 如需跨平台相容性，請使用 `Path.Combine`。  
- **屬性類型：** 確保您指定的資料類型與所賦值相符；不匹配會拋出執行時例外。  
- **大型資料集：** 若有數千筆要素，建議批次插入或使用 `layer.BeginTransaction()` / `Commit()` 以提升效能。

## 結論
您現在已學會如何使用 Aspose.GIS for .NET **建立 TopoJSON** 檔案，從設定圖層到以自訂屬性與點幾何圖形填充圖層。此基礎讓您在 GIS 應用程式成長時，能擴展至更複雜的幾何圖形（線、面）與大型資料集。

## 常見問答
**Q: 我可以將 Aspose.GIS for .NET 與其他 GIS 函式庫一起使用嗎？**  
A: Aspose.GIS 可獨立運作，但您可透過讀寫常見格式（如 GeoJSON、Shapefile 或 KML）與其他函式庫交換資料。

**Q: Aspose.GIS 有哪些授權方案？**  
A: 有，您可以在 [此處](https://purchase.aspose.com/buy) 探索授權選項並進行購買。

**Q: 是否提供 Aspose.GIS for .NET 的免費試用？**  
A: 當然！您可於 [此處](https://releases.aspose.com/) 取得免費試用。

**Q: 我該到哪裡尋求支援或加入 Aspose.GIS 社群？**  
A: 前往 [Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33) 取得社群支援與討論。

**Q: 如何取得 Aspose.GIS 的臨時授權？**  
A: 您可於 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

---

**最後更新：** 2026-05-05  
**測試環境：** Aspose.GIS for .NET（截至 2026 年 5 月的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
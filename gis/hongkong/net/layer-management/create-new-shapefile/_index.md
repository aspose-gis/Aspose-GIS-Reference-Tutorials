---
date: 2026-06-30
description: 了解如何使用 Aspose.GIS for .NET 建立 Shapefile。本分步指南會示範如何定義向量圖層、加入日期屬性，以及有效管理空間資料。
keywords:
- how to create shapefile
- temporal gis shapefile
- Aspose.GIS vector layer
- GIS data automation
linktitle: 建立新 Shapefile
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create shapefile using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to define a vector layer, add a date attribute, and manage
    spatial data efficiently.
  headline: How to Create Shapefile with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS primarily supports .NET, but there are versions available for
      Java as well.
    question: Can I use Aspose.GIS with other programming languages?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I find support for Aspose.GIS?
  - answer: Get your temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license?
  - answer: You can buy the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 建立 Shapefile
url: /zh-hant/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立新 Shapefile

## 簡介
如果你正在使用 .NET 進行地理資訊系統（GIS）開發，Aspose.GIS 是你程式化 **如何建立 shapefile** 的首選解決方案。此函式庫讓你完整掌控向量圖層、屬性結構與檔案格式相容性，從而能在數分鐘內自動化資料管線或產生測試資料集。

## 快速解答
- **本教學教什麼？** 如何建立新 shapefile、定義向量圖層，並加入屬性（包括日期欄位）。  
- **需要哪個函式庫？** Aspose.GIS for .NET。  
- **需要授權嗎？** 免費試用可用於學習；正式環境需購買商業授權。  
- **應該使用哪個 IDE？** Visual Studio（任何近期版本）。  
- **實作需要多長時間？** 基本範例大約需要 10‑15 分鐘。

## 如何使用 Aspose.GIS for .NET 建立 shapefile？
載入 Aspose.GIS 函式庫，設定輸出資料夾，建立 `VectorLayer`，定義屬性，並加入要素——整個工作流程可在不到 30 行 C# 程式碼內完成。函式庫會自動處理幾何建立、屬性類型與檔案寫入，讓你不必自行管理低階 Shapefile 規格。

## 先決條件
在開始本教學之前，請確保已具備以下先決條件：
- 具備 C# 程式語言的基本了解。  
- 機器上已安裝 Visual Studio。  
- Aspose.GIS for .NET 函式庫。可於 [此處](https://releases.aspose.com/gis/net/) 下載。

## 匯入命名空間
Start by importing the necessary namespaces to leverage the functionality of Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 步驟 1：設定專案
首先在 Visual Studio 中建立新的 C# 專案，並加入 Aspose.GIS 函式庫。

## 步驟 2：定義文件目錄
```csharp
string dataDir = "Your Document Directory";
```
將 *Your Document Directory* 替換為實際想要儲存新 shapefile 的路徑。

## 步驟 3：建立 VectorLayer
`VectorLayer` 類別代表單一的 shapefile 圖層，用於儲存幾何與屬性資料。  
在此步驟中，我們定義向量圖層並宣告三個屬性：文字欄位 (`name`)、整數欄位 (`age`) 與日期時間欄位 (`dob`)。加入日期屬性對於 **時間性 GIS shapefile** 分析至關重要。

```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```

## 步驟 4：加入要素
### 案例 1：逐一設定值
`SetValues` 方法會依照屬性定義的順序，將屬性值指派給要素。  
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
此處我們建立兩個點，分別設定每個屬性，並將要素加入圖層。

### 案例 2：一次設定所有屬性的新值
或者，你也可以使用 `SetValues` 搭配物件陣列一次提供所有屬性值。  
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
此方式透過一次呼叫的物件陣列填入所有屬性值，當屬性眾多時相當方便。

## 為何這很重要？
以程式方式建立 shapefile 可讓你自動化資料管線、產生測試資料集，或直接將 GIS 輸出嵌入 Web 服務。Aspose.GIS 支援 **30 多種向量與影像格式**，且能在不將整個檔案載入記憶體的情況下寫入上百頁的 shapefile，提供速度與可擴充性。

## 常見陷阱與技巧
- **路徑分隔符號：** 請使用 `Path.Combine` 以確保跨平台相容性，而非字串串接。  
- **屬性順序：** `SetValues` 中的值順序必須與你加入屬性的順序相符。  
- **日期處理：** 若 GIS 資料將跨時區共享，請始終使用 `DateTimeKind.Utc`。

## 結論
恭喜！你已成功使用 Aspose.GIS for .NET 建立新 shapefile。本教學涵蓋了設定專案、定義向量圖層以及加入要素（含日期屬性）的基礎。欲深入探索，請參考 [文件說明](https://reference.aspose.com/gis/net/) 以了解進階功能與特性。

## 常見問與答
**Q: 我可以將 Aspose.GIS 用於其他程式語言嗎？**  
A: Aspose.GIS 主要支援 .NET，但也提供 Java 版。  

**Q: 是否提供免費試用？**  
A: 是的，你可於 [此處](https://releases.aspose.com/) 取得免費試用。  

**Q: 在哪裡可以取得 Aspose.GIS 的支援？**  
A: 請前往 [Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33) 獲取社群支援與討論。  

**Q: 如何取得暫時授權？**  
A: 可於 [此處](https://purchase.aspose.com/temporary-license/) 取得暫時授權。  

**Q: 哪裡可以購買 Aspose.GIS for .NET？**  
A: 可於 [此處](https://purchase.aspose.com/buy) 購買此函式庫。  

---

**最後更新：** 2026-06-30  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [取得圖層屬性 – 使用 Aspose.GIS for .NET 取得圖層屬性資訊](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [建立向量圖層並設定圖層空間參考系統](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [在 File GDB 中建立向量圖層 – Aspose.GIS .NET 教學](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
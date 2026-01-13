---
date: 2026-01-13
description: 學習如何使用 Aspose.GIS for .NET 建立新的 shapefile。本一步一步的指南將示範如何定義向量圖層、加入日期屬性以及管理空間資料。
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
title: 建立新 Shapefile
url: /zh-hant/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立新 Shapefile

## 介紹
如果您正在使用 .NET 開發地理資訊系統（GIS），Aspose.GIS 是您的首選解決方案。這個功能強大的函式庫讓開發者能夠無縫處理空間資料，在本教學中，我們將指導您如何使用 Aspose.GIS for .NET **建立新 shapefile**。您將了解為何定義向量圖層並加入日期屬性是打造穩健 GIS 專案的關鍵步驟。

## 快速解答
- **本教學教什麼？** 如何建立新 shapefile、定義向量圖層，並加入屬性（包括日期欄位）。  
- **需要哪個函式庫？** Aspose.GIS for .NET。  
- **需要授權嗎？** 免費試用版可用於學習；正式環境需購買商業授權。  
- **建議使用哪個 IDE？** Visual Studio（任何近期版本）。  
- **實作大約需要多久？** 基本範例約 10‑15 分鐘即可完成。

## 前置條件
在開始教學之前，請確保您已具備以下條件：
- 具備 C# 程式語言的基本概念。  
- 已在電腦上安裝 Visual Studio。  
- Aspose.GIS for .NET 函式庫。您可於 [此處](https://releases.aspose.com/gis/net/) 下載。

## 匯入命名空間
首先匯入必要的命名空間，以使用 Aspose.GIS 的功能：

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
在 Visual Studio 中建立新的 C# 專案，並加入 Aspose.GIS 函式庫。

## 步驟 2：定義文件目錄
```csharp
string dataDir = "Your Document Directory";
```
將 *Your Document Directory* 替換為您想要儲存新 shapefile 的實際路徑。

## 步驟 3：建立 VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
此程式碼段 **定義了一個向量圖層**，並宣告三個屬性：文字欄位 (`name`)、整數欄位 (`age`) 與日期時間欄位 (`dob`)。加入日期屬性對於時間序列 GIS 分析至關重要。

## 步驟 4：新增要素
### 情況 1：逐一設定值
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

### 情況 2：一次設定所有屬性值
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
此方法使用物件陣列一次性填入所有屬性值，當屬性眾多時相當方便。

## 為何重要
以程式方式建立 shapefile 可讓您自動化資料流程、產生測試資料集，或將 GIS 輸出直接整合至 Web 服務。掌握使用 Aspose.GIS **建立 shapefile** 的技巧，即可完全掌控要素幾何、屬性結構與檔案格式的相容性。

## 常見問題與技巧
- **路徑分隔符號：** 請使用 `Path.Combine` 以確保跨平台相容性，避免直接字串拼接。  
- **屬性順序：** `SetValues` 中的值順序必須與先前加入屬性的順序相同。  
- **日期處理：** 若 GIS 資料需跨時區共享，請務必使用 `DateTimeKind.Utc`。

## 結論
恭喜！您已成功使用 Aspose.GIS for .NET 建立新 shapefile。本教學說明了專案設定、向量圖層定義以及新增要素（含日期屬性）的基礎步驟。欲深入探索，請參考 [文件說明](https://reference.aspose.com/gis/net/) 了解進階功能與特性。

## 常見問答
### Q：我可以在其他程式語言中使用 Aspose.GIS 嗎？
Aspose.GIS 主要支援 .NET，也提供 Java 版。

### Q：是否提供免費試用？
是的，您可於 [此處](https://releases.aspose.com/) 取得免費試用。

### Q：在哪裡可以取得 Aspose.GIS 的支援？
請前往 [Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33) 獲取社群支援與討論。

### Q：如何取得臨時授權？
可於 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

### Q：在哪裡可以購買 Aspose.GIS for .NET？
您可於 [此處](https://purchase.aspose.com/buy) 購買此函式庫。

**最後更新：** 2026-01-13  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
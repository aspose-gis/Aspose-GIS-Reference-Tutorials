---
date: 2026-01-10
description: 學習如何使用 C# 讀取 shapefile，並使用 Aspose.GIS for .NET 將多邊形 shapefile 轉換為線串。透過清晰的逐步指引，提升您的
  GIS 開發能力。
linktitle: Convert Polygon Shapefile to Linestring
second_title: Aspose.GIS .NET API
title: 讀取 Shapefile C# – 將多邊形 Shapefile 轉換為線串
url: /zh-hant/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 讀取 Shapefile C# – 將多邊形 Shapefile 轉換為線串

## 介紹
如果您在 .NET 中使用地理資訊系統 (GIS)，**read shapefile c#** 是在操作資料前的常見第一步。Aspose.GIS 讓此流程變得簡單，只需幾行程式碼即可將 Polygon Shapefile 轉換為 Linestring。當您需要從多邊形資料集中提取線性特徵以執行路徑規劃、網路分析或資料視覺化等任務時，這項功能特別實用。

## 快速回答
- **哪個函式庫可協助您讀取 shapefile c#？** Aspose.GIS for .NET  
- **您能將多邊形轉換為線嗎？** 是 – 使用 `LineString` 搭配多邊形的外環。  
- **生產環境需要授權嗎？** 需要商業授權才能在生產環境使用。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **是否提供試用版？** 當然可以 – 從 Aspose 網站下載免費試用版。

## 什麼是 “read shapefile c#”？
在 C# 中讀取 shapefile 意味著將 `.shp` 檔案載入記憶體，以便您查詢、修改或轉換其幾何圖形。Aspose.GIS 提供簡易的 API，抽象低階細節，讓您專注於 GIS 邏輯。

## 為什麼使用 Aspose.GIS 將多邊形轉換為線？
- **保留拓撲結構** – 轉換會保留每個多邊形的精確外部邊界。  
- **效能** – 此函式庫針對大型資料集進行最佳化，使批次轉換快速。  
- **彈性** – 您之後可以將線串寫入其他 shapefile、GeoJSON 或任何支援的格式。

## 前置條件
在開始教學之前，請確保您已具備以下項目：

- **Aspose.GIS 函式庫** – 從 [website](https://releases.aspose.com/gis/net/) 下載並安裝 Aspose.GIS 函式庫。  
- **Shapefile 資料** – 準備好要轉換的 Polygon Shapefile。若沒有，可取得範例資料或自行建立。  
- **開發環境** – 設定好具備必要工具（Visual Studio、.NET SDK 等）的 .NET 開發環境。

## 匯入命名空間
在您的 C# 程式碼中，需要匯入 Aspose.GIS 的命名空間以存取所需的類別與方法。請在程式檔案開頭加入以下命名空間：

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 如何將 shapefile 從多邊形轉換為線？
以下是一個逐步指南，說明 **如何將 shapefile** 資料從多邊形轉換為線，使用 Aspose.GIS。

### 步驟 1：設定文件目錄
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
將 `"Your Document Directory"` 替換為實際存放 shapefile 的路徑。

### 步驟 2：開啟來源 Shapefile
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
此行 **開啟來源 Polygon Shapefile**，以便讀取其要素。

### 步驟 3：建立目標 Linestring Shapefile
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
在此我們 **建立一個新的 Linestring Shapefile**，用來儲存轉換後的幾何圖形。

### 步驟 4：遍歷來源要素
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
此迴圈會走訪原始檔案中的每個多邊形要素。

### 步驟 5：將多邊形轉換為線串並寫入目標檔案
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
在此區塊我們 **將多邊形轉換為線** (`LineString`) 並將新要素加入目標 shapefile。

## 常見問題與技巧
- **座標系統不匹配** – 確保來源與目標圖層使用相同的空間參考；否則線可能會偏移。  
- **大型檔案** – 處理極大 shapefile 時，考慮串流特徵而非一次載入全部至記憶體。  
- **空幾何** – 防範具有空幾何的要素，以避免執行時例外。

## 常見問答

**Q: Aspose.GIS 是否相容所有 .NET 版本？**  
A: 是的，Aspose.GIS 支援多種 .NET 版本，確保與您的開發環境相容。

**Q: 我可以在商業專案中使用 Aspose.GIS 嗎？**  
A: 可以。若要在商業專案中使用 Aspose.GIS，請考慮在此處 [購買授權](https://purchase.aspose.com/buy)。

**Q: 有範例或文件可供參考嗎？**  
A: 有，您可以在 [documentation page](https://reference.aspose.com/gis/net/) 找到完整的文件與範例。

**Q: 有提供試用版嗎？**  
A: 有，您可透過前往 [this link](https://releases.aspose.com/) 取得免費試用版，體驗 Aspose.GIS。

**Q: 我可以在哪裡尋求協助或支援？**  
A: 請造訪 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 取得任何協助或支援相關的問題。

---

**最後更新：** 2026-01-10  
**測試環境：** Aspose.GIS for .NET (最新發行版)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
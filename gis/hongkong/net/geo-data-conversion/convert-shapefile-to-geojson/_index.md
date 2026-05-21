---
date: 2026-02-02
description: 學習如何使用 Aspose.GIS 在 .NET 中輕鬆將 Shapefile 轉換為 GeoJSON，並在 C# 讀取 Shapefile
  時實現無縫的地理空間資料互通。
linktitle: Convert Shapefile to GeoJSON
second_title: Aspose.GIS .NET API
title: 將 Shapefile 轉換為 GeoJSON
url: /zh-hant/net/geo-data-conversion/convert-shapefile-to-geojson/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將 Shapefile 轉換為 GeoJSON

## 簡介
在現代的地理資訊系統 (GIS) 中，**地理空間資料互通性** 是釋放強大空間分析能力的關鍵。最常見的轉換任務之一是**將 shapefile 轉換為 geojson**，讓資料能以輕量方式在 Web 地圖、行動應用程式與雲端服務之間交換。在本教學中，您將學會如何**在 C# 中讀取 shapefile**，並使用 Aspose.GIS .NET 函式庫將其匯出為 GeoJSON，從而直接在您的應用程式中整合此轉換功能。

## 快速回答
- **什麼程式庫負責轉換？** Aspose.GIS for .NET  
- **實作需要多長時間？** 單一檔案通常在 10 分鐘以內  
- **需要授權嗎？** 免費試用可用於開發；正式環境需購買授權  
- **支援的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7  
- **可以一次轉換多個檔案嗎？** 可以 – 只要在 `VectorLayer.Convert` 呼叫上加上迴圈即可  

## 什麼是「將 shapefile 轉換為 geojson」？
將 Shapefile（`.shp`、`.shx`、`.dbf` 三個檔案）轉換成 GeoJSON，會把資料變成單一的 JSON 為基礎格式，易於閱讀、編輯與在瀏覽器中呈現。GeoJSON 特別適合用於 Leaflet、Mapbox 等 JavaScript 地圖函式庫。

## 為什麼使用 Aspose.GIS for .NET 進行 GIS 資料格式轉換？
- **全功能 API** – 可處理數十種格式（GeoTIFF、KML、GML、CSV 等），不需外部工具。  
- **零相依轉換** – 無需 GDAL 或其他原生函式庫。  
- **高效能** – 為大型資料集與批次處理優化。  
- **豐富客製化** – 可指定座標系統、屬性過濾等。  

## 先決條件
在開始之前，請確保您已具備以下項目：

1. **已安裝 Aspose.GIS for .NET** – 請依照官方 [Aspose.GIS for .NET 文件](https://reference.aspose.com/gis/net/) 的說明，將 NuGet 套件加入您的專案。  
2. **來源 Shapefile** – 可從開放資料平台、政府機構取得，或使用 QGIS/ArcGIS 建立。  
3. **基本的 C# 知識** – 程式碼範例使用 C# 語法與 .NET 慣例。  

## 匯入命名空間
首先，匯入可讓您使用 Aspose.GIS 類別與標準 .NET 工具的命名空間：

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 逐步指南

### 步驟 1：定義輸入與輸出路徑
設定包含 Shapefile 的資料夾以及 GeoJSON 檔案的目標位置。請依您的環境調整路徑。

```csharp
string dataDir = "Your Document Directory";
string shapefilePath = dataDir + "InputShapeFile.shp";
string jsonPath = dataDir + "output_out.json";
```

> **小技巧：** 使用 `Path.Combine(dataDir, "InputShapeFile.shp")` 以建立跨平台的路徑。

### 步驟 2：執行轉換
呼叫靜態的 `VectorLayer.Convert` 方法。這一行程式碼即會讀取 Shapefile、轉換並寫入 GeoJSON 檔案。

```csharp
VectorLayer.Convert(shapefilePath, Drivers.Shapefile, jsonPath, Drivers.GeoJson);
```

執行完畢後，`output_out.json` 會包含有效的 GeoJSON FeatureCollection，您可以將其載入任何網頁地圖檢視器。

## 為什麼這很重要
- **互通性：** 轉換為 GeoJSON 後，您可與各種基於網路的 GIS 工具共享資料，無需擔心專有格式。  
- **效能：** Aspose.GIS 在記憶體中處理轉換，比呼叫外部指令列工具更快。  
- **可擴充性：** 同樣的做法可包在迴圈或背景服務中，以處理資料管線的大量轉換。  

## 常見問題與解決方案
| 問題 | 發生原因 | 解決方式 |
|------|----------|----------|
| **檔案未找到** | `dataDir` 錯誤或缺少 `.shp` 檔案 | 檢查路徑，並確保三個 Shapefile 組件（`.shp`、`.shx`、`.dbf`）皆存在。 |
| **座標系統不匹配** | 來源 Shapefile 使用的投影未被消費者識別 | 在轉換前使用 `VectorLayer.Open(...).CoordinateSystem` 重新投影。 |
| **大型檔案導致記憶體壓力** | 整個資料集一次載入記憶體 | 將特徵分批處理或使用 `VectorLayer.Stream` 進行串流轉換。 |

## 常見問答

**Q: 我可以使用 Aspose.GIS for .NET 一次將多個 Shapefile 轉換為 GeoJSON 嗎？**  
A: 可以。將轉換程式碼放在 `foreach` 迴圈中，遍歷目錄下的每個 `.shp` 檔案。

**Q: Aspose.GIS for .NET 是否相容於所有 .NET Framework 版本？**  
A: 支援 .NET Framework 4.5 及以上版本，同時支援 .NET Core 3.1+ 以及 .NET 5/6/7。

**Q: Aspose.GIS for .NET 是否支援除 Shapefile 與 GeoJSON 之外的其他地理空間格式？**  
A: 當然。此函式庫支援包括 GeoTIFF、KML、GML、CSV 等多種格式。

**Q: 我可以自訂轉換流程，例如指定座標系統或屬性映射嗎？**  
A: 可以。API 提供多載方法與屬性，可設定目標座標系統、過濾屬性，並在轉換過程中修改要素幾何。

**Q: 是否有 Aspose.GIS for .NET 的試用版？**  
A: 有，您可從 [Aspose 官方網站](https://releases.aspose.com/) 下載免費試用版。

## 結論
依照上述步驟，您現在已掌握如何使用 **Aspose.GIS for .NET** 高效地**將 shapefile 轉換為 geojson**。此功能解鎖了無縫的**地理空間資料互通性**，讓您能將空間資料輸入現代 Web 地圖、API 與分析管線。探索 Aspose.GIS 更廣泛的**GIS 資料格式轉換**功能，處理 KML、GML、影像格式等，隨著專案需求持續成長。

---

**最後更新：** 2026-02-02  
**測試環境：** Aspose.GIS for .NET 24.11  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
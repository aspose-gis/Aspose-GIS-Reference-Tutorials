---
date: 2026-02-13
description: 了解如何使用 Aspose.GIS for .NET 將座標轉換為度分秒（DMS）。本一步一步的 C# 教學示範了 C# 轉換緯度與經度、十進位度數至度分秒等操作。
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 將座標轉換為 DMS
url: /zh-hant/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS 將座標轉換為 DMS

## Introduction
在本教學中，您將學習 **如何將座標** 轉換為 DMS（度、分、秒）使用功能強大的 Aspose.GIS .NET 函式庫。無論您需要 **c# convert lat long**、產生人類可讀的定位字串，或只是探索不同的座標格式，本指南都會以清晰的說明與可直接執行的 C# 程式碼逐步帶領您完成。

## Quick Answers
- **「將座標轉換為 DMS」是什麼意思？** 它將數值緯度/經度轉換為傳統的度‑分‑秒表示法。  
- **哪個函式庫負責轉換？** Aspose.GIS for .NET 提供 `GeoConvert` 類別，內建格式支援。  
- **我需要授權才能試用嗎？** 提供免費試用版；正式使用需購買商業授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、 .NET Core 3.1 以上，以及 .NET 5/6 以上。  
- **我可以使用相同程式碼轉換其他格式嗎？** 可以，只需更改 `PointFormats` 列舉值（例如 `DecimalDegrees`、`GeoRef`）。  

## 如何將座標轉換為 DMS
在深入程式碼之前，先說明為何 DMS 仍然有價值。製圖師、飛行員以及許多 GIS 資料提供者都依賴 DMS，因為它對人類友好且符合傳統地圖。Aspose.GIS 免除手動計算的需求，讓您專注於應用程式邏輯。

## 什麼是座標轉換為 DMS？
將座標轉換為 DMS 會把十進位緯度與經度重新寫成類似 `25°30'00"N 45°30'00"E` 的格式。此表示法廣泛應用於製圖、導航與 GIS 資料交換。

## 為什麼使用 Aspose.GIS 進行座標轉換？
- **全功能 API** – 無需外部函式庫或複雜運算；Aspose.GIS 內部處理解析與格式化。  
- **高精度** – 精確處理負值與半球指示等邊緣情況。  
- **跨平台** – 在 Windows、Linux 與 macOS .NET 執行環境上表現相同。  
- **可擴充** – 可輕鬆在 DMS、十進位度、度‑十進位分與 GeoRef 格式之間切換。  

## 前置條件
在開始之前，請確保您已具備以下條件：

1. **C# 基礎知識** – 熟悉變數、方法呼叫與主控台輸出。  
2. **已安裝 Aspose.GIS** – 從 [Aspose.GIS 官方網站](https://releases.aspose.com/gis/net/) 下載最新套件。  

## 匯入命名空間
首先，匯入 GIS 操作所需的命名空間：

```csharp
using System;
using Aspose.Gis;
```

## 步驟說明

### 步驟 1：啟動轉換程序
我們會印出友善訊息，讓您知道示範已開始。

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### 步驟 2：轉換為十進位度  
即使最終目標是 DMS，我們仍先顯示原始的十進位表示。這同時示範了稍後會使用的 **decimal degrees to dms** 路徑。

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### 步驟 3：轉換為度‑十進位分  
此格式（`DD°MM.m'`）是常見的中間步驟，當您需要 *convert lat long degree minutes* 時。

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### 步驟 4：轉換為度‑分‑秒 (DMS)  
這是本教學的核心——**convert coordinates to DMS**。

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### 步驟 5：轉換為 GeoRef  
為了完整性，我們也示範 `GeoRef` 格式，該格式在遙測工作流程中很有用。

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## 常見問題與解決方案
- **半球字母不正確** – 確認對北/東傳入正值，對南/西傳入負值；API 會自動加入正確的後綴。  
- **輸出意外為空** – 確認已正確參考 `Aspose.Gis` 程式集，且專案目標為支援的 .NET 版本。  
- **找不到授權** – 將授權檔案放在應用程式根目錄，或以程式碼設定：`License license = new License(); license.SetLicense("Aspose.GIS.lic");`。  

## 常見問答

**Q: Aspose.GIS 是否相容其他程式語言？**  
A: Aspose.GIS 主要針對 .NET 開發者，但亦提供 Java 版。

**Q: 我可以在購買前試用 Aspose.GIS 嗎？**  
A: 可以，您可從[網站](https://releases.aspose.com/) 取得 Aspose.GIS 的免費試用版。

**Q: 如何取得 Aspose.GIS 的支援？**  
A: 您可前往 Aspose.GIS 社群論壇[此處](https://forum.aspose.com/c/gis/33)尋求協助。

**Q: 是否提供 Aspose.GIS 的臨時授權？**  
A: 有，您可在[臨時授權頁面](https://purchase.aspose.com/temporary-license/)取得。

**Q: 在哪裡可以購買 Aspose.GIS？**  
A: 您可於[購買頁面](https://purchase.aspose.com/buy)購買。

## 結論
透過上述步驟，您現在已了解如何使用 Aspose.GIS for .NET **convert coordinates to DMS** 以及其他常見 GIS 格式。此功能讓您能將人類可讀的定位字串無縫整合至地圖應用、報告或任何空間資料工作流程。歡迎嘗試不同的緯度/經度值，並探索 `GeoConvert` 類別提供的其他格式。

---

**最後更新：** 2026-02-13  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
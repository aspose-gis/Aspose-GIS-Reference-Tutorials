---
date: 2025-12-11
description: 了解如何使用 Aspose.GIS for .NET 將座標轉換為 DMS。包括 C# 範例、C# 轉換緯度經度，以及逐步指南。
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: 使用 Aspose.GIS for .NET 將座標轉換為度分秒
url: /zh-hant/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS 將座標轉換為 DMS

## 介紹
在本教學中，您將了解如何使用功能強大的 Aspose.GIS .NET 函式庫 **convert coordinates to DMS**（度、分、秒）。無論您是需要 c# convert latitude longitude 以供製圖應用、產生人類可讀的定位字串，或只是想探索不同的座標格式，本指南都會以清晰的說明和可直接執行的 C# 程式碼，逐步帶領您完成。

## 快速解答
- **什麼是「convert coordinates to DMS」的意思？** 它將數值緯度/經度轉換為傳統的度‑分‑秒表示法。  
- **哪個函式庫負責轉換？** Aspose.GIS for .NET 提供 `GeoConvert` 類別，內建格式支援。  
- **我需要授權才能試用嗎？** 可使用免費試用版；商業授權則需於正式環境使用。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+ 以及 .NET 5/6+。  
- **我可以用相同程式碼處理其他格式嗎？** 可以，只需變更 `PointFormats` 列舉值（例如 `DecimalDegrees`、`GeoRef`）。

## 什麼是座標轉換為 DMS？
將座標轉換為 DMS 會把十進位緯度與經度重新寫成類似 `25°30'00"N 45°30'00"E` 的格式。此表示法廣泛應用於製圖、導航以及 GIS 資料交換。

## 為何使用 Aspose.GIS 進行座標轉換？
- **All‑in‑one API** – 無需外部函式庫或複雜計算，Aspose.GIS 於內部處理解析與格式化。  
- **High accuracy** – 精確處理負值與半球指示等邊緣情況。  
- **Cross‑platform** – 在 Windows、Linux 及 macOS .NET 執行環境上皆能一致運作。  
- **Extensible** – 可輕鬆在 DMS、十進位度、度‑十進位分以及 GeoRef 格式之間切換。

## 前置條件
在開始之前，請確保您已具備以下條件：

1. **Basic knowledge of C#** – 熟悉變數、方法呼叫與主控台輸出。  
2. **Aspose.GIS installed** – 從 [Aspose.GIS website](https://releases.aspose.com/gis/net/) 下載最新套件。

## 匯入命名空間
首先，匯入 GIS 操作所需的命名空間：

```csharp
using System;
using Aspose.Gis;
```

## 步驟說明

### 步驟 1：開始轉換程序
我們會輸出友善訊息，讓您知道示範已開始。

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### 步驟 2：轉換為十進位度
雖然最終目標是 DMS，我們仍先展示原始的十進位表示。

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### 步驟 3：轉換為度‑十進位分
此格式（`DD°MM.m'`）是常見的中間步驟，當您需要 *convert lat long degree minutes* 時會使用。

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### 步驟 4：轉換為度‑分‑秒 (DMS)
以下為本教學的核心——**convert coordinates to DMS**。

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### 步驟 5：轉換為 GeoRef
為了完整性，我們亦示範 `GeoRef` 格式，於遙測工作流程中相當有用。

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## 常見問題與解決方案
- **Incorrect hemisphere letters** – 確認對北/東傳入正值，對南/西傳入負值；API 會自動加入正確的後綴。  
- **Unexpected blank output** – 檢查是否正確參考 `Aspose.Gis` 程式集，且專案目標為支援的 .NET 版本。  
- **License not found** – 將授權檔放置於應用程式根目錄，或以程式碼設定：`License license = new License(); license.SetLicense("Aspose.GIS.lic");`。

## 常見問答

**Q: Aspose.GIS 是否相容於其他程式語言？**  
A: Aspose.GIS 主要針對 .NET 開發者，但亦提供 Java 版。

**Q: 我可以在購買前試用 Aspose.GIS 嗎？**  
A: 可以，您可從 [website](https://releases.aspose.com/) 取得 Aspose.GIS 免費試用版。

**Q: 如何取得 Aspose.GIS 的支援？**  
A: 您可前往 Aspose.GIS 社群論壇 [here](https://forum.aspose.com/c/gis/33) 尋求協助。

**Q: 是否提供 Aspose.GIS 臨時授權？**  
A: 有，您可從 [temporary license page](https://purchase.aspose.com/temporary-license/) 取得。

**Q: 在哪裡可以購買 Aspose.GIS？**  
A: 您可於 [purchase page](https://purchase.aspose.com/buy) 購買。

## 結論
透過上述步驟，您現在已了解如何使用 Aspose.GIS for .NET **convert coordinates to DMS** 以及其他常見 GIS 格式。此功能讓您能將人類可讀的定位字串無縫整合至製圖應用、報告或任何空間資料工作流程中。歡迎自行嘗試不同的緯度/經度值，並探索 `GeoConvert` 類別提供的其他格式。

---

**最後更新：** 2025-12-11  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
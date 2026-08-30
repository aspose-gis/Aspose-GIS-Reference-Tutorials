---
date: 2026-08-18
description: 使用 Aspose.GIS for .NET 將 decimal degrees 轉換為 dms。本逐步 C# 教學說明如何將 latitude/longitude、decimal
  degrees 轉換為 dms 以及其他操作。
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: 轉換座標
og_description: 使用 Aspose.GIS for .NET 輕鬆完成 decimal degrees 轉 dms 的轉換。學習將 latitude‑longitude
  值轉換為以 minutes 表示的 dms 格式。
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: 如何使用 Aspose.GIS for .NET 將 decimal degrees 轉換為 dms
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  headline: How to convert decimal degrees to dms with Aspose.GIS for .NET
  type: TechArticle
- description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  name: How to convert decimal degrees to dms with Aspose.GIS for .NET
  steps:
  - name: start the conversion process
    text: We print a friendly message so you know the demo has begun.
  - name: convert to decimal degrees
    text: Even though the final goal is DMS, we start by showing the original decimal
      representation. This also demonstrates the **decimal degrees to dms** path you’ll
      later follow.
  - name: convert to degree decimal minutes
    text: This format (`DD°MM.m'`) is a common intermediate step when you need to
      **convert lat long degree minutes**.
  - name: convert to degree minutes seconds (dms)
    text: Here’s the core of our tutorial—**convert coordinates to dms**.
  - name: convert to GeoRef
    text: For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing
      workflows.
  type: HowTo
- questions:
  - answer: Aspose.GIS primarily targets .NET developers, but a Java version is also
      available.
    question: Is Aspose.GIS compatible with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.GIS before purchasing?
  - answer: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  - answer: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert coordinates
- Aspose.GIS
- .NET GIS processing
title: 如何使用 Aspose.GIS for .NET 將 decimal degrees 轉換為 dms
url: /zh-hant/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS 將十進位度轉換為度分秒 (DMS)

## 簡介
在本教學中，您將學習 **如何將十進位度轉換為度分秒**，使用功能強大的 Aspose.GIS .NET 函式庫。無論您需要 **C# 轉換緯度經度**、為報告產生易於閱讀的位置字串，或只是探索不同的座標格式，本指南都會以清晰的說明與可直接執行的 C# 程式碼片段，逐步帶領您完成每個步驟。

## 快速解答
- **「將座標轉換為 DMS」是什麼意思？** 它會將數值緯度/經度轉換為傳統的度‑分‑秒表示法。  
- **哪個函式庫負責此轉換？** Aspose.GIS for .NET 提供具備內建格式支援的 `GeoConvert` 類別。  
- **我需要授權才能試用嗎？** 提供免費試用版；正式使用則需商業授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上，以及 .NET 5/6+。  
- **我可以使用相同程式碼處理其他格式嗎？** 可以，只需更改 `PointFormats` 列舉值（例如 `DecimalDegrees`、`GeoRef`）。

## 什麼是座標轉換為 DMS？
將座標轉換為 DMS 會將十進位緯度與經度重新寫成類似 `25°30'00"N 45°30'00"E` 的格式。此過程會將每個十進位度拆分為整度、分（度的六十分之一）與秒（分的六十分之一），再加上相應的半球指示字母（N、S、E、W）。此易於閱讀的形式對於許多舊有資料集以及在不使用十進位表示法的情況下傳達精確位置皆相當重要。

## 為何使用 Aspose.GIS 進行座標轉換？
Aspose.GIS 支援 **超過 50 種輸入與輸出格式**，且能在不將整個資料集載入記憶體的情況下處理數百頁的 GIS 檔案。API 在負值與半球指示等特殊情況下提供次毫米級的精度，且可在 Windows、Linux 與 macOS .NET 執行環境中一致運作。

## 先決條件
在開始之前，請確保您已具備以下條件：

1. **C# 基礎知識** – 熟悉變數、方法呼叫與主控台輸出。  
2. **已安裝 Aspose.GIS** – 從 [Aspose.GIS 官方網站](https://releases.aspose.com/gis/net/) 下載最新套件。您亦可於 [Aspose 釋出網站](https://releases.aspose.com/) 瀏覽主要的 Aspose 版本。

## 匯入命名空間
首先，匯入 GIS 操作所需的命名空間：

Import Namespaces 佔位符保持不變。

## 逐步指南

### 什麼是 GeoConvert 類別？
`GeoConvert` 類別提供靜態方法，用於在十進位度、DMS 與 GeoRef 等座標格式之間進行轉換。它包含接受原始數值或 `Point` 物件的多載，並回傳格式化字串或新的 `Point` 實例。透過處理負座標與四捨五入等邊緣情況，該類別確保輸出符合標準 GIS 規範，簡化在任何 .NET 地圖應用程式中的整合。

### 步驟 1：開始轉換程序
我們會印出友善訊息，讓您知道示範已開始。

```csharp
using System;
using Aspose.Gis;
```

### 步驟 2：轉換為十進位度
雖然最終目標是 DMS，我們仍先顯示原始的十進位表示。這同時示範了稍後將會使用的 **十進位度轉換為 DMS** 流程。

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### 步驟 3：轉換為度十進位分
此格式（`DD°MM.m'`）是常見的中間步驟，當您需要 **將緯度經度轉換為度分** 時會使用。

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### 步驟 4：轉換為度分秒 (DMS)
這就是本教學的核心——**將座標轉換為 DMS**。

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### 步驟 5：轉換為 GeoRef
為了完整性，我們亦示範 `GeoRef` 格式，該格式在遙測工作流程中相當有用。

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## 常見問題與解決方案
- **半球字母不正確** – 請確保對北/東傳入正值，對南/西傳入負值；API 會自動加上正確的後綴。  
- **意外的空白輸出** – 請確認已正確引用 `Aspose.Gis` 程式集，且專案目標為受支援的 .NET 版本。  
- **找不到授權** – 請將授權檔案放置於應用程式根目錄，或以程式碼設定：`License license = new License(); license.SetLicense("Aspose.GIS.lic");`。

## 常見問與答

**Q: Aspose.GIS 是否相容於其他程式語言？**  
A: Aspose.GIS 主要針對 .NET 開發者，但亦提供 Java 版。

**Q: 我可以在購買前試用 Aspose.GIS 嗎？**  
A: 可以，您可從[網站](https://releases.aspose.com/) 取得 Aspose.GIS 的免費試用版。

**Q: 如何取得 Aspose.GIS 的支援？**  
A: 您可前往 Aspose.GIS 社群論壇[此處](https://forum.aspose.com/c/gis/33) 尋求協助。

**Q: 是否提供 Aspose.GIS 的臨時授權？**  
A: 有，您可從[臨時授權頁面](https://purchase.aspose.com/temporary-license/) 取得。

**Q: 我該從哪裡購買 Aspose.GIS？**  
A: 您可於[購買頁面](https://purchase.aspose.com/buy) 購買 Aspose.GIS。

## 結論
透過上述步驟，您現在已了解如何使用 Aspose.GIS for .NET **將十進位度轉換為 DMS** 以及其他常見 GIS 格式。此功能讓您能將易於閱讀的位置字串無縫整合至地圖應用程式、報告或任何空間資料工作流程中。歡迎自行嘗試不同的緯度/經度值，並探索 `GeoConvert` 類別提供的其他格式。

---

**最後更新：** 2026-08-18  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## 相關教學

- [如何使用 Aspose.GIS for .NET 建立點幾何並取得幾何類型](/gis/net/geometry-analysis/get-geometry-type/)
- [如何轉換 GeoJSON – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [使用 Aspose.GIS 建立 MultiPoint 幾何（.NET）](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2025-12-21
description: 學習如何使用 Aspose.GIS for .NET 的 ExtendedPostGis 變體來建立線串幾何並將幾何轉換為 WKB。
linktitle: Specify WKB Variant on Translation
second_title: Aspose.GIS .NET API
title: 在 Aspose.GIS .NET 中建立線串幾何與 WKB 變體
url: /zh-hant/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.GIS for .NET 中指定 WKB 變體於轉換

## 介紹
在地理資訊系統 (GIS) 開發領域，Aspose.GIS for .NET 以其強大的工具組脫穎而出。若您需要 **建立 linestring 幾何**，再 **將幾何轉換為 WKB**，本篇正是您的最佳參考。其彈性與效能使其成為開發者在 .NET 應用程式中無縫整合 GIS 功能的首選。本指南將完整說明如何在 Aspose.GIS for .NET 中於翻譯過程中指定 WKB（Well‑Known Binary）變體。

## 快速回答
- **WKB 代表什麼？** Well‑Known Binary，幾何物件的緊湊二進位表示。  
- **哪種 WKB 變體能儲存 SRID 資訊？** `ExtendedPostGis`（EWKB）變體。  
- **執行程式碼是否需要授權？** 生產環境必須使用臨時或正式授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上，以及 .NET 5/6 以上。  
- **實作大約需要多久？** 基本範例通常在 10 分鐘內完成。

## 什麼是 Linestring 幾何？
Linestring 是由一系列點以直線段相連組成的簡單幾何形狀，常用於表示道路、河流或任何線性特徵。

## 為什麼要指定 WKB 變體？
選擇正確的 WKB 變體可確保重要的中繼資料（例如空間參考系統識別碼 SRID）在儲存或交換幾何資料時不會遺失。`ExtendedPostGis` 變體（EWKB）在與 PostgreSQL/PostGIS 或任何需要在二進位中嵌入 SRID 資訊的系統合作時特別有用。

## 前置條件
在深入探討 Aspose.GIS for .NET 中指定 WKB 變體的細節之前，請先確保已具備以下前置條件：

### 安裝 Aspose.GIS for .NET
1. 下載 Aspose.GIS：前往 [download link](https://releases.aspose.com/gis/net/) 取得 Aspose.GIS for .NET 套件。  
2. 安裝套件：依照文件中的安裝說明，將 Aspose.GIS 無縫整合至您的 .NET 環境。

### 熟悉 C# 程式設計
1. 基礎 C# 知識：確保您具備 C# 語言語法與概念的基本了解。

## 匯入命名空間
要順利啟動 Aspose.GIS for .NET 並有效使用其功能，您需要在專案中匯入必要的命名空間。以下提供逐步說明：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

上述命名空間讓您得以輕鬆存取 Aspose.GIS 的功能，處理地理資料不再是難題。

## 如何建立 linestring 幾何？
讓我們將範例拆解為多個步驟，深入了解在翻譯過程中指定 WKB 變體的完整流程。

### 步驟 1：建立 Geometry 物件
```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
在此步驟中，我們 **建立一個 linestring 幾何**，以指定的座標表示線性特徵。

### 步驟 2：產生 WKB 表示
```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
此處，我們使用 `ExtendedPostGis` 變體 **將幾何轉換為 WKB**，並將 SRID 資訊嵌入其中。

### 步驟 3：寫入檔案
```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
最後，我們將產生的 WKB 二進位資料寫入名為 `EWkbFile.ewkb` 的檔案，存放於您指定的目錄下。

## 常見問題與解決方案
| 問題 | 原因 | 解決方案 |
|------|------|----------|
| **檔案為空** | `Path.Combine` 指向不存在的目錄。 | 確認目標目錄已存在，或使用 `Directory.CreateDirectory` 建立。 |
| **SRID 錯誤** | 使用預設的 `WkbVariant.Standard` 會遺失 SRID。 | 需要保留 SRID 時，務必使用 `WkbVariant.ExtendedPostGis`。 |
| **授權例外** | 生產環境未使用有效授權。 | 在生產環境執行程式前，先套用臨時或正式授權。 |

## 常見問答
### Aspose.GIS for .NET 是否相容所有 .NET 版本？
Aspose.GIS for .NET 設計上相容多種 .NET 版本，提供開發者彈性與便利。

### 使用 Aspose.GIS for .NET 時，我可以請求支援或協助嗎？
可以，您可透過專屬的 [Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33) 向專家與其他開發者尋求協助。

### Aspose.GIS for .NET 是否提供免費試用？
有，您可前往 [此連結](https://releases.aspose.com/) 取得免費試用版，體驗其功能與效能。

### 如何取得 Aspose.GIS for .NET 的臨時授權？
請造訪 [臨時授權頁面](https://purchase.aspose.com/temporary-license/)，依照指示取得臨時授權。

### 我可以從哪裡購買 Aspose.GIS for .NET 的正式授權？
請至購買頁面 [此連結](https://purchase.aspose.com/buy) 完成授權購買。

## Frequently Asked Questions
**Q: 可以將 EWKB 檔案與 PostGIS 一起使用嗎？**  
A: 可以，`ExtendedPostGis` 變體產生的 EWKB 含有 SRID，PostGIS 能直接讀取。

**Q: 能否將 WKB 檔案讀回成 Geometry 物件？**  
A: 當然可以。使用 `Geometry.FromBinary(byteArray)` 即可重建幾何。

**Q: 此函式庫是否支援其他幾何類型，例如多邊形？**  
A: 支援。Aspose.GIS 可處理點、linestring、polygon、multipolygon 等多種幾何。

**Q: 建立幾何時如何指定不同的 SRID？**  
A: 在呼叫 `AsBinary` 前，先設定幾何物件的 SRID，例如 `geometry.SRID = 4326;`。

**Q: 這段程式碼能在 .NET Core 上執行嗎？**  
A: 能，相同的 API 在 .NET Framework、 .NET Core 以及 .NET 5/6 上皆可使用。

---

**最後更新：** 2025-12-21  
**測試環境：** Aspose.GIS for .NET 23.9（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
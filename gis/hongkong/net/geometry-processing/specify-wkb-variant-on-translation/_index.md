---
date: 2026-06-10
description: 了解如何在 .NET 中建立 linestring geometry，並使用 Aspose.GIS for .NET 及 ExtendedPostGis
  變體將 geometry 轉換為 WKB。
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: 在翻譯時指定 WKB Variant
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  headline: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  name: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  steps:
  - name: Creating a Geometry Object
    text: The `Geometry` class is Aspose.GIS's base type that represents any spatial
      object in memory. Linestring represents a series of connected points forming
      a linear geometry. In this step we instantiate a `Linestring` with a collection
      of coordinate pairs that model a simple road segment.
  - name: Generating WKB Representation
    text: '`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to
      include SRID in the output binary. Here we call the `AsBinary` method, passing
      the EWKB variant, which returns a `byte[]` containing the full binary representation.'
  - name: Writing to File
    text: '`File.WriteAllBytes` writes the binary array to disk. The resulting file
      (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB`
      function.'
  type: HowTo
- questions:
  - answer: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which
      PostGIS reads directly via `ST_GeomFromEWKB`.
    question: Can I use the EWKB file with PostGIS?
  - answer: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry
      from its binary form.
    question: Is it possible to read a WKB file back into a geometry object?
  - answer: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons,
      and many more spatial types.
    question: Does the library support other geometry types like polygons?
  - answer: Set the `SRID` property on the geometry object before calling `AsBinary`,
      e.g., `linestring.SRID = 4326;`.
    question: How do I specify a different SRID when creating the geometry?
  - answer: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6
      without modification.
    question: Will this code work on .NET Core?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 在 Aspose.GIS for .NET 中建立 Linestring Geometry 與 WKB Variant
url: /zh-hant/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS for .NET 建立 Linestring 幾何與 WKB 變體

## 介紹
如果您需要 **在 .NET 中建立 linestring 幾何**，並將該幾何轉換為二進位形式，Aspose.GIS for .NET 提供一套簡潔且高效能的 API，支援 .NET Framework、.NET Core 以及 .NET 5/6+。本教學將逐步說明從匯入命名空間到寫入 EWKB 檔案的全部流程，讓您能保留 SRID 資訊，並輕鬆將 GIS 資料整合至 PostgreSQL/PostGIS 或任何基於二進位的工作流程。

## 快速解答
- **WKB 代表什麼？** Well‑Known Binary，幾何物件的緊湊二進位表示。  
- **哪種 WKB 變體會儲存 SRID？** `ExtendedPostGis`（EWKB）變體會直接在二進位中嵌入 SRID。  
- **我需要授權嗎？** 在正式部署時需要臨時或完整的 Aspose.GIS 授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+ 以及 .NET 5/6+。  
- **實作需要多長時間？** 基本範例通常在 10 分鐘以內完成。

## 什麼是 Linestring 幾何？
Linestring 幾何是一種由有序點列表組成、以直線段相連的簡單形狀。它是空間資料庫中道路、管線或河流路徑等線性特徵的首選表示方式。

## 為什麼要指定 WKB 變體？
使用正確的 WKB 變體可確保關鍵的中繼資料——尤其是空間參考系統識別碼 (SRID)——隨幾何一起傳遞。`ExtendedPostGis`（EWKB）變體會將 SRID 儲存在二進位負載中，從而實現與 PostGIS、Oracle Spatial 或任何需要 SRID 資訊的二進位系統之間的無縫往返。

## 前置條件
在開始之前，請確保您已具備以下條件：

### 安裝 Aspose.GIS for .NET
1. 下載 Aspose.GIS：前往[下載連結](https://releases.aspose.com/gis/net/)取得最新套件。  
2. 將 NuGet 套件加入您的專案（例如 `Install-Package Aspose.GIS`）。  

### 熟悉 C# 程式設計
- 具備 C# 語法與專案結構的基本了解。  
- 能夠執行 .NET 主控台或類別庫專案。

## 匯入命名空間
`Aspose.GIS` 命名空間讓您可以存取所有與幾何相關的類別。  

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

這些命名空間提供核心 GIS 功能，包括幾何建立、轉換以及二進位序列化。

## 如何建立 linestring 幾何？
若要建立 linestring，請以有序的座標對集合實例化 `Linestring` 物件，必要時設定其 SRID，然後將其序列化為指定的 WKB 變體。此過程包含三個步驟：建立幾何、選擇保留 SRID 的 `ExtendedPostGis` 變體，以及將產生的位元組陣列寫入檔案。

### 步驟 1：建立幾何物件
`Geometry` 類別是 Aspose.GIS 的基礎類型，用於在記憶體中表示任何空間物件。Linestring 代表一系列相連的點，形成線性幾何。  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
在此步驟中，我們以座標對集合實例化 `Linestring`，模擬一段簡單的道路。

### 步驟 2：產生 WKB 表示
`WkbVariant.ExtendedPostGis` 為列舉值，指示 Aspose.GIS 在輸出二進位中包含 SRID。  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
此處呼叫 `AsBinary` 方法，傳入 EWKB 變體，返回包含完整二進位表示的 `byte[]`。

### 步驟 3：寫入檔案
`File.WriteAllBytes` 會將二進位陣列寫入磁碟。  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
產生的檔案（`EWkbFile.ewkb`）可直接使用 `ST_GeomFromEWKB` 函式匯入至 PostGIS 資料表。

## 常見問題與解決方案
| 問題 | 原因 | 解決方案 |
|-------|--------|----------|
| **空檔案** | `Path.Combine` 指向不存在的目錄。 | 確保目標目錄存在，或使用 `Directory.CreateDirectory` 建立它。 |
| **SRID 錯誤** | 使用預設的 `WkbVariant.Standard` 會遺失 SRID。 | 在需要保留 SRID 時，務必使用 `WkbVariant.ExtendedPostGis`。 |
| **授權例外** | 在生產環境中未使用有效授權執行。 | 在生產環境執行程式碼前，先套用臨時或完整授權。 |

## 常見問答
**Q: 我可以在 PostGIS 中使用 EWKB 檔案嗎？**  
A: 是的，`ExtendedPostGis` 變體會產生包含 SRID 的 EWKB，PostGIS 可直接透過 `ST_GeomFromEWKB` 讀取。  

**Q: 能否將 WKB 檔案讀回為幾何物件？**  
A: 當然可以。使用 `Geometry.FromBinary(byteArray)` 從二進位形式重建幾何。  

**Q: 此函式庫是否支援其他幾何類型，例如多邊形？**  
A: 是的，Aspose.GIS 支援點、linestring、polygon、multipolygon 以及更多空間類型。  

**Q: 建立幾何時，如何指定不同的 SRID？**  
A: 在呼叫 `AsBinary` 前，設定幾何物件的 `SRID` 屬性，例如 `linestring.SRID = 4326;`。  

**Q: 此程式碼能在 .NET Core 上執行嗎？**  
A: 可以，相同的 API 在 .NET Framework、 .NET Core 以及 .NET 5/6 上皆可無需修改使用。  

**最後更新：** 2026-06-10  
**測試環境：** Aspose.GIS for .NET 23.9（撰寫時的最新版本）  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [使用 Aspose.GIS for .NET 將幾何轉換為 WKB 格式](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [使用 Aspose.GIS 指定 WKT 變體進行轉換](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [使用 Aspose.GIS for .NET 建立 MultiLineString 幾何](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
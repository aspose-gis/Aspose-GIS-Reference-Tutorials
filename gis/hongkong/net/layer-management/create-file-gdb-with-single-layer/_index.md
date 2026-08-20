---
date: 2026-06-30
description: 了解如何使用 Aspose.GIS for .NET 在 File Geodatabase 中建立向量圖層。使用空間參考 WGS84 及
  File GDB 選項管理地理空間資料。
keywords:
- create vector layer
- add line feature
- manage geospatial data
- feature count example
- file gdb compression
linktitle: 建立單層 File GDB
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  headline: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  type: TechArticle
- description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  name: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  steps:
  - name: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
    text: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
  - name: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
    text: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
  type: HowTo
- questions:
  - answer: It means adding a new vector dataset (points, lines, or polygons) to a
      geodatabase file.
    question: What does “create vector layer” mean?
  - answer: Aspose.GIS for .NET provides full support for File GDB creation and editing.
    question: Which library should I use?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `SpatialReferenceSystem.Wgs84` for the common WGS84 datum.
    question: Can I set the spatial reference?
  - answer: Less than 30 lines to create the GDB, add a line feature, and read back
      the feature count.
    question: How many lines of code?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 在 File GDB 中建立向量圖層 – Aspose.GIS .NET 教程
url: /zh-hant/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 File GDB 中建立向量圖層

## 介紹
如果您需要在 File Geodatabase (GDB) 中 **create vector layer** 並有效管理地理空間資料，Aspose.GIS for .NET 為您提供乾淨的 code‑first 方法。在本步驟指南中，我們將示範如何寫入線狀要素、設定檔案 GDB 選項，並使用空間參考 WGS84——全部只需幾行 C# 程式碼。完成後，您將能計算圖層中的要素數量，並將產生的 GDB 整合至任何 .NET 地圖或分析工作流程。

## 快速解答
- **什麼是「create vector layer」的意思？** 它表示在地理資料庫檔案中新增一個向量資料集（點、線或多邊形）。  
- **應該使用哪個函式庫？** Aspose.GIS for .NET 完全支援 File GDB 的建立與編輯。  
- **開發時需要授權嗎？** 免費試用版可用於測試；正式環境需購買商業授權。  
- **可以設定空間參考嗎？** 可以 – 使用 `SpatialReferenceSystem.Wgs84` 以設定常用的 WGS84 基準。  
- **需要多少行程式碼？** 少於 30 行即可建立 GDB、加入線狀要素，並讀取要素計數。

## 「create vector layer」操作是什麼？
建立向量圖層即在地理資料庫中定義一個新表格，用來儲存幾何物件（點、線、多邊形）及其屬性。每一列代表一個要素，幾何欄位保存其形狀。於 Aspose.GIS 中，您可透過在 `FileGdbDataSource` 內實例化 `FeatureClass` 並指定幾何類型來完成此操作。

## 為什麼使用 Aspose.GIS 來建立向量圖層？
Aspose.GIS 消除外部相依，支援 **50+** GIS 格式，成為 .NET 開發者的一站式解決方案。  
它內建檔案 GDB 壓縮（對一般向量資料可減少高達 70 %）、空間索引，並即時支援完整的 WGS84 處理。此函式庫相容 .NET Framework 4.6+、.NET Core 2.0+ 以及 .NET 5/6，讓您無需額外原生函式庫即可在任何現代 Windows 或跨平台環境上使用。

## 前置條件
在開始之前，請確保您已具備：

1. **Aspose.GIS for .NET** – 從 [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/) 下載。  
2. **.NET 開發環境** – Visual Studio、Rider，或 `dotnet` CLI。  
3. **一個資料夾** 用於建立 File GDB（我們稱之為 *Your Document Directory*）。

## 匯入命名空間
`using` 陳述式將所需類型帶入作用域。  

`Document` 命名空間提供核心 GIS 物件，而 `System.IO` 處理檔案路徑。

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```

## 步驟 1：設定您的 Document 目錄
將 `"Your Document Directory"` 替換為您希望 File GDB 存放的絕對路徑。  
提前建立目錄可避免常見的 “File not found” 錯誤，這是新手最常遇到的問題。

```csharp
string dataDir = "Your Document Directory";
```

## 步驟 2：建立單一圖層的 File Geodatabase
`FileGdbOptions` 是一個類別，可讓您設定檔案 Geodatabase 的壓縮、空間索引及其他選項。  
此程式碼片段 **creates a vector layer**，使用 `FileGdbOptions` 寫入簡單的線狀要素，並將其存入使用 **spatial reference WGS84** 的 File GDB。

```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```

## 步驟 3：開啟 File Geodatabase 並取得圖層資訊
`FileGdbDataSource` 是建立與開啟 File Geodatabase 的入口點。  
`FeatureClass` 代表地理資料庫內的向量圖層，並提供對其要素的存取。  
此處我們透過開啟資料集並印出要素數量 **count features in the layer**，此例中為 `1`。

```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```

## 如何驗證圖層已正確建立？
使用 `FileGdbDataSource.Open` 開啟資料庫並查詢 `FeatureClass`。`Count` 屬性會回傳要素總數，證實線狀要素已成功寫入。此快速驗證步驟可協助您在大量匯入自動化時及早發現問題。

## 常見問題與解決方案
| Issue | Reason | Fix |
|-------|--------|-----|
| **`File not found`** | `path` 變數不正確 | 確認 `dataDir` 指向已存在的資料夾，且 `path` 正確與檔名結合，例如 `Path.Combine(dataDir, "MyData.gdb")`。 |
| **`Unsupported geometry`** | 使用了 File GDB 不允許的幾何類型 | 請使用 `Point`、`LineString` 或 `Polygon` 這些基本圖層的幾何類型。 |
| **`License not set`** | 在正式環境中未設定有效授權 | 使用以下程式碼註冊授權：`License license = new License(); license.SetLicense("Aspose.GIS.lic");`。 |

## 常見問答
### 我可以在現有的 .NET 專案中使用 Aspose.GIS for .NET 嗎？
可以，Aspose.GIS for .NET 可無縫整合至您現有的 .NET 專案。

### 是否提供 Aspose.GIS for .NET 的試用版？
可以，您可下載 [free trial version](https://releases.aspose.com/) 以探索 Aspose.GIS for .NET 的功能。

### 我可以在哪裡找到 Aspose.GIS for .NET 的詳細文件？
請參考 [documentation](https://reference.aspose.com/gis/net/) 取得 Aspose.GIS for .NET 的完整資訊。

### 如何取得 Aspose.GIS for .NET 的支援？
前往 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 取得社群支援與協助。

### 是否提供 Aspose.GIS for .NET 的臨時授權？
可以，您可取得 [temporary license](https://purchase.aspose.com/temporary-license/) 以供 Aspose.GIS for .NET 使用。

---

**Last Updated:** 2026-06-30  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## 相關教學

- [使用 Aspose.GIS 建立 File Geodatabase .NET 資料集](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [建立向量圖層並設定圖層空間參考系統](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [如何使用 Aspose.GIS 從 File GDB 資料集刪除圖層](/gis/net/layer-data-operations/remove-layers-from-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}
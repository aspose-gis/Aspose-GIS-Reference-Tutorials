---
date: 2026-01-10
description: 學習如何使用 Aspose.GIS for .NET 在檔案地理資料庫中建立向量圖層，並以 WGS84 空間參考及檔案 GDB 選項管理地理空間資料。
linktitle: Create File GDB with Single Layer
second_title: Aspose.GIS .NET API
title: 在 File GDB 中建立向量圖層 – Aspose.GIS .NET 教學
url: /zh-hant/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 File GDB 中建立向量圖層

## 介紹
如果您需要在 File Geodatabase (GDB) 中 **建立向量圖層**，並且有效管理地理空間資料，Aspose.GIS for .NET 為您提供乾淨的 code‑first 方式。在本分步指南中，我們將示範如何寫入線狀要素、設定 file gdb 選項，並使用空間參考 WGS84——全部只需幾行 C# 程式碼。完成後，您將能計算圖層中的要素數量，並將產生的 GDB 整合至任何 .NET 地圖或分析工作流程。

## 快速解答
- **「建立向量圖層」是什麼意思？** 代表在地理資料庫檔案中新增一個向量資料集（點、線或多邊形）。  
- **應該使用哪個函式庫？** Aspose.GIS for .NET 完整支援 File GDB 的建立與編輯。  
- **開發時需要授權嗎？** 免費試用可用於測試；正式環境需購買商業授權。  
- **可以設定空間參考嗎？** 可以——使用 `SpatialReferenceSystem.Wgs84` 取得常用的 WGS84 基準。  
- **需要多少行程式碼？** 不到 30 行即可建立 GDB、加入線狀要素，並讀回要素計數。

## 「建立向量圖層」操作是什麼？
建立向量圖層即是在地理資料庫內定義一個新表格，用以儲存幾何物件（點、線、多邊形）以及其屬性。此操作是任何需要 **管理地理空間資料** 的 GIS 應用程式的基礎。

## 為什麼使用 Aspose.GIS 來建立向量圖層？
- **零外部相依** – API 可直接在 .NET Framework、.NET Core 以及 .NET 5/6 上使用。  
- **完整支援 File GDB** – 可透過 `FileGdbOptions` 設定壓縮、空間索引等參數。  
- **內建空間參考處理** – 只要傳入 `SpatialReferenceSystem.Wgs84` 即可使用全球座標系統。  
- **簡潔 API** – 寫入線狀要素、加入圖層，並以少量方法呼叫取得要素計數。

## 前置條件
在開始之前，請確保您已具備：

1. **Aspose.GIS for .NET** – 從 [Aspose.GIS for .NET 下載頁面](https://releases.aspose.com/gis/net/) 取得。  
2. **.NET 開發環境** – Visual Studio、Rider，或 `dotnet` CLI。  
3. **一個資料夾** 用來放置即將建立的 File GDB（以下稱為 *Your Document Directory*）。

## 匯入命名空間
在 C# 檔案的最上方加入必要的 `using` 陳述式：

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

## 步驟 1：設定文件目錄
```csharp
string dataDir = "Your Document Directory";
```
將 `"Your Document Directory"` 替換為您希望 File GDB 所在的絕對路徑。

## 步驟 2：建立單一圖層的 File Geodatabase
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
此程式碼片段 **建立向量圖層**，使用 `FileGdbOptions`，寫入簡單的線狀要素，並以 **空間參考 WGS84** 儲存於 File GDB 中。

## 步驟 3：開啟 File Geodatabase 並取得圖層資訊
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```
此處我們 **計算圖層要素數量**，透過開啟資料集並印出要素數量——本例為 `1`。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|-------|--------|-----|
| **`File not found`** | `path` 變數不正確 | 確認 `dataDir` 指向已存在的資料夾，且 `path` 正確組合檔名，例如 `Path.Combine(dataDir, "MyData.gdb")`。 |
| **`Unsupported geometry`** | 使用了 File GDB 不支援的幾何類型 | 基本圖層請使用 `Point`、`LineString` 或 `Polygon`。 |
| **`License not set`** | 生產環境未設定有效授權 | 使用 `License license = new License(); license.SetLicense("Aspose.GIS.lic");` 註冊授權。 |

## 常見問答
### 我可以在現有的 .NET 專案中使用 Aspose.GIS for .NET 嗎？
可以，Aspose.GIS for .NET 可無縫整合至您現有的 .NET 專案。

### 是否提供 Aspose.GIS for .NET 的試用版？
可以，您可下載 [免費試用版](https://releases.aspose.com/) 來體驗 Aspose.GIS for .NET 的功能。

### 我可以在哪裡找到 Aspose.GIS for .NET 的詳細文件？
請參考 [文件說明](https://reference.aspose.com/gis/net/) 取得完整資訊。

### 我該如何取得 Aspose.GIS for .NET 的支援？
前往 [Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33) 取得社群支援與協助。

### 是否提供 Aspose.GIS for .NET 的臨時授權？
可以，您可申請 [臨時授權](https://purchase.aspose.com/temporary-license/) 以供測試使用。

---

**最後更新：** 2026-01-10  
**測試版本：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2025-12-06
description: 學習如何在 C# 中使用 Aspose.GIS for .NET 建立 LineString、向 LineString 添加點，並檢查幾何圖形是否覆蓋另一個。
linktitle: Create LineString C# – Check Geometry Covers Another
second_title: Aspose.GIS .NET API
title: 建立 LineString C# – 檢查幾何是否覆蓋另一個
url: /zh-hant/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 檢查幾何圖形覆蓋另一個

## 簡介
Aspose.GIS for .NET 是一個功能強大的函式庫，為開發人員提供在 .NET 應用程式中有效處理地理資料的工具。無論您是要建置地圖應用程式、分析空間資料，或將地理功能整合到軟體中，Aspose.GIS 都提供完整的功能集合，簡化開發流程。在本教學中，您將學習 **如何在 C# 中建立 LineString**、向線段加入點，並使用 `Covers` 與 `CoveredBy` 方法執行 **點在線上檢查**。

## 快速答覆
- **「在 C# 中建立 LineString」是什麼意思？** 代表實例化 `LineString` 幾何物件並填入座標點。  
- **哪個方法可檢查點是否位於線上？** 在 `LineString` 上使用 `Covers` 方法，或在 `Point` 上使用 `CoveredBy` 方法。  
- **執行範例是否需要授權？** 評估時可使用臨時授權；正式上線需購買完整授權。  
- **可以在 .NET Core 上使用嗎？** 可以，Aspose.GIS 同時支援 .NET Framework 與 .NET Core。  
- **LineString 可以加入多少個點？** 沒有硬性上限，您可以依需求加入任意數量的點。

## 什麼是 **create LineString C#**？
`LineString` 是由有序點列表組成、以直線段相連的幾何形狀。於 C# 中，您只需從 `Aspose.Gis.Geometries` 命名空間實例化 `LineString` 類別，然後使用 `AddPoint` 方法 **將點加入 LineString**。

## 為何使用 Aspose.GIS 進行點在線上檢查？
- **精確度** – 正確處理浮點運算與空間謂詞。  
- **跨平台** – 支援 .NET Framework、.NET Core 以及 .NET 5/6 以上版本。  
- **豐富 API** – 提供完整的空間關係方法（`Covers`、`CoveredBy`、`Intersects` 等）。

## 前置條件
在開始使用 Aspose.GIS for .NET 前，請確保已完成以下設定：

### 1. 安裝 Visual Studio
確保您的系統已安裝 Visual Studio。Aspose.GIS for .NET 可無，提供順暢的開發體驗。

### 2. 取得 Aspose.GIS for .NET
從[官方網站](https://releases.aspose.com/gis/net/)下載 Aspose.GIS for .NET 函式庫。您可以直接下載檔案，或使用 NuGet 等套件管理工具將其安裝至專案。

### 3. 熟悉 .NET Framework
具備 .NET Framework 與 C# 程式語言的基本知識，才能有效使用 Aspose.GIS for .NET。

### 4. 取得文件與支援
參考[文件說明](https://reference.aspose.com/gis/net/)取得 Aspose.GIS API 與功能的詳細資訊。如遇問題或有疑問，請前往[Aspose.GIS 論壇](https://forum.aspose.com/c/gis/33)尋求協助。

### 5. 可選：臨時授權
若您正在探索 Aspose.GIS for .NET，可從[此處](https://purchase.aspose.com/temporary-license/)取得臨時授權，以評估函式庫功能。

## 匯入命名空間
在專案中使用 Aspose.GIS for .NET 前，需匯入必要的命名空間：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

接下來，我們將範例程式分解為多個步驟，說明如何使用 Aspose.GIS for .NET **檢查一個幾何圖形是否覆蓋另一個**。

## 如何 **create LineString C#** – 步驟說明

### 步驟 1：建立 LineString 物件
```csharp
var line = new LineString();
```
此處，我們實例化一個新的 `LineString` 物件，代表二維空間中一系列相連的線段。

### 步驟 2：**將點加入 LineString**
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
我們使用 `AddPoint` 方法 **將點加入 LineString**。本範例加入兩個點：(0, 0) 與 (1, 1)，形成一條簡單的對角線段。

### 步驟 3：建立 Point 物件
```csharp
var point = new Point(0, 0);
```
實例化一個 `Point` 物件，代表二維空間中的單一座標點。此處建立座標為 (0, 0) 的點。

### 步驟 4 **點在線上檢查** – 線段是否覆蓋該點？
```csharp
Console.WriteLine(line.Covers(point));    // True
```
使用 `Covers` 方法檢查線段是否覆蓋該點。此例會回傳 `True`，因為點 (0, 0) 正好位於線上。

### 步驟 5：驗證反向關係 – 點是否被線段覆蓋？
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
同理，使用 `CoveredBy` 方法檢查點是否被線段覆蓋。由於點 (0, 0) 位於線上，亦會回傳 `True`。

## 常見問題與解決方案
| 問題 | 為何會發生 | 解決方式 |
|------|------------|----------|
| `line.Covers(point)` 回傳 `False`，即使點看起來在直線上 | 由於浮點精度，點座標可能不完全相同。 | 使用 `Math.Round` 處理座標，或以容差方式檢查 `line.Distance(point) < epsilon`。 |
| 缺少 `using Aspose.Gis.Geometries;` | 未匯入命名空間，導致編譯錯誤。 | 確認已加入匯入語句（見 **匯入命名空間** 章節）。 |
| 執行時出現授權例外 | 未載入有效授權。 | 使用 `License license = new License(); license.SetLicense("Aspose.GIS.lic");` 載入臨時或正式授權。 |

## 常見問答

**Q: 我可以在商業專案中使用 Aspose.GIS for .NET 嗎？**  
A: 可以，取得相應授權後，您可在商業與非商業專案中使用 Aspose.GIS for .NET。

**Q: Aspose.GIS for .NET 是否相容 .NET Core？**  
A: 是的，Aspose.GIS for .NET 同時支援 .NET Framework 與 .NET Core 環境。

**Q: Aspose.GIS for .NET 支援哪些 GIS 格式？**  
A: 支援多種 GIS 格式，包括 Shapefile、GeoJSON、KML 等。

**Q: 我可以為 Aspose.GIS for .NET 的開發貢獻程式碼嗎？**  
A: Aspose.GIS for .NET 為專有函式庫，外部無法直接貢獻程式碼。但您可提供回饋與建議，協助改進產品。

**Q: Aspose.GIS for .NET 的更新頻率如何？**  
A: 會定期釋出新版本，加入功能、改進與錯誤修正。請至[官方網站](https://releases.aspose.com/gis/net/)查詢最新發佈資訊。

## 結論
總結來說，Aspose.GIS for .NET 為 .NET 應用程式提供強大的地理資料處理工具。依照上述步驟，您即可順利 **在 C# 中建立 LineString**、**將點加入 LineString**，並執行 **點在線上檢查**，判斷一個幾何圖形是否覆蓋另一個。此功能可提升軟體的空間分析能力，並為更進階的 GIS 操作鋪路。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2025-12-06  
**測試環境：** Aspose.GIS for .NET（最新發佈版）  
**作者：** Aspose
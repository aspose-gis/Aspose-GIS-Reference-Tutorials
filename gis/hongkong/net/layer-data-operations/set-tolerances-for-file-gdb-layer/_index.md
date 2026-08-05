---
date: 2026-04-30
description: 學習如何使用 Aspose.GIS for .NET 建立 GDB 檔案、設定圖層精度，並透過檔案 GDB 選項控制容差。
keywords:
- how to create gdb
- create gis layer
- how to set tolerances
- set layer precision
- file gdb options
linktitle: 設定檔案 GDB 圖層的容差
second_title: Aspose.GIS .NET API
title: 如何建立 GDB 資料集並為圖層設定容差
url: /zh-hant/net/layer-data-operations/set-tolerances-for-file-gdb-layer/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何建立 GDB 資料集並為圖層設定容差

## 介紹
如果您需要 **create file GDB dataset** 並控制其精度，您來對地方了。在本教學中，我們將逐步說明整個流程——從設定 .NET 專案、建立 File Geodatabase (GDB) 資料集，到對新圖層套用 XY、Z 與 M 容差。完成後，您將擁有一個可直接使用、能順暢搭配 ArcGIS 工具及其他 GIS 應用的資料集。本指南示範 **how to create gdb** 檔案的程式化方式，讓您能自動化資料管線，免除手動操作。

## 快速解答
- **What does “create file GDB dataset” mean?** 它會在磁碟上建立一個新的 File Geodatabase 容器，可容納多個 GIS 圖層。  
- **Why set tolerances?** 容差定義了幾何運算的精度，避免在空間分析中出現四捨五入錯誤。  
- **Which Aspose.GIS class is used?** 使用 `Dataset.Create` 搭配 `FileGdbOptions`。  
- **Do I need a license for development?** 測試時使用臨時授權即可，正式環境則需完整授權。  
- **What .NET versions are supported?** 支援 .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 什麼是 File GDB 資料集？
File Geodatabase (GDB) 是以資料夾為基礎的資料儲存，內含 GIS 圖層、資料表與關聯。使用 Aspose.GIS，您可以程式化 **create file GDB dataset**，無需安裝 ArcGIS，十分適合自動化管線或自訂應用程式。

## 為何要為圖層設定容差？
設定容差可確保幾何計算（例如交集、緩衝或貼齊）符合所需的精度。這在處理高解析度資料或匯出至其他要求特定容差值的 GIS 平台時尤為重要。換句話說，您正透過 **setting layer precision** 來避免意外的幾何錯誤。

## 前置條件
- **Aspose.GIS for .NET Library** – 從 [download link](https://releases.aspose.com/gis/net/) 下載並安裝 Aspose.GIS 函式庫。若尚未取得，您可於 [documentation](https://reference.aspose.com/gis/net/) 進一步了解。
- **Development Environment** – Visual Studio、Rider，或任何支援 .NET 開發的 IDE。
- **A valid license** – 測試時使用臨時授權，正式環境則使用完整授權（請參閱 FAQ 部分的連結）。

現在您已備妥所有項目，讓我們匯入所需的命名空間。

## 匯入命名空間
在您的 .NET 應用程式中，加入以下命名空間以使用 Aspose.GIS 的功能：

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

有了這些命名空間，我們即可開始建構資料集。

## 如何建立 GDB 資料集？
以下是逐步指南，帶您完成資料集的建立與容差設定。

### 步驟 1：定義文件目錄
首先，將程式指向您想建立 File GDB 的資料夾：

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** 若需以跨平台方式組合路徑，請使用 `Path.Combine`。

### 步驟 2：建立 File GDB 資料集
現在我們實際在磁碟上 **create file GDB dataset**。`Dataset.Create` 方法接受完整路徑與驅動程式類型（`Drivers.FileGdb`）。

```csharp
var path = dataDir + "TolerancesForFileGdbLayer_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

> `using` 區塊確保在完成後資料集能正確關閉並寫入磁碟。

### 步驟 3：使用 `FileGdbOptions` 設定容差
在建立圖層之前，先定義所需的容差。`FileGdbOptions` 允許您指定 XY、Z 與 M 容差——這是控制精度的 **file gdb options** 物件。

```csharp
var options = new FileGdbOptions
{
    XYTolerance = 0.001,
    ZTolerance = 0.1,
    MTolerance = 0.1,
};
```

這些數值適用於高精度工程資料，您亦可依專案需求調整。

### 步驟 4：使用指定的容差建立 GIS 圖層
最後，在資料集中建立新圖層，傳入剛剛設定好的 options 物件。此步驟示範 **how to set tolerances** 同時 **creating a GIS layer**。

```csharp
using (var layer = dataset.CreateLayer("layer_name", options))
{
    // The layer is created with the provided tolerances, ready for use in ArcGIS features/tools.
}
```

當 `using` 區塊結束時，圖層會以您定義的容差儲存。

## 常見問題與解決方案
| 問題 | 發生原因 | 解決方法 |
|-------|----------------|-----|
| **Dataset path not found** | `dataDir` 變數指向一個不存在的資料夾。 | 確保該目錄存在，或使用 `Directory.CreateDirectory(dataDir)` 建立。 |
| **Invalid tolerance values** | 容差必須為非負數值。 | 使用正值；除非特意不需要容差，否則避免使用零。 |
| **License error** | 試用或臨時授權已過期。 | 套用新的臨時授權或升級為完整授權。 |

## 常見問答

**Q: 我可以將 Aspose.GIS for .NET 與其他 GIS 函式庫一起使用嗎？**  
A: 可以，Aspose.GIS 支援互通性，讓您能與如 NetTopologySuite 或 GDAL 等函式庫整合。

**Q: 是否提供 Aspose.GIS for .NET 的試用版？**  
A: 當然！您可透過 [free trial version](https://releases.aspose.com/) 體驗功能。

**Q: 我該如何取得 Aspose.GIS for .NET 的支援？**  
A: 前往 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 與社群聯繫並尋求協助。

**Q: 測試時是否需要臨時授權？**  
A: 是的，您可取得 [temporary license](https://purchase.aspose.com/temporary-license/) 以供測試與評估。

**Q: 我可以從哪裡購買 Aspose.GIS for .NET 授權？**  
A: 您可於 [buy page](https://purchase.aspose.com/buy) 購買授權。

## 結論
本指南說明了 **how to create gdb** 檔案、設定幾何容差，並使用 Aspose.GIS for .NET 儲存可直接使用的圖層。這些步驟讓您對空間資料擁有精確的控制，使 GIS 應用更可靠且具互通性。

---  
**最後更新：** 2026-04-30  
**測試版本：** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
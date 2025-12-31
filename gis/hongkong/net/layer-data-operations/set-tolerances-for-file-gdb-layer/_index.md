---
date: 2025-12-31
description: 探索 Aspose.GIS for .NET，學習如何輕鬆建立檔案 GDB 資料集並設定容差，提供一步一步的指導。提升您的 .NET 應用程式。
linktitle: Set Tolerances for File GDB Layer
second_title: Aspose.GIS .NET API
title: 建立檔案 GDB 資料集並為圖層設定容差
url: /zh-hant/net/layer-data-operations/set-tolerances-for-file-gdb-layer/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立檔案 GDB 資料集並為圖層設定容差

## 簡介
If you need to **create file GDB dataset** and control its precision, you’re in the right place. In this tutorial we’ll walk through the entire process—starting from setting up your .NET project, creating a File Geodatabase (GDB) dataset, and then applying XY, Z, and M tolerances to a new layer. By the end you’ll have a ready‑to‑use dataset that works smoothly with ArcGIS tools and other GIS applications.

## 快速解答
- **「create file GDB dataset」是什麼意思？** 它會在磁碟上建立一個新的 File Geodatabase 容器，可容納多個 GIS 圖層。  
- **為什麼要設定容差？** 容差定義了幾何運算的精度，可防止空間分析中的四捨五入錯誤。  
- **使用哪個 Aspose.GIS 類別？** `Dataset.Create` together with `FileGdbOptions`.  
- **開發時需要授權嗎？** 測試時使用臨時授權即可；正式環境則需要完整授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## 什麼是檔案 GDB 資料集？
A File Geodatabase (GDB) is a folder‑based data store that holds GIS layers, tables, and relationships. Using Aspose.GIS you can programmatically **create file GDB dataset** without needing ArcGIS installed, making it ideal for automated pipelines or custom applications.

## 為什麼要為圖層設定容差？
Setting tolerances ensures that geometry calculations (like intersections, buffering, or snapping) respect the precision you need. This is especially important when working with high‑resolution data or when exporting to other GIS platforms that expect specific tolerance values.

## 先決條件
- **Aspose.GIS for .NET Library** – 從 [download link](https://releases.aspose.com/gis/net/) 下載並安裝 Aspose.GIS 函式庫。如果您尚未取得，可在 [documentation](https://reference.aspose.com/gis/net/) 中進一步了解此函式庫。  
- **Development Environment** – Visual Studio、Rider，或任何支援 .NET 開發的 IDE。  
- **A valid license** – 測試時使用臨時授權，正式環境則需完整授權（請參閱 FAQ 部分的連結）。

現在您已備妥所有項目，讓我們匯入所需的命名空間。

## 匯入命名空間
In your .NET application, include the following namespaces to leverage the functionalities of Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

With the namespaces in place, we can start building the dataset.

## 逐步指南

### 步驟 1：定義文件目錄
First, point the code to the folder where you want the File GDB to be created:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** 如果需要以跨平台方式組合路徑，請使用 `Path.Combine`。

### 步驟 2：建立檔案 GDB 資料集
Now we actually **create file GDB dataset** on disk. The `Dataset.Create` method takes the full path and the driver type (`Drivers.FileGdb`).

```csharp
var path = dataDir + "TolerancesForFileGdbLayer_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

> `using` 區塊可確保在完成後正確關閉資料集並將資料寫入磁碟。

### 步驟 3：使用 `FileGdbOptions` 設定容差
Before creating a layer, define the tolerances you need. `FileGdbOptions` lets you specify XY, Z, and M tolerances.

```csharp
var options = new FileGdbOptions
{
    XYTolerance = 0.001,
    ZTolerance = 0.1,
    MTolerance = 0.1,
};
```

These values are typical for high‑precision engineering data, but you can adjust them to suit your project.

### 步驟 4：使用指定的容差建立圖層
Finally, create a new layer inside the dataset, passing the options object we just configured.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options))
{
    // The layer is created with the provided tolerances, ready for use in ArcGIS features/tools.
}
```

When the `using` block ends, the layer is saved with the tolerances you defined.

## 常見問題與解決方案
| 問題 | 發生原因 | 解決方法 |
|------|----------|----------|
| **找不到資料集路徑** | `dataDir` 變數指向一個不存在的資料夾。 | 確保該目錄存在，或使用 `Directory.CreateDirectory(dataDir)` 建立它。 |
| **容差值無效** | 容差必須為非負數。 | 使用正值；除非特意不需要容差，否則避免使用零。 |
| **授權錯誤** | 試用或臨時授權已過期。 | 套用新的臨時授權或升級為完整授權。 |

## 常見問題

**問：我可以將 Aspose.GIS for .NET 與其他 GIS 函式庫一起使用嗎？**  
A: 是的，Aspose.GIS 支援互通性，允許您與如 NetTopologySuite 或 GDAL 等函式庫整合。

**問：是否有 Aspose.GIS for .NET 的試用版可供使用？**  
A: 當然！您可透過 [free trial version](https://releases.aspose.com/) 來體驗功能。

**問：如何取得 Aspose.GIS for .NET 的支援？**  
A: 請前往 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 與社群聯繫並尋求協助。

**問：測試時是否需要臨時授權？**  
A: 是的，您可以取得 [temporary license](https://purchase.aspose.com/temporary-license/) 以供測試與評估。

**問：在哪裡可以購買 Aspose.GIS for .NET 授權？**  
A: 您可於 [buy page](https://purchase.aspose.com/buy) 購買授權。

## 結論
In this guide we covered how to **create file GDB dataset**, configure geometry tolerances, and save a ready‑to‑use layer with Aspose.GIS for .NET. These steps give you precise control over spatial data, making your GIS applications more reliable and interoperable.

---  
**最後更新：** 2025-12-31  
**測試環境：** Aspose.GIS for .NET 24.11（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
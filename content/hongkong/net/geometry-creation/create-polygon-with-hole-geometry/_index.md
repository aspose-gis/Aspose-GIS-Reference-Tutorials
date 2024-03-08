---
title: 使用 Aspose.GIS 建立具有孔幾何形狀的多邊形
linktitle: 使用孔幾何形狀建立多邊形
second_title: Aspose.GIS .NET API
description: 了解如何使用 Aspose.GIS for .NET 建立具有孔幾何形狀的多邊形。帶有程式碼範例的分步教程。
type: docs
weight: 13
url: /zh-hant/net/geometry-creation/create-polygon-with-hole-geometry/
---
## 介紹
在本教學中，我們將逐步介紹使用 Aspose.GIS for .NET 建立具有孔幾何形狀的多邊形的過程。 Aspose.GIS 是一個功能強大的程式庫，使開發人員能夠在其 .NET 應用程式中處理地理空間資料。 
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
1. Aspose.GIS for .NET Library：您可以從以下位置下載：[這裡](https://releases.aspose.com/gis/net/).
2. 開發環境：確保您已設定安裝了 Visual Studio 或任何其他 .NET IDE 的開發環境。
## 導入命名空間
首先，您需要匯入必要的命名空間以使用 Aspose.GIS 功能。操作方法如下：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

現在，讓我們繼續使用 Aspose.GIS for .NET 建立具有孔幾何形狀的多邊形。
## 第1步：建立多邊形對象
```csharp
Polygon polygon = new Polygon();
```
## 步驟 2：定義外環
```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```
## 步驟 3：定義內環（孔）
```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```
## 步驟 4：指派外環並將內環加入多邊形
```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```
## 結論
恭喜！您已成功學習如何使用 Aspose.GIS for .NET 建立具有孔幾何形狀的多邊形。這些知識對於各種地理空間應用將是有益的，在這些應用中，此類幾何形狀是必不可少的。
## 常見問題解答
### 1.什麼是Aspose.GIS？
Aspose.GIS 是一個 .NET 函式庫，使開發人員能夠處理地理空間數據，從而建立、讀取和操作各種地理空間檔案格式。
### 2.我可以將Aspose.GIS用於商業專案嗎？
是的，您可以透過購買許可證將 Aspose.GIS 用於個人和商業專案。訪問[這裡](https://purchase.aspose.com/buy)更多細節。
### 3. Aspose.GIS有免費試用版嗎？
是的，您可以從以下位置免費試用 Aspose.GIS：[這裡](https://releases.aspose.com/).
### 4. 在哪裡可以找到對 Aspose.GIS 的支援？
您可以在以下位置找到對 Aspose.GIS 的支持[Aspose.GIS論壇](https://forum.aspose.com/c/gis/33).
### 5. 如何取得Aspose.GIS的臨時許可證？
您可以從以下位置取得 Aspose.GIS 的臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
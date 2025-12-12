---
date: 2025-12-12
description: 學習如何使用 Aspose.GIS for .NET 建立向量圖層並新增圓形線幾何——快速構建 GIS 應用程式的方式。
linktitle: Create Circular String Geometry
second_title: Aspose.GIS .NET API
title: 在 Aspose.GIS for .NET 中建立向量圖層與圓形字串
url: /zh-hant/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.GIS for .NET 建立向量圖層與圓形串線幾何

## 介紹
如果您正在 .NET 平台上開發 GIS 應用程式，第一步通常是 **建立向量圖層** 物件，以儲存空間要素。Aspose.GIS for .NET 讓這個流程變得簡單，並且可以為圖層加入如圓形串線等進階幾何圖形。在本教學中，您將學會如何建立向量圖層、加入圓形串線幾何，並將結果儲存為 Shapefile——全部使用乾淨、可投入生產的 C# 程式碼。

## 快速回答
- **「create vector layer」是什麼意思？** 它會建立一個新的容器（圖層），可容納點、線或多邊形等空間要素。  
- **哪個類別代表圓形串線？** `CircularString`（來自 `Aspose.Gis.Geometries`）。  
- **我可以將圖層儲存為 Shapefile 嗎？** 可以 – 在建立圖層時使用 `Drivers.Shapefile`。  
- **開發時需要授權嗎？** 臨時授權可用於評估；正式環境需購買完整授權。  
- **.NET 支援的版本有哪些？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## 「create vector layer」是什麼？
向量圖層是將向量要素（點、線、面）以邏輯方式分組，存放於單一資料來源中的容器。在 Aspose.GIS 中，您透過呼叫 `VectorLayer.Create`，傳入目標檔案路徑與欲使用的驅動程式（例如 Shapefile）即可實例化圖層。圖層建立後，即可加入要素、指派幾何圖形，並執行空間運算。

## 為什麼要加入圓形串線？
圓形串線是一種 **線性幾何**，透過一系列點來近似弧線。它適用於表示彎曲道路、河流彎道，或任何需要平滑曲線而不想使用大量小線段的情況。

## 前置需求
在開始之前，請確保您已具備：

- **.NET Framework 或 .NET Core** 已安裝於您的機器上。  
- **Aspose.GIS for .NET** 函式庫 – 從官方網站 **[here](https://releases.aspose.com/gis/net/)** 下載。  
- 開發環境，例如 **Visual Studio** 或 **JetBrains Rider**。  
- 具備 **C#** 程式設計的基本知識。

## 匯入命名空間
在 C# 檔案中加入必要的命名空間：

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 步驟說明

### 步驟 1：定義輸出檔案路徑
設定 Shapefile 要寫入的位置。

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

將 `"Your Document Directory"` 替換為您系統上實際的資料夾路徑。

### 步驟 2：**建立向量圖層**
使用 `Create` 方法開啟 `VectorLayer`。這是 **create vector layer** 操作的核心。

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### 步驟 3：建立新要素
要素代表圖層內的單筆空間記錄。

```csharp
    var feature = layer.ConstructFeature();
```

### 步驟 4：建構圓形串線幾何
加入定義曲線形狀的點。點的序列會形成一段弧線，起點與終點相同，構成閉合的圓形串線。

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### 步驟 5：指派幾何並將要素加入圖層
將幾何圖形連結至要素，並儲存至圖層。

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

當 `using` 區塊結束時，圖層會自動寫入磁碟上的 Shapefile。

## 常見問題與解決方案
| 問題 | 解決方案 |
|------|----------|
| **檔案路徑無效** | 確認目錄已存在且您具有寫入權限。 |
| **CircularString 顯示為直線** | 檢查點的加入順序是否正確；閉合形狀的首尾點應相同。 |
| **授權例外** | 在開發期間套用臨時授權，正式環境則需購買完整授權。 |

## 常見問答

### Aspose.GIS for .NET 是否相容所有 .NET Framework 版本？
是的，Aspose.GIS for .NET 設計支援廣泛的 .NET 版本，從 Framework 4.5 到最新的 .NET 8 皆可使用。

### 我可以將 Aspose.GIS for .NET 與其他 GIS 函式庫整合嗎？
當然可以！您可以使用其他函式庫讀取資料，透過 Aspose.GIS 進行處理，然後再寫回，得益於其彈性的 API。

### Aspose.GIS for .NET 支援空間資料可視化嗎？
支援，函式庫內建渲染工具，可產生地圖與幾何圖形的視覺化表示。

### 有沒有社群論壇可以取得 Aspose.GIS for .NET 的協助？
有，您可以前往 Aspose.GIS 論壇 **[here](https://forum.aspose.com/c/gis/33)** 提問與分享經驗。

### 我可以取得臨時授權來評估 Aspose.GIS for .NET 嗎？
可以！臨時評估授權可於 **[here](https://purchase.aspose.com/temporary-license/)** 取得。

### 如何在同一圖層中加入更複雜的幾何（例如 MultiLineString）？
建立相應的幾何物件（如 `MultiLineString`），將個別的 `LineString` 加入其中，指派給 `feature.Geometry`，然後如同圓形串線的做法將要素加入圖層。

## 結論
透過上述步驟，您現在已掌握如何 **建立向量圖層** 物件，並使用 Aspose.GIS for .NET 為其加入圓形串線幾何。這個基礎讓您能構建更豐富的 GIS 解決方案——無論是繪製交通網路、視覺化環境資料，或開發自訂的空間分析工具。

---

**最後更新：** 2025-12-12  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
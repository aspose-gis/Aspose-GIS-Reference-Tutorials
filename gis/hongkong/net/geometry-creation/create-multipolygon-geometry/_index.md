---
date: 2026-03-29
description: 學習如何使用 Aspose.GIS for .NET 建立多邊形集合幾何並將多邊形加入多邊形集合。一步一步的指南，並提供免費試用。
linktitle: Create MultiPolygon Geometry
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS 建立 MultiPolygon 幾何圖形
url: /zh-hant/net/geometry-creation/create-multipolygon-geometry/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.GIS 建立 MultiPolygon 幾何

## 簡介
如果您正在尋找在 .NET 環境中 **如何建立 MultiPolygon** 形狀，您已來對地方。Aspose.GIS for .NET 為您提供乾淨、物件導向的 API，以建構複雜的地理空間物件，而本教學將一步步帶您完成——從安裝函式庫到將個別多邊形合併為單一 MultiPolygon。完成後，您將能自信地 **將多邊形加入 MultiPolygon** 結構。

## 快速解答
- **什麼是 MultiPolygon？** 一種將兩個或多個 Polygon 物件聚合為單一集合的幾何圖形。  
- **為何使用 Aspose.GIS？** 它支援多種 GIS 格式，可在 .NET Framework 與 .NET Core 上執行，且不需要外部原生函式庫。  
- **範例需要多久時間？** 大約 5 分鐘即可輸入並執行。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## 什麼是 MultiPolygon 幾何？
MultiPolygon 是一種複合幾何圖形，包含多個 Polygon 物件，每個物件可能還有其內部環（洞）。此結構非常適合表示不相連的土地分割、島嶼，或任何共享相同屬性的獨立區域集合。

## 為何要將多邊形加入 MultiPolygon？
將多邊形加入 MultiPolygon 可讓您將多個獨立形狀視為單一實體。這簡化了空間查詢、渲染與資料交換，因為您可以使用一個物件來儲存、傳輸與操作整個集合，而不必分別處理每個多邊形。

## 先決條件
在開始編寫程式碼之前，請確保您具備以下條件：

- **已安裝 Aspose.GIS for .NET**（請參考以下步驟）。  
- .NET 開發環境（Visual Studio、VS Code 或您偏好的任何 IDE）。  
- 基本的 C# 語法熟悉度。

### 安裝 Aspose.GIS for .NET
1. 下載 Aspose.GIS：前往[下載頁面](https://releases.aspose.com/gis/net/)並選擇適合您開發環境的版本。  
2. 安裝 Aspose.GIS：依照文件中提供的安裝說明，在您的機器上安裝 Aspose.GIS for .NET。

## 匯入命名空間
要在 .NET 專案中使用 Aspose.GIS，請匯入必要的命名空間：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 步驟 1：建立 LinearRing
首先，我們需要為每個多邊形建立 **LinearRing** 物件。LinearRing 是一條封閉的線串，用於定義多邊形的外部邊界（以及可選的內部洞）。

```csharp
LinearRing firstRing = new LinearRing();
firstRing.AddPoint(8.5, -2.5);
firstRing.AddPoint(-8.5, 2.5);
firstRing.AddPoint(8.5, -2.5);
LinearRing secondRing = new LinearRing();
secondRing.AddPoint(7.6, -3.6);
secondRing.AddPoint(-9.6, 1.5);
secondRing.AddPoint(7.6, -3.6);
```

## 步驟 2：建立 Polygon
接著，我們將每個 LinearRing 轉換為 **Polygon** 物件。這些多邊形稍後會加入到 MultiPolygon 中。

```csharp
Polygon firstPolygon = new Polygon(firstRing);
Polygon secondPolygon = new Polygon(secondRing);
```

## 步驟 3：建立 MultiPolygon
現在，讓我們將這些多邊形合併為單一的 **MultiPolygon** 幾何。這就是我們 **將多邊形加入 MultiPolygon** 的步驟。

```csharp
MultiPolygon multiPolygon = new MultiPolygon();
multiPolygon.Add(firstPolygon);
multiPolygon.Add(secondPolygon);
```

恭喜！您已成功使用 Aspose.GIS for .NET 建立 MultiPolygon 幾何。

## 常見問題與解決方案
| 問題 | 原因 | 解決方法 |
|-------|-------|-----|
| **點未閉合環** | 首尾點不同。 | 確保首尾座標相同；Aspose.GIS 會自動閉合環，但明確閉合可避免混淆。 |
| **座標順序不正確 (X, Y 與 Lon, Lat)** | 經緯度混淆。 | 遵循 Aspose.GIS 使用的 (X, Y) 順序；X 為經度，Y 為緯度。 |
| **執行時找不到函式庫** | 缺少 NuGet 參考或 DLL。 | 確認在專案檔中已參考 Aspose.GIS 套件，且 DLL 已複製至輸出資料夾。 |

## 常見問題
**Q: Aspose.GIS for .NET 是否適合初學者？**  
A: 絕對適合！Aspose.GIS 提供完整的文件與教學，協助各層級開發者快速入門。

**Q: 我可以在購買前試用 Aspose.GIS 嗎？**  
A: 可以，您可從[此處](https://releases.aspose.com/)下載免費試用版，先行體驗功能再決定是否購買。

**Q: 我該從哪裡取得 Aspose.GIS 的支援？**  
A: 您可前往 Aspose.GIS 論壇[此處](https://forum.aspose.com/c/gis/33)提問，獲得社群協助。

**Q: 是否提供 Aspose.GIS 的臨時授權？**  
A: 有，您可從[此處](https://purchase.aspose.com/temporary-license/)取得臨時授權以供評估使用。

**Q: 我可以直接購買 Aspose.GIS 嗎？**  
A: 可以，您可在網站[此處](https://purchase.aspose.com/buy)直接購買 Aspose.GIS。

---

**最後更新：** 2026-03-29  
**測試環境：** Aspose.GIS 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
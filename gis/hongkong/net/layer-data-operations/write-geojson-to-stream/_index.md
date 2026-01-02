---
date: 2026-01-02
description: 學習如何使用 Aspose.GIS for .NET 在 C# 中將 GeoJSON 寫入串流。展示 GeoJSON C# 範例，提升您的地理空間應用程式。
linktitle: Write GeoJSON to Stream
second_title: Aspose.GIS .NET API
title: 如何使用 Aspose.GIS for .NET 將 GeoJSON 寫入串流
url: /zh-hant/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何將 GeoJSON 寫入串流

## Introduction
如果您需要在 .NET 應用程式中直接將 **how to write geojson** 寫入記憶體或檔案串流，您來對地方了。在本教學中，我們將逐步說明如何使用 Aspose.GIS for .NET 函式庫將 GeoJSON 寫入串流，並示範如何在主控台中 **display GeoJSON C#** 輸出。完成後，您將擁有可在任何地理空間專案中使用的可重用模式。

## Quick Answers
- **What does “write GeoJSON to stream” mean?** 它表示將向量圖層序列化為 GeoJSON 格式，並將位元組傳送至 `Stream` 物件（例如 `MemoryStream`）。  
- **Which library handles this?** Aspose.GIS for .NET 提供內建的 GeoJSON 驅動程式。  
- **Do I need a license for development?** 開發階段可使用免費試用版；正式環境需購買商業授權。  
- **Can I run this on Linux?** 可以 — Aspose.GIS 為跨平台，支援 Windows、Linux 及 macOS。  
- **What .NET versions are supported?** 支援 .NET Framework 4.5 以上、 .NET Core 3.1 以上、 .NET 5/6/7。

## What is “how to write geojson” in .NET?
Aspose.GIS 讓您建立 `VectorLayer`、加入要素，然後使用 `Drivers.GeoJson` 驅動程式將圖層序列化。該驅動程式會直接將 GeoJSON 文字寫入任何 `Stream`，讓您完全掌控資料的去向（記憶體、檔案、網路等）。

## Why use Aspose.GIS for this task?
- **Zero‑dependency serialization** – 無需外部 JSON 函式庫。  
- **Full GeoJSON spec compliance** – 完全符合 GeoJSON 規範，支援 FeatureCollections、屬性與座標精度。  
- **Cross‑platform** – 在 Windows、Linux 及 macOS 上表現相同。  
- **Performance‑optimized** – 直接寫入串流，無需中間字串，效能最佳化。

## Prerequisites
1. **Aspose.GIS for .NET** – 前往[此處](https://releases.aspose.com/gis/net/)下載。  
2. **Document directory** – 決定暫存檔或輸出串流的存放目錄。

現在，讓我們深入程式碼。

## Import Namespaces
首先，加入可使用 Aspose.GIS 類別與 .NET 標準 I/O 工具的命名空間：

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Step 1: Set up the Document Directory
設定將放置任何暫存檔的資料夾。

```csharp
string dataDir = "Your Document Directory";
```

將 `"Your Document Directory"` 替換為您機器上的實際路徑。

## Step 2: Create a Memory Stream
建立 `MemoryStream` 可將 GeoJSON 保留於記憶體中，這對於 API 或直接回傳給客戶端非常適合。

```csharp
using (var memoryStream = new MemoryStream())
{
    // Subsequent steps will be placed inside this block
}
```

## Step 3: Create a Vector Layer with GeoJSON Driver
在 memory‑stream 區塊內，建立使用 GeoJSON 驅動程式的 `VectorLayer`。這告訴 Aspose.GIS 將圖層序列化為 GeoJSON。

```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Feature creation goes here
}
```

## Step 4: Define Feature Attributes
新增屬性定義，這些會在最終的 GeoJSON 輸出中作為屬性出現。

```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Step 5: Construct and Add Features
建立兩個示範點，指派屬性值，並將它們加入圖層。

```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);

// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## Step 6: Display GeoJSON C# Output
在圖層填充完畢後，將串流的位元組轉為 UTF‑8 字串並寫入主控台。這示範了如何 **display GeoJSON C#** 結果。

```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

您應該會在終端機看到有效的 GeoJSON FeatureCollection。

## Common Issues and Solutions
| 問題 | 發生原因 | 解決方法 |
|------|----------|----------|
| 輸出為空 | 讀取時串流位置在結尾 | 在轉換為字串前，先呼叫 `memoryStream.Position = 0;`。 |
| 幾何圖形無效 | 座標超出有效範圍 | 確認緯度介於 -90 到 90 之間，經度介於 -180 到 180 之間。 |
| 授權例外 | 在正式環境未使用有效授權執行 | 使用以下程式碼套用暫時或完整授權：`License license = new License(); license.SetLicense("Aspose.GIS.lic");` |

## Frequently Asked Questions
### 我可以在 Windows 與 Linux 環境中皆使用 Aspose.GIS for .NET 嗎？
是的，Aspose.GIS for .NET 相容於 Windows 與 Linux 系統。

### 是否提供免費試用？
當然！您可在[此處](https://releases.aspose.com/)探索免費試用版。

### 哪裡可以找到詳細文件？
請參閱[此處](https://reference.aspose.com/gis/net/)的文件。

### 如何取得暫時授權？
暫時授權可於[此處](https://purchase.aspose.com/temporary-license/)取得。

### 需要協助或有其他問題？
請前往我們的支援論壇[此處](https://forum.aspose.com/c/gis/33)。

## FAQ
**Q: 我可以直接將 GeoJSON 寫入檔案而非記憶體串流嗎？**  
A: 可以 — 將 `MemoryStream` 換成 `FileStream` 並提供檔案路徑，即可使用相同的驅動程式。

**Q: 我如何控制產生的 GeoJSON 的縮排或格式？**  
A: Aspose.GIS 預設輸出緊湊的 JSON。若需美化輸出，可在字串後處理時使用 `JsonSerializerOptions { WriteIndented = true }`。

**Q: 能否在圖層中加入更複雜的幾何形狀（例如多邊形）？**  
A: 當然可以。建立 `Polygon` 或 `LineString` 物件，指定給 `Feature.Geometry`，然後如前所示加入要素。

**Q: 大型資料集能放入 `MemoryStream` 嗎？**  
A: 若資料量極大，建議直接串流至檔案或使用 `BufferedStream`，以避免過高的記憶體使用。

**Q: GeoJSON 驅動程式是否支援 CRS（座標參考系統）定義？**  
A: 支援 — 若需非 WGS84 CRS，請在加入要素前設定圖層的 `SpatialReferenceSystem` 屬性。

## Conclusion
您現在已掌握使用 Aspose.GIS 將 **how to write geojson** 寫入任何 .NET 串流的完整、可投入生產的模式。無論是從 Web API 回傳 GeoJSON、儲存至檔案，或僅在主控台顯示，上述步驟皆涵蓋整個工作流程。可進一步探索函式庫以處理 Shapefile、KML、GML 等其他格式，持續打造更豐富的地理空間應用程式。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-01-02  
**測試環境：** Aspose.GIS 24.11 for .NET  
**作者：** Aspose
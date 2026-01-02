---
date: 2026-01-02
description: 學習如何使用 Aspose.GIS for .NET 新增點要素，同時設定欄位名稱並讀取物件 ID。開發人員的逐步指南。
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
title: 新增點要素並指定物件編號與幾何欄位名稱
url: /zh-hant/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 新增點要素並指定 Object ID 與 Geometry 欄位名稱

## 簡介
踏入使用 Aspose.GIS for .NET 的地理資訊系統 (GIS) 世界，為開發者與愛好者開啟無限可能。在本教學中，**您將學習如何新增點要素**，同時**設定欄位名稱**以及**讀取 object id**值，讓您全面掌控空間資料。

## 快速解答
- **本指南的主要目的為何？** 示範如何新增點要素並設定 Object ID 與 Geometry 欄位名稱。  
- **使用哪個函式庫？** Aspose.GIS for .NET。  
- **需要授權嗎？** 提供免費試用版；正式環境需購買授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **插入後能讀取 Object ID 嗎？** 可以——本教學示範如何從圖層讀取 object id。  

## 先決條件
在開始教學之前，請先確保具備以下先決條件：

- Aspose.GIS for .NET：從 [here](https://releases.aspose.com/gis/net/) 下載並安裝函式庫。  
- 文件目錄：建立一個目錄以儲存地理資料庫。  
- .NET 環境：確保已安裝可運作的 .NET 環境。  

## 匯入命名空間
首先，您需要在專案中匯入必要的命名空間。這些命名空間提供與 Aspose.GIS for .NET 互動所需的核心類別與方法。

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## 步驟 1：新增點要素並指定 Object ID 與 Geometry 欄位名稱
在本步驟中，您將學習如何為 GIS 資料設定 Object ID 與 Geometry 欄位名稱。這對於有效的資料管理以及之後**讀取 object id**至關重要。

### 步驟 1.1：設定文件目錄
首先定義文件目錄的路徑：

```csharp
string dataDir = "Your Document Directory";
```

### 步驟 1.2：建立 GeoDatabase 並定義選項
建立一個 GeoDatabase，並使用想要的 **設定欄位名稱** 來指定 Object ID 與 Geometry：

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

### 步驟 1.3：建立並新增圖層
在 GeoDatabase 中建立圖層，並新增一個代表點幾何的要素：

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

### 步驟 1.4：開啟圖層並取得資料
開啟圖層並取得剛剛新增的要素。此範例示範如何從資料集中**讀取 object id**：

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## 為何設定自訂欄位名稱？
自訂 Object ID 與 Geometry 欄位名稱，可在與既有資料庫整合或遵循下游應用程式所需的命名慣例時提供彈性。此舉亦使資料更具自我說明性，簡化維護與協作。

## 常見問題與故障排除
- **目錄遺失** – 確認 `dataDir` 指向已存在的資料夾；否則 `Dataset.Create` 會拋出例外。  
- **欄位名稱衝突** – 若地理資料庫中已存在同名欄位，建立將失敗。請選擇唯一的名稱。  
- **空間參考不匹配** – 請務必使空間參考系統（例如 WGS84）與您欲儲存的資料相符。  

## 結論
恭喜！您已成功學會使用 Aspose.GIS for .NET **新增點要素**、**設定欄位名稱**以及**讀取 object id**。此基礎讓您能自信地建構穩健的 GIS 應用程式並管理空間資料。

## 常見問答
### Q: 我可以在 Web 應用程式中使用 Aspose.GIS for .NET 嗎？
A: 可以，Aspose.GIS for .NET 適用於桌面與 Web 應用程式，提供多樣的地理空間功能。

### Q: 購買前是否有試用版？
A: 有的，您可透過 [here](https://releases.aspose.com/) 取得免費試用版，體驗 Aspose.GIS for .NET 的功能。

### Q: 我該如何取得 Aspose.GIS for .NET 的臨時授權？
A: 您可在 [here](https://purchase.aspose.com/temporary-license/) 取得臨時授權，以供評估使用。

### Q: Aspose.GIS for .NET 支援哪些空間參考系統？
A: Aspose.GIS for .NET 支援多種空間參考系統，為不同的地理資料集提供彈性。

### Q: 我可以在哪裡尋求協助或討論 Aspose.GIS 相關問題？
A: 請前往 Aspose.GIS 論壇 [here](https://forum.aspose.com/c/gis/33) 獲得支援與討論。

## 其他常見問答

**Q: 我可以在圖層建立後變更 Object ID 欄位嗎？**  
A: 不能。欄位名稱於圖層建立時即已設定；若要變更必須使用新的 `FileGdbOptions` 物件重新建立圖層。

**Q: 我該如何取得除 Object ID 之外的其他屬性值？**  
A: 使用 `feature.GetValue<T>("FieldName")`，其中 `FieldName` 為您欲讀取的屬性名稱。

**Q: 是否可以一次批次新增多個點要素？**  
A: 可以。遍歷您的資料，為每個點建立要素、設定其幾何，並在同一個 `using` 區塊內呼叫 `layer.Add(feature)`。

**Q: Aspose.GIS 是否支援其他幾何類型？**  
A: 當然支援。您可透過建立相應的幾何物件來使用 `LineString`、`Polygon`、`MultiPoint` 等。

**Q: 若嘗試讀取不存在的 Object ID 會發生什麼情況？**  
A: 存取超出範圍的索引（例如僅有一個要素時使用 `layer[10]`）會拋出 `IndexOutOfRangeException`。請先檢查 `layer.Count`。

---

**最後更新：** 2026-01-02  
**測試環境：** Aspose.GIS for .NET 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
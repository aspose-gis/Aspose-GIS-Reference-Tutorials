---
description: 學習如何使用 Aspose.GIS for .NET 的動態類型轉換從 shapefile 取得屬性值。包括顯式類型轉換範例。
linktitle: Get Feature Attribute Value using Dynamic Type Casting
second_title: Aspose.GIS .NET API
title: 使用動態類型轉換取得要素屬性值
url: /zh-hant/net/layer-interaction-and-data-access/get-feature-attribute-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用動態類型轉換取得要素屬性值

## Introduction
歡迎來到 Aspose.GIS for .NET 的世界，這是一個功能強大的函式庫，讓 .NET 開發者能夠無縫處理地理資訊系統（GIS）資料。在本教學中，您將了解 **動態型別轉換** 如何簡化從 shapefile 取得要素屬性值的過程，同時也會涵蓋傳統的 **顯式型別轉換** 方法。無論您是在 .NET 應用程式中讀取 shapefile，或是需要 **取得屬性值** 進行分析，這些技巧都能讓您的程式碼更簡潔、更具彈性。

## Quick Answers
- **什麼是動態型別轉換？** 一種在執行期間取得屬性值的方式，無需事先指定目標類型。  
- **為什麼使用 Aspose.GIS？** 它提供統一的 API 來讀取 shapefile .NET 資料，且支援兩種轉換方法。  
- **是否需要授權？** 提供免費試用版；正式上線需購買商業授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、 .NET Core 3.1 以上、 .NET 5/6 及更高版本。  
- **能否從大型檔案取得屬性值？** 可以——如範例所示，以有效率的方式遍歷要素。

## Prerequisites
在開始本教學之前，請確保您已具備以下前置條件：
- 具備 .NET 開發的基本概念。  
- 電腦已安裝 Visual Studio。  
- Aspose.GIS for .NET 函式庫，可從 [download link](https://releases.aspose.com/gis/net/) 下載。  
- 熟悉 GIS 的概念與術語。

## Import Namespaces
要啟動您的專案，請確保匯入必要的命名空間。此步驟對於存取 Aspose.GIS for .NET 所提供的功能至關重要。於程式碼中加入以下命名空間：
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## How to Use Dynamic Type Casting to Fetch Attribute Values
以下是一個逐步指南，說明如何設定專案、開啟 shapefile，並使用 **顯式型別轉換** 與 **動態型別轉換** 取得屬性值。

### Step 1: Set up Your Project
在 Visual Studio 中建立新的 .NET 專案，並參考 Aspose.GIS 函式庫。

### Step 2: Define Your Document Directory
設定文件目錄的路徑。此目錄放置您的 shapefile (`InputShapeFile.shp`)。
```csharp
string dataDir = "Your Document Directory";
```

### Step 3: Open the Vector Layer
使用 Aspose.GIS 開啟向量圖層。請務必指定驅動程式，此例使用 Shapefile 驅動程式。
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the vector layer goes here
}
```

### Step 4: Retrieve Feature Attribute Values
現在，遍歷圖層中的每個要素並取得屬性值。Aspose.GIS 提供多種方式取得屬性值。

#### Case 1: Explicit Type Casting
```csharp
for (int i = 0; i < layer.Count; i++)
{
    Feature feature = layer[i];
    Console.WriteLine("Entry {0} information\n ========================", i);
    string nameValue = feature.GetValue<string>("name"); // attribute name is case-sensitive
    int ageValue = feature.GetValue<int>("age");
    string dobValue = feature.GetValue<DateTime>("dob").ToString();
    Console.WriteLine("Attribute value for feature #{0} is: {1}, {2}", nameValue, ageValue, dobValue);
}
```

#### Case 2: Dynamic Type Casting
```csharp
for (int i = 0; i < layer.Count; i++)
{
    Feature feature = layer[i];
    Console.WriteLine("Entry {0} information\n ========================", i);
    var objName = feature.GetValue("name"); // attribute name is case-sensitive
    var objAge = feature.GetValue("age");
    var objDob = feature.GetValue("dob");
    Console.WriteLine("Attribute object for feature #{0} is: {1}, {2}", objName, objAge, objDob);
}
```

> **專業提示：** 當您不確定屬性的確切資料類型，或希望撰寫可在多個 shapefile 中通用的程式碼時，請使用動態型別轉換。若需要編譯時的類型安全，則改用顯式型別轉換。

## Common Issues and Solutions
常見問題與解決方案
- **屬性名稱不匹配：** GIS 屬性名稱區分大小寫。請再次確認 shapefile 結構中的精確拼寫。  
- **空值：** `GetValue` 會在屬性缺失時回傳 `null`，請妥善處理以避免 `NullReferenceException`。  
- **大型資料集：** 使用 `foreach` 或分頁方式遍歷，以降低記憶體使用量。

## Frequently Asked Questions
### Q: Aspose.GIS 是否適合新手與有經驗的開發者？
A: 當然！Aspose.GIS 為各層次開發者提供直觀的 API，方便進行 GIS 資料操作。

### Q: 我可以在商業專案中使用 Aspose.GIS 嗎？
A: 可以，Aspose.GIS 為商業產品。授權資訊請參閱 [purchase page](https://purchase.aspose.com/buy)。

### Q: 是否提供測試用的臨時授權？
A: 可以，您可從 [here](https://purchase.aspose.com/temporary-license/) 取得測試用臨時授權。

### Q: 在哪裡可以取得 Aspose.GIS 的社群支援？
A: 請前往 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 參與討論，尋求協助並與其他使用者交流。

### Q: 是否有 Aspose.GIS 的免費試用版？
A: 當然！您可從 [here](https://releases.aspose.com/) 下載免費試用版，體驗 Aspose.GIS 功能。

### Q: 如何在不知屬性類型的情況下取得 shapefile 屬性值？
A: 使用動態型別轉換方式（`feature.GetValue("attributeName")`），它會以 `object` 回傳值，您可於執行時自行轉型。

### Q: 我能在 .NET Core 應用程式中讀取 shapefile .NET 資料嗎？
A: 可以，Aspose.GIS for .NET 完全支援 .NET Core、 .NET 5 及更高版本。

## Conclusion
結論
恭喜！您已成功學會如何使用 Aspose.GIS for .NET 透過 **顯式型別轉換** 與 **動態型別轉換** 取得要素屬性值。這些技巧讓您能有效取得 **shapefile 屬性** 資料，無論是開發桌面 GIS 工具，或是將空間分析整合至 Web 服務，都能得心應手。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-01-05  
**測試環境：** Aspose.GIS for .NET (latest)  
**作者：** Aspose
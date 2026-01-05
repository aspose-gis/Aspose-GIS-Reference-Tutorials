---
date: 2026-01-05
description: 学习如何使用 Aspose.GIS for .NET 在 C# 中读取 shapefile，检索所有要素属性值，并高效地导出属性。
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
title: 读取 Shapefile（C#）——获取所有要素属性值
url: /zh/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 获取所有要素属性值

## 介绍
欢迎来到 Aspose.GIS for .NET 的地理空间开发世界！在本教程中，您将学习 **如何在 C# 中读取 shapefile** 并获取其要素的每个属性值。无论是构建地图应用还是批量处理空间数据，掌握属性提取都是必不可少的。让我们一起深入代码实践吧。

## 快速答案
- **这段代码做什么？** 它打开一个 Shapefile，并读取每个要素的全部、部分或转储的属性值。  
- **需要哪个库？** Aspose.GIS for .NET（兼容 .NET Framework 和 .NET Core）。  
- **需要许可证吗？** 临时许可证可用于测试；生产环境需要正式许可证。  
- **可以读取其他格式吗？** 可以——相同的 API 支持 GeoJSON、KML 等多种格式。  
- **如何转储属性？** 使用 `feature.GetValuesDump()` 获取灵活的对象数组。

## 什么是 “read shapefile C#”？
在 C# 中读取 Shapefile 意味着使用 GIS 库打开 .shp 文件，遍历其矢量要素，并访问伴随的 .dbf 文件中存储的属性数据。Aspose.GIS 抽象了底层文件处理，让您专注于所需的属性值。

## 为什么使用 Aspose.GIS 读取属性？
- **简洁的 API** – 直观的方法如 `GetValues` 和 `GetValuesDump`。  
- **跨平台** – 在 Windows、Linux 和 macOS 上均可使用 .NET Core 运行。  
- **丰富的格式支持** – 无需额外插件即可处理 Shapefile、GeoJSON、GML 等。  
- **性能优化** – 对大数据集进行快速迭代。

## 前置条件
在开始这段激动人心的旅程之前，请确保已满足以下前置条件：
- Aspose.GIS for .NET：从 [Aspose.GIS for .NET 下载页面](https://releases.aspose.com/gis/net/) 下载并安装库。  
- 开发环境：搭建 .NET 开发环境，例如 Visual Studio。  
- Shapefile：准备好一个示例 Shapefile（例如 “InputShapeFile.shp”），放在文档目录中。

## 导入命名空间
在 C# 代码中，首先导入必要的命名空间以使用 Aspose.GIS 功能：
```csharp
using System;
using Aspose.Gis;
```

## 步骤 1：设置文档目录
```csharp
string dataDir = "Your Document Directory";
```
将 “Your Document Directory” 替换为实际的 Shapefile 所在路径。

## 步骤 2：打开 VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
此步骤使用 Aspose.GIS 打开 Shapefile，指定文件路径和格式（此处为 Shapefile）。

## 步骤 3：检索所有要素属性值
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
该代码片段展示了 **如何读取每个要素的属性**，并将其加载到固定大小的数组中。

## 步骤 4：检索部分要素属性值
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
这里演示 **如何读取特定属性值**，当您只需要部分字段时使用。

## 步骤 5：以对象转储形式检索属性值
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
最后一步展示了 **如何使用 `GetValuesDump()` 转储属性**，返回一个灵活的集合，您可以检查或序列化。

## 常见问题及解决方案
- **数组大小不匹配** – 确保传递给 `GetValues` 的数组大小与预期的属性数量相符，否则会出现 `null` 条目。  
- **文件未找到** – 核实 `dataDir` 指向正确的文件夹，并确保 Shapefile 名称拼写完全正确。  
- **许可证异常** – 若出现许可证错误，请在调用任何 API 方法前应用临时或正式许可证。

## 常见问答
### Aspose.GIS 与 .NET Core 兼容吗？
是的，Aspose.GIS 完全兼容 .NET Core，支持跨平台应用开发。

### 我可以使用 Aspose.GIS 处理其他 GIS 文件格式吗？
当然可以！Aspose.GIS 支持多种格式，包括 Shapefile、GeoJSON 等。

### 是否有 Aspose.GIS 的社区论坛？
有，您可以在 [support forum](https://forum.aspose.com/c/gis/33) 上获取帮助并与社区交流。

### 如何获取 Aspose.GIS 的临时许可证？
您可以在 [here](https://purchase.aspose.com/temporary-license/) 获取用于测试的临时许可证。

### 哪里可以找到 Aspose.GIS 的详细文档？
完整文档可在 [here](https://reference.aspose.com/gis/net/) 查看。

### 如何仅检索每个要素的 “Name” 属性？
使用 `GetValues` 并将数组大小设为 1，传入 “Name” 字段的索引，或直接调用 `feature["Name"]`。

### `GetValues` 与 `GetValuesDump` 有何区别？
`GetValues` 将原始值填充到预先分配的数组中，而 `GetValuesDump` 返回一个对象数组，可在未知模式的情况下直接枚举。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-01-05  
**测试环境：** Aspose.GIS for .NET（最新发布）  
**作者：** Aspose  

---
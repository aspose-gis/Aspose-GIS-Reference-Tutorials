---
date: 2026-06-15
description: 了解如何在 C# 中使用 Aspose.GIS for .NET 读取 shapefile 属性值，检索每个要素属性，并高效地转储属性。
keywords:
- read shapefile attribute values
- Aspose.GIS attribute extraction
- C# GIS tutorial
linktitle: 获取所有要素属性值
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to read shapefile attribute values in C# using Aspose.GIS
    for .NET, retrieve every feature attribute, and dump attributes efficiently.
  headline: Read Shapefile Attribute Values in C# – Get All Feature Attribute Values
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS fully supports .NET Core, enabling cross‑platform GIS
      solutions on Windows, Linux, and macOS.
    question: Is Aspose.GIS compatible with .NET Core?
  - answer: Absolutely. The library handles Shapefile, GeoJSON, KML, GML, CSV, and
      over 30 other formats without additional plugins.
    question: Can I work with different GIS file formats using Aspose.GIS?
  - answer: You can acquire a temporary license for evaluation [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for testing?
  - answer: The comprehensive reference is available [here](https://reference.aspose.com/gis/net/).
    question: Where is the official documentation for Aspose.GIS?
  - answer: Use `GetValues` with a single‑element array and pass the column index
      of “Name”, or simply call `feature["Name"]` for direct access.
    question: How do I retrieve only the “Name” attribute from each feature?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: 在 C# 中读取 Shapefile 属性值 – 获取所有要素属性值
url: /zh/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 获取所有要素属性值

## 介绍
在本教程中，您将了解**如何读取 shapefile 属性值**，使用 C# 与 Aspose.GIS for .NET。无论您是构建实时映射应用程序、执行批量空间分析，还是仅需导出属性表，从 Shapefile 中提取每个字段都是一项基础技能。我们将完整演示工作流程，从设置数据目录到转储属性集合，并强调保持代码整洁高效的最佳实践技巧。

## 快速答案
- **这段代码做什么？** 它打开一个 Shapefile，遍历每个要素，并检索每个属性值或选定的子集。  
- **需要哪个库？** Aspose.GIS for .NET（兼容 .NET Framework、.NET Core、.NET 5/6）。  
- **我需要许可证吗？** 测试时临时许可证即可；生产部署必须使用正式许可证。  
- **我可以读取其他格式吗？** 可以——相同的 API 可读取 GeoJSON、KML、GML、CSV 等 30 多种 GIS 格式。  
- **如何转储属性？** 调用 `feature.GetValuesDump()` 获取可直接序列化或检查的对象数组。

## 什么是 “read shapefile C#”？
在 C# 中读取 Shapefile 意味着使用 GIS 库打开 `.shp` 文件，遍历其矢量要素，并访问伴随的 `.dbf` 文件中存储的属性数据。Aspose.GIS 抽象了底层文件处理，让您只需几行代码即可提取属性值。

## 为什么使用 Aspose.GIS 读取属性？
Aspose.GIS 提供高性能、跨平台的 API，简化了从 Shapefile 中提取属性的过程。它支持 **30+ GIS 格式**，在标准 4 核服务器上可处理高达 **500 000 要素每秒**，并提供直观的方法如 `GetValues` 和 `GetValuesDump`，省去手动解析 DBF 的步骤。当您需要可靠、（测试时）免许可证的代码，并在 Windows、Linux、macOS 上无额外插件运行时，使用它是理想选择。

## 前提条件
- **Aspose.GIS for .NET** – 从 [Aspose.GIS for .NET 下载页面](https://releases.aspose.com/gis/net/) 下载。  
- **开发环境** – Visual Studio 2022、Rider 或任何支持 .NET 6+ 的 IDE。  
- **示例 Shapefile** – 将类似 `InputShapeFile.shp` 的文件放置在机器上的已知文件夹中。  

## 导入命名空间
`Aspose.Gis` 命名空间包含核心 GIS 类型，如 `VectorLayer` 和 `Feature`。  
`VectorLayer` 表示矢量数据集（如 Shapefile），而 `Feature` 表示单个空间记录。  
```csharp
using System;
using Aspose.Gis;
```

## 步骤 1：设置文档目录
定义保存 Shapefile 的文件夹，以便 API 能定位 `.shp`、`.shx` 和 `.dbf` 文件。  
```csharp
string dataDir = "Your Document Directory";
```
将 “Your Document Directory” 替换为实际的 Shapefile 所在路径。

## 步骤 2：打开 VectorLayer
`VectorLayer` 表示矢量数据集（Shapefile、GeoJSON 等）。打开它会加载模式而不读取所有几何数据，从而保持低内存占用。  
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
此步骤指定文件路径和格式（Shapefile）。

## 步骤 3：检索所有要素属性值
`GetValues` 用预先分配的数组填充要素的原始属性值。当您需要确定性、固定大小的结果集时，此方法非常理想。  
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
代码片段展示了如何将 **每个** 要素的属性读取到固定大小的数组中。

## 步骤 4：检索多个要素属性值
当只需要字段的子集时，您可以传入更小的数组或使用列索引限制传输的数据量。这可以降低内存开销并加快处理速度。  
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
这里演示了读取特定属性值（例如 “Name” 和 “Population”）。

## 步骤 5：以对象转储方式检索属性值
`GetValuesDump` 返回一个 `object[]`，其中包含要素的所有属性值，匹配要素的模式。这样您可以在不了解字段顺序或类型的情况下枚举字段。  
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
此最终步骤展示了一种灵活、与模式无关的方式，用于调试或序列化时转储属性。

## 常见问题及解决方案
- **数组大小不匹配** – 确保传递给 `GetValues` 的数组大小与预期的属性数量相符，否则会得到 `null` 条目。  
- **文件未找到** – 核实 `dataDir` 指向正确的文件夹，并且 Shapefile 名称拼写完全正确，包括 `.shp` 扩展名。  
- **许可证异常** – 若出现许可证错误，请在调用任何 API 方法前应用临时或正式许可证。

## 常见问题
**Q: Aspose.GIS 与 .NET Core 兼容吗？**  
A: 是的，Aspose.GIS 完全支持 .NET Core，能够在 Windows、Linux 和 macOS 上实现跨平台 GIS 解决方案。

**Q: 我可以使用 Aspose.GIS 处理不同的 GIS 文件格式吗？**  
A: 当然。该库可处理 Shapefile、GeoJSON、KML、GML、CSV 等超过 30 种格式，无需额外插件。

**Q: 如何获取用于测试的临时许可证？**  
A: 您可以在 [此处](https://purchase.aspose.com/temporary-license/) 获取用于评估的临时许可证。

**Q: Aspose.GIS 的官方文档在哪里？**  
A: 完整的参考手册可在 [此处](https://reference.aspose.com/gis/net/) 查看。

**Q: 如何仅检索每个要素的 “Name” 属性？**  
A: 使用单元素数组调用 `GetValues` 并传入 “Name” 的列索引，或直接使用 `feature["Name"]` 进行访问。

**Q: `GetValues` 与 `GetValuesDump` 有何区别？**  
A: `GetValues` 将原始值填充到预分配的数组中，而 `GetValuesDump` 返回一个 `object[]`，无需提前了解模式即可枚举。

**Q: 遇到问题时可以在哪里获取帮助？**  
A: 请访问 Aspose GIS [支持论坛](https://forum.aspose.com/c/gis/33) 获取社区帮助和官方支持。

---

**最后更新：** 2026-06-15  
**测试环境：** Aspose.GIS for .NET（最新发布）  
**作者：** Aspose

## 相关教程

- [获取图层属性 – 使用 Aspose.GIS for .NET 检索图层属性信息](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [如何使用 Aspose.GIS for .NET 获取属性值（默认）](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [读取 Shapefile C# – 使用 Aspose.GIS 按属性过滤要素](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
date: 2026-01-13
description: Узнайте, как добавить слой в набор данных File GDB с помощью Aspose.GIS,
  с поддержкой пространственной привязки WGS84. Следуйте этому пошаговому руководству,
  чтобы добавить слой в GDB в .NET.
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: Пространственная система координат WGS84 – Добавить слой в GDB с помощью Aspose.GIS
url: /ru/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# spatial reference wgs84 – Добавление слоя в GDB с помощью Aspose.GIS

## Introduction
Готовы ускорить ваш GIS‑рабочий процесс с Aspose.GIS для .NET? В этом руководстве вы узнаете, **как добавить слой в набор данных File GDB**, работая с координатной системой **spatial reference wgs84**. Мы пройдём каждый шаг, от подготовки папки с данными до проверки только что созданного слоя, чтобы вы могли уверенно манипулировать географическими данными.

## Quick Answers
- **What is the primary coordinate system used?** spatial reference wgs84 (WGS 84)  
- **Which library provides the API?** Aspose.GIS for .NET  
- **Do I need a license for testing?** Yes – a temporary Aspose license is available.  
- **Can I add attributes to the new layer?** Absolutely, you can define any number of feature attributes.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## What is spatial reference wgs84?
spatial reference wgs84 (World Geodetic System 1984) — самая широко используемая географическая координатная система. Она определяет широту и долготу в градусах и служит CRS по умолчанию для многих GIS‑наборов данных, включая тот, который мы создадим в этом руководстве.

## Why use Aspose.GIS to add a layer?
- **No external dependencies:** Работает сразу «из коробки» на чистом .NET‑коде.  
- **Full control over schema:** Вы можете определить пользовательские атрибуты и типы геометрии.  
- **Cross‑platform:** Совместима с Windows, Linux и macOS.  
- **Robust licensing:** Временные лицензии позволяют быстро оценить возможности перед покупкой.

## Prerequisites
Перед началом убедитесь, что у вас есть:

- Aspose.GIS for .NET Library: Скачайте и установите библиотеку из [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Document Directory: Создайте отдельную папку на вашем компьютере для хранения GIS‑файлов.

## Import Namespaces
Добавьте необходимые `using`‑операторы в ваш C#‑проект, чтобы получить доступ к классам Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step 1: Copy Directory
Сначала продублируйте папку, содержащую оригинальный набор данных GDB. Наличие копии защищает исходные данные во время экспериментов.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Step 2: Open Dataset and Verify Creation Capability
Откройте только что скопированный набор данных и убедитесь, что он может создавать новые слои. Свойство `CanCreateLayers` должно вернуть **True**.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Step 3: Create and Populate a New Layer with spatial reference wgs84
Теперь создаём слой с именем **data** и явно задаём его пространственную ссылку **Wgs84**. Мы также добавляем простой атрибут **Name** и вставляем одну точечную фичу.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## Step 4: Open and Validate the Added Layer
Наконец, откройте только что созданный слой и проверьте его содержимое. Консоль покажет, что слой содержит одну фичу и что атрибут **Name** соответствует заданному значению.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Common Issues & Tips
- **Incorrect path:** Убедитесь, что `dataDir` заканчивается разделителем пути (`/` или `\`), чтобы склеенные строки образовали корректные пути к файлам.  
- **License errors:** Если появляются предупреждения о лицензировании, примените временную лицензию из портала Aspose перед запуском кода.  
- **CRS mismatch:** При открытии слоя позже в другом GIS‑инструменте убедитесь, что он распознаёт WGS 84 (EPSG:4326) как координатную систему.

## Frequently Asked Questions
### Q: Can I use Aspose.GIS for .NET with other GIS libraries?
Aspose.GIS for .NET разработан для автономной работы, но его можно интегрировать с другими библиотеками для расширения функциональности.  

### Q: Is a temporary license available for testing purposes?
Yes, you can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/) for testing and evaluation.  

### Q: What spatial reference systems does Aspose.GIS for .NET support?
Aspose.GIS for .NET supports a wide range of spatial reference systems, providing flexibility in geographic data handling.  

### Q: Can I contribute to the Aspose.GIS community?
Absolutely! Join the discussions and share your experiences on the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).  

### Q: Where can I find detailed documentation for Aspose.GIS for .NET?
Explore the comprehensive documentation [here](https://reference.aspose.com/gis/net/) for in‑depth information on Aspose.GIS for .NET.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS for .NET (latest stable version)  
**Author:** Aspose
---
date: 2026-01-10
description: Узнайте, как читать shapefile на C# и преобразовать полигональный shapefile
  в linestring с помощью Aspose.GIS для .NET. Повышайте эффективность разработки GIS
  с помощью ясных пошаговых инструкций.
linktitle: Convert Polygon Shapefile to Linestring
second_title: Aspose.GIS .NET API
title: Чтение Shapefile C# – Преобразование полигонального Shapefile в Linestring
url: /ru/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Чтение Shapefile C# – Преобразование Polygon Shapefile в Linestring

## Introduction
Если вы работаете с географическими информационными системами (GIS) в .NET, **read shapefile c#** — это обычный первый шаг перед тем, как вы сможете манипулировать данными. Aspose.GIS упрощает этот процесс, позволяя преобразовать Polygon Shapefile в Linestring всего несколькими строками кода. Эта возможность особенно полезна, когда нужно извлечь линейные объекты из полигональных наборов данных для таких задач, как планирование маршрутов, сетевой анализ или визуализация данных.

## Quick Answers
- **Which library helps you read shapefile c#?** Aspose.GIS for .NET  
- **Can you convert a polygon to a line?** Yes – use `LineString` with the polygon’s exterior ring.  
- **Do I need a license for production?** A commercial license is required for production use.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Is a trial available?** Absolutely – download a free trial from the Aspose site.

## What is “read shapefile c#”?
Чтение shapefile в C# означает загрузку файла `.shp` в память, чтобы вы могли выполнять запросы, изменять или преобразовывать его геометрии. Aspose.GIS предоставляет простой API, который абстрагирует детали низкого уровня и позволяет сосредоточиться на GIS‑логике.

## Why convert polygon to line with Aspose.GIS?
- **Preserve topology** – преобразование сохраняет точную внешнюю границу каждого полигона.  
- **Performance** – библиотека оптимизирована для больших наборов данных, обеспечивая быструю пакетную конверсию.  
- **Flexibility** – позже вы можете записать полученные Linestring в другой shapefile, GeoJSON или любой поддерживаемый формат.

## Prerequisites
Before we dive into the tutorial, make sure you have the following in place:

- **Aspose.GIS Library** – Download and install the Aspose.GIS library from the [website](https://releases.aspose.com/gis/net/).  
- **Shapefile Data** – Have a Polygon Shapefile ready for conversion. If you don’t have one, you can find sample data or create your own.  
- **Development Environment** – Set up your .NET development environment with the necessary tools (Visual Studio, .NET SDK, etc.).

## Import Namespaces
In your C# code, you need to import the Aspose.GIS namespaces to access the required classes and methods. Add the following namespaces at the beginning of your code file:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## How to convert shapefile from polygon to line?
Below is a step‑by‑step guide that shows **how to convert shapefile** data from a polygon to a line using Aspose.GIS.

### Step 1: Set the Document Directory
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
Replace `"Your Document Directory"` with the actual path where your shapefile resides.

### Step 2: Open the Source Shapefile
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
This line **opens the source Polygon Shapefile** so you can read its features.

### Step 3: Create the Destination Linestring Shapefile
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Here we **create a new Linestring Shapefile** that will store the converted geometries.

### Step 4: Iterate Through Source Features
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
The loop walks through each polygon feature in the original file.

### Step 5: Convert Polygon to Linestring and Write to Destination
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
In this block we **convert polygon to line** (`LineString`) and add the new feature to the destination shapefile.

## Common Issues and Tips
- **Coordinate System Mismatch** – Ensure both source and destination layers use the same spatial reference; otherwise, the lines may appear displaced.  
- **Large Files** – When processing very large shapefiles, consider streaming features instead of loading them all into memory at once.  
- **Null Geometries** – Guard against features with empty geometries to avoid runtime exceptions.

## Frequently Asked Questions

**Q: Is Aspose.GIS compatible with all versions of .NET?**  
A: Yes, Aspose.GIS supports various .NET versions, ensuring compatibility with your development environment.

**Q: Can I use Aspose.GIS for commercial projects?**  
A: Yes, you can. To use Aspose.GIS in commercial projects, consider purchasing a license [here](https://purchase.aspose.com/buy).

**Q: Are there any examples or documentation available?**  
A: Yes, you can find comprehensive documentation and examples on the [documentation page](https://reference.aspose.com/gis/net/).

**Q: Is there a trial version available?**  
A: Yes, you can explore Aspose.GIS with a free trial by visiting [this link](https://releases.aspose.com/).

**Q: Where can I seek help or support?**  
A: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for any assistance or support‑related queries.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
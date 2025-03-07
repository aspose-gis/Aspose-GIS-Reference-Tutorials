---
title: Specify WKT Variant on Translation using Aspose.GIS
linktitle: Specify WKT Variant on Translation
second_title: Aspose.GIS .NET API
description: Learn how to specify WKT variants in Aspose.GIS for .NET to control spatial data representation format and precision effectively.
weight: 19
url: /net/geometry-processing/specify-wkt-variant-on-translation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Specify WKT Variant on Translation using Aspose.GIS

## Introduction
Aspose.GIS for .NET is a powerful library that allows developers to work with geographic information system (GIS) data in their .NET applications effortlessly. One of the essential features provided by Aspose.GIS is the ability to specify the Well-Known Text (WKT) variant during translation, enabling users to control the format and precision of spatial data representations. In this tutorial, we will explore how to specify WKT variants step by step using Aspose.GIS for .NET.
## Prerequisites
Before we begin, ensure you have the following prerequisites in place:
1. Aspose.GIS for .NET: Download and install Aspose.GIS for .NET from the [download page](https://releases.aspose.com/gis/net/).
2. Development Environment: Make sure you have a .NET development environment set up.
3. Basic Knowledge: Familiarity with C# programming language and .NET framework.

## Import Namespaces
Before using Aspose.GIS functionality in your code, import the necessary namespaces:
```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```
## Step 1: Create a Point Object
First, create a `Point` object with latitude, longitude, and optional measure (M) values:
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## Step 2: Set Spatial Reference System (SRS)
Assign a spatial reference system (SRS) to the point object. In this example, we use the WGS84 spatial reference system:
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## Step 3: Specify WKT Variant
Now, specify the WKT variant for translation. Aspose.GIS supports various WKT variants, including `Iso`, `SimpleFeatureAccessOutdated`, and `ExtendedPostGis`. Choose the appropriate variant based on your requirements:
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```
## Step 4: Control Numeric Format
You can control the numeric format of the coordinates in the WKT representation. Aspose.GIS provides options to specify the decimal precision:
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## Conclusion
In this tutorial, we've learned how to specify WKT variants on translation using Aspose.GIS for .NET. By following the steps outlined above, developers can effectively control the format and precision of spatial data representations in their .NET applications, enhancing the flexibility and usability of geographic information systems.
## FAQ's
### Is Aspose.GIS compatible with all versions of .NET?
Yes, Aspose.GIS supports .NET Framework 4.0 and higher.
### Can I use Aspose.GIS for commercial projects?
Yes, Aspose.GIS can be used for both personal and commercial projects.
### Does Aspose.GIS provide support for other spatial data formats?
Yes, Aspose.GIS supports a wide range of spatial data formats, including ESRI Shapefile, GeoJSON, and KML.
### Is there a free trial available for Aspose.GIS?
Yes, you can download a free trial version of Aspose.GIS from [here](https://releases.aspose.com/).
### Where can I get help or support for Aspose.GIS?
You can post your queries or seek assistance from the Aspose.GIS community at the [forum](https://forum.aspose.com/c/gis/33).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

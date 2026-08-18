---
date: 2026-08-18
description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
  C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
images:
- /net/geometry-creation/convert-coordinates/og-image.png
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: Convert Coordinates
og_description: decimal degrees to dms conversion made easy with Aspose.GIS for .NET.
  Learn to transform latitude‑longitude values into DMS format in minutes.
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: Convert decimal degrees to dms with Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  headline: How to convert decimal degrees to dms with Aspose.GIS for .NET
  type: TechArticle
- description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  name: How to convert decimal degrees to dms with Aspose.GIS for .NET
  steps:
  - name: start the conversion process
    text: We print a friendly message so you know the demo has begun.
  - name: convert to decimal degrees
    text: Even though the final goal is DMS, we start by showing the original decimal
      representation. This also demonstrates the **decimal degrees to dms** path you’ll
      later follow.
  - name: convert to degree decimal minutes
    text: This format (`DD°MM.m'`) is a common intermediate step when you need to
      **convert lat long degree minutes**.
  - name: convert to degree minutes seconds (dms)
    text: Here’s the core of our tutorial—**convert coordinates to dms**.
  - name: convert to GeoRef
    text: For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing
      workflows.
  type: HowTo
- questions:
  - answer: Aspose.GIS primarily targets .NET developers, but a Java version is also
      available.
    question: Is Aspose.GIS compatible with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.GIS before purchasing?
  - answer: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  - answer: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert coordinates
- Aspose.GIS
- .NET GIS processing
title: How to convert decimal degrees to dms with Aspose.GIS for .NET
url: /net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to convert decimal degrees to dms with Aspose.GIS

## Introduction
In this tutorial you’ll learn **how to convert decimal degrees to dms** using the powerful Aspose.GIS library for .NET. Whether you need to **c# convert lat long**, generate human‑readable location strings for reports, or simply explore different coordinate formats, this guide walks you through every step with clear explanations and ready‑to‑run C# snippets.

## Quick answers
- **What does “convert coordinates to dms” mean?** It transforms numeric latitude/longitude values into the traditional degrees‑minutes‑seconds notation.  
- **Which library handles the conversion?** Aspose.GIS for .NET provides the `GeoConvert` class with built‑in format support.  
- **Do I need a license to try it?** A free trial is available; a commercial license is required for production use.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6+.  
- **Can I use the same code for other formats?** Yes—simply change the `PointFormats` enum value (e.g., `DecimalDegrees`, `GeoRef`).  

## What is coordinate conversion to dms?
Converting coordinates to DMS rewrites decimal latitude and longitude values into a format like `25°30'00"N 45°30'00"E`. The process splits each decimal degree into whole degrees, minutes (one‑sixtieth of a degree), and seconds (one‑sixtieth of a minute), then appends the appropriate hemisphere indicator (N, S, E, W). This human‑readable form is essential for many legacy datasets and for communicating precise locations without relying on decimal notation.

## Why use Aspose.GIS for coordinate conversion?
Aspose.GIS supports **50+ input and output formats** and can process multi‑hundred‑page GIS files without loading the entire dataset into memory. The API delivers sub‑millimeter accuracy for edge cases such as negative values and hemispheric designators, and it runs consistently on Windows, Linux, and macOS .NET runtimes.

## Prerequisites
Before you start, make sure you have:

1. **Basic knowledge of C#** – familiarity with variables, method calls, and console output.  
2. **Aspose.GIS installed** – download the latest package from the [Aspose.GIS website](https://releases.aspose.com/gis/net/). You can also explore the main Aspose releases site at the [Aspose releases website](https://releases.aspose.com/).  

## Import namespaces
First, import the namespaces required for GIS operations:

Import Namespaces placeholder remains unchanged.

## Step‑by‑step guide

### What is the GeoConvert class?
The `GeoConvert` class provides static methods for converting between coordinate formats such as decimal degrees, DMS, and GeoRef. It includes overloads that accept raw numeric values or `Point` objects and returns formatted strings or new `Point` instances. By handling edge cases like negative coordinates and rounding, the class guarantees that the output conforms to standard GIS specifications, simplifying integration into any .NET mapping application.

### Step 1: start the conversion process
We print a friendly message so you know the demo has begun.

```csharp
using System;
using Aspose.Gis;
```

### Step 2: convert to decimal degrees
Even though the final goal is DMS, we start by showing the original decimal representation. This also demonstrates the **decimal degrees to dms** path you’ll later follow.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Step 3: convert to degree decimal minutes
This format (`DD°MM.m'`) is a common intermediate step when you need to **convert lat long degree minutes**.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Step 4: convert to degree minutes seconds (dms)
Here’s the core of our tutorial—**convert coordinates to dms**.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Step 5: convert to GeoRef
For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing workflows.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## Common issues and solutions
- **Incorrect hemisphere letters** – Ensure you pass positive values for north/east and negative for south/west; the API automatically adds the correct suffix.  
- **Unexpected blank output** – Verify that the `Aspose.Gis` assembly is referenced correctly and that the project targets a supported .NET version.  
- **License not found** – Place your license file in the application root or set it programmatically with `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.

## Frequently asked questions

**Q: Is Aspose.GIS compatible with other programming languages?**  
A: Aspose.GIS primarily targets .NET developers, but a Java version is also available.

**Q: Can I try Aspose.GIS before purchasing?**  
A: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).

**Q: How can I get support for Aspose.GIS?**  
A: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).

**Q: Are temporary licenses available for Aspose.GIS?**  
A: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Where can I purchase Aspose.GIS?**  
A: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).

## Conclusion
By following these steps, you now know how to **convert decimal degrees to dms** and other common GIS formats using Aspose.GIS for .NET. This capability lets you seamlessly integrate human‑readable location strings into mapping applications, reports, or any spatial data workflow. Feel free to experiment with different latitude/longitude values and explore the other formats offered by the `GeoConvert` class.

---

**Last Updated:** 2026-08-18  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Related Tutorials

- [How to Create Point Geometry and Get Geometry Type with Aspose.GIS for .NET](/gis/net/geometry-analysis/get-geometry-type/)
- [How to Convert GeoJSON – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [Create MultiPoint Geometry .NET with Aspose.GIS](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
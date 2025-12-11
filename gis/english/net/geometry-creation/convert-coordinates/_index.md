---
title: Convert Coordinates to DMS with Aspose.GIS for .NET
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
description: Learn how to convert coordinates to DMS using Aspose.GIS for .NET. Includes C# examples, c# convert latitude longitude, and step‑by‑step guide.
weight: 25
url: /net/geometry-creation/convert-coordinates/
date: 2025-12-11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convert Coordinates to DMS with Aspose.GIS

## Introduction
In this tutorial, you'll discover how to **convert coordinates to DMS** (degrees, minutes, seconds) using the powerful Aspose.GIS library for .NET. Whether you need to c# convert latitude longitude for mapping applications, generate human‑readable location strings, or simply explore different coordinate formats, this guide walks you through every step with clear explanations and ready‑to‑run C# code.

## Quick Answers
- **What does “convert coordinates to DMS” mean?** It transforms numeric latitude/longitude values into the traditional degrees‑minutes‑seconds notation.  
- **Which library handles the conversion?** Aspose.GIS for .NET provides the `GeoConvert` class with built‑in format support.  
- **Do I need a license to try it?** A free trial is available; a commercial license is required for production use.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6+.  
- **Can I use the same code for other formats?** Yes—simply change the `PointFormats` enum value (e.g., `DecimalDegrees`, `GeoRef`).  

## What is coordinate conversion to DMS?
Converting coordinates to DMS rewrites decimal latitude and longitude values into a format like `25°30'00"N 45°30'00"E`. This representation is widely used in cartography, navigation, and GIS data exchange.

## Why use Aspose.GIS for coordinate conversion?
- **All‑in‑one API** – No external libraries or complex math; Aspose.GIS handles parsing and formatting internally.  
- **High accuracy** – Precise handling of edge cases such as negative values and hemispheric designators.  
- **Cross‑platform** – Works the same on Windows, Linux, and macOS .NET runtimes.  
- **Extensible** – Easily switch between DMS, decimal degrees, degree‑decimal‑minutes, and GeoRef formats.

## Prerequisites
Before you start, make sure you have:

1. **Basic knowledge of C#** – Familiarity with variables, method calls, and console output.  
2. **Aspose.GIS installed** – Download the latest package from the [Aspose.GIS website](https://releases.aspose.com/gis/net/).  

## Import Namespaces
First, import the namespaces required for GIS operations:

```csharp
using System;
using Aspose.Gis;
```

## Step‑by‑step guide

### Step 1: Start the conversion process
We print a friendly message so you know the demo has begun.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Step 2: Convert to Decimal Degrees  
Even though the final goal is DMS, we start by showing the original decimal representation.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Step 3: Convert to Degree Decimal Minutes  
This format (`DD°MM.m'`) is a common intermediate step when you need *convert lat long degree minutes*.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Step 4: Convert to Degree Minutes Seconds (DMS)  
Here’s the core of our tutorial—**convert coordinates to DMS**.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### Step 5: Convert to GeoRef  
For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing workflows.

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Common Issues and Solutions
- **Incorrect hemisphere letters** – Ensure you pass positive values for north/east and negative for south/west; the API automatically adds the correct suffix.  
- **Unexpected blank output** – Verify that the `Aspose.Gis` assembly is referenced correctly and that the project targets a supported .NET version.  
- **License not found** – Place your license file in the application root or set it programmatically with `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.

## Frequently Asked Questions

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
By following these steps, you now know how to **convert coordinates to DMS** and other common GIS formats using Aspose.GIS for .NET. This capability lets you seamlessly integrate human‑readable location strings into mapping applications, reports, or any spatial data workflow. Feel free to experiment with different latitude/longitude values and explore the other formats offered by the `GeoConvert` class.

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
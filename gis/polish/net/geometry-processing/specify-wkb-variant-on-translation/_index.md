---
date: 2026-06-10
description: Dowiedz się, jak tworzyć geometrię linestring w .NET i konwertować geometrię
  do formatu WKB przy użyciu Aspose.GIS dla .NET z wariantem ExtendedPostGis.
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: Określ wariant WKB przy tłumaczeniu
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  headline: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  name: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  steps:
  - name: Creating a Geometry Object
    text: The `Geometry` class is Aspose.GIS's base type that represents any spatial
      object in memory. Linestring represents a series of connected points forming
      a linear geometry. In this step we instantiate a `Linestring` with a collection
      of coordinate pairs that model a simple road segment.
  - name: Generating WKB Representation
    text: '`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to
      include SRID in the output binary. Here we call the `AsBinary` method, passing
      the EWKB variant, which returns a `byte[]` containing the full binary representation.'
  - name: Writing to File
    text: '`File.WriteAllBytes` writes the binary array to disk. The resulting file
      (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB`
      function.'
  type: HowTo
- questions:
  - answer: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which
      PostGIS reads directly via `ST_GeomFromEWKB`.
    question: Can I use the EWKB file with PostGIS?
  - answer: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry
      from its binary form.
    question: Is it possible to read a WKB file back into a geometry object?
  - answer: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons,
      and many more spatial types.
    question: Does the library support other geometry types like polygons?
  - answer: Set the `SRID` property on the geometry object before calling `AsBinary`,
      e.g., `linestring.SRID = 4326;`.
    question: How do I specify a different SRID when creating the geometry?
  - answer: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6
      without modification.
    question: Will this code work on .NET Core?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Tworzenie geometrii Linestring i wariantu WKB w Aspose.GIS dla .NET
url: /pl/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz geometrię Linestring i wariant WKB w Aspose.GIS dla .NET

## Wprowadzenie
If you need to **create linestring geometry .NET** and then translate that geometry into a binary form, Aspose.GIS for .NET gives you a clean, high‑performance API that works across .NET Framework, .NET Core, and .NET 5/6+. In this tutorial we’ll walk through every step—from importing namespaces to writing an EWKB file—so you can preserve SRID information and integrate GIS data into PostgreSQL/PostGIS or any binary‑based workflow without hassle.

## Szybkie odpowiedzi
- **Co oznacza skrót WKB?** Well‑Known Binary, a compact binary representation of geometric objects.  
- **Który wariant WKB przechowuje SRID?** The `ExtendedPostGis` (EWKB) variant embeds SRID directly in the binary.  
- **Czy potrzebna jest licencja?** A temporary or full Aspose.GIS license is required for production deployments.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6+.  
- **Jak długo trwa implementacja?** Typically under 10 minutes for a basic example.

## Czym jest geometria Linestring?
A linestring geometry is a simple shape made of an ordered list of points connected by straight line segments. It’s the go‑to representation for linear features such as roads, pipelines, or river paths in spatial databases.

## Dlaczego określić wariant WKB?
Using the correct WKB variant guarantees that critical metadata—especially the Spatial Reference System Identifier (SRID)—travels with your geometry. The `ExtendedPostGis` (EWKB) variant stores the SRID inside the binary payload, enabling seamless round‑tripping with PostGIS, Oracle Spatial, or any system that expects SRID‑aware binaries.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz następujące elementy:

### Instalacja Aspose.GIS dla .NET
1. Download Aspose.GIS: Visit the [download link](https://releases.aspose.com/gis/net/) to acquire the latest package.  
2. Add the NuGet package to your project (e.g., `Install-Package Aspose.GIS`).  

### Znajomość programowania w C#
- Basic understanding of C# syntax and project structure.  
- Ability to run a .NET console or class‑library project.

## Importowanie przestrzeni nazw
The `Aspose.GIS` namespace gives you access to all geometry‑related classes.  

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

These namespaces provide the core GIS functionality, including geometry creation, transformation, and binary serialization.

## Jak utworzyć geometrię linestring?
To create a linestring, instantiate a `Linestring` object with an ordered list of coordinate pairs, set its SRID if needed, and then serialize it to the desired WKB variant. The process involves three steps: building the geometry, choosing the `ExtendedPostGis` variant to retain SRID, and writing the resulting byte array to a file.

### Krok 1: Tworzenie obiektu Geometry
The `Geometry` class is Aspose.GIS's base type that represents any spatial object in memory.  
Linestring represents a series of connected points forming a linear geometry.  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
In this step we instantiate a `Linestring` with a collection of coordinate pairs that model a simple road segment.

### Krok 2: Generowanie reprezentacji WKB
`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to include SRID in the output binary.  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Here we call the `AsBinary` method, passing the EWKB variant, which returns a `byte[]` containing the full binary representation.

### Krok 3: Zapis do pliku
`File.WriteAllBytes` writes the binary array to disk.  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
The resulting file (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB` function.

## Typowe problemy i rozwiązania
| Problem | Powód | Rozwiązanie |
|-------|--------|----------|
| **Pusty plik** | `Path.Combine` points to a non‑existent directory. | Ensure the target directory exists or create it with `Directory.CreateDirectory`. |
| **Nieprawidłowy SRID** | Using the default `WkbVariant.Standard` drops SRID. | Always use `WkbVariant.ExtendedPostGis` when SRID preservation is required. |
| **Wyjątek licencyjny** | Running without a valid license in production. | Apply a temporary or full license before executing the code in a production environment. |

## Najczęściej zadawane pytania
**Q: Czy mogę używać pliku EWKB z PostGIS?**  
A: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which PostGIS reads directly via `ST_GeomFromEWKB`.  

**Q: Czy można odczytać plik WKB z powrotem do obiektu geometrycznego?**  
A: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry from its binary form.  

**Q: Czy biblioteka obsługuje inne typy geometrii, takie jak wielokąty?**  
A: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons, and many more spatial types.  

**Q: Jak określić inny SRID przy tworzeniu geometrii?**  
A: Set the `SRID` property on the geometry object before calling `AsBinary`, e.g., `linestring.SRID = 4326;`.  

**Q: Czy ten kod będzie działał na .NET Core?**  
A: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6 without modification.

---

**Ostatnia aktualizacja:** 2026-06-10  
**Testowano z:** Aspose.GIS for .NET 23.9 (latest at time of writing)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane tutoriale

- [Tłumaczenie geometrii do formatu WKB przy użyciu Aspose.GIS dla .NET](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [Określenie wariantu WKT przy tłumaczeniu przy użyciu Aspose.GIS](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [Utworzenie geometrii MultiLineString przy użyciu Aspose.GIS dla .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
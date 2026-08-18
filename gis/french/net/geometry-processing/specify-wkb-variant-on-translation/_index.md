---
date: 2026-06-10
description: Apprenez à créer une géométrie linestring en .NET et à convertir la géométrie
  en WKB en utilisant Aspose.GIS pour .NET avec la variante ExtendedPostGis.
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: Spécifier la variante WKB lors de la traduction
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
title: Créer une géométrie Linestring et la variante WKB dans Aspose.GIS pour .NET
url: /fr/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une géométrie Linestring et une variante WKB dans Aspose.GIS pour .NET

## Introduction
If you need to **créer une géométrie linestring .NET** and then translate that geometry into a binary form, Aspose.GIS for .NET gives you a clean, high‑performance API that works across .NET Framework, .NET Core, and .NET 5/6+. In this tutorial we’ll walk through every step—from importing namespaces to writing an EWKB file—so you can preserve SRID information and integrate GIS data into PostgreSQL/PostGIS or any binary‑based workflow without hassle.

## Réponses rapides
- **Que signifie WKB ?** Well‑Known Binary, a compact binary representation of geometric objects.  
- **Quelle variante WKB stocke le SRID ?** The `ExtendedPostGis` (EWKB) variant embeds SRID directly in the binary.  
- **Ai‑je besoin d’une licence ?** A temporary or full Aspose.GIS license is required for production deployments.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6+.  
- **Combien de temps prend l’implémentation ?** Typically under 10 minutes for a basic example.

## Qu’est‑ce qu’une géométrie Linestring ?
A linestring geometry is a simple shape made of an ordered list of points connected by straight line segments. It’s the go‑to representation for linear features such as roads, pipelines, or river paths in spatial databases.

## Pourquoi spécifier une variante WKB ?
Using the correct WKB variant guarantees that critical metadata—especially the Spatial Reference System Identifier (SRID)—travels with your geometry. The `ExtendedPostGis` (EWKB) variant stores the SRID inside the binary payload, enabling seamless round‑tripping with PostGIS, Oracle Spatial, or any system that expects SRID‑aware binaries.

## Prérequis

### Installation d’Aspose.GIS pour .NET
1. Téléchargez Aspose.GIS : visitez le [download link](https://releases.aspose.com/gis/net/) to acquire the latest package.  
2. Ajoutez le package NuGet à votre projet (par ex., `Install-Package Aspose.GIS`).  

### Familiarité avec la programmation C#
- Compréhension de base de la syntaxe C# et de la structure d’un projet.  
- Capacité à exécuter un projet console ou bibliothèque de classes .NET.

## Importer les espaces de noms
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

## Comment créer une géométrie linestring ?
To create a linestring, instantiate a `Linestring` object with an ordered list of coordinate pairs, set its SRID if needed, and then serialize it to the desired WKB variant. The process involves three steps: building the geometry, choosing the `ExtendedPostGis` variant to retain SRID, and writing the resulting byte array to a file.

### Étape 1 : Création d’un objet Géométrie
The `Geometry` class is Aspose.GIS's base type that represents any spatial object in memory.  
Linestring represents a series of connected points forming a linear geometry.  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
In this step we instantiate a `Linestring` with a collection of coordinate pairs that model a simple road segment.

### Étape 2 : Génération de la représentation WKB
`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to include SRID in the output binary.  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Here we call the `AsBinary` method, passing the EWKB variant, which returns a `byte[]` containing the full binary representation.

### Étape 3 : Écriture dans un fichier
`File.WriteAllBytes` writes the binary array to disk.  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
The resulting file (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB` function.

## Problèmes courants et solutions
| Issue | Reason | Solution |
|-------|--------|----------|
| **Fichier vide** | `Path.Combine` points to a non‑existent directory. | Ensure the target directory exists or create it with `Directory.CreateDirectory`. |
| **SRID incorrect** | Using the default `WkbVariant.Standard` drops SRID. | Always use `WkbVariant.ExtendedPostGis` when SRID preservation is required. |
| **Exception de licence** | Running without a valid license in production. | Apply a temporary or full license before executing the code in a production environment. |

## Questions fréquentes
**Q : Puis‑je utiliser le fichier EWKB avec PostGIS ?**  
R : Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which PostGIS reads directly via `ST_GeomFromEWKB`.  

**Q : Est‑il possible de lire un fichier WKB dans un objet géométrie ?**  
R : Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry from its binary form.  

**Q : La bibliothèque prend‑elle en charge d’autres types de géométrie comme les polygones ?**  
R : Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons, and many more spatial types.  

**Q : Comment spécifier un SRID différent lors de la création de la géométrie ?**  
R : Set the `SRID` property on the geometry object before calling `AsBinary`, e.g., `linestring.SRID = 4326;`.  

**Q : Ce code fonctionnera‑t‑il sur .NET Core ?**  
R : Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6 without modification.

---

**Dernière mise à jour :** 2026-06-10  
**Testé avec :** Aspose.GIS for .NET 23.9 (latest at time of writing)  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Traduire la géométrie au format WKB avec Aspose.GIS pour .NET](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [Spécifier la variante WKT lors de la traduction avec Aspose.GIS](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [Créer une géométrie MultiLineString avec Aspose.GIS pour .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
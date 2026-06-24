---
date: 2026-06-10
description: Leer hoe u Linestring-geometry in .NET maakt en geometry converteert
  naar WKB met Aspose.GIS voor .NET met de ExtendedPostGis-variant.
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: Specificeer WKB-variant bij vertaling
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
title: Maak Linestring-geometry & WKB-variant in Aspose.GIS voor .NET
url: /nl/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak Linestring-geometrie & WKB-variant in Aspose.GIS voor .NET

## Inleiding
Als je **linestring geometry .NET** moet maken en die geometrie vervolgens naar een binaire vorm wilt vertalen, biedt Aspose.GIS voor .NET een nette, high‑performance API die werkt op .NET Framework, .NET Core en .NET 5/6+. In deze tutorial lopen we elke stap door—van het importeren van namespaces tot het schrijven van een EWKB‑bestand—zodat je SRID‑informatie kunt behouden en GIS‑data kunt integreren in PostgreSQL/PostGIS of elke binaire workflow zonder gedoe.

## Snelle antwoorden
- **Wat betekent WKB?** Well‑Known Binary, een compacte binaire representatie van geometrische objecten.  
- **Welke WKB-variant slaat SRID op?** De `ExtendedPostGis` (EWKB) variant embeddeert SRID direct in de binaire data.  
- **Heb ik een licentie nodig?** Een tijdelijke of volledige Aspose.GIS‑licentie is vereist voor productie‑implementaties.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, en .NET 5/6+.  
- **Hoe lang duurt de implementatie?** Meestal minder dan 10 minuten voor een basisvoorbeeld.

## Wat is een Linestring-geometrie?
Een linestring‑geometrie is een eenvoudige vorm bestaande uit een geordende lijst van punten die met rechte lijnsegmenten verbonden zijn. Het is de standaardrepresentatie voor lineaire kenmerken zoals wegen, pijpleidingen of rivierlopen in ruimtelijke databases.

## Waarom een WKB-variant specificeren?
Het gebruik van de juiste WKB‑variant garandeert dat kritieke metadata—met name de Spatial Reference System Identifier (SRID)—mee‑reist met je geometrie. De `ExtendedPostGis` (EWKB) variant slaat de SRID op binnen de binaire payload, waardoor naadloze round‑tripping met PostGIS, Oracle Spatial of elk systeem dat SRID‑bewuste binaries verwacht, mogelijk is.

## Voorvereisten
Voordat je begint, zorg dat je het volgende hebt:

### Aspose.GIS voor .NET installeren
1. Download Aspose.GIS: Bezoek de [download link](https://releases.aspose.com/gis/net/) om het nieuwste pakket te verkrijgen.  
2. Voeg het NuGet‑pakket toe aan je project (bijv. `Install-Package Aspose.GIS`).  

### Bekendheid met C#-programmeren
- Basiskennis van C#‑syntaxis en projectstructuur.  
- Vermogen om een .NET‑console‑ of class‑library‑project uit te voeren.

## Namespaces importeren
De `Aspose.GIS` namespace geeft je toegang tot alle geometrie‑gerelateerde klassen.  

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Deze namespaces bieden de kern‑GIS‑functionaliteit, inclusief het maken van geometrieën, transformatie en binaire serialisatie.

## Hoe maak je een linestring-geometrie?
Om een linestring te maken, instantiateer je een `Linestring`‑object met een geordende lijst van coördinaatparen, stel je eventueel de SRID in, en serialiseer je het vervolgens naar de gewenste WKB‑variant. Het proces bestaat uit drie stappen: de geometrie bouwen, de `ExtendedPostGis`‑variant kiezen om SRID te behouden, en de resulterende byte‑array naar een bestand schrijven.

### Stap 1: Een geometrie‑object maken
De `Geometry`‑klasse is het basistype van Aspose.GIS dat elk ruimtelijk object in het geheugen vertegenwoordigt.  
Linestring vertegenwoordigt een reeks verbonden punten die een lineaire geometrie vormen.  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
In deze stap instantiateer je een `Linestring` met een collectie coördinaatparen die een eenvoudig wegsegment modelleren.

### Stap 2: WKB-representatie genereren
`WkbVariant.ExtendedPostGis` is de enum‑waarde die Aspose.GIS vertelt SRID op te nemen in de output‑binary.  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Hier roepen we de `AsBinary`‑methode aan, waarbij we de EWKB‑variant doorgeven; deze retourneert een `byte[]` met de volledige binaire representatie.

### Stap 3: Naar bestand schrijven
`File.WriteAllBytes` schrijft de binaire array naar schijf.  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
Het resulterende bestand (`EWkbFile.ewkb`) kan direct worden geïmporteerd in een PostGIS‑tabel met behulp van de `ST_GeomFromEWKB`‑functie.

## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **Leeg bestand** | `Path.Combine` wijst naar een niet‑bestaande map. | Zorg dat de doelmap bestaat of maak deze aan met `Directory.CreateDirectory`. |
| **Onjuiste SRID** | Het gebruik van de standaard `WkbVariant.Standard` verwijdert de SRID. | Gebruik altijd `WkbVariant.ExtendedPostGis` wanneer SRID‑behoud vereist is. |
| **Licentie‑exception** | Uitvoeren zonder geldige licentie in productie. | Pas een tijdelijke of volledige licentie toe voordat je de code in een productie‑omgeving uitvoert. |

## Veelgestelde vragen
**Q: Kan ik het EWKB‑bestand gebruiken met PostGIS?**  
A: Ja, de `ExtendedPostGis`‑variant produceert EWKB die SRID bevat, en PostGIS leest dit direct via `ST_GeomFromEWKB`.  

**Q: Is het mogelijk om een WKB‑bestand terug te lezen in een geometrie‑object?**  
A: Absoluut. Gebruik `Geometry.FromBinary(byteArray)` om de geometrie uit de binaire vorm te reconstrueren.  

**Q: Ondersteunt de bibliotheek andere geometrietypen zoals polygonen?**  
A: Ja, Aspose.GIS verwerkt punten, linestrings, polygonen, multipolygonen en nog veel meer ruimtelijke types.  

**Q: Hoe specificeer ik een andere SRID bij het maken van de geometrie?**  
A: Stel de `SRID`‑eigenschap in op het geometrie‑object voordat je `AsBinary` aanroept, bijv. `linestring.SRID = 4326;`.  

**Q: Werkt deze code op .NET Core?**  
A: Ja, dezelfde API werkt op .NET Framework, .NET Core en .NET 5/6 zonder aanpassingen.

---

**Laatst bijgewerkt:** 2026-06-10  
**Getest met:** Aspose.GIS for .NET 23.9 (latest at time of writing)  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Geometrie vertalen naar WKB-indeling met Aspose.GIS voor .NET](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [WKT-variant specificeren bij vertaling met Aspose.GIS](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [MultiLineString-geometrie maken met Aspose.GIS voor .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
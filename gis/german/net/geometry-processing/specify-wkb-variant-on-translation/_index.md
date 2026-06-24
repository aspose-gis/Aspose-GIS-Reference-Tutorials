---
date: 2026-06-10
description: Erfahren Sie, wie Sie in .NET Linestring-Geometrie erstellen und Geometrie
  mit Aspose.GIS für .NET in WKB konvertieren, wobei die ExtendedPostGis-Variante
  verwendet wird.
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: WKB-Variante bei der Übersetzung angeben
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
title: Linestring-Geometrie & WKB-Variante in Aspose.GIS für .NET erstellen
url: /de/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Linestring-Geometrie & WKB-Variante in Aspose.GIS für .NET erstellen

## Einführung
Wenn Sie **create linestring geometry .NET** benötigen und anschließend diese Geometrie in ein Binärformat übersetzen möchten, bietet Aspose.GIS für .NET eine saubere, leistungsstarke API, die auf .NET Framework, .NET Core und .NET 5/6+ funktioniert. In diesem Tutorial führen wir Sie durch jeden Schritt – vom Importieren von Namespaces bis zum Schreiben einer EWKB‑Datei – damit Sie SRID‑Informationen erhalten und GIS‑Daten in PostgreSQL/PostGIS oder jeden binär‑basierten Workflow problemlos integrieren können.

## Schnelle Antworten
- **Wofür steht WKB?** Well‑Known Binary, eine kompakte binäre Darstellung geometrischer Objekte.  
- **Welche WKB‑Variante speichert SRID?** Die `ExtendedPostGis` (EWKB)-Variante bettet die SRID direkt in das Binärformat ein.  
- **Benötige ich eine Lizenz?** Eine temporäre oder vollständige Aspose.GIS‑Lizenz ist für Produktions‑Deployments erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, und .NET 5/6+.  
- **Wie lange dauert die Implementierung?** In der Regel weniger als 10 Minuten für ein einfaches Beispiel.

## Was ist eine Linestring‑Geometrie?
Eine Linestring‑Geometrie ist eine einfache Form, die aus einer geordneten Liste von Punkten besteht, die durch gerade Liniensegmente verbunden sind. Sie ist die gängige Darstellung für lineare Merkmale wie Straßen, Rohrleitungen oder Flussverläufe in räumlichen Datenbanken.

## Warum eine WKB‑Variante angeben?
Die Verwendung der richtigen WKB‑Variante stellt sicher, dass kritische Metadaten – insbesondere der Spatial Reference System Identifier (SRID) – zusammen mit Ihrer Geometrie transportiert werden. Die `ExtendedPostGis` (EWKB)-Variante speichert die SRID im Binär‑Payload, wodurch ein nahtloses Round‑Trip‑Verfahren mit PostGIS, Oracle Spatial oder jedem System, das SRID‑bewusste Binärdateien erwartet, ermöglicht wird.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

### Installation von Aspose.GIS für .NET
1. Download Aspose.GIS: Besuchen Sie den [download link](https://releases.aspose.com/gis/net/), um das neueste Paket zu erhalten.  
2. Fügen Sie das NuGet‑Paket zu Ihrem Projekt hinzu (z. B. `Install-Package Aspose.GIS`).  

### Vertrautheit mit C#‑Programmierung
- Grundlegendes Verständnis der C#‑Syntax und Projektstruktur.  
- Fähigkeit, ein .NET‑Konsolen‑ oder Klassenbibliotheks‑Projekt auszuführen.

## Namespaces importieren
Der `Aspose.GIS`‑Namespace gibt Ihnen Zugriff auf alle geometriebezogenen Klassen.  

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Diese Namespaces stellen die Kern‑GIS‑Funktionalität bereit, einschließlich Geometrieerstellung, Transformation und binärer Serialisierung.

## Wie erstellt man eine Linestring‑Geometrie?
Um einen Linestring zu erstellen, instanziieren Sie ein `Linestring`‑Objekt mit einer geordneten Liste von Koordinatenpaaren, setzen bei Bedarf dessen SRID und serialisieren es anschließend in die gewünschte WKB‑Variante. Der Prozess umfasst drei Schritte: Aufbau der Geometrie, Auswahl der `ExtendedPostGis`‑Variante zum Beibehalten der SRID und Schreiben des resultierenden Byte‑Arrays in eine Datei.

### Schritt 1: Erstellen eines Geometrie‑Objekts
Die Klasse `Geometry` ist der Basistyp von Aspose.GIS, der jedes räumliche Objekt im Speicher repräsentiert.  
Linestring repräsentiert eine Reihe verbundener Punkte, die eine lineare Geometrie bilden.  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
In diesem Schritt instanziieren wir ein `Linestring` mit einer Sammlung von Koordinatenpaaren, die ein einfaches Straßensegment modellieren.

### Schritt 2: Generieren der WKB‑Darstellung
`WkbVariant.ExtendedPostGis` ist der Enum‑Wert, der Aspose.GIS anweist, die SRID in das Ausgabebinärformat einzuschließen.  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Hier rufen wir die Methode `AsBinary` auf und übergeben die EWKB‑Variante, die ein `byte[]` mit der vollständigen binären Darstellung zurückgibt.

### Schritt 3: Schreiben in eine Datei
`File.WriteAllBytes` schreibt das Binär‑Array auf die Festplatte.  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
Die resultierende Datei (`EWkbFile.ewkb`) kann direkt in eine PostGIS‑Tabelle importiert werden, indem die Funktion `ST_GeomFromEWKB` verwendet wird.

## Häufige Probleme und Lösungen
| Problem | Grund | Lösung |
|-------|--------|----------|
| **Leere Datei** | `Path.Combine` points to a non‑existent directory. | Ensure the target directory exists or create it with `Directory.CreateDirectory`. |
| **Falsche SRID** | Using the default `WkbVariant.Standard` drops SRID. | Always use `WkbVariant.ExtendedPostGis` when SRID preservation is required. |
| **Lizenzausnahme** | Running without a valid license in production. | Apply a temporary or full license before executing the code in a production environment. |

## Häufig gestellte Fragen
**Q: Kann ich die EWKB‑Datei mit PostGIS verwenden?**  
A: Ja, die `ExtendedPostGis`‑Variante erzeugt EWKB, das die SRID enthält, die PostGIS direkt über `ST_GeomFromEWKB` liest.  

**Q: Ist es möglich, eine WKB‑Datei wieder in ein Geometrie‑Objekt zu lesen?**  
A: Absolut. Verwenden Sie `Geometry.FromBinary(byteArray)`, um die Geometrie aus ihrer Binärform zu rekonstruieren.  

**Q: Unterstützt die Bibliothek andere Geometrietypen wie Polygone?**  
A: Ja, Aspose.GIS verarbeitet Punkte, Linestrings, Polygone, Multipolygone und viele weitere räumliche Typen.  

**Q: Wie gebe ich beim Erstellen der Geometrie eine andere SRID an?**  
A: Setzen Sie die `SRID`‑Eigenschaft des Geometrie‑Objekts, bevor Sie `AsBinary` aufrufen, z. B. `linestring.SRID = 4326;`.  

**Q: Wird dieser Code auf .NET Core funktionieren?**  
A: Ja, dieselbe API funktioniert über .NET Framework, .NET Core und .NET 5/6 hinweg ohne Änderungen.  

---

**Zuletzt aktualisiert:** 2026-06-10  
**Getestet mit:** Aspose.GIS for .NET 23.9 (latest at time of writing)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Geometrie in WKB-Format mit Aspose.GIS für .NET übersetzen](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [WKT-Variante beim Übersetzen mit Aspose.GIS angeben](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [MultiLineString-Geometrie mit Aspose.GIS für .NET erstellen](/gis/net/geometry-creation/create-multilinestring-geometry/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
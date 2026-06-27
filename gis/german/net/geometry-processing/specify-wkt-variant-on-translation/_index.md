---
date: 2026-04-09
description: Erfahren Sie, wie Sie beim Erstellen von Punkten in C# mit Aspose.GIS
  für .NET in Ihren .NET‑Anwendungen den räumlichen Bezug zuweisen und die Dezimalgenauigkeit
  festlegen.
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: WKT‑Variante bei Übersetzung angeben
second_title: Aspose.GIS .NET API
title: Räumliche Referenz zuweisen & WKT‑Variante festlegen mit Aspose.GIS
url: /de/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Räumliche Referenz zuweisen & WKT-Variante festlegen mit Aspose.GIS

## Einleitung
In diesem Tutorial lernen Sie, wie Sie **räumliche Referenz** einer Geometrie zuweisen und das genaue WKT‑Ausgabeformat mit Aspose.GIS für .NET steuern. Egal, ob Sie **C#‑Punktobjekte** für Kartierung, Analytik oder Datenaustausch erstellen müssen, die Möglichkeit, die richtige WKT‑Variante und numerische Präzision zu wählen, macht Ihre räumlichen Daten interoperabel und leicht lesbar. Lassen Sie uns den Prozess Schritt für Schritt durchgehen.

## Schnelle Antworten
- **Was bedeutet „räumliche Referenz zuweisen“?** Es bindet eine Geometrie an ein bestimmtes Koordinatensystem wie WGS‑84.  
- **Welche WKT-Varianten werden unterstützt?** Iso, SimpleFeatureAccessOutdated und ExtendedPostGis.  
- **Wie kann ich die Dezimalpräzision steuern?** Verwenden Sie die `NumericFormat`‑Optionen wie `General`, `RoundTrip` oder `Flat`.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche .NET-Versionen sind kompatibel?** .NET Framework 4.0+ und .NET Core/5/6+.

## Was bedeutet „räumliche Referenz zuweisen“?
Das Zuweisen einer räumlichen Referenz (oder eines räumlichen Referenzsystems, SRS) teilt GIS‑Software mit, wie die Koordinatenwerte einer Geometrie zu interpretieren sind. Ohne ein SRS haben die Breiten‑ und Längengradzahlen eines Punktes keine reale Bedeutung.

## Warum die WKT-Variante und das numerische Format steuern?
Verschiedene GIS‑Werkzeuge erwarten leicht unterschiedliche WKT‑Syntaxen. Die Auswahl der richtigen Variante gewährleistet einen nahtlosen Datenaustausch, während das Festlegen der Dezimalpräzision Rundungsfehler oder übermäßig lange Zahlen verhindert, die Protokolle und Dateien unübersichtlich machen.

## Voraussetzungen
1. Aspose.GIS für .NET – Download von der [download page](https://releases.aspose.com/gis/net/).  
2. Eine .NET‑Entwicklungsumgebung (Visual Studio, VS Code oder Rider).  
3. Grundlegende Kenntnisse in C# und dem .NET‑Framework.

## Namespaces importieren
Bevor Sie Aspose.GIS‑Klassen verwenden, importieren Sie die erforderlichen Namespaces:

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

## Schritt 1: Ein Punktobjekt erstellen (create point C#)
Wir beginnen mit der Konstruktion eines `Point` mit Breiten‑, Längen‑ und einem optionalen Maß (M) Wert:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Schritt 2: Räumliches Referenzsystem zuweisen (SRS)
Jetzt **weisen wir dem Punkt eine räumliche Referenz** zu. Hier verwenden wir das weit verbreitete WGS‑84‑System (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Schritt 3: Gewünschte WKT‑Variante angeben
Wählen Sie die WKT‑Variante, die zu Ihrer nachgelagerten Anwendung passt:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Schritt 4: Dezimalpräzision für die WKT‑Ausgabe festlegen
Steuern Sie, wie viele Stellen im endgültigen String erscheinen, mit `NumericFormat`:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Häufige Fallstricke & Tipps
- **Fallstrick:** Das Vergessen, das SRS vor dem Aufruf von `AsText` zu setzen, kann dazu führen, dass SRID‑Informationen fehlen.  
- **Tipp:** Verwenden Sie `NumericFormat.RoundTrip`, wenn Sie eine verlustfreie Rundreise von Koordinaten benötigen.  
- **Tipp:** Die `Iso`‑Variante ist am portabelsten; wählen Sie `ExtendedPostGis` nur, wenn Sie ein eingebettetes SRID benötigen.

## Fazit
Sie wissen jetzt, wie Sie **räumliche Referenz zuweisen**, die passende WKT‑Variante wählen und **Dezimalpräzision festlegen**, wenn Sie **C#‑Punktobjekte** mit Aspose.GIS erstellen. Diese Steuerungen geben Ihnen die Flexibilität, die genauen Anforderungen jedes GIS‑Workflows zu erfüllen, von einfacher Visualisierung bis hin zu hochpräziser räumlicher Analyse.

## Häufig gestellte Fragen

**Q:** Ist Aspose.GIS mit allen .NET‑Versionen kompatibel?  
**A:** Ja, Aspose.GIS unterstützt .NET Framework 4.0 und höher sowie .NET Core/5/6.

**Q:** Kann ich Aspose.GIS für kommerzielle Projekte nutzen?  
**A:** Absolut. Für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich, aber eine kostenlose Testversion steht zur Evaluierung bereit.

**Q:** Unterstützt Aspose.GIS andere räumliche Datenformate?  
**A:** Ja, es arbeitet mit ESRI Shapefile, GeoJSON, KML und vielen weiteren Formaten.

**Q:** Wo kann ich eine kostenlose Testversion herunterladen?  
**A:** Sie können eine kostenlose Testversion von Aspose.GIS [hier](https://releases.aspose.com/) herunterladen.

**Q:** Wie bekomme ich Hilfe, wenn ich auf Probleme stoße?  
**A:** Stellen Sie Ihre Fragen im Aspose.GIS‑Community‑[Forum](https://forum.aspose.com/c/gis/33), wo sowohl Aspose‑Mitarbeiter als auch Community‑Mitglieder unterstützen können.

---

**Zuletzt aktualisiert:** 2026-04-09  
**Getestet mit:** Aspose.GIS for .NET (latest release)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
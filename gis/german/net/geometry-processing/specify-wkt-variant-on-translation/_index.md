---
date: 2026-09-15
description: Erfahren Sie, wie Sie coordinate system zuweisen, das WKT variant festlegen
  und die decimal precision steuern, wenn Sie point geometry in C# mit Aspose.GIS
  für .NET erstellen.
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: WKT variant bei Übersetzung festlegen
og_description: Erfahren Sie, wie Sie coordinate system zuweisen, das WKT variant
  festlegen und die decimal precision steuern, wenn Sie point geometry in C# mit Aspose.GIS
  für .NET erstellen.
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: coordinate system zuweisen, WKT variant mit Aspose.GIS festlegen
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: coordinate system zuweisen, WKT variant mit Aspose.GIS festlegen
url: /de/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Koordinatensystem zuweisen, WKT-Variante mit Aspose.GIS festlegen

## Einführung
In diesem Tutorial lernen Sie, wie Sie **Koordinatensystem zuweisen**, die richtige WKT-Variante auswählen und die Dezimalgenauigkeit steuern, wenn Sie **Punktgeometrie** in C# mit Aspose.GIS für .NET **erstellen**. Egal, ob Sie einen Mapping‑Dienst aufbauen, räumliche Analysen durchführen oder Daten zwischen GIS‑Plattformen austauschen, diese Einstellungen gewährleisten, dass Ihre Ausgabe sowohl interoperabel als auch leicht lesbar ist. Lassen Sie uns den Prozess Schritt für Schritt durchgehen.

## Schnelle Antworten
- **Was bedeutet „Koordinatensystem zuweisen“?** Es bindet eine Geometrie an ein bestimmtes Koordinatenreferenzsystem wie WGS‑84.  
- **Welche WKT-Varianten werden unterstützt?** Iso, SimpleFeatureAccessOutdated und ExtendedPostGis.  
- **Wie kann ich die Dezimalgenauigkeit steuern?** Verwenden Sie das `NumericFormat`‑Enum (`General`, `RoundTrip`, `Flat`).  
- **Benötige ich eine Lizenz für Aspose.GIS?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche .NET‑Versionen sind kompatibel?** .NET Framework 4.0+ und .NET Core/5/6+.

## Was bedeutet „Koordinatensystem zuweisen“?
Das Zuweisen einer räumlichen Referenz (oder eines Spatial Reference Systems, SRS) teilt GIS‑Software mit, wie die Koordinatenwerte einer Geometrie zu interpretieren sind, indem die Zahlen mit einem realen Koordinatensystem wie WGS‑84 verknüpft werden. Ohne ein SRS haben die Breiten‑ und Längengradzahlen eines Punktes keine reale Bedeutung.

## Warum die WKT‑Variante und das numerische Format steuern?
Über 30 GIS‑Tools erwarten bestimmte WKT‑Syntaxen, sodass die Auswahl der richtigen Variante Importfehler verhindert. Das Festlegen des numerischen Formats reduziert Rundungsrauschen und hält die Ausgabe kompakt, was besonders wichtig ist, wenn Protokolle oder Dateien programmgesteuert ausgewertet werden.

## Voraussetzungen
1. Aspose.GIS für .NET – Download von der [Download-Seite](https://releases.aspose.com/gis/net/).  
2. Eine .NET‑Entwicklungsumgebung (Visual Studio, VS Code oder Rider).  
3. Grundlegende Kenntnisse in C# und dem .NET‑Framework.

## Namensräume importieren
Bevor Sie Aspose.GIS‑Klassen verwenden, importieren Sie die erforderlichen Namensräume:

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

## Wie weist man einem Punkt ein Koordinatensystem zu?
Laden Sie eine `Point`‑Instanz und fügen Sie dann mithilfe der Klasse `SpatialReference` ein räumliches Referenzsystem (SRS) hinzu. Dieses Zwei‑Schritt‑Muster stellt sicher, dass die Geometrie beim Export ihre Koordinatensystem‑Metadaten trägt, sodass nachgelagerte Werkzeuge die Koordinaten korrekt interpretieren können. Die Klasse `Point` repräsentiert einen einzelnen Ort, definiert durch X‑ (Längengrad) und Y‑ (Breitengrad) Koordinaten.

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Schritt 2: räumliches Referenzsystem (SRS) zuweisen
Jetzt **weisen wir dem Punkt eine räumliche Referenz** zu. `SpatialReference` repräsentiert ein Koordinatenreferenzsystem, das durch eine SRID identifiziert wird. Hier verwenden wir das weit verbreitete WGS‑84‑System (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Schritt 3: gewünschte WKT‑Variante angeben
Wählen Sie die WKT‑Variante, die zu Ihrer nachgelagerten Anwendung passt:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Wie stellt man die Dezimalgenauigkeit für die WKT‑Ausgabe ein?
Steuern Sie, wie viele Stellen im endgültigen String erscheinen, indem Sie das `NumericFormat`‑Enum verwenden, das Formatierungsregeln wie `General`, `RoundTrip` oder `Flat` definiert. Die Auswahl von `RoundTrip` bewahrt die volle Koordinaten‑Genauigkeit für Round‑Trip‑Szenarien, während `General` eine kompakte Darstellung für die meisten Visualisierungsaufgaben liefert. Das `NumericFormat`‑Enum bestimmt, wie Koordinatenzahlen in der WKT‑Ausgabe formatiert werden.

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Häufige Fallstricke & Tipps
- **Fallstrick:** Das Vergessen, das SRS vor dem Aufruf von `AsText` zu setzen, kann dazu führen, dass SRID‑Informationen fehlen.  
- **Tipp:** Verwenden Sie `NumericFormat.RoundTrip`, wenn Sie einen verlustfreien Round‑Trip von Koordinaten benötigen.  
- **Tipp:** Die `Iso`‑Variante ist am portabelsten; wählen Sie `ExtendedPostGis` nur, wenn Sie eine eingebettete SRID benötigen.

## Fazit
Sie wissen jetzt, wie Sie **ein Koordinatensystem zuweisen**, die passende WKT‑Variante auswählen und **die Dezimalgenauigkeit festlegen**, wenn Sie **Punktgeometrie** mit Aspose.GIS **erstellen**. Diese Steuerungen geben Ihnen die Flexibilität, die genauen Anforderungen jedes GIS‑Workflows zu erfüllen, von einfacher Visualisierung bis hin zu hochpräziser räumlicher Analyse.

## Häufig gestellte Fragen

**Q:** Ist Aspose.GIS mit allen Versionen von .NET kompatibel?  
**A:** Ja, Aspose.GIS unterstützt .NET Framework 4.0 und höher sowie .NET Core/5/6.

**Q:** Kann ich Aspose.GIS für kommerzielle Projekte nutzen?  
**A:** Absolut. Für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich, aber eine kostenlose Testversion steht für die Evaluierung zur Verfügung.

**Q:** Unterstützt Aspose.GIS weitere räumliche Datenformate?  
**A:** Ja, es arbeitet mit über 30 Formaten, darunter ESRI Shapefile, GeoJSON, KML, CSV und viele weitere.

**Q:** Wo kann ich eine kostenlose Testversion herunterladen?  
**A:** Sie können eine kostenlose Testversion von Aspose.GIS von der [Aspose.GIS Free‑Trial‑Download‑Seite](https://releases.aspose.com/) herunterladen.

**Q:** Wie bekomme ich Hilfe, wenn ich auf Probleme stoße?  
**A:** Stellen Sie Ihre Fragen im Aspose.GIS‑Community‑[Forum](https://forum.aspose.com/c/gis/33), wo sowohl Aspose‑Mitarbeiter als auch Community‑Mitglieder unterstützen können.

---

**Zuletzt aktualisiert:** 2026-09-15  
**Getestet mit:** Aspose.GIS für .NET (neueste Version)  
**Autor:** Aspose

## Verwandte Tutorials

- [Vektorlayer erstellen und sein räumliches Referenzsystem festlegen](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Wie man Geometrie mit Aspose.GIS für .NET in WKT übersetzt](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [Wie man die Präzision beim Schreiben von Geometrien mit Aspose.GIS begrenzt](/gis/net/geometry-processing/limit-precision-writing-geometries/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
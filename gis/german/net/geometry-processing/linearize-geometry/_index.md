---
date: 2026-04-06
description: Erfahren Sie, wie Sie Kurven in Linien umwandeln und Geometrie mit Aspose.GIS
  für .NET linearisieren, um eine schnelle geospatiale Verarbeitung und Analyse in
  Ihren .NET-Anwendungen zu ermöglichen.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS linearize geometry
linktitle: Geometrie linearisieren
second_title: Aspose.GIS .NET API
title: Kurven in Linien konvertieren mit Aspose.GIS für .NET
url: /de/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kurven in Linien konvertieren mit Aspose.GIS für .NET

## Einleitung
Wenn Sie **Kurven in Linien konvertieren** müssen für Kartierung, räumliche Analyse oder Daten‑Austausch‑Aufgaben, bietet Aspose.GIS für .NET eine saubere, programmatische Möglichkeit, dies zu tun. In diesem Tutorial führen wir Sie durch ein vollständiges, praxisnahes Beispiel, das zeigt, wie man eine komplexe Geometrie – die Kurven und zusammengesetzte Formen enthält – in eine einfache lineare Darstellung umwandelt, die mit jedem GIS‑System funktioniert.

## Schnelle Antworten
- **Was bedeutet die Linearisation einer Geometrie?** Umwandlung von Kurven und komplexen Formen in gerade Liniensegmente.  
- **Warum Aspose.GIS verwenden?** Es unterstützt Dutzende von GIS‑Formaten und erledigt die Geometrie‑Konvertierung ohne externe Werkzeuge.  
- **Voraussetzungen?** .NET Framework oder .NET Core, Visual Studio und die Aspose.GIS‑Bibliothek.  
- **Wie lange dauert das Beispiel?** Unter fünf Minuten, sobald die Bibliothek installiert ist.  
- **Kann ich in andere Formate speichern?** Ja – ersetzen Sie den KML‑Treiber durch Shapefile, GeoJSON usw.

## Was bedeutet die Linearisation von Geometrien?
Die Linearisation von Geometrien bedeutet, jede gekrümmte oder zusammengesetzte Form in eine Reihe von geraden Liniensegmenten (eine „lineare Geometrie“) zu zerlegen. Dies vereinfacht das Rendern, die Analyse und die Interoperabilität mit Werkzeugen, die nur Linien und Punkte verstehen.

## Warum Kurven in Linien umwandeln?
- **Performance:** Lineare Geometrien lassen sich schneller rendern und abfragen.  
- **Kompatibilität:** Viele GIS‑Plattformen (z. B. ältere Kartendienste) akzeptieren nur lineare Features.  
- **Vereinfachung:** Nützlich zum Erstellen von Thumbnails, schnellen Vorschaubildern oder zum Einspeisen von Daten in Algorithmen, die lineare Eingaben benötigen.

## Voraussetzungen
Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Aspose.GIS für .NET** – laden Sie es von der [Aspose.GIS‑Website](https://releases.aspose.com/gis/net/) herunter.  
2. **.NET Framework** (oder .NET Core) auf Ihrem Entwicklungsrechner installiert.  
3. **Visual Studio** (oder jede C#‑kompatible IDE) zum Schreiben und Ausführen des Beispiels.

## Namespaces importieren
Um die Aspose.GIS‑Funktionalität zu nutzen, importieren Sie die erforderlichen Namespaces.

### Schritt 1: Die Aspose.GIS Core Namespaces importieren
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Schritt 2: Den Treiber für das Zielformat importieren
Für dieses Beispiel schreiben wir das Ergebnis in eine KML‑Datei:
```csharp
using Aspose.GIS.Kml;
```

## Wie man Kurven in Linien konvertiert – Schritt‑für‑Schritt‑Anleitung
Im Folgenden finden Sie eine detaillierte Durchgang durch jede Codezeile, die erklärt, **wie man Kurven in Linien konvertiert** und warum jeder Schritt wichtig ist.

### Schritt 1: Den Ausgabepfad festlegen
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Ersetzen Sie `"Your Document Directory"` durch den Ordner, in dem Sie die KML‑Datei speichern möchten.

### Schritt 2: Einen Layer für die Ausgabedatei erstellen
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
Ein *Layer* ist ein Container für geografische Features. Hier erstellen wir einen neuen KML‑Layer, der unsere linearisierten Geometrien enthält.

### Schritt 3: Ein neues Feature erstellen
```csharp
var feature = layer.ConstructFeature();
```
Ein *Feature* repräsentiert ein einzelnes geografisches Objekt (Punkt, Linie, Polygon usw.). Wir werden unsere lineare Geometrie an dieses Feature anhängen.

### Schritt 4: Die ursprüngliche komplexe Geometrie definieren
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Wir erzeugen eine Geometrie aus einem Well‑Known‑Text (WKT)‑String. Dieses Beispiel enthält einen `LineString`, einen `CompoundCurve` und einen `CircularString` – ideal, um die Umwandlung von Kurven in Linien zu demonstrieren.

### Schritt 5: Die Geometrie linearieren
```csharp
var linear = geometry.ToLinearGeometry();
```
Die Methode `ToLinearGeometry()` konvertiert alle Kurven in gerade Liniensegmente und erzeugt eine *lineare* Version der ursprünglichen Geometrie.

### Schritt 6: Die lineare Geometrie dem Feature zuweisen
```csharp
feature.Geometry = linear;
```
Jetzt enthält das Feature die vereinfachte, lineare Geometrie.

### Schritt 7: Das Feature dem Layer hinzufügen
```csharp
layer.Add(feature);
```
Abschließend fügen wir das Feature dem KML‑Layer hinzu, der die lineare Geometrie in die Ausgabedatei schreibt, wenn der `using`‑Block endet.

## Häufige Fallstricke & Tipps
- **Pfadtrennzeichen:** Verwenden Sie `Path.Combine` für plattformübergreifende Pfadkonstruktion.  
- **Große Geometrien:** Das Linearieren sehr komplexer Formen kann viele Scheitelpunkte erzeugen; erwägen Sie die Verwendung von `Simplify()` nach der Linearisation, wenn Sie weniger Punkte benötigen.  
- **Treiberwahl:** Wenn Sie ein anderes Ausgabeformat benötigen, ersetzen Sie `Drivers.Kml` durch `Drivers.Shapefile`, `Drivers.GeoJson` usw. und passen Sie die Dateierweiterung entsprechend an.

## Häufig gestellte Fragen (verbessert)

**F: Ist Aspose.GIS für .NET mit .NET Core kompatibel?**  
A: Ja, Aspose.GIS für .NET funktioniert mit .NET Core und ermöglicht den Bau plattformübergreifender Anwendungen.

**F: Kann ich mit verschiedenen GIS‑Dateiformaten arbeiten, wenn ich Aspose.GIS für .NET verwende?**  
A: Absolut! Aspose.GIS unterstützt KML, Shapefile, GeoJSON und viele weitere Formate.

**F: Bietet Aspose.GIS Unterstützung für räumliche Operationen und Analysen?**  
A: Ja, es stellt ein breites Spektrum an räumlichen Operationen und Analysefunktionen zur Verfügung, um komplexe geospatiale Aufgaben zu bewältigen.

**F: Gibt es eine kostenlose Testversion von Aspose.GIS für .NET?**  
A: Ja, Sie können eine kostenlose Testversion von der [Aspose‑Website](https://releases.aspose.com/) herunterladen.

**F: Wo finde ich Hilfe und Support für Aspose.GIS?**  
A: Besuchen Sie das [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) für Unterstützung durch die Community und das Aspose‑Supportteam.

**F: Kann ich Geometrien linearieren, die 3D‑ (Z‑)Koordinaten enthalten?**  
A: Ja, `ToLinearGeometry()` funktioniert sowohl mit 2D‑ als auch mit 3D‑Geometrien; die Z‑Werte bleiben in den resultierenden Liniensegmenten erhalten.

**F: Wie wirkt sich die Linearisation auf die Größe der Ausgabedatei aus?**  
A: Das Umwandeln von Kurven in viele kurze Liniensegmente kann die Dateigröße erhöhen. Verwenden Sie `Simplify()` nach der Linearisation, wenn die Dateigröße ein Problem darstellt.

**F: Ist es möglich, die Segmentlänge bei der Linearisation zu steuern?**  
A: Die Standardmethode verwendet eine interne Toleranz. Für benutzerdefinierte Segmentierung können Sie Kurven manuell tessellieren, bevor Sie `ToLinearGeometry()` aufrufen.

## Fazit
In diesem Tutorial haben wir **wie man Kurven in Linien konvertiert** mit Aspose.GIS für .NET behandelt, von der Einrichtung der Umgebung bis zum Schreiben des linearisierten Ergebnisses in eine KML‑Datei. Sie können diesen Workflow nun in Kartenanwendungen, Datenverarbeitungspipelines oder jedes GIS‑bezogene Projekt integrieren, das vereinfachte Geometrien erfordert.

---

**Last Updated:** 2026-04-06  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
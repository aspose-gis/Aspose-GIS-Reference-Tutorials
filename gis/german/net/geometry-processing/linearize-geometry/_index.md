---
date: 2025-12-21
description: Erfahren Sie, wie Sie Geometrie mit Aspose.GIS für .NET linearisieren,
  um eine effiziente Verarbeitung von Geodaten, räumliche Analysen und Geometrie-Manipulationen
  in Ihren .NET-Anwendungen zu ermöglichen.
linktitle: Linearize a Geometry
second_title: Aspose.GIS .NET API
title: Wie man Geometrie mit Aspose.GIS für .NET linearisiert
url: /de/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Geometrie linearisieren

## Einführung
Wenn Sie **wie man Geometrien linearisiert** für Kartierung, räumliche Analyse oder Daten‑austausch‑Aufgaben benötigen, bietet Aspose.GIS für .NET eine saubere, programmatische Möglichkeit, dies zu tun. In diesem Tutorial führen wir Sie durch ein vollständiges, praxisnahes Beispiel, das zeigt, wie man eine komplexe Geometrie – mit Kurven und zusammengesetzten Formen – in eine einfache lineare Darstellung umwandelt, die mit jedem GIS‑System funktioniert.

## Schnelle Antworten
- **Was bedeutet das Linearisieren einer Geometrie?** Umwandlung von Kurven und komplexen Formen in gerade Liniensegmente.  
- **Warum Aspose.GIS verwenden?** Es unterstützt Dutzende von GIS‑Formaten und erledigt die Geometriekonvertierung ohne externe Werkzeuge.  
- **Voraussetzungen?** .NET Framework oder .NET Core, Visual Studio und die Aspose.GIS‑Bibliothek.  
- **Wie lange dauert das Beispiel?** Unter fünf Minuten, sobald die Bibliothek installiert ist.  
- **Kann ich in andere Formate speichern?** Ja – ersetzen Sie den KML‑Treiber durch Shapefile, GeoJSON usw.

## Was bedeutet das Linearisieren von Geometrien?
Das Linearisieren von Geometrien bedeutet, jede gekrümmte oder zusammengesetzte Form in eine Reihe von geraden Liniensegmenten (eine „lineare Geometrie“) zu zerlegen. Dies vereinfacht das Rendern, die Analyse und die Interoperabilität mit Werkzeugen, die nur Linien und Punkte verstehen.

## Warum Geometrien linearisieren?
- **Leistung:** Lineare Geometrien lassen sich schneller rendern und abfragen.  
- **Kompatibilität:** Viele GIS‑Plattformen (z. B. ältere Kartendienste) akzeptieren nur lineare Features.  
- **Vereinfachung:** Nützlich zum Erstellen von Thumbnails, schnellen Vorschauen oder zum Einspeisen von Daten in Algorithmen, die lineare Eingaben benötigen.

## Voraussetzungen
Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Aspose.GIS für .NET** – laden Sie es von der [Aspose.GIS-Website](https://releases.aspose.com/gis/net/) herunter.  
2. **.NET Framework** (oder .NET Core) auf Ihrem Entwicklungsrechner installiert.  
3. **Visual Studio** (oder eine beliebige C#‑kompatible IDE) zum Schreiben und Ausführen des Beispiels.

## Namespaces importieren
Um die Aspose.GIS‑Funktionalität zu nutzen, importieren Sie die erforderlichen Namespaces.

### Schritt 1: Importieren der Aspose.GIS Core Namespaces
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Schritt 2: Importieren des Treibers für Ihr Zielformat
Für dieses Beispiel schreiben wir das Ergebnis in eine KML‑Datei:
```csharp
using Aspose.GIS.Kml;
```

## Wie man Geometrien linearisiert – Schritt‑für‑Schritt‑Anleitung
Unten finden Sie eine detaillierte Durchgang durch jede Codezeile, die erklärt, **wie man Geometrien linearisiert** und warum jeder Schritt wichtig ist.

### Schritt 1: Definieren des Ausgabepfads
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Ersetzen Sie `"Your Document Directory"` durch den Ordner, in dem Sie die KML‑Datei speichern möchten.

### Schritt 2: Erstellen einer Ebene für die Ausgabedatei
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
Eine *Ebene* ist ein Container für geografische Features. Hier erstellen wir eine neue KML‑Ebene, die unsere linearisierten Geometrien enthält.

### Schritt 3: Erstellen eines neuen Features
```csharp
var feature = layer.ConstructFeature();
```
Ein *Feature* repräsentiert ein einzelnes geografisches Objekt (Punkt, Linie, Polygon usw.). Wir werden unsere lineare Geometrie an dieses Feature anhängen.

### Schritt 4: Definieren der ursprünglichen komplexen Geometrie
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Wir erstellen eine Geometrie aus einem Well‑Known Text (WKT)‑String. Dieses Beispiel enthält einen `LineString`, einen `CompoundCurve` und einen `CircularString` – ideal, um die Linearisation zu demonstrieren.

### Schritt 5: Linearisieren der Geometrie
```csharp
var linear = geometry.ToLinearGeometry();
```
Die Methode `ToLinearGeometry()` wandelt alle Kurven in gerade Liniensegmente um und erzeugt eine *lineare* Version der ursprünglichen Geometrie.

### Schritt 6: Zuweisen der linearen Geometrie zum Feature
```csharp
feature.Geometry = linear;
```
Jetzt enthält das Feature die vereinfachte, lineare Geometrie.

### Schritt 7: Hinzufügen des Features zur Ebene
```csharp
layer.Add(feature);
```
Abschließend fügen wir das Feature zur KML‑Ebene hinzu, die die lineare Geometrie in die Ausgabedatei schreibt, wenn der `using`‑Block endet.

## Häufige Fallstricke & Tipps
- **Pfadtrennzeichen:** Verwenden Sie `Path.Combine` für plattformübergreifende Pfaderstellung.  
- **Große Geometrien:** Das Linearisieren sehr komplexer Formen kann viele Scheitelpunkte erzeugen; erwägen Sie die Verwendung von `Simplify()` nach der Linearisation, wenn Sie weniger Punkte benötigen.  
- **Treiberwahl:** Wenn Sie ein anderes Ausgabeformat benötigen, ersetzen Sie `Drivers.Kml` durch `Drivers.Shapefile`, `Drivers.GeoJson` usw. und passen Sie die Dateierweiterung entsprechend an.

## Fazit
In diesem Tutorial haben wir **wie man Geometrien linearisiert** mit Aspose.GIS für .NET behandelt, von der Einrichtung der Umgebung bis zum Schreiben des linearisierten Ergebnisses in eine KML‑Datei. Sie können diesen Workflow nun in Kartenanwendungen, Datenverarbeitungspipelines oder jedes GIS‑bezogene Projekt integrieren, das vereinfachte Geometrien erfordert.

## FAQ
### Q: Ist Aspose.GIS für .NET mit .NET Core kompatibel?
Ja, Aspose.GIS für .NET ist mit .NET Core kompatibel und ermöglicht den Bau plattformübergreifender Anwendungen.

### Q: Kann ich mit verschiedenen GIS‑Dateiformaten mit Aspose.GIS für .NET arbeiten?
Absolut! Aspose.GIS unterstützt verschiedene GIS‑Dateiformate, darunter KML, Shapefile, GeoJSON und mehr.

### Q: Bietet Aspose.GIS Unterstützung für räumliche Operationen und Analysen?
Ja, Aspose.GIS bietet eine breite Palette von räumlichen Operationen und Analysefunktionen zur Bewältigung komplexer geospatialer Aufgaben.

### Q: Gibt es eine kostenlose Testversion von Aspose.GIS für .NET?
Ja, Sie können eine kostenlose Testversion von der [Aspose-Website](https://releases.aspose.com/) herunterladen.

### Q: Wo finde ich Hilfe und Support für Aspose.GIS?
Sie können das [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) besuchen, um Unterstützung von der Community und dem Aspose‑Supportteam zu erhalten.

## Häufig gestellte Fragen (Zusätzlich)

**Q: Kann ich Geometrien linearisieren, die 3D‑ (Z‑)Koordinaten enthalten?**  
A: Ja, `ToLinearGeometry()` funktioniert mit 2D‑ und 3D‑Geometrien; die Z‑Werte werden in den resultierenden Liniensegmenten beibehalten.

**Q: Wie wirkt sich die Linearisation auf die Größe der Ausgabedatei aus?**  
A: Das Umwandeln von Kurven in viele kurze Liniensegmente kann die Dateigröße erhöhen. Verwenden Sie `Simplify()` nach der Linearisation, wenn die Dateigröße ein Problem darstellt.

**Q: Ist es möglich, die Segmentlänge beim Linearisieren zu steuern?**  
A: Die Standardmethode verwendet eine interne Toleranz. Für benutzerdefinierte Segmentierung können Sie Kurven manuell tessellieren, bevor Sie `ToLinearGeometry()` aufrufen.

---

**Zuletzt aktualisiert:** 2025-12-21  
**Getestet mit:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
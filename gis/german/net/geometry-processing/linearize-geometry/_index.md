---
date: 2026-04-09
description: Erfahren Sie, wie Sie Kurven in Linien (Geometrie linearieren) mit Aspose.GIS
  für .NET konvertieren, um eine effiziente geospatiale Verarbeitung und Analyse in
  Ihren .NET‑Anwendungen zu ermöglichen.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
linktitle: Geometrie linearisieren
second_title: Aspose.GIS .NET API
title: Wie man Kurven in Linien mit Aspose.GIS für .NET konvertiert
url: /de/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kurven in Linien umwandeln (Geometrie linearieren) mit Aspose.GIS für .NET

## Einleitung
Wenn Sie **Kurven in Linien umwandeln** für Kartierung, räumliche Analyse oder Daten‑Austausch‑Aufgaben benötigen, bietet Aspose.GIS für .NET eine saubere, programmatische Möglichkeit, dies zu tun. In diesem Tutorial führen wir Sie durch ein vollständiges, praxisnahes Beispiel, das zeigt, wie Sie eine komplexe Geometrie — mit Kurven und zusammengesetzten Formen — in eine einfache lineare Darstellung verwandeln, die mit jedem GIS‑System funktioniert.

## Schnelle Antworten
- **Was bedeutet „Kurven in Linien umwandeln“?** Es wandelt gekrümmte Geometrien in gerade Liniensegmente um.  
- **Warum Aspose.GIS wählen?** Die Bibliothek unterstützt Dutzende von GIS‑Formaten und erledigt die Geometrie‑Konvertierung ohne externe Werkzeuge.  
- **Was benötige ich vorher?** .NET Framework oder .NET Core, Visual Studio (oder jede C#‑IDE) und das Aspose.GIS‑NuGet‑Paket.  
- **Wie lange läuft das Beispiel?** Weniger als fünf Minuten, sobald die Bibliothek installiert ist.  
- **Kann ich in andere Formate exportieren?** Absolut — ersetzen Sie den KML‑Treiber durch Shapefile, GeoJSON usw.

## Was bedeutet Kurven in Linien umwandeln?
Das Umwandeln von Kurven in Linien (auch **Linearizing Geometry** genannt) zerlegt jede gekrümmte oder zusammengesetzte Form in eine Reihe von geraden Liniensegmenten, die als „lineare Geometrie“ bezeichnet werden. Diese Vereinfachung sorgt für schnellere Darstellung, verbessert die Kompatibilität mit älteren GIS‑Diensten und reduziert die Komplexität räumlicher Algorithmen.

## Warum Kurven in Linien umwandeln?
- **Leistung:** Lineare Geometrien rendern und werden schneller abgefragt.  
- **Kompatibilität:** Viele GIS‑Plattformen (insbesondere Legacy‑Dienste) akzeptieren nur lineare Features.  
- **Vereinfachung:** Ideal für Thumbnails, schnelle Vorschauen oder die Einspeisung von Daten in Algorithmen, die lineare Eingaben benötigen.

## Voraussetzungen
Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Aspose.GIS für .NET** – laden Sie es von der [Aspose.GIS-Website](https://releases.aspose.com/gis/net/) herunter.  
2. **.NET Framework** (oder .NET Core) auf Ihrer Entwicklungsmaschine installiert.  
3. **Visual Studio** (oder jede C#‑kompatible IDE) zum Schreiben und Ausführen des Beispiels.

## Namespaces importieren
Um die Funktionalität von Aspose.GIS zu nutzen, importieren Sie die erforderlichen Namespaces.

### Schritt 1: Kern‑Namespaces von Aspose.GIS
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Schritt 2: Treiber für das Zielformat
Für dieses Beispiel schreiben wir das Ergebnis in eine KML‑Datei:
```csharp
using Aspose.GIS.Kml;
```

## Schritt‑für‑Schritt‑Anleitung zum Umwandeln von Kurven in Linien
Im Folgenden finden Sie eine detaillierte Durchsicht jeder Codezeile, die erklärt, **wie Kurven in Linien umgewandelt** werden und warum jeder Schritt wichtig ist.

### Schritt 1: Ausgabepfad festlegen
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Ersetzen Sie `"Your Document Directory"` durch den Ordner, in dem Sie die KML‑Datei speichern möchten. Die Verwendung von `Path.Combine` wird für plattformübergreifende Kompatibilität empfohlen.

### Schritt 2: Einen Layer für die Ausgabedatei erstellen
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
Ein *Layer* ist ein Container für geografische Features. Hier erstellen wir einen neuen KML‑Layer, der unsere linearisierten Geometrien enthält.

### Schritt 3: Ein neues Feature erstellen
```csharp
var feature = layer.ConstructFeature();
```
Ein *Feature* repräsentiert ein einzelnes geografisches Objekt (Punkt, Linie, Polygon usw.). Wir werden unsere lineare Geometrie diesem Feature zuweisen.

### Schritt 4: Die ursprüngliche komplexe Geometrie definieren
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Wir erzeugen eine Geometrie aus einem Well‑Known‑Text‑String (WKT). Dieses Beispiel enthält einen `LineString`, einen `CompoundCurve` und einen `CircularString` — ideal, um **Kurven in Linien umwandeln** zu demonstrieren.

### Schritt 5: Kurven in Linien umwandeln
```csharp
var linear = geometry.ToLinearGeometry();
```
Die Methode `ToLinearGeometry()` wandelt alle Kurven in gerade Liniensegmente um und erzeugt eine *lineare* Version der ursprünglichen Geometrie.

### Schritt 6: Die lineare Geometrie dem Feature zuweisen
```csharp
feature.Geometry = linear;
```
Jetzt enthält das Feature die vereinfachte, lineare Geometrie.

### Schritt 7: Das Feature dem Layer hinzufügen
```csharp
layer.Add(feature);
```
Abschließend fügen wir das Feature dem KML‑Layer hinzu, der die lineare Geometrie beim Verlassen des `using`‑Blocks in die Ausgabedatei schreibt.

## Häufige Fallstricke & Pro‑Tipps
- **Pfadtrennzeichen:** Verwenden Sie `Path.Combine`, um Probleme unter Windows vs. Linux zu vermeiden.  
- **Sehr große Geometrien:** Das Linearizieren komplexer Formen kann Tausende von Scheitelpunkten erzeugen; erwägen Sie nach dem Linearizieren `Simplify()` aufzurufen, um die Punktzahl zu reduzieren.  
- **Treiberauswahl:** Wenn Sie ein anderes Ausgabeformat benötigen, ersetzen Sie `Drivers.Kml` durch `Drivers.Shapefile`, `Drivers.GeoJson` usw. und passen Sie die Dateierweiterung entsprechend an.  
- **Z‑Werte erhalten:** `ToLinearGeometry()` behält 3‑D‑(Z‑)Koordinaten bei, sodass Sie keine Höhendaten verlieren.

## Häufig gestellte Fragen (FAQ)

**F: Ist Aspose.GIS für .NET mit .NET Core kompatibel?**  
A: Ja, Aspose.GIS funktioniert mit .NET Core und ermöglicht plattformübergreifende Anwendungen.

**F: Kann ich mit Aspose.GIS für .NET verschiedene GIS‑Dateiformate verwenden?**  
A: Absolut! Die Bibliothek unterstützt KML, Shapefile, GeoJSON und viele weitere Formate.

**F: Bietet Aspose.GIS räumliche Operationen und Analysen?**  
A: Ja, sie stellt ein breites Spektrum an räumlichen Funktionen bereit, von Pufferungen bis zu räumlichen Joins.

**F: Gibt es eine kostenlose Testversion?**  
A: Ja, Sie können eine kostenlose Testversion von der [Aspose-Website](https://releases.aspose.com/) herunterladen.

**F: Wo bekomme ich Hilfe, wenn ich auf Probleme stoße?**  
A: Besuchen Sie das [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) für Community‑ und Support‑Unterstützung.

### Weitere häufige Fragen

**F: Kann ich Geometrien, die 3D‑(Z‑)Koordinaten enthalten, linearisieren?**  
A: Ja, `ToLinearGeometry()` funktioniert sowohl mit 2D‑ als auch mit 3D‑Geometrien; Z‑Werte werden beibehalten.

**F: Wie wirkt sich die Linearisation auf die Dateigröße aus?**  
A: Das Umwandeln von Kurven in viele kurze Liniensegmente kann die Dateigröße erhöhen. Verwenden Sie nach der Linearisation `Simplify()`, wenn die Größe ein Problem darstellt.

**F: Kann ich die Segmentlänge beim Umwandeln von Kurven in Linien steuern?**  
A: Die Standardmethode verwendet eine interne Toleranz. Für benutzerdefinierte Segmentierung können Sie Kurven vor dem Aufruf von `ToLinearGeometry()` manuell tessellieren.

## Fazit
In diesem Tutorial haben wir **wie man Kurven in Linien umwandelt** (Geometrie linearisiert) mit Aspose.GIS für .NET behandelt, von der Einrichtung bis zum Schreiben des linearisierten Ergebnisses in eine KML‑Datei. Sie können diesen Workflow nun in Mapping‑Anwendungen, Daten‑Verarbeitungspipelines oder jedes GIS‑bezogene Projekt einbetten, das vereinfachte Geometrien erfordert.

---

**Zuletzt aktualisiert:** 2026-04-09  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
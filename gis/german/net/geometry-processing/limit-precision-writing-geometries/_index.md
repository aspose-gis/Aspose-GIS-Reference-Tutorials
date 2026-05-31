---
date: 2026-05-31
description: Erfahren Sie, wie Sie die Präzision beim Schreiben von Geometrien mit
  Aspose.GIS für .NET begrenzen, die GeoJSON-Größe reduzieren und die Koordinatenkontrolle
  beibehalten.
keywords:
- how to limit precision
- reduce geojson size
- Aspose.GIS precision control
linktitle: Präzision beim Schreiben von Geometrien begrenzen
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  headline: How to Limit Precision Writing Geometries with Aspose.GIS
  type: TechArticle
- description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  name: How to Limit Precision Writing Geometries with Aspose.GIS
  steps:
  - name: Define Precision Options
    text: The `GeoJsonOptions` class lets you specify how many fractional digits to
      keep for X/Y and Z coordinates. `PrecisionModel` defines how coordinate values
      are rounded or kept exact during writing.
  - name: Set Output Path
    text: Specify where the resulting GeoJSON file will be saved. `VectorLayer` is
      Aspose.GIS's container for a collection of features that share the same schema;
      it writes to the path you provide using the options set earlier.
  - name: Create and Populate Geometry
    text: Open a new `VectorLayer` with the options defined above, construct a `Point`
      geometry, and add it to the layer. `Point` represents a single coordinate (X,
      Y, optional Z) in a spatial reference system. It is the simplest geometry type
      and is used here to demonstrate precision rounding.
  - name: Read and Verify Precision
    text: Open the file you just created and print the coordinates. You should see
      the X/Y values rounded to three decimal places while the Z value remains exact.
      When you read the file back, Aspose.GIS parses the rounded values directly,
      so the in‑memory `Point` reflects the precision you defined during writ
  type: HowTo
- questions:
  - answer: Yes, it supports **50+** formats—including Shapefile, GeoJSON, KML, GML,
      and CSV—allowing seamless conversion between them.
    question: Is Aspose.GIS for .NET compatible with other GIS formats?
  - answer: Absolutely. A free trial is available from the download page, giving you
      full access to all features for evaluation.
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: Temporary evaluation licenses can be generated via the Aspose license
      portal; they are valid for 30 days.
    question: How do I obtain a temporary license for testing?
  - answer: The Aspose.GIS forum and Stack Overflow tag `aspose-gis` are great places
      to ask questions and find community solutions.
    question: Where can I get help if I run into issues?
  - answer: Yes, Aspose.GIS is designed to handle everything from quick prototypes
      to high‑throughput server workloads, processing multi‑gigabyte datasets with
      low memory overhead.
    question: Does the library work for both small scripts and enterprise‑scale applications?
  type: FAQPage
second_title: Aspise.GIS .NET API
title: Wie man die Präzision beim Schreiben von Geometrien mit Aspose.GIS begrenzt
url: /de/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Präzision beim Schreiben von Geometrien mit Aspose.GIS begrenzt

Wenn Sie sich fragen **wie man die Präzision begrenzt** beim Schreiben von Geometrien in einer .NET GIS‑Anwendung, bietet Aspose.GIS für .NET eine unkomplizierte, leistungsstarke Methode zur Steuerung der Koordinatenrundung. In diesem Tutorial führen wir Sie durch den gesamten Prozess – von der Einrichtung der Umgebung bis zur Überprüfung, dass die Ausgabe die von Ihnen definierten Präzisionsregeln einhält.

## Schnelle Antworten
- **Was bedeutet „limit precision“?** Es rundet Koordinatenwerte auf eine definierte Anzahl von Nachkommastellen, während eine räumliche Datei geschrieben wird.  
- **Welches Format wird im Beispiel verwendet?** GeoJSON, aber dieselben Optionen gelten für andere unterstützte Formate.  
- **Benötige ich eine Lizenz, um dies auszuprobieren?** Eine kostenlose Testversion funktioniert für Entwicklung und Tests; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Kann ich die Z‑Koordinaten‑Präzision separat steuern?** Ja – verwenden Sie `ZPrecisionModel`, um exakte oder gerundete Werte festzulegen.

## Wie man die Präzision beim Schreiben von Geometrien begrenzt

Laden Sie Ihren GeoJSON‑Writer mit einem `GeoJsonOptions`‑Objekt, das die gewünschte X/Y‑ und Z‑Präzision angibt, schreiben Sie dann die Geometrie und lesen Sie sie wieder ein – dieser gesamte Arbeitsablauf passt in weniger als zehn Codezeilen und garantiert, dass alle Koordinaten exakt nach Ihren Vorgaben gerundet werden.

Die Begrenzung der Präzision ist wichtig, wenn Sie eine konsistente Koordinatenrepräsentation über verschiedene GIS‑Werkzeuge hinweg benötigen, die Dateigröße reduzieren oder Daten‑austausch‑Standards einhalten müssen. Im Folgenden definieren wir Präzisionsoptionen, schreiben eine Geometrie und lesen sie anschließend ein, um die Rundung zu bestätigen.

## Was ist Präzisionsbegrenzung?

Präzisionsbegrenzung ist der Prozess, bei dem der Nachkommanteil von Koordinatenwerten vor dem Persistieren der Geometrie in ein Dateiformat auf eine feste Anzahl von Stellen gerundet wird. Dies stellt sicher, dass jeder Verbraucher der Datei dieselben numerischen Werte sieht, was hilft, winzige Abweichungen zu vermeiden, die Topologie‑Fehler verursachen können.

## Warum Aspose.GIS für die Präzisionssteuerung verwenden?

Aspose.GIS unterstützt **50+** Eingabe‑ und Ausgabeformate – darunter GeoJSON, Shapefile, KML und GML – und kann Dateien mit **Hunderten von Tausenden von Features** verarbeiten, ohne den gesamten Datensatz in den Speicher zu laden. Seine integrierten Präzisionsmodelle ermöglichen das Runden von Koordinaten in einem einzigen Aufruf und beseitigen damit den Bedarf an manuellen Nachbearbeitungsskripten.

## Voraussetzungen

### 1. Download und Installation
Laden Sie das neueste Aspose.GIS‑Paket für .NET von der offiziellen Seite herunter: [download link](https://releases.aspose.com/gis/net/). Befolgen Sie die Installationsanleitung, um das NuGet‑Paket zu Ihrem Projekt hinzuzufügen.

### 2. Namespace‑Import
Fügen Sie die erforderlichen Namespaces hinzu, damit Sie auf die GIS‑Klassen und Hilfs‑Utilities zugreifen können.

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Präzisionsoptionen definieren
Die Klasse `GeoJsonOptions` ermöglicht es Ihnen, festzulegen, wie viele Nachkommastellen für X/Y‑ und Z‑Koordinaten beibehalten werden.

`PrecisionModel` definiert, wie Koordinatenwerte beim Schreiben gerundet oder exakt beibehalten werden.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Schritt 2: Ausgabepfad festlegen
Geben Sie an, wo die resultierende GeoJSON‑Datei gespeichert werden soll.

`VectorLayer` ist Aspose.GIS' Container für eine Sammlung von Features, die dasselbe Schema teilen; er schreibt in den von Ihnen angegebenen Pfad unter Verwendung der zuvor festgelegten Optionen.  

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### Schritt 3: Geometrie erstellen und befüllen
Öffnen Sie ein neues `VectorLayer` mit den oben definierten Optionen, erstellen Sie eine `Point`‑Geometrie und fügen Sie sie dem Layer hinzu.

`Point` stellt einen einzelnen Koordinatenpunkt (X, Y, optional Z) in einem räumlichen Referenzsystem dar. Es ist der einfachste Geometrietyp und wird hier verwendet, um die Präzisionsrundung zu demonstrieren.  

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### Schritt 4: Präzision lesen und überprüfen
Öffnen Sie die gerade erstellte Datei und geben Sie die Koordinaten aus. Sie sollten sehen, dass die X/Y‑Werte auf drei Dezimalstellen gerundet sind, während der Z‑Wert exakt bleibt.

Wenn Sie die Datei erneut lesen, parst Aspose.GIS die gerundeten Werte direkt, sodass das im Speicher befindliche `Point` die während des Schreibens definierte Präzision widerspiegelt.  

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    var point = new Point();
    point.X = 1.8888888;
    point.Y = 1.00123;
    point.Z = 1.123456789;

    Feature feature = layer.ConstructFeature();
    feature.Geometry = point;
    layer.Add(feature);
}
```

## Häufige Probleme & Tipps

- **Pfad‑Fehler:** Stellen Sie sicher, dass das Verzeichnis in `path` existiert, oder verwenden Sie `Path.Combine` mit `Environment.CurrentDirectory`, um einen sicheren Dateipfad zu erstellen.  
- **Präzision nicht angewendet:** Vergewissern Sie sich, dass Sie beim Erstellen des Layers das `GeoJsonOptions`‑Objekt übergeben; andernfalls wird die Standardpräzision (voller Double) verwendet.  
- **Große Datensätze:** Für Bulk‑Operationen sollten Sie in Erwägung ziehen, eine einzelne `VectorLayer`‑Instanz wiederzuverwenden und Features stapelweise hinzuzufügen, um die Leistung zu verbessern.

## Häufig gestellte Fragen

**Q: Ist Aspose.GIS für .NET mit anderen GIS‑Formaten kompatibel?**  
A: Ja, es unterstützt **50+** Formate – darunter Shapefile, GeoJSON, KML, GML und CSV – und ermöglicht nahtlose Konvertierungen zwischen ihnen.

**Q: Kann ich Aspose.GIS für .NET vor dem Kauf testen?**  
A: Absolut. Eine kostenlose Testversion ist auf der Download‑Seite verfügbar und bietet vollen Zugriff auf alle Funktionen für die Evaluierung.

**Q: Wie erhalte ich eine temporäre Lizenz für Tests?**  
A: Temporäre Evaluationslizenzen können über das Aspose‑Lizenzportal generiert werden; sie sind 30 Tage gültig.

**Q: Wo kann ich Hilfe erhalten, wenn ich auf Probleme stoße?**  
A: Das Aspose.GIS‑Forum und das Stack‑Overflow‑Tag `aspose-gis` sind gute Anlaufstellen, um Fragen zu stellen und Community‑Lösungen zu finden.

**Q: Funktioniert die Bibliothek sowohl für kleine Skripte als auch für Unternehmens‑Anwendungen?**  
A: Ja, Aspose.GIS ist so konzipiert, dass es alles von schnellen Prototypen bis zu hochdurchsatz‑Server‑Workloads bewältigt und Multi‑Gigabyte‑Datensätze mit geringem Speicherverbrauch verarbeitet.

---

**Zuletzt aktualisiert:** 2026-05-31  
**Getestet mit:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [Vektorlayer erstellen, Präzision begrenzen mit Aspose.GIS für .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Wie man GeoJSON konvertiert – Aspose.GIS für .NET](/gis/net/geo-data-conversion/)
- [Wie man Geometrie prüft mit Aspose.GIS für .NET](/gis/net/geometry-analysis/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

{{< /blocks/products/pf/main-wrap-class >}}
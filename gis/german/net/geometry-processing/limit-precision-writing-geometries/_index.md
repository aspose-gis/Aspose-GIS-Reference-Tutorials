---
date: 2025-12-20
description: Erfahren Sie, wie Sie die Präzision beim Schreiben von Geometrien mit
  Aspose.GIS für .NET begrenzen können. Diese Schritt‑für‑Schritt‑Anleitung hilft
  Ihnen, räumliche Daten mit genauer Koordinatenkontrolle zu verwalten.
linktitle: Limit Precision Writing Geometries
second_title: Aspose.GIS .NET API
title: Wie man die Präzision beim Schreiben von Geometrien mit Aspose.GIS begrenzt
url: /de/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Präzision beim Schreiben von Geometrien mit Aspose.GIS begrenzt

Wenn Sie sich fragen, **wie man die Präzision** beim Schreiben von Geometrien in einer .NET‑GIS‑Anwendung begrenzt, bietet Aspose.GIS für .NET eine unkomplizierte, leistungsstarke Methode zur Steuerung der Koordinatenrundung. In diesem Tutorial führen wir Sie durch den gesamten Prozess – von der Einrichtung der Umgebung bis zur Überprüfung, dass die Ausgabe die von Ihnen definierten Präzisionsregeln einhält.

## Schnelle Antworten
- **Was bedeutet „Präzision begrenzen“?** Es rundet Koordinatenwerte beim Schreiben einer räumlichen Datei auf eine definierte Anzahl von Nachkommastellen.  
- **Welches Format wird im Beispiel verwendet?** GeoJSON, aber dieselben Optionen gelten für andere unterstützte Formate.  
- **Benötige ich eine Lizenz, um dies auszuprobieren?** Eine kostenlose Testversion funktioniert für Entwicklung und Tests; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Kann ich die Präzision der Z‑Koordinate separat steuern?** Ja – verwenden Sie `ZPrecisionModel`, um exakte oder gerundete Werte festzulegen.

## Wie man die Präzision beim Schreiben von Geometrien begrenzt
Die Begrenzung der Präzision ist wichtig, wenn Sie eine konsistente Koordinatenrepräsentation über verschiedene GIS‑Werkzeuge hinweg benötigen, die Dateigröße reduzieren oder Daten­austausch‑Standards einhalten müssen. Im Folgenden definieren wir Präzisionsoptionen, schreiben eine Geometrie und lesen sie anschließend wieder ein, um die Rundung zu bestätigen.

## Voraussetzungen

### 1. Download und Installation
Laden Sie das neueste Aspose.GIS‑Paket für .NET von der offiziellen Seite herunter: [download link](https://releases.aspose.com/gis/net/). Befolgen Sie die Installationsanleitung, um das NuGet‑Paket zu Ihrem Projekt hinzuzufügen.

### 2. Namespace‑Import
Fügen Sie die erforderlichen Namespaces hinzu, damit Sie auf die GIS‑Klassen und Hilfs‑Utilities zugreifen können.

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

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Präzisionsoptionen definieren
Erstellen Sie eine Instanz von `GeoJsonOptions` und geben Sie Aspose.GIS an, wie viele Nachkommastellen Sie für X/Y‑ und Z‑Koordinaten wünschen.

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### Schritt 2: Ausgabepfad festlegen
Geben Sie an, wo die resultierende GeoJSON‑Datei gespeichert werden soll.

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### Schritt 3: Geometrie erstellen und befüllen
Öffnen Sie ein neues `VectorLayer` mit den oben definierten Optionen, erstellen Sie eine `Point`‑Geometrie und fügen Sie sie dem Layer hinzu.

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

### Schritt 4: Präzision lesen und überprüfen
Öffnen Sie die gerade erstellte Datei und geben Sie die Koordinaten aus. Sie sollten sehen, dass die X/Y‑Werte auf drei Dezimalstellen gerundet sind, während der Z‑Wert exakt bleibt.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

## Häufige Probleme & Tipps

- **Pfad‑Fehler:** Stellen Sie sicher, dass das Verzeichnis in `path` existiert, oder verwenden Sie `Path.Combine` mit `Environment.CurrentDirectory`, um einen sicheren Dateipfad zu erstellen.  
- **Präzision nicht angewendet:** Überprüfen Sie, dass Sie das `GeoJsonOptions`‑Objekt beim Erstellen des Layers übergeben; andernfalls wird die Standardpräzision (voller Double) verwendet.  
- **Große Datensätze:** Bei Massenoperationen sollten Sie in Erwägung ziehen, eine einzelne `VectorLayer`‑Instanz wiederzuverwenden und Features stapelweise hinzuzufügen, um die Leistung zu verbessern.

## Häufig gestellte Fragen

**F: Ist Aspose.GIS für .NET mit anderen GIS‑Formaten kompatibel?**  
A: Ja, es unterstützt Shapefile, GeoJSON, KML, GML und viele weitere, sodass eine nahtlose Konvertierung zwischen Formaten möglich ist.

**F: Kann ich Aspose.GIS für .NET vor dem Kauf testen?**  
A: Selbstverständlich. Eine kostenlose Testversion ist auf der Download‑Seite verfügbar und bietet vollen Zugriff auf alle Funktionen zur Evaluierung.

**F: Wie erhalte ich eine temporäre Lizenz für Tests?**  
A: Temporäre Evaluationslizenzen können über das Aspose‑Lizenz‑Portal erstellt werden; sie sind 30 Tage gültig.

**F: Wo kann ich Hilfe erhalten, wenn ich auf Probleme stoße?**  
A: Das Aspose.GIS‑Forum und der Stack‑Overflow‑Tag `aspose-gis` sind gute Anlaufstellen, um Fragen zu stellen und Community‑Lösungen zu finden.

**F: Funktioniert die Bibliothek sowohl für kleine Skripte als auch für Unternehmens‑Anwendungen?**  
A: Ja, Aspose.GIS ist darauf ausgelegt, alles von schnellen Prototypen bis hin zu hochdurchsatzfähigen Serveranwendungen zu bewältigen.

## Fazit
Wenn Sie die obigen Schritte befolgt haben, wissen Sie jetzt **wie man die Präzision** beim Schreiben von Geometrien mit Aspose.GIS für .NET begrenzt. Die Steuerung der Koordinatenrundung hilft, Ihre räumlichen Daten sauber, interoperabel und speichereffizient zu halten – zentrale Vorteile für jedes GIS‑zentrierte Projekt.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2025-12-20  
**Getestet mit:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose
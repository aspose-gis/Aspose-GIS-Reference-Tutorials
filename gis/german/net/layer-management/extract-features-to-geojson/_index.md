---
date: 2026-01-13
description: Erfahren Sie, wie Sie Shapefile mit Aspose.GIS für .NET in GeoJSON konvertieren.
  Der Leitfaden behandelt außerdem das Kopieren von Attributen zwischen Ebenen und
  das Erzeugen einer GeoJSON‑Datei mit C#.
linktitle: Extract Features to GeoJSON
second_title: Aspose.GIS .NET API
title: Wie man Shapefile in GeoJSON mit Aspose.GIS für .NET konvertiert
url: /de/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Shapefile in GeoJSON konvertieren mit Aspose.GIS für .NET

## Einleitung
In diesem umfassenden, Schritt‑für‑Schritt‑Tutorial lernen Sie **wie man shapefile in geojson konvertiert** mit der leistungsstarken Aspose.GIS‑Bibliothek für .NET. Egal, ob Sie einen Mapping‑Webservice erstellen, Daten für eine mobile GIS‑App vorbereiten oder einfach Daten zwischen Formaten austauschen müssen, dieser Leitfaden zeigt Ihnen genau, was zu tun ist, warum jeder Schritt wichtig ist und wie Sie häufige Fallstricke vermeiden können.

## Schnelle Antworten
- **Worum geht es in diesem Tutorial?** Konvertierung eines Shapefiles in eine GeoJSON‑Datei, Kopieren von Attributen zwischen Layern und Erzeugen der Ausgabe mit C#.
- **Welche Bibliothek wird benötigt?** Aspose.GIS für .NET.
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder vollständige Lizenz erforderlich; eine kostenlose Testversion reicht für die Evaluierung.
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für eine einfache Konvertierung.
- **Kann ich das auf .NET Core/.NET 6 ausführen?** Ja – der Code funktioniert auf allen unterstützten .NET‑Versionen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Aspose.GIS für .NET: Stellen Sie sicher, dass die Bibliothek installiert ist. Falls nicht, können Sie sie von der [Aspose.GIS für .NET Seite](https://releases.aspose.com/gis/net/) herunterladen.
- Shapefile‑Daten: Haben Sie ein Shapefile bereit für die Eingabe. Wenn Sie Beispieldaten benötigen, finden Sie diese in der [Aspose.GIS Dokumentation](https://reference.aspose.com/gis/net/).
- .NET‑Umgebung: Richten Sie eine .NET‑Umgebung ein, um den bereitgestellten Code auszuführen.
- Dokumentenverzeichnis: Definieren Sie den Pfad zu Ihrem Dokumentenverzeichnis im Code‑Snippet.

Jetzt, da alles bereit ist, lassen Sie uns mit der Konvertierung von shapefile zu geojson beginnen!

## Was bedeutet „convert shapefile to geojson“?
Das Konvertieren eines Shapefiles in GeoJSON bedeutet, Vektor‑Features aus dem klassischen ESRI‑Shapefile‑Format zu lesen und sie als modernes, web‑freundliches GeoJSON‑Dokument zu schreiben. GeoJSON wird häufig in JavaScript‑Mapping‑Bibliotheken (Leaflet, Mapbox GL) und APIs verwendet, wodurch die Konvertierung eine häufige Aufgabe in der GIS‑Entwicklung ist.

## Warum Aspose.GIS für diese Konvertierung verwenden?
Aspose.GIS abstrahiert die Low‑Level‑Details von Dateiformaten, ermöglicht das mühelose Kopieren von Attributtabellen und bietet eine saubere, objektorientierte API, die auf .NET Framework, .NET Core und .NET 5/6 funktioniert. Das bedeutet, Sie können sich auf die Geschäftslogik konzentrieren, anstatt Binärdateien zu parsen.

## Namespaces importieren
Zuerst fügen Sie die erforderlichen Namespaces in Ihrem Code ein:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Diese Namespaces sind essenziell für die Arbeit mit den Aspose.GIS‑Funktionalitäten.

## Wie man Shapefile in GeoJSON konvertiert
Unten finden Sie den vollständigen Workflow, aufgeteilt in klare Schritte. Jeder Schritt enthält eine kurze Erklärung, gefolgt vom genauen Code‑Block, den Sie in Ihr Projekt kopieren müssen.

### Schritt 1: Eingabe‑Shapefile öffnen
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```
Öffnen Sie das Eingabe‑Shapefile mit der Methode `VectorLayer.Open`. Dadurch erhalten Sie eine aufzählbare Sammlung von `Feature`‑Objekten.

### Schritt 2: Ausgabe‑GeoJSON erstellen
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```
Erstellen Sie die Ausgabedatei mit der Methode `VectorLayer.Create` und geben Sie den Treiber `Drivers.GeoJson` an.

### Schritt 3: Attribute zwischen Layern kopieren
```csharp
outputLayer.CopyAttributes(inputLayer);
```
Diese einzelne Zeile kopiert das Attributschema (Feldnamen, Typen) vom Quell‑Shapefile zum neuen GeoJSON‑Layer – genau das, was das sekundäre Schlüsselwort *copy attributes between layers* beschreibt.

### Schritt 4: Features verarbeiten
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```
Iterieren Sie über jedes Feature im Shapefile, um beliebige benutzerdefinierte Logik anzuwenden, bevor Sie es schreiben.

### Schritt 5: Features nach Datum filtern
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
In diesem Beispiel überspringen wir Datensätze, deren Feld `dob` (Geburtsdatum) fehlt oder vor dem 1. Jan 1982 liegt. Passen Sie den Filter gerne an Ihre eigenen Datenanforderungen an.

### Schritt 6: Neues Feature erstellen (C# GeoJSON‑Datei generieren)
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Hier erstellen wir ein neues `Feature` für den GeoJSON‑Layer, kopieren die Geometrie und Attributwerte und fügen es der Ausgabe hinzu. Das ist der Kern von *c# generate geojson file*.

Herzlichen Glückwunsch! Sie haben erfolgreich **shapefile in geojson konvertiert** und dabei gelernt, wie man Attribute zwischen Layern kopiert.

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|---------|-------------------|--------|
| Ausgabedatei ist leer | `CopyAttributes` wurde aufgerufen, nachdem der Ausgabelayer geschlossen wurde | Stellen Sie sicher, dass der `using`‑Block für `outputLayer` offen bleibt, bis alle Features hinzugefügt wurden. |
| Datumsfilter entfernt alle Datensätze | Falscher Feldname oder unerwartetes Datumsformat | Überprüfen Sie den Attributnamen (`dob`) und verwenden Sie `GetValue<string>`, falls Daten als Zeichenketten gespeichert sind. |
| Lizenzausnahme | Ausführung ohne gültige Aspose.GIS‑Lizenz in der Produktion | Wenden Sie eine temporäre oder vollständige Lizenz an, wie in der Aspose‑Dokumentation beschrieben. |

## Häufig gestellte Fragen
**Q: Wo finde ich weitere Dokumentation?**  
A: Besuchen Sie die [Aspose.GIS Dokumentation](https://reference.aspose.com/gis/net/) für ausführliche Informationen.

**Q: Wie kann ich eine temporäre Lizenz erhalten?**  
A: Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erhalten.

**Q: Wo kann ich Unterstützung erhalten?**  
A: Treten Sie dem [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) für Community‑Support und Diskussionen bei.

**Q: Gibt es eine kostenlose Testversion?**  
A: Ja, Sie finden die kostenlose Testversion [hier](https://releases.aspose.com/).

**Q: Wo kann ich Aspose.GIS für .NET erwerben?**  
A: Sie können das Produkt [hier](https://purchase.aspose.com/buy) kaufen.

## Fazit
In diesem Tutorial haben wir den vollständigen Prozess des **convert shapefile to geojson** mit Aspose.GIS für .NET untersucht, gezeigt, wie man Attribute zwischen Layern kopiert, und eine saubere Methode zum *c# generate geojson file* demonstriert. Experimentieren Sie mit verschiedenen Filtern, größeren Datensätzen oder zusätzlichen Geometrie‑Transformationen, um die Möglichkeiten der Bibliothek voll auszuschöpfen.

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS for .NET (latest stable release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
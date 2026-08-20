---
date: 2026-07-05
description: Erfahren Sie, wie Sie Shapefile mit Aspose.GIS für .NET in GeoJSON konvertieren.
  Der Leitfaden behandelt außerdem das Kopieren von Attributen zwischen Ebenen und
  das Erzeugen einer GeoJSON-Datei mit C#.
keywords:
- convert shapefile to geojson
- export shapefile as geojson
- aspose gis conversion
- read shapefile c#
- write geojson c#
linktitle: Features nach GeoJSON extrahieren
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  headline: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  name: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  steps:
  - name: Open Input Shapefile
    text: The `VectorLayer.Open` method reads a Shapefile and returns an enumerable
      collection of `Feature` objects that you can iterate over.
  - name: Create Output GeoJSON
    text: '`VectorLayer.Create` with the `Drivers.GeoJson` driver creates an empty
      GeoJSON file ready to receive features.'
  - name: Copy Attributes Between Layers
    text: '`CopyAttributes` copies the attribute schema (field names and data types)
      from the source Shapefile to the new GeoJSON layer in a single call.'
  - name: Process Features
    text: Iterate through each feature in the Shapefile so you can apply any custom
      logic before writing it out.
  - name: Filter Features by Date
    text: In this example we skip records whose `dob` (date of birth) field is missing
      or earlier than 1 Jan 1982. Adjust the filter to match your own data requirements.
  - name: Construct a New Feature (C# Generate GeoJSON File)
    text: A `Feature` represents a single spatial element containing geometry and
      attribute data. Here we build a new `Feature` for the GeoJSON layer, copy the
      geometry and attribute values, and add it to the output. This is the core of
      *c# generate geojson file*. Congratulations! You’ve successfully **conver
  type: HowTo
- questions:
  - answer: Visit the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/)
      for in‑depth information.
    question: Where can I find more documentation?
  - answer: You can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license?
  - answer: Join the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I seek support?
  - answer: Yes, you can find the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can buy the product [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Shapefile in GeoJSON konvertieren mit Aspose.GIS für .NET
url: /de/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Shapefile in GeoJSON konvertieren mit Aspose.GIS für .NET

## Einleitung
In diesem umfassenden, Schritt‑für‑Schritt‑Tutorial lernen Sie **wie man Shapefile in GeoJSON konvertiert** mit der leistungsstarken Aspose.GIS‑Bibliothek für .NET. Egal, ob Sie einen Mapping‑Webservice erstellen, Daten für eine mobile GIS‑App vorbereiten oder einfach Daten zwischen Formaten austauschen müssen, dieser Leitfaden zeigt Ihnen genau, was zu tun ist, warum jeder Schritt wichtig ist und wie Sie häufige Fallstricke vermeiden können.

## Schnelle Antworten
- **Worum geht es in diesem Tutorial?** Konvertieren einer Shapefile in eine GeoJSON‑Datei, Kopieren von Attributen zwischen Layern und Erzeugen der Ausgabe mit C#.
- **Welche Bibliothek wird benötigt?** Aspose.GIS für .NET.
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder vollständige Lizenz erforderlich; eine kostenlose Testversion funktioniert für Evaluierungszwecke.
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für eine grundlegende Konvertierung.
- **Kann ich das auf .NET Core/.NET 6 ausführen?** Ja – der Code funktioniert auf allen unterstützten .NET‑Versionen.

## Was bedeutet das Konvertieren von Shapefile zu GeoJSON?
Das Konvertieren einer Shapefile in GeoJSON bedeutet, Vektor‑Features aus dem klassischen ESRI‑Shapefile‑Format zu lesen und sie als modernes, web‑freundliches GeoJSON‑Dokument zu schreiben. Diese Transformation ermöglicht es, GIS‑Daten direkt in JavaScript‑Mapping‑Bibliotheken wie Leaflet oder Mapbox GL einzuspeisen und vereinfacht den Datenaustausch zwischen Desktop‑GIS‑Tools und Web‑APIs.

## Warum Aspose.GIS für diese Konvertierung verwenden?
Aspose.GIS abstrahiert die Low‑Level‑Binär‑Parsen, unterstützt über 50 Eingabe‑ und Ausgabeformate und kann mehrhundertseitige Datensätze verarbeiten, ohne die gesamte Datei in den Speicher zu laden. Die Bibliothek bietet zudem eine saubere, objektorientierte API, die auf .NET Framework, .NET Core und .NET 5/6 funktioniert, sodass Sie Zeit für die Geschäftslogik statt für Format‑Eigenheiten aufwenden.

## Voraussetzungen
- Aspose.GIS für .NET: Stellen Sie sicher, dass die Bibliothek installiert ist. Falls nicht, können Sie sie von der [Aspose.GIS für .NET‑Seite](https://releases.aspose.com/gis/net/) herunterladen.
- Shapefile‑Daten: Haben Sie eine Shapefile bereit für die Eingabe. Wenn Sie Beispieldaten benötigen, finden Sie diese in der [Aspose.GIS‑Dokumentation](https://reference.aspose.com/gis/net/).
- .NET‑Umgebung: Richten Sie eine .NET‑Umgebung ein, um den bereitgestellten Code auszuführen.
- Dokumentenverzeichnis: Definieren Sie den Pfad zu Ihrem Dokumentenverzeichnis im Code‑Snippet.

Jetzt, da Sie alles bereit haben, lassen Sie uns mit der Konvertierung von Shapefile zu GeoJSON beginnen!

## Wie man Shapefile in GeoJSON konvertiert
Laden Sie die Quell‑Shapefile, erstellen Sie einen Ziel‑GeoJSON‑Layer, kopieren Sie das Attribut‑Schema, filtern Sie Datensätze und schreiben Sie die Ergebnisse – alles in wenigen prägnanten Schritten. Der komplette Workflow passt bequem in einen einzelnen `using`‑Block, wodurch Ressourcen automatisch freigegeben werden.

### Schritt 1: Eingabe‑Shapefile öffnen
Die Methode `VectorLayer.Open` liest eine Shapefile und gibt eine aufzählbare Sammlung von `Feature`‑Objekten zurück, über die Sie iterieren können.

```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```

### Schritt 2: Ausgabe‑GeoJSON erstellen
`VectorLayer.Create` mit dem Treiber `Drivers.GeoJson` erstellt eine leere GeoJSON‑Datei, die bereit ist, Features zu empfangen.

```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```

### Schritt 3: Attribute zwischen Layern kopieren
`CopyAttributes` kopiert das Attribut‑Schema (Feldnamen und Datentypen) von der Quell‑Shapefile in den neuen GeoJSON‑Layer in einem einzigen Aufruf.

```csharp
outputLayer.CopyAttributes(inputLayer);
```

### Schritt 4: Features verarbeiten
Iterieren Sie über jedes Feature in der Shapefile, um beliebige benutzerdefinierte Logik anzuwenden, bevor Sie es schreiben.

```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```

### Schritt 5: Features nach Datum filtern
In diesem Beispiel überspringen wir Datensätze, deren Feld `dob` (Geburtsdatum) fehlt oder vor dem 1. Jan 1982 liegt. Passen Sie den Filter an Ihre eigenen Datenanforderungen an.

```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```

### Schritt 6: Neues Feature erstellen (C# GeoJSON‑Datei erzeugen)
Ein `Feature` repräsentiert ein einzelnes räumliches Element, das Geometrie‑ und Attributdaten enthält.  
Hier erstellen wir ein neues `Feature` für den GeoJSON‑Layer, kopieren die Geometrie und Attributwerte und fügen es der Ausgabe hinzu. Dies ist der Kern von *c# generate geojson file*.

```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```

Herzlichen Glückwunsch! Sie haben erfolgreich **Shapefile in GeoJSON konvertiert** und dabei gelernt, **Attribute zwischen Layern zu kopieren**.

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|---------|-------------------|--------|
| Ausgabedatei ist leer | `CopyAttributes` wurde aufgerufen, nachdem der Ausgabelayer geschlossen wurde | Stellen Sie sicher, dass der `using`‑Block für `outputLayer` geöffnet bleibt, bis alle Features hinzugefügt wurden. |
| Datumsfilter entfernt alle Datensätze | Falscher Feldname oder unerwartetes Datumsformat | Überprüfen Sie den Attributnamen (`dob`) und verwenden Sie `GetValue<string>`, falls Daten als Zeichenketten gespeichert sind. |
| Lizenzausnahme | Ausführung ohne gültige Aspose.GIS‑Lizenz in der Produktion | Wenden Sie eine temporäre oder vollständige Lizenz an, wie in der Aspose‑Dokumentation beschrieben. |

## Häufig gestellte Fragen
**F: Wo finde ich weitere Dokumentation?**  
A: Besuchen Sie die [Aspose.GIS‑Dokumentation](https://reference.aspose.com/gis/net/) für ausführliche Informationen.

**F: Wie kann ich eine temporäre Lizenz erhalten?**  
A: Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erhalten.

**F: Wo kann ich Unterstützung erhalten?**  
A: Treten Sie dem [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) für Community‑Support und Diskussionen bei.

**F: Gibt es eine kostenlose Testversion?**  
A: Ja, Sie finden die kostenlose Testversion [hier](https://releases.aspose.com/).

**F: Wo kann ich Aspose.GIS für .NET erwerben?**  
A: Sie können das Produkt [hier](https://purchase.aspose.com/buy) kaufen.

## Fazit
In diesem Tutorial haben wir den vollständigen Prozess des **Shapefile in GeoJSON konvertierens** mit Aspose.GIS für .NET untersucht, gezeigt, wie man **Attribute zwischen Layern kopiert**, und eine saubere Methode zum *c# generate geojson file* vorgestellt. Experimentieren Sie mit verschiedenen Filtern, größeren Datensätzen oder zusätzlichen Geometrie‑Transformationen, um die Möglichkeiten der Bibliothek voll auszuschöpfen.

**Zuletzt aktualisiert:** 2026-07-05  
**Getestet mit:** Aspose.GIS für .NET (neueste stabile Version)  
**Autor:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Verwandte Tutorials

- [Wie man GeoJSON in File GDB mit Aspose.GIS für .NET konvertiert](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Wie man GeoJSON aus einem Stream mit Aspose.GIS für .NET liest](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Wie man GeoJSON in TopoJSON mit Aspose.GIS konvertiert](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
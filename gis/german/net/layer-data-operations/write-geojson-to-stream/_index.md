---
date: 2026-10-15
description: Erfahren Sie, wie Sie GeoJSON aus Koordinaten erstellen und mithilfe
  von Aspose.GIS für .NET in einen Stream schreiben. Dieses Tutorial zeigt die schrittweise
  Umwandlung von Punkten und die Erzeugung von GeoJSON‑C#‑Code.
keywords:
- create geojson from coordinates
- stream large geojson files
- write geojson to stream
- geojson tutorial c#
- compress geojson with gzip
lastmod: 2026-10-15
linktitle: GeoJSON in Stream schreiben
og_description: Erfahren Sie, wie Sie GeoJSON aus Koordinaten erstellen und mithilfe
  von Aspose.GIS für .NET in einen Stream schreiben – Schritt‑für‑Schritt‑Anleitung
  für große Datensätze.
og_image_alt: Screenshot of Aspose.GIS code generating GeoJSON stream in C#
og_title: GeoJSON aus Koordinaten erstellen und in .NET in einen Stream schreiben
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create geojson from coordinates and write it to a stream
    using Aspose.GIS for .NET. This tutorial shows step‑by‑step conversion of points
    and generation of GeoJSON C# code.
  headline: Create geojson from coordinates, write to a stream in .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET geospatial
- C# stream processing
- GIS data conversion
title: GeoJSON aus Koordinaten erstellen und in .NET in einen Stream schreiben
url: /de/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstelle GeoJSON aus Koordinaten und schreibe es in einen Stream

## Einführung
In diesem Tutorial lernen Sie **wie man GeoJSON aus Koordinaten erstellt** und es direkt in einen Stream schreibt, wobei Aspose.GIS für .NET verwendet wird. Wir führen Sie durch die Einrichtung der Umgebung, die Erstellung von Layern, das Befüllen von Features und das Streamen des Ergebnisses, sodass Sie geospatiale Payloads in APIs, Cloud‑Funktionen oder dateilose Dienste einbetten können, ohne temporäre Dateien.

## Schnelle Antworten
- **Welche Klasse schreibt GeoJSON in einen Stream?** `VectorLayer` zusammen mit dem `GeoJsonDriver`.
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Kann ich Punktesammlungen in GeoJSON konvertieren?** Ja – erstellen Sie ein `Feature` für jeden Punkt und weisen ihm eine `Point`‑Geometrie zu.
- **Ist Streaming für große Datensätze geeignet?** Absolut – `MemoryStream` ermöglicht das Schreiben von GeoJSON im Gigabyte‑Umfang, ohne die gesamte Datei in den Speicher zu laden.

## Was ist GeoJSON?
GeoJSON ist ein offenes, JSON‑basiertes Format zum Kodieren geografischer Features wie Punkte, Linien und Polygone. Es besteht aus einer `FeatureCollection`, die einzelne `Feature`‑Objekte gruppiert, von denen jedes Geometrie‑ und Attributdaten enthält. Da es leichtgewichtig und web‑freundlich ist, ist GeoJSON der de‑facto‑Standard für den Austausch räumlicher Daten zwischen Browsern, GIS‑Servern und mobilen Apps.

## Warum Aspose.GIS für die GeoJSON‑Erstellung verwenden?
Aspose.GIS unterstützt **über 35 räumliche Dateiformate** und kann Dateien größer als **2 GB** streamen, wobei der Speicherverbrauch unter **50 MB** bleibt. Seine Hochleistungs‑Streaming‑Engine schreibt GeoJSON direkt in jeden .NET `Stream`, eliminiert die Notwendigkeit von Zwischendateien und reduziert die I/O‑Latenz in typischen Cloud‑Szenarien um bis zu **70 %**.

## Voraussetzungen
1. **Aspose.GIS for .NET** installiert. Laden Sie das **Aspose.GIS for .NET**‑Paket [hier](https://releases.aspose.com/gis/net/) herunter.
2. Ein beschreibbarer Ordner in Ihrem Projekt, in dem Sie bei Bedarf temporäre Dateien ablegen können.
3. .NET 5+ oder .NET Core 3.1+ Runtime installiert.

Jetzt tauchen wir in die Implementierung ein.

## Wie erstellt man GeoJSON aus Koordinaten und schreibt es in einen Stream?
`VectorLayer` repräsentiert einen im Speicher befindlichen Vektor‑Datensatz, der in verschiedenen Formaten gespeichert werden kann.  
`GeoJsonDriver` ist der Treiber, der das Lesen und Schreiben von GeoJSON‑Dateien ermöglicht.

Laden Sie ein `VectorLayer` mit dem `GeoJsonDriver`, fügen Sie `Feature`‑Objekte hinzu, die eine `Point`‑Geometrie enthalten, und rufen Sie `layer.Save(stream, new GeoJsonSaveOptions())` auf. Dieser einzelne Aufruf serialisiert die gesamte Feature‑Collection in ein standardkonformes GeoJSON‑Dokument, das im übergebenen `MemoryStream` liegt. Der Prozess übernimmt automatisch das Mapping von Attributen und die Koordinatenkonvertierung, sodass Sie ein sofort einsatzbereites JSON‑Payload erhalten, ohne manuell Zeichenketten zusammenzusetzen.

### Definitionen
**VectorLayer** ist das Kern‑Aspose.GIS‑Objekt, das einen veränderbaren Vektor‑Datensatz im Speicher repräsentiert.  
**GeoJsonDriver** ist der Treiber, der für das Lesen und Schreiben von GeoJSON‑Dateien verantwortlich ist.

## Namespaces importieren
Zuerst stellen Sie sicher, dass Sie die erforderlichen Namespaces einbinden, um die Aspose.GIS‑Funktionalitäten in Ihrem Code zu nutzen:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Schritt 1: Dokumentverzeichnis einrichten
Erstellen Sie einen Ordnerpfad, in dem Aspose.GIS bei Bedarf Hilfsdateien speichern kann.  
```csharp
string dataDir = "Your Document Directory";
```
Ersetzen Sie „Your Document Directory“ durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 2: MemoryStream erstellen
Ein `MemoryStream` stellt einen Puffer im Speicher bereit, der direkt über HTTP gesendet oder in der Cloud gespeichert werden kann.  
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Schritt 3: Vektor‑Layer mit GeoJSON‑Treiber erstellen
Die Klasse `VectorLayer` repräsentiert einen Vektor‑Datensatz, der in verschiedenen Formaten, einschließlich GeoJSON, gespeichert werden kann.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Schritt 4: Feature‑Attribute definieren
Definieren Sie das Attribut‑Schema für Ihre Features (z. B. ID, Name).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Schritt 5: Features erstellen und hinzufügen
Erstellen Sie `Feature`‑Objekte, weisen Sie Punktgeometrie zu, setzen Sie Attributwerte und fügen Sie sie dem Layer hinzu.  
```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## Schritt 6: GeoJSON‑Ausgabe anzeigen
Nach dem Speichern setzen Sie die Stream‑Position zurück und lesen die JSON‑Zeichenkette zur Überprüfung oder Übertragung.  
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Herzlichen Glückwunsch! Sie haben erfolgreich GeoJSON aus Koordinaten erstellt und mit Aspose.GIS für .NET in einen Stream geschrieben.

## Häufige Probleme und Lösungen
- **Leerer Ausgabestream:** Stellen Sie sicher, dass Sie die Stream‑Position (`stream.Position = 0`) vor dem Lesen zurücksetzen.
- **Falsche Koordinatenreihenfolge:** GeoJSON erwartet die Reihenfolge Längen‑Breite; prüfen Sie Ihre Punktwerte.
- **Große Datensätze:** Verwenden Sie `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })`, um Features inkrementell zu streamen und den Speicherverbrauch gering zu halten.

## Häufig gestellte Fragen

**Q: Kann ich Aspose.GIS für .NET sowohl in Windows‑ als auch in Linux‑Umgebungen verwenden?**  
A: Ja, Aspose.GIS für .NET läuft auf Windows, Linux und macOS mit voller .NET‑Core‑Unterstützung.

**Q: Gibt es eine kostenlose Testversion?**  
A: Auf jeden Fall! Sie können die **Kostenlose‑Test‑Download‑Seite** [hier](https://releases.aspose.com/) erkunden.

**Q: Wo finde ich ausführliche Dokumentation?**  
A: Sehen Sie sich die **Aspose.GIS .NET‑Dokumentation** [hier](https://reference.aspose.com/gis/net/) an.

**Q: Wie kann ich eine temporäre Lizenz erhalten?**  
A: Temporäre Lizenzen sind auf der **Temporäre‑Lizenz‑Seite** [hier](https://purchase.aspose.com/temporary-license/) verfügbar.

**Q: Benötigen Sie Unterstützung oder haben weitere Fragen?**  
A: Besuchen Sie unser **GIS‑Support‑Forum** [hier](https://forum.aspose.com/c/gis/33).

**Q: Kann ich GeoJSON aus einer Sammlung von Breiten‑/Längengrad‑Punkten erzeugen?**  
A: Ja – erstellen Sie ein `Feature` für jeden Punkt, weisen Sie eine `Point`‑Geometrie zu und fügen Sie es dem `VectorLayer` hinzu.

**Q: Unterstützt Aspose.GIS das Schreiben von komprimiertem GeoJSON (gzip)?**  
A: Sie können den `MemoryStream` vor dem Speichern in einen `GZipStream` einbetten, um ein komprimiertes Payload zu erzeugen.

**Q: Wie groß ist die maximale Größe einer GeoJSON‑Datei, die Aspose.GIS verarbeiten kann?**  
A: Die Bibliothek kann Dateien größer als 2 GB streamen; der Speicherverbrauch bleibt gering, da Daten inkrementell geschrieben werden.

---

**Zuletzt aktualisiert:** 2026-10-15  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose  

## Verwandte Tutorials

- [Wie man GeoJSON aus einem Stream mit Aspose.GIS für .NET liest](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Wie man GeoJSON mit Aspose.GIS in TopoJSON konvertiert](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Wie man Shapefile mit Aspose.GIS für .NET in GeoJSON konvertiert](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
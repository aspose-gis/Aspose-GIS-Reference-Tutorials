---
date: 2026-05-21
description: Erfahren Sie, wie Sie GeoJSON in einen Stream schreiben, indem Sie Aspose.GIS
  für .NET verwenden. Dieses GeoJSON‑Tutorial für .NET zeigt die schrittweise Konvertierung
  von Punkten und die Erzeugung von GeoJSON‑C#‑Code.
keywords:
- how to write geojson
- convert points geojson
- geojson tutorial .net
- generate geojson c#
linktitle: GeoJSON in Stream schreiben
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to write GeoJSON to stream using Aspose.GIS for .NET. This
    geojson tutorial .net shows step‑by‑step conversion of points and generation of
    GeoJSON C# code.
  headline: How to Write GeoJSON to Stream with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Wie man GeoJSON in einen Stream schreibt mit Aspose.GIS für .NET
url: /de/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GeoJSON in Stream schreiben

## Einführung
In diesem Tutorial lernen Sie **wie man GeoJSON in einen Stream schreibt** in einer .NET-Anwendung mit Aspose.GIS. Wir gehen jeden Schritt durch, von der Einrichtung der Umgebung bis zur Ausgabe eines gültigen GeoJSON-Dokuments, damit Sie Geodaten nahtlos in Ihre Dienste integrieren können.

## Schnelle Antworten
- **Was ist die primäre Klasse für die GeoJSON-Ausgabe?** `VectorLayer` mit dem `GeoJsonDriver`.
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.
- **Welche .NET-Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Kann ich Punktesammlungen in GeoJSON konvertieren?** Ja – verwenden Sie die Klasse `Feature` und definieren Sie Punktgeometrie.
- **Wird Streaming für große Datensätze unterstützt?** Absolut; `MemoryStream` ermöglicht das Schreiben ohne Zwischendateien.

## Was ist GeoJSON?
GeoJSON ist ein offenes Standardformat zur Kodierung verschiedener geografischer Datenstrukturen mit JSON. Es definiert Objekte wie FeatureCollection, Feature und Geometrietypen (Point, LineString, Polygon). Diese leichte, web‑freundliche Darstellung ermöglicht einen einfachen Austausch und die Visualisierung von räumlichen Daten über viele Plattformen und Programmiersprachen hinweg.

## Warum Aspose.GIS für die GeoJSON-Erstellung verwenden?
Aspose.GIS unterstützt mehr als 30 räumliche Dateiformate und kann Dateien größer als 2 GB verarbeiten, ohne das gesamte Dokument in den Speicher zu laden. Seine Hochleistungs‑Streaming‑Engine schreibt GeoJSON direkt in Streams und reduziert den I/O‑Overhead. Das macht es ideal für Unternehmens‑Skalige Geodaten‑Workloads, Cloud‑Dienste und Echtzeitanwendungen.

## Voraussetzungen
Bevor wir mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Aspose.GIS für .NET Bibliothek: Stellen Sie sicher, dass die Aspose.GIS für .NET Bibliothek installiert ist. Sie können sie [hier](https://releases.aspose.com/gis/net/) herunterladen.
2. Dokumentverzeichnis: Richten Sie ein Dokumentverzeichnis in Ihrem Projekt ein und notieren Sie dessen Pfad.

Jetzt starten wir mit dem Tutorial!

## Wie schreibe ich GeoJSON in einen Stream?
VectorLayer repräsentiert einen Vektor‑Datensatz, der in verschiedenen Formaten, einschließlich GeoJSON, gespeichert werden kann.  
GeoJsonDriver ist der Treiber, den Aspose.GIS zum Lesen und Schreiben von GeoJSON-Dateien verwendet.  
`layer.Save` schreibt den Layer-Inhalt in den bereitgestellten Stream unter Verwendung der angegebenen Speicheroptionen.  

Laden Sie ein `VectorLayer` mit dem `GeoJsonDriver`, fügen Sie Features hinzu, die Punktgeometrie enthalten, und rufen Sie dann `layer.Save(stream, new GeoJsonSaveOptions())` auf. Dies schreibt ein vollständiges, den Standards entsprechendes GeoJSON-Dokument direkt in den bereitgestellten `MemoryStream` in nur wenigen Codezeilen. Die Methode serialisiert die Feature‑Collection, verarbeitet Attributdaten und Geometrie‑Konvertierung automatisch, sodass Sie eine einsatzbereite JSON‑Payload erhalten, ohne manuelle String‑Manipulation.

## Namespaces importieren
Zuerst sollten Sie die erforderlichen Namespaces einbinden, um die Aspose.GIS‑Funktionalitäten in Ihrem Code zu nutzen:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Schritt 1: Dokumentverzeichnis einrichten
```csharp
string dataDir = "Your Document Directory";
```
Ersetzen Sie "Your Document Directory" durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 2: Memory Stream erstellen
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Schritt 3: Vector Layer mit GeoJSON‑Treiber erstellen
Die Klasse `VectorLayer` repräsentiert einen Vektor‑Datensatz, der in verschiedenen Formaten, einschließlich GeoJSON, gespeichert werden kann.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Schritt 4: Feature‑Attribute definieren
Definieren Sie das Attribut‑Schema für Ihre Features (z. B. ID, Name).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Schritt 5: Features erstellen und hinzufügen
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

## Schritt 6: GeoJSON‑Ausgabe anzeigen
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Herzlichen Glückwunsch! Sie haben GeoJSON erfolgreich in einen Stream geschrieben mit Aspose.GIS für .NET.

## Häufige Probleme und Lösungen
- **Leerer Ausgabestream:** Stellen Sie sicher, dass Sie die Stream‑Position (`stream.Position = 0`) vor dem Lesen zurücksetzen.
- **Falsche Koordinatenreihenfolge:** GeoJSON erwartet die Reihenfolge Längengrad‑Breitengrad; überprüfen Sie Ihre Punktwerte.
- **Große Datensätze:** Verwenden Sie `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })`, um Features schrittweise zu streamen.

## Häufig gestellte Fragen
### Kann ich Aspose.GIS für .NET sowohl in Windows- als auch in Linux-Umgebungen verwenden?
Ja, Aspose.GIS für .NET ist mit sowohl Windows- als auch Linux‑Systemen kompatibel.  

### Gibt es eine kostenlose Testversion?
Absolut! Sie können eine kostenlose Testversion [hier](https://releases.aspose.com/) erkunden.  

### Wo finde ich detaillierte Dokumentation?
Sehen Sie sich die Dokumentation [hier](https://reference.aspose.com/gis/net/) an.  

### Wie kann ich eine temporäre Lizenz erhalten?
Temporäre Lizenzen sind [hier](https://purchase.aspose.com/temporary-license/) verfügbar.  

### Benötigen Sie Unterstützung oder haben Sie weitere Fragen?
Besuchen Sie unser Support‑Forum [hier](https://forum.aspose.com/c/gis/33).  

**F: Kann ich GeoJSON aus einer Sammlung von Breitengrad-/Längengrad‑Punkten erzeugen?**  
A: Ja – erstellen Sie für jeden Punkt ein `Feature`, weisen Sie eine `Point`‑Geometrie zu und fügen Sie es dem `VectorLayer` hinzu.  

**F: Unterstützt Aspose.GIS das Schreiben von komprimiertem GeoJSON (gzip)?**  
A: Sie können den `MemoryStream` vor dem Speichern in einen `GZipStream` einbetten, um eine komprimierte Payload zu erzeugen.  

**F: Wie groß ist die maximale Größe einer GeoJSON‑Datei, die Aspose.GIS verarbeiten kann?**  
A: Die Bibliothek kann Dateien größer als 2 GB streamen; der Speicherverbrauch bleibt gering, da Daten schrittweise geschrieben werden.  

---

**Zuletzt aktualisiert:** 2026-05-21  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Wie man GeoJSON aus einem Stream liest mit Aspose.GIS für .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Wie man GeoJSON in TopoJSON konvertiert mit Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Wie man Shapefile in GeoJSON konvertiert mit Aspose.GIS für .NET](/gis/net/layer-management/extract-features-to-geojson/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
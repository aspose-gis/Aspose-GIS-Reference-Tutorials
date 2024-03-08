---
title: Extrahieren Sie Features nach GeoJSON
linktitle: Extrahieren Sie Features nach GeoJSON
second_title: Aspose.GIS .NET-API
description: Entdecken Sie die Schritt-für-Schritt-Anleitung zur Verwendung von Aspose.GIS für .NET zum Extrahieren von Features in GeoJSON. Nutzen Sie die Leistungsfähigkeit von GIS ganz einfach! #Aspose #GIS
type: docs
weight: 23
url: /de/net/layer-management/extract-features-to-geojson/
---
## Einführung
Willkommen zu unserem Schritt-für-Schritt-Tutorial zum Extrahieren von Features nach GeoJSON mit Aspose.GIS für .NET! Egal, ob Sie ein erfahrener Entwickler sind oder gerade erst mit der GIS-Programmierung beginnen, dieser Leitfaden führt Sie durch den Prozess und stellt sicher, dass Sie die volle Leistungsfähigkeit von Aspose.GIS für .NET nutzen.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
-  Aspose.GIS für .NET: Stellen Sie sicher, dass Sie die Bibliothek installiert haben. Wenn nicht, können Sie es hier herunterladen[Aspose.GIS für .NET-Seite](https://releases.aspose.com/gis/net/).
-  Shapefile-Daten: Halten Sie ein Shapefile zur Eingabe bereit. Wenn Sie Beispieldaten benötigen, finden Sie diese im[Aspose.GIS-Dokumentation](https://reference.aspose.com/gis/net/).
- .NET-Umgebung: Richten Sie eine .NET-Umgebung ein, um den bereitgestellten Code auszuführen.
- Dokumentenverzeichnis: Definieren Sie den Pfad zu Ihrem Dokumentenverzeichnis im Code-Snippet.
Nachdem Sie nun alles eingerichtet haben, beginnen wir mit dem Extrahieren von Funktionen in GeoJSON!
## Namespaces importieren
Fügen Sie zunächst die erforderlichen Namespaces in Ihren Code ein:
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Diese Namespaces sind für die Arbeit mit Aspose.GIS-Funktionen unerlässlich.
## Schritt 1: Öffnen Sie das Eingabe-Shapefile
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Hier finden Sie Ihren Code zur Verarbeitung des Eingabe-Shapefiles
}
```
 Öffnen Sie das Eingabe-Shapefile mit`VectorLayer.Open` Methode.
## Schritt 2: Ausgabe-GeoJSON erstellen
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Ihr Code zum Erstellen der GeoJSON-Ausgabe finden Sie hier
}
```
 Erstellen Sie die Ausgabe-GeoJSON mit`VectorLayer.Create` Methode.
## Schritt 3: Attribute kopieren
```csharp
outputLayer.CopyAttributes(inputLayer);
```
 Kopieren Sie mithilfe von Attribute vom Eingabe-Layer in den Ausgabe-Layer`CopyAttributes` Methode.
## Schritt 4: Merkmale verarbeiten
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Hier finden Sie Ihren Code zur Verarbeitung der einzelnen Eingabefunktionen
}
```
Durchlaufen Sie jedes Feature in der Eingabeebene und verarbeiten Sie sie einzeln.
## Schritt 5: Filtern Sie die Funktionen nach Datum
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
Filtern Sie Funktionen basierend auf einer Datumsbedingung. In diesem Beispiel werden Features mit einem Geburtsdatum vor 1982 übersprungen.
## Schritt 6: Konstruieren Sie ein neues Feature
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Konstruieren Sie ein neues Feature für den Ausgabe-Layer und kopieren Sie dabei die Geometrie und Werte aus dem Eingabe-Feature.
Glückwunsch! Sie haben Features mit Aspose.GIS für .NET erfolgreich nach GeoJSON extrahiert.
## Abschluss
In diesem Tutorial haben wir den Prozess des Extrahierens von Features in GeoJSON mithilfe von Aspose.GIS für .NET untersucht. Diese leistungsstarke Bibliothek eröffnet eine Welt voller Möglichkeiten für die GIS-Entwicklung. Experimentieren Sie mit verschiedenen Datensätzen und Funktionen, um das volle Potenzial von Aspose.GIS auszuschöpfen.
## FAQs
### F: Wo finde ich weitere Dokumentation?
 Besuche den[Aspose.GIS-Dokumentation](https://reference.aspose.com/gis/net/) für ausführliche Informationen.
### F: Wie kann ich eine temporäre Lizenz erhalten?
 Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
### F: Wo kann ich Unterstützung suchen?
 Treten Sie der bei[Aspose.GIS-Forum](https://forum.aspose.com/c/gis/33) für Community-Unterstützung und Diskussionen.
### F: Gibt es eine kostenlose Testversion?
 Ja, Sie können die kostenlose Testversion finden[Hier](https://releases.aspose.com/).
### F: Wo kann ich Aspose.GIS für .NET kaufen?
 Sie können das Produkt kaufen[Hier](https://purchase.aspose.com/buy).
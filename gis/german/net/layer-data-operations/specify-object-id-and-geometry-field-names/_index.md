---
title: Geben Sie Objekt-ID und Geometriefeldnamen an
linktitle: Geben Sie Objekt-ID und Geometriefeldnamen an
second_title: Aspose.GIS .NET-API
description: Entdecken Sie die GIS-Magie mit Aspose.GIS für .NET! Verwalten Sie Geodaten mühelos. Laden Sie es jetzt herunter und entfesseln Sie die Kraft der räumlichen Intelligenz.
weight: 20
url: /de/net/layer-data-operations/specify-object-id-and-geometry-field-names/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Geben Sie Objekt-ID und Geometriefeldnamen an

## Einführung
Wenn Sie sich mit Aspose.GIS für .NET auf eine Reise in die Welt der geografischen Informationssysteme (GIS) begeben, eröffnen sich Entwicklern und Enthusiasten gleichermaßen eine Welt voller Möglichkeiten. Diese leistungsstarke Bibliothek ermöglicht Ihnen den mühelosen Umgang mit Geodaten. In diesem Tutorial führen wir Sie durch den Prozess der Angabe von Objekt-ID- und Geometriefeldnamen und legen so den Grundstein für Ihre GIS-Bemühungen.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
-  Aspose.GIS für .NET: Laden Sie die Bibliothek herunter und installieren Sie sie[Hier](https://releases.aspose.com/gis/net/).
- Dokumentenverzeichnis: Richten Sie ein Verzeichnis für Ihre Dokumente ein, um die Geodatenbanken zu speichern.
- .NET-Umgebung: Stellen Sie sicher, dass Sie über eine funktionierende .NET-Umgebung verfügen.
## Namespaces importieren
Um loszulegen, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren. Diese Namespaces stellen die wesentlichen Klassen und Methoden für die Interaktion mit Aspose.GIS für .NET bereit.
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```
## Schritt 1: Geben Sie Objekt-ID und Geometriefeldnamen an
In diesem Schritt erfahren Sie, wie Sie die Feldnamen „Objekt-ID“ und „Geometrie“ für Ihre GIS-Daten einrichten. Dies ist entscheidend für ein effizientes Datenmanagement.
## Schritt 1.1: Dokumentenverzeichnis festlegen
Definieren Sie zunächst den Pfad zu Ihrem Dokumentverzeichnis:
```csharp
string dataDir = "Your Document Directory";
```
## Schritt 1.2: Erstellen Sie eine GeoDatabase und definieren Sie Optionen
Erstellen Sie eine GeoDatabase mit der angegebenen Objekt-ID und den angegebenen Geometriefeldnamen:
```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Geben Sie den Feldnamen „Objekt-ID“ an
        GeometryFieldName = "POINT",       // Geben Sie den Namen des Geometriefelds an
    };
```
## Schritt 1.3: Erstellen Sie eine Ebene und fügen Sie sie hinzu
Erstellen Sie einen Layer innerhalb der GeoDatabase und fügen Sie ein Feature mit einer bestimmten Geometrie hinzu:
```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  //Geben Sie die Geometrie an (in diesem Fall einen Punkt).
    layer.Add(feature);
}
```
## Schritt 1.4: Öffnen und Abrufen von Daten aus der Ebene
Öffnen Sie den Layer und rufen Sie Daten daraus basierend auf der angegebenen Objekt-ID ab:
```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Ausgabe: 1
}
```
## Abschluss
Glückwunsch! Sie haben den Prozess der Angabe von Objekt-ID- und Geometriefeldnamen mit Aspose.GIS für .NET erfolgreich durchlaufen. Dies bildet eine solide Grundlage für Ihre GIS-Projekte und ermöglicht Ihnen die einfache Verwaltung von Geodaten.
## Häufig gestellte Fragen
### F: Kann ich Aspose.GIS für .NET in meinen Webanwendungen verwenden?
A: Ja, Aspose.GIS für .NET eignet sich sowohl für Desktop- als auch für Webanwendungen und bietet vielseitige Geodatenfunktionen.
### F: Gibt es vor dem Kauf eine Testversion?
 A: Ja, Sie können die Funktionen von Aspose.GIS für .NET mit einer kostenlosen Testversion erkunden[Hier](https://releases.aspose.com/).
### F: Wie kann ich eine temporäre Lizenz für Aspose.GIS für .NET erhalten?
 A: Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/) zu Auswertungszwecken.
### F: Welche räumlichen Bezugssysteme unterstützt Aspose.GIS für .NET?
A: Aspose.GIS für .NET unterstützt verschiedene Raumbezugssysteme und bietet so Flexibilität für verschiedene geografische Datensätze.
### F: Wo kann ich Hilfe suchen oder Aspose.GIS-bezogene Fragen besprechen?
 A: Besuchen Sie das Aspose.GIS-Forum[Hier](https://forum.aspose.com/c/gis/33) für Unterstützung und Diskussionen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

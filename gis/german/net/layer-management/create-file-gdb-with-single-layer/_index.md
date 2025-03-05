---
title: Erstellen Sie eine Datei-GDB mit einer Ebene
linktitle: Erstellen Sie eine Datei-GDB mit einer Ebene
second_title: Aspose.GIS .NET-API
description: Erschließen Sie mit Aspose.GIS das Potenzial der Geodatenverwaltung in .NET. Erfahren Sie Schritt für Schritt, wie Sie File-Geodatabases und Layer erstellen. Jetzt downloaden!
type: docs
weight: 11
url: /de/net/layer-management/create-file-gdb-with-single-layer/
---
## Einführung
Sind Sie bereit, Ihre Geodatenanwendungen mit robusten File-Geodatenbanken und Layern zu erweitern? Suchen Sie nicht weiter als Aspose.GIS für .NET. In diesem Tutorial führen wir Sie durch den Prozess der Erstellung einer File-Geodatabase (GDB) mit einer einzelnen Ebene mithilfe von Aspose.GIS für .NET. Nutzen Sie mühelos die Leistungsfähigkeit der räumlichen Datenverwaltung und -visualisierung in Ihren .NET-Anwendungen.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1.  Aspose.GIS für .NET: Stellen Sie sicher, dass die Aspose.GIS-Bibliothek installiert ist. Sie können es hier herunterladen[Aspose.GIS für .NET-Downloadseite](https://releases.aspose.com/gis/net/).
2. Entwicklungsumgebung: Richten Sie eine funktionierende .NET-Entwicklungsumgebung auf Ihrem Computer ein.
3. Dokumentenverzeichnis: Wählen oder erstellen Sie ein Verzeichnis auf Ihrem System, in dem Sie Ihre Geodatendateien speichern.
## Namespaces importieren
Um zu beginnen, müssen Sie die erforderlichen Namespaces in Ihr .NET-Projekt importieren. Diese Namespaces bieten Zugriff auf die Aspose.GIS-Funktionen. Fügen Sie am Anfang Ihrer Codedatei die folgenden Zeilen hinzu:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```
## Schritt 1: Richten Sie Ihr Dokumentenverzeichnis ein
```csharp
string dataDir = "Your Document Directory";
```
Ersetzen Sie „Ihr Dokumentverzeichnis“ durch den Pfad zu dem Verzeichnis, in dem Sie Ihre Geodatendateien speichern möchten.
## Schritt 2: Erstellen Sie eine File-Geodatabase mit einem einzelnen Layer
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Dieses Code-Snippet erstellt eine File-Geodatabase mit einem einzelnen Layer und fügt ihr ein Linien-Feature hinzu.
## Schritt 3: Öffnen Sie die File-Geodatabase und rufen Sie Layer-Informationen ab
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Ausgabe: Anzahl der Features: 1
}
```
In diesem Schritt öffnen wir die erstellte File-Geodatabase, rufen den Layer mit dem Namen „Layer“ ab und drucken die Anzahl der Features im Layer aus.
## Abschluss
Glückwunsch! Sie haben mit Aspose.GIS für .NET erfolgreich eine File-Geodatabase mit einem einzelnen Layer erstellt. Entdecken Sie ganz einfach die umfangreichen Möglichkeiten des Geodatenmanagements in Ihren Anwendungen.
## Häufig gestellte Fragen
### Kann ich Aspose.GIS für .NET in meinen bestehenden .NET-Projekten verwenden?
Ja, Aspose.GIS für .NET kann nahtlos in Ihre bestehenden .NET-Projekte integriert werden.
### Gibt es eine Testversion für Aspose.GIS für .NET?
 Ja, Sie können die Funktionen von Aspose.GIS für .NET erkunden, indem Sie das herunterladen[kostenlose Testversion](https://releases.aspose.com/).
### Wo finde ich eine ausführliche Dokumentation zu Aspose.GIS für .NET?
 Siehe die[Dokumentation](https://reference.aspose.com/gis/net/) Für umfassende Informationen zu Aspose.GIS für .NET.
### Wie erhalte ich Unterstützung für Aspose.GIS für .NET?
 Besuche den[Aspose.GIS-Forum](https://forum.aspose.com/c/gis/33) für die Unterstützung und Unterstützung der Gemeinschaft.
### Sind temporäre Lizenzen für Aspose.GIS für .NET verfügbar?
 Ja, Sie können eine erhalten[temporäre Lizenz](https://purchase.aspose.com/temporary-license/) für Aspose.GIS für .NET.
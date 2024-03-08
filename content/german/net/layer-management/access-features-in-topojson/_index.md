---
title: Freischalten von TopoJSON-Funktionen mit Aspose.GIS für .NET
linktitle: Zugriffsfunktionen in TopoJSON
second_title: Aspose.GIS .NET-API
description: Entdecken Sie Aspose.GIS für .NET und erfahren Sie Schritt für Schritt, wie Sie auf TopoJSON-Funktionen zugreifen. Tauchen Sie ein in die Dokumentation und nutzen Sie mühelos Geodatenfunktionen.
type: docs
weight: 15
url: /de/net/layer-management/access-features-in-topojson/
---
## Einführung
Aspose.GIS für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, mühelos mit Geodaten zu arbeiten. In diesem Tutorial befassen wir uns mit dem Zugriff auf Funktionen in TopoJSON mithilfe von Aspose.GIS für .NET. TopoJSON ist ein Format, das geografische Merkmale kompakt und effizient darstellt.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Grundkenntnisse in C# und .NET.
-  Aspose.GIS für .NET-Bibliothek installiert. Sie können es herunterladen[Hier](https://releases.aspose.com/gis/net/).
-  Beispiel-TopoJSON-Datei zum Testen. Einen finden Sie im[Dokumentation](https://reference.aspose.com/gis/net/).
## Namespaces importieren
Beginnen Sie mit dem Importieren der erforderlichen Namespaces in Ihren C#-Code:
```csharp
using Aspose.Gis;
using System;
using System.Text;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Erstellen Sie zunächst ein neues C#-Projekt und fügen Sie Aspose.GIS für .NET als Referenz hinzu. Stellen Sie sicher, dass Ihr Projekt für die Verwendung der Bibliothek konfiguriert ist.
## Schritt 2: TopoJSON-Daten laden
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";
string sampleTopoJsonPath = dataDir + "sample.topojson";
StringBuilder builder = new StringBuilder();
// Öffnen Sie die TopoJSON-Datei
using (VectorLayer layer = VectorLayer.Open(sampleTopoJsonPath, Drivers.TopoJson))
{
    // Durchlaufen Sie jedes Feature in der Ebene
    foreach (Feature feature in layer)
    {
        // ID-Eigenschaft erhalten
        int id = feature.GetValue<int>("id");
        // Rufen Sie den Namen des Objekts ab, das diese Funktion enthält
        string objectName = feature.GetValue<string>("topojson_object_name");
        // Holen Sie sich die Namensattributeigenschaft, die sich im Objekt „properties“ befindet
        string name = feature.GetValue<string>("name");
        // Holen Sie sich die Geometrie des Features.
        string geometry = feature.Geometry.AsText();
        // Erstellen Sie die Ausgabezeichenfolge
        builder.AppendFormat("Feature with ID {0}:\n", id);
        builder.AppendFormat("Object Name = {0}\n", objectName);
        builder.AppendFormat("Name        = {0}\n", name);
        builder.AppendFormat("Geometry    = {0}\n", geometry);
    }
}
// Zeigen Sie die Ausgabe an
Console.WriteLine("Output:");
Console.WriteLine(builder.ToString());
```
## Abschluss
Glückwunsch! Sie haben mit Aspose.GIS für .NET erfolgreich auf Features in TopoJSON zugegriffen. In diesem Tutorial wurden die grundlegenden Schritte für den Einstieg behandelt, aber Sie können mit der Bibliothek noch viel mehr erkunden.
## FAQs
### F: Wo finde ich weitere Dokumentation?
 Besuche den[Aspose.GIS für .NET-Dokumentation](https://reference.aspose.com/gis/net/).
### F: Wie kann ich Aspose.GIS für .NET herunterladen?
 Laden Sie die Bibliothek herunter[Hier](https://releases.aspose.com/gis/net/).
### F: Wo kann ich Unterstützung für Aspose.GIS erhalten?
 Treten Sie der bei[Aspose.GIS-Forum](https://forum.aspose.com/c/gis/33) zur Hilfe.
### F: Gibt es eine kostenlose Testversion?
Ja, Sie können auf eine kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).
### F: Wie kaufe ich eine Lizenz?
 Kaufen Sie eine Lizenz[Hier](https://purchase.aspose.com/buy).
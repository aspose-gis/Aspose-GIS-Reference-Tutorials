---
title: Neues Shapefile erstellen
linktitle: Neues Shapefile erstellen
second_title: Aspose.GIS .NET-API
description: Erfahren Sie, wie Sie mit Aspose.GIS für .NET ein neues Shapefile erstellen. Befolgen Sie unsere Schritt-für-Schritt-Anleitung und nutzen Sie die Möglichkeiten der Geodatenmanipulation.
type: docs
weight: 12
url: /de/net/layer-management/create-new-shapefile/
---
## Einführung
Wenn Sie sich mit der Entwicklung geografischer Informationssysteme (GIS) mit .NET befassen, ist Aspose.GIS Ihre Lösung der Wahl. Diese leistungsstarke Bibliothek ermöglicht Entwicklern die nahtlose Arbeit mit räumlichen Daten. In diesem Tutorial führen wir Sie durch den Prozess der Erstellung eines neuen Shapefiles mit Aspose.GIS für .NET.
## Voraussetzungen
Bevor wir mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundlegendes Verständnis der Programmiersprache C#.
- Visual Studio ist auf Ihrem Computer installiert.
-  Aspose.GIS für .NET-Bibliothek. Sie können es herunterladen[Hier](https://releases.aspose.com/gis/net/).
## Namespaces importieren
Beginnen Sie mit dem Importieren der erforderlichen Namespaces, um die Funktionalität von Aspose.GIS zu nutzen:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Beginnen Sie mit der Erstellung eines neuen C#-Projekts in Visual Studio und beziehen Sie die Aspose.GIS-Bibliothek ein.
## Schritt 2: Definieren Sie das Dokumentenverzeichnis
```csharp
string dataDir = "Your Document Directory";
```
Ersetzen Sie „Ihr Dokumentverzeichnis“ durch den tatsächlichen Pfad, in dem Sie Ihr neues Shapefile speichern möchten.
## Schritt 3: Erstellen Sie einen VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //Fügen Sie Attribute hinzu, bevor Sie Features hinzufügen
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Dieses Codesegment richtet die Vektorebene ein und definiert Attribute für Ihre Features.
## Schritt 4: Funktionen hinzufügen
### Fall 1: Werte individuell festlegen
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
### Fall 2: Legt neue Werte für alle Attribute fest
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## Abschluss
 Glückwunsch! Sie haben mit Aspose.GIS für .NET erfolgreich ein neues Shapefile erstellt. In diesem Tutorial wurden die Grundlagen zum Einrichten Ihres Projekts, zum Definieren von Attributen und zum Hinzufügen von Funktionen behandelt. Weitere Informationen finden Sie im[Dokumentation](https://reference.aspose.com/gis/net/) für erweiterte Features und Funktionalitäten.
## Häufig gestellte Fragen
### F: Kann ich Aspose.GIS mit anderen Programmiersprachen verwenden?
Aspose.GIS unterstützt hauptsächlich .NET, es sind jedoch auch Versionen für Java verfügbar.
### F: Gibt es eine kostenlose Testversion?
 Ja, Sie können auf die kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).
### F: Wo finde ich Unterstützung für Aspose.GIS?
 Besuche den[Aspose.GIS-Forum](https://forum.aspose.com/c/gis/33) für Community-Unterstützung und Diskussionen.
### F: Wie kann ich eine temporäre Lizenz erhalten?
 Holen Sie sich Ihre temporäre Lizenz[Hier](https://purchase.aspose.com/temporary-license/).
### F: Wo kann ich Aspose.GIS für .NET kaufen?
 Sie können die Bibliothek kaufen[Hier](https://purchase.aspose.com/buy).
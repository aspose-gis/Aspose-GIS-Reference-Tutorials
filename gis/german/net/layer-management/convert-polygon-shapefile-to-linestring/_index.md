---
title: Konvertieren Sie Polygon-Shapefile in Linestring
linktitle: Konvertieren Sie Polygon-Shapefile in Linestring
second_title: Aspose.GIS .NET-API
description: Entdecken Sie die Leistungsfähigkeit von Aspose.GIS für .NET und konvertieren Sie Polygon-Shapefiles mühelos in Linienfolgen. Steigern Sie noch heute Ihre GIS-Entwicklung!
type: docs
weight: 18
url: /de/net/layer-management/convert-polygon-shapefile-to-linestring/
---
## Einführung
Wenn Sie mit geografischen Informationssystemen (GIS) in .NET arbeiten, ist Aspose.GIS eine leistungsstarke Bibliothek, die Ihre Aufgaben vereinfachen kann. In diesem Tutorial führen wir Sie durch den Prozess der Konvertierung eines Polygon-Shapefiles in einen Linestring mit Aspose.GIS. Dies kann besonders nützlich sein, wenn Sie für verschiedene Anwendungen wie Routenplanung oder Netzwerkanalyse lineare Features aus Polygondaten extrahieren müssen.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass Sie Folgendes eingerichtet haben:
-  Aspose.GIS-Bibliothek: Laden Sie die Aspose.GIS-Bibliothek von herunter und installieren Sie sie[Webseite](https://releases.aspose.com/gis/net/).
- Shapefile-Daten: Halten Sie ein Polygon-Shapefile zur Konvertierung bereit. Wenn Sie noch keine haben, können Sie Beispieldaten finden oder Ihre eigenen erstellen.
- Entwicklungsumgebung: Richten Sie Ihre .NET-Entwicklungsumgebung mit den erforderlichen Tools ein.
## Namespaces importieren
In Ihrem C#-Code müssen Sie die Aspose.GIS-Namespaces importieren, um auf die erforderlichen Klassen und Methoden zuzugreifen. Fügen Sie am Anfang Ihrer Codedatei die folgenden Namespaces hinzu:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Schritt 1: Legen Sie das Dokumentverzeichnis fest
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";
```
Ersetzen Sie „Ihr Dokumentverzeichnis“ durch den Pfad zu dem Verzeichnis, in dem sich Ihr Shapefile befindet.
## Schritt 2: Öffnen Sie das Quell-Shapefile
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Der Rest des Codes wird hier eingefügt
}
```
Dieser Schritt öffnet das Quell-Polygon-Shapefile zum Lesen.
## Schritt 3: Erstellen Sie das Ziel-Linestring-Shapefile
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Der Rest des Codes wird hier eingefügt
}
```
Hier erstellen wir ein neues Linestring-Shapefile zum Schreiben der konvertierten Daten.
## Schritt 4: Durchlaufen Sie die Quellfunktionen
```csharp
foreach (Feature sourceFeature in source)
{
    // Der Rest des Codes wird hier eingefügt
}
```
Diese Schleife durchläuft jedes Feature im Quell-Polygon-Shapefile.
## Schritt 5: Konvertieren Sie ein Polygon in eine Linienfolge und schreiben Sie es in das Ziel
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
In diesem Schritt wird jedes Polygon-Feature in einen Linestring umgewandelt und das resultierende Linestring-Feature in das Ziel-Shapefile geschrieben.
## Abschluss
Wenn Sie diese Schritte befolgen, können Sie mit Aspose.GIS für .NET ganz einfach ein Polygon-Shapefile in einen Linienstring konvertieren. Dieser Prozess eröffnet neue Möglichkeiten zur Datenanalyse und Visualisierung in GIS-Anwendungen.

## FAQs
### Ist Aspose.GIS mit allen Versionen von .NET kompatibel?
Ja, Aspose.GIS unterstützt verschiedene Versionen von .NET und gewährleistet so die Kompatibilität mit Ihrer Entwicklungsumgebung.
### Kann ich Aspose.GIS für kommerzielle Projekte verwenden?
 Ja, du kannst. Um Aspose.GIS in kommerziellen Projekten zu verwenden, sollten Sie den Kauf einer Lizenz in Betracht ziehen[Hier](https://purchase.aspose.com/buy).
### Gibt es Beispiele oder Dokumentationen?
 Ja, eine umfassende Dokumentation und Beispiele finden Sie auf der[Dokumentationsseite](https://reference.aspose.com/gis/net/).
### Gibt es eine Testversion?
 Ja, Sie können Aspose.GIS mit einer kostenlosen Testversion erkunden[dieser Link](https://releases.aspose.com/).
### Wo kann ich Hilfe oder Unterstützung suchen?
 Besuche den[Aspose.GIS-Forum](https://forum.aspose.com/c/gis/33) für jegliche Unterstützung oder Supportanfragen.
---
title: Erstellen Sie eine Vektorebene mit SRS
linktitle: Erstellen Sie eine Vektorebene mit SRS
second_title: Aspose.GIS .NET-API
description: Entdecken Sie Aspose.GIS für .NET – Ihr Schlüssel zur nahtlosen GIS-Integration. Erstellen Sie mühelos Vektorebenen mit festgelegten räumlichen Bezugssystemen. Jetzt downloaden!
weight: 13
url: /de/net/layer-management/create-vector-layer-with-srs/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen Sie eine Vektorebene mit SRS

## Einführung
Aspose.GIS für .NET ist eine leistungsstarke Bibliothek, die Entwicklern die nahtlose Arbeit mit Geoinformationssystemdaten (GIS) in .NET-Anwendungen ermöglicht. In diesem Tutorial konzentrieren wir uns auf die Erstellung einer Vektorebene mit einem räumlichen Bezugssystem (SRS). Am Ende dieses Leitfadens werden Sie in der Lage sein, GIS-Funktionen mühelos in Ihre .NET-Projekte zu integrieren.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundkenntnisse in C#- und .NET-Entwicklung.
-  Aspose.GIS für .NET-Bibliothek installiert. Sie können es herunterladen[Hier](https://releases.aspose.com/gis/net/).
- Eine Entwicklungsumgebung eingerichtet und bereit.
## Namespaces importieren
Stellen Sie sicher, dass Sie die erforderlichen Namespaces am Anfang Ihrer C#-Datei importiert haben:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Schritt 1: Richten Sie das projizierte räumliche Bezugssystem ein
Lassen Sie uns am Beispiel der World Mercator-Projektion ein projiziertes räumliches Referenzsystem (SRS) erstellen. Folge diesen Schritten:
```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```
## Schritt 2: Erstellen Sie eine Vektorebene und fügen Sie Features hinzu
Erstellen wir nun ein Shapefile und fügen Features mit dem angegebenen SRS hinzu:
```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // Dadurch wird eine Ausnahme ausgelöst, da die Geometrie ein anderes SRS hat
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## Schritt 3: Überprüfen Sie das räumliche Bezugssystem
Zum Schluss öffnen wir die Ebene und überprüfen ihr räumliches Bezugssystem:
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // „WGS 84 / Welt Mercator“
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Sollte true zurückgeben
}
```
Durch Befolgen dieser Schritte haben Sie mit Aspose.GIS für .NET erfolgreich eine Vektorebene mit einem angegebenen räumlichen Bezugssystem erstellt.
## Abschluss
Dank Aspose.GIS war die Integration von GIS-Funktionen in Ihre .NET-Anwendungen noch nie so einfach. Mit der Möglichkeit, mühelos Vektorebenen zu erstellen und Raumbezugssysteme zu verwalten, können Sie Ihre Projekte mit leistungsstarken Geodatenfunktionen erweitern.
## FAQs
### Ist Aspose.GIS mit allen GIS-Dateiformaten kompatibel?
 Aspose.GIS unterstützt verschiedene GIS-Formate, darunter Shapefile, GeoJSON, KML und mehr. Überprüf den[Dokumentation](https://reference.aspose.com/gis/net/) für die vollständige Liste.
### Kann ich Aspose.GIS in einer Webanwendung verwenden?
Absolut! Aspose.GIS für .NET ist vielseitig und kann in Webanwendungen, Desktopanwendungen und sogar mobilen Apps verwendet werden.
### Wo erhalte ich Support für Aspose.GIS?
 Eine hilfreiche Community finden Sie unter[Aspose.GIS-Forum](https://forum.aspose.com/c/gis/33) für alle Fragen oder Probleme, auf die Sie stoßen könnten.
### Gibt es eine kostenlose Testversion?
 Ja, Sie können die Funktionen von Aspose.GIS erkunden, indem Sie eine kostenlose Testversion erhalten[Hier](https://releases.aspose.com/).
### Wie kann ich eine Lizenz für Aspose.GIS erwerben?
 Um eine Lizenz zu erwerben, besuchen Sie die[Kaufseite](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

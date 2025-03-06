---
title: Legen Sie das räumliche Referenzsystem des Layers fest
linktitle: Legen Sie das räumliche Referenzsystem des Layers fest
second_title: Aspose.GIS .NET-API
description: Master-Einstellung des Layer-Raumbezugssystems mit Aspose.GIS für .NET. Verbessern Sie Ihre GIS-Projekte mit dieser Schritt-für-Schritt-Anleitung.
weight: 19
url: /de/net/layer-data-operations/set-layer-spatial-reference-system/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Legen Sie das räumliche Referenzsystem des Layers fest

## Einführung
In der riesigen Landschaft der geografischen Informationssysteme (GIS) sticht Aspose.GIS für .NET als robustes und vielseitiges Tool für Entwickler hervor. Dieses Tutorial führt Sie durch den Prozess der Einrichtung des Layer-Raumbezugssystems mit Aspose.GIS für .NET. Unabhängig davon, ob Sie ein erfahrener Entwickler oder ein Neuling in der GIS-Entwicklung sind, hilft Ihnen diese Schritt-für-Schritt-Anleitung dabei, die Leistungsfähigkeit von Aspose.GIS zu nutzen, um Ihre Fähigkeiten im Umgang mit Geodaten zu verbessern.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundkenntnisse in der .NET-Programmierung.
- Visual Studio ist auf Ihrem System installiert.
-  Aspose.GIS für .NET-Bibliothek, die Sie herunterladen können[Hier](https://releases.aspose.com/gis/net/).
- Ein grundlegendes Verständnis räumlicher Bezugssysteme in GIS.
## Namespaces importieren
Beginnen Sie in Ihrem .NET-Projekt mit dem Importieren der erforderlichen Namespaces, um auf die von Aspose.GIS bereitgestellten Funktionen zuzugreifen. Verwenden Sie den folgenden Codeausschnitt:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```
## Schritt 1: Geben Sie das Dokumentverzeichnis an
Geben Sie zunächst den Pfad zu Ihrem Dokumentverzeichnis an. Dies ist der Ort, an dem Ihre Geodatendateien gespeichert werden.
```csharp
string dataDir = "Your Document Directory";
```
## Schritt 2: Erstellen und legen Sie ein räumliches Bezugssystem fest
Definieren Sie den Pfad für das Shapefile und erstellen Sie ein neues räumliches Bezugssystem mit dem EPSG-Code (in diesem Beispiel 26918).
```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```
## Schritt 3: Vektorebene erstellen
Verwenden Sie Aspose.GIS, um eine Vektorebene mit dem angegebenen Shapefile-Pfad, Treibertyp (Shapefile) und räumlichen Bezugssystem zu erstellen.
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Hier finden Sie Ihren Code für weitere Operationen auf der Ebene
}
```
## Schritt 4: Feature zum Layer hinzufügen
Konstruieren Sie ein neues Feature und legen Sie seine Geometrie fest (in diesem Fall einen Punkt mit den Koordinaten 60, 24). Fügen Sie das Feature zur Vektorebene hinzu.
```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```
## Schritt 5: Informationen zum räumlichen Referenzsystem abrufen
Öffnen Sie die Vektorebene und rufen Sie Informationen zum räumlichen Bezugssystem ab.
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```
Wiederholen Sie diese Schritte entsprechend Ihrem spezifischen Anwendungsfall, und Sie sind auf dem besten Weg, die Kunst des Festlegens des räumlichen Layer-Referenzsystems mit Aspose.GIS für .NET zu meistern.
## Abschluss
In diesem Tutorial haben wir die wesentlichen Schritte zum Festlegen des räumlichen Layer-Referenzsystems mit Aspose.GIS für .NET untersucht. Mit seiner intuitiven API und leistungsstarken Funktionen ermöglicht Aspose.GIS Entwicklern die nahtlose Verarbeitung räumlicher Daten. Integrieren Sie diese Techniken in Ihre GIS-Projekte, um Ihre Fähigkeiten zur Verarbeitung räumlicher Daten zu verbessern.
## Häufig gestellte Fragen
### Ist Aspose.GIS mit anderen GIS-Bibliotheken kompatibel?
Ja, Aspose.GIS lässt sich gut in andere GIS-Bibliotheken integrieren und kann in Verbindung mit diesen verwendet werden.
### Kann ich Aspose.GIS sowohl für Desktop- als auch für Webanwendungen verwenden?
Absolut! Aspose.GIS ist vielseitig und kann sowohl in Desktop- als auch in webbasierten Anwendungen verwendet werden.
### Gibt es Lizenzoptionen für Aspose.GIS?
 Ja, Sie können Lizenzoptionen erkunden und einen Kauf tätigen[Hier](https://purchase.aspose.com/buy).
### Gibt es eine kostenlose Testversion für Aspose.GIS?
 Sicherlich! Sie können eine kostenlose Testversion herunterladen[Hier](https://releases.aspose.com/).
### Wo kann ich Unterstützung für Fragen zu Aspose.GIS erhalten?
 Für Unterstützung oder Fragen besuchen Sie die[Aspose.GIS-Forum](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

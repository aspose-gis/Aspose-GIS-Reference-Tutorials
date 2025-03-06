---
title: Beherrschen der Feature-Beschriftung mit Aspose.GIS für .NET
linktitle: Beschriften Sie Features auf der Karte
second_title: Aspose.GIS .NET-API
description: Entdecken Sie Aspose.GIS für .NET und beherrschen Sie die Kunst der Feature-Beschriftung auf Karten. Verbessern Sie Ihre Geodatenvisualisierungen mühelos. #Aspose #GIS
weight: 11
url: /de/net/map-rendering/label-features-on-map/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Beherrschen der Feature-Beschriftung mit Aspose.GIS für .NET

## Einführung
In der Welt der Geodatenvisualisierung spielt die Beschriftung von Features auf einer Karte eine entscheidende Rolle bei der effektiven Informationsvermittlung. Aspose.GIS für .NET bietet ein leistungsstarkes Toolkit, um dies nahtlos zu erreichen. In diesem Tutorial erkunden wir verschiedene Methoden zum Beschriften von Punkten auf einer Karte mit Aspose.GIS und verbessern Ihre Kartenvisualisierungen mit informativen Beschriftungen.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundkenntnisse in C# und dem .NET Framework.
-  Aspose.GIS für .NET installiert. Sie können es herunterladen[Hier](https://releases.aspose.com/gis/net/).
- Eine GeoJSON-Datei mit Punktdaten. Wenn Sie keine haben, können Sie zum Testen eine Beispieldatei verwenden.
## Namespaces importieren
Stellen Sie in Ihrem C#-Code sicher, dass Sie die erforderlichen Namespaces für die Arbeit mit Aspose.GIS importieren:
```csharp
using System;
using System.Drawing;
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Labelings;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.GIS.Examples.CSharp;
using FontStyle = Aspose.Gis.Rendering.Labelings.FontStyle;
```
Lassen Sie uns nun jedes Beispiel in einer Schritt-für-Schritt-Anleitung in mehrere Schritte unterteilen.
##  Punktebeschriftung

### Schritt 1: Legen Sie den Pfad zu Ihrem Dokumentenverzeichnis fest:
```csharp
string dataDir = "Your Document Directory";
```
### Schritt 2: Erstellen Sie eine Karte mit einem einfachen Markierungssymbol:
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Fügen Sie eine Vektorebene hinzu und wenden Sie eine Beschriftung an
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Rendern Sie die Karte in eine SVG-Datei
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```
## Punktbeschriftung gestaltet

Befolgen Sie die Schritte 1 und 2 aus dem vorherigen Beispiel.

### Schritt 1: Passen Sie den Beschriftungsstil an:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Die restlichen Schritte bleiben gleich
```
## Punktebeschriftung platziert

Befolgen Sie die Schritte 1 und 2 aus dem ersten Beispiel.
### Schritt 2: Passen Sie die Etikettenplatzierung an:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        HorizontalOffset = 2,
        VerticalOffset = 2,
        Rotation = 10,
    }
};
// Die restlichen Schritte bleiben gleich
```
## Punktbeschriftung funktionsbasiert

Befolgen Sie die Schritte 1 und 2 aus dem ersten Beispiel.

### Schritt 1: Featurebasierte Kennzeichnung implementieren:
```csharp
var pointLabeling = new SimpleLabeling("name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        VerticalOffset = 4,
        HorizontalOffset = 4,
    },
    FeatureBasedConfiguration = (feature, labeling) =>
    {
        // Rufen Sie die Bevölkerung aus dem Feature ab.
        var population = feature.GetValue<int>("population");
        // Die Schriftgröße wird berechnet und basiert auf der Bevölkerung.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // Die Priorität des Labels richtet sich auch nach der Bevölkerungszahl.
        // Je höher die Priorität ist, desto wahrscheinlicher ist es, dass die Beschriftung auf dem Ausgabebild erscheint.
        labeling.Priority = population;
    }
};
// Die restlichen Schritte bleiben gleich
```
## Abschluss
Glückwunsch! Sie haben gelernt, wie Sie Ihre Kartenvisualisierungen durch die Beschriftung von Features mit Aspose.GIS für .NET verbessern. Experimentieren Sie mit verschiedenen Stilen und Platzierungen, um überzeugende Karten zu erstellen, die auf Ihre Daten zugeschnitten sind.
## FAQs
### Kann ich Features mit benutzerdefinierten Schriftarten beschriften?
Ja, Sie können den Schriftstil und die Schriftgröße in der Beschriftungskonfiguration anpassen.
### Ist Aspose.GIS mit anderen GIS-Datenformaten kompatibel?
Aspose.GIS unterstützt verschiedene Geodatenformate, darunter GeoJSON, Shapefile und mehr.
### Wie kann ich mit großen Datensätzen zur Beschriftung umgehen?
Aspose.GIS ist auf Leistung optimiert, Sie sollten jedoch die Verwendung funktionsbasierter Konfigurationen in Betracht ziehen, um Beschriftungen basierend auf Datenattributen zu priorisieren.
### Gibt es erweiterte Optionen zur Etikettenplatzierung?
Ja, Sie können die Beschriftungsplatzierung mithilfe von Optionen wie Drehung, Ankerpunkten und Versätzen optimieren.
### Kann ich die Etikettenerstellung in einem Batch-Prozess automatisieren?
Auf jeden Fall können Sie Aspose.GIS in Ihre automatisierten Arbeitsabläufe zur Stapeletikettenerstellung integrieren.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

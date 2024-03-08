---
title: Functielabeling beheersen met Aspose.GIS voor .NET
linktitle: Label functies op kaart
second_title: Aspose.GIS .NET-API
description: Verken Aspose.GIS voor .NET en beheers de kunst van het labelen van objecten op kaarten. Verbeter uw geospatiale visualisaties moeiteloos. #Aspose #GIS
type: docs
weight: 11
url: /nl/net/map-rendering/label-features-on-map/
---
## Invoering
In de wereld van geospatiale datavisualisatie speelt het labelen van kenmerken op een kaart een cruciale rol bij het effectief overbrengen van informatie. Aspose.GIS voor .NET biedt een krachtige toolkit om dit naadloos te bereiken. In deze zelfstudie verkennen we verschillende methoden voor het labelen van punten op een kaart met behulp van Aspose.GIS, waardoor uw kaartvisualisaties worden verbeterd met informatieve labels.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Een praktische kennis van C# en het .NET-framework.
-  Aspose.GIS voor .NET geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/gis/net/).
- Een GeoJSON-bestand met puntgegevens. Als u er geen heeft, kunt u een voorbeeldbestand gebruiken om te testen.
## Naamruimten importeren
Zorg ervoor dat u in uw C#-code de benodigde naamruimten importeert om met Aspose.GIS te werken:
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
Laten we nu elk voorbeeld opsplitsen in meerdere stappen in een stapsgewijze handleiding.
##  Puntenlabeling

### Stap 1: Stel het pad naar uw documentenmap in:
```csharp
string dataDir = "Your Document Directory";
```
### Stap 2: Maak een kaart met een eenvoudig markeringssymbool:
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Voeg een vectorlaag toe en pas labels toe
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Render de kaart naar een SVG-bestand
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```
## Puntenlabeling gestileerd

Volg stap 1 en 2 uit het vorige voorbeeld.

### Stap 1: Pas de labelstijl aan:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// De rest van de stappen blijven hetzelfde
```
## Puntenlabeling geplaatst

Volg stap 1 en 2 uit het eerste voorbeeld.
### Stap 2: Pas de plaatsing van het label aan:
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
// De rest van de stappen blijven hetzelfde
```
## Puntenlabeling op basis van functies

Volg stap 1 en 2 uit het eerste voorbeeld.

### Stap 1: Op functies gebaseerde labels implementeren:
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
        // Haal de populatie op uit het object.
        var population = feature.GetValue<int>("population");
        // De lettergrootte wordt berekend en is gebaseerd op de populatie.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // De prioriteit van het label is ook gebaseerd op de populatie.
        // Hoe groter de prioriteit is, hoe waarschijnlijker het is dat het label op de uitvoerafbeelding verschijnt.
        labeling.Priority = population;
    }
};
// De rest van de stappen blijven hetzelfde
```
## Conclusie
Gefeliciteerd! U hebt geleerd hoe u uw kaartvisualisaties kunt verbeteren door objecten te labelen met Aspose.GIS voor .NET. Experimenteer met verschillende stijlen en plaatsingen om aantrekkelijke kaarten te maken die zijn afgestemd op uw gegevens.
## Veelgestelde vragen
### Kan ik elementen labelen met aangepaste lettertypen?
Ja, u kunt de letterstijl en -grootte aanpassen in de labelconfiguratie.
### Is Aspose.GIS compatibel met andere GIS-gegevensformaten?
Aspose.GIS ondersteunt verschillende georuimtelijke formaten, waaronder GeoJSON, Shapefile en meer.
### Hoe kan ik grote datasets verwerken voor labeling?
Aspose.GIS is geoptimaliseerd voor prestaties, maar overweeg het gebruik van op functies gebaseerde configuraties om labels prioriteit te geven op basis van gegevensattributen.
### Zijn er geavanceerde opties voor het plaatsen van labels beschikbaar?
Ja, u kunt de plaatsing van labels nauwkeurig afstemmen met behulp van opties zoals rotatie, ankerpunten en offsets.
### Kan ik het genereren van labels in een batchproces automatiseren?
Absoluut, u kunt Aspose.GIS integreren in uw geautomatiseerde workflows voor het genereren van batchlabels.
---
date: 2026-01-15
description: Leer hoe u kaartobjecten labelt met Aspose.GIS voor .NET, met aangepaste
  labelstijlopties voor het labelen van grote datasets.
linktitle: Label Features on Map
second_title: Aspose.GIS .NET API
title: Label kaartobjecten met Aspose.GIS voor .NET
url: /nl/net/map-rendering/label-features-on-map/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kaartfeatures labelen met Aspose.GIS voor .NET

## Inleiding
Het labelen van kaartfeatures is essentieel om ruwe georuimtelijke gegevens om te zetten in duidelijke, gebruiksvriendelijke visualisaties. In deze tutorial ontdek je **hoe je kaartfeatures labelt** (het primaire zoekwoord) met Aspose.GIS voor .NET, verken je aangepaste labelstijlen, en zie je technieken die zelfs werken met grote datasets. Aan het einde kun je informatieve tekst direct op je kaarten toevoegen, waardoor ze inzichtelijker worden voor analisten en eindgebruikers.

## Snelle antwoorden
- **Wat is de hoofdklasse voor rendering?** `Map` (Aspose.Gis.Rendering)
- **Welke labelklasse voegt eenvoudige tekst toe?** `SimpleLabeling`
- **Kan ik labels stylen (halo, lettertype, rotatie)?** Ja – via eigenschappen zoals `HaloSize`, `FontStyle` en `Placement`
- **Hoe ga ik om met grote datasets?** Gebruik `FeatureBasedConfiguration` om labels te prioriteren op basis van attribuutwaarden
- **Heb ik een licentie nodig?** Een proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie

## Wat zijn labelkaartfeatures?
`label map features` betekent het toevoegen van leesbare tekst (zoals stadsnamen, bevolkingscijfers of aangepaste identifiers) aan geometrische objecten—punten, lijnen of polygonen—zodat de kaart zowel ruimtelijke als attribuutinformatie in één oogopslag weergeeft.

## Waarom Aspose.GIS gebruiken voor het labelen van kaartfeatures?
- **Geen externe afhankelijkheden** – pure .NET-bibliotheek, geen native GIS-binaries vereist.  
- **Rijke stylingopties** – halos, aangepaste lettertypen, rotatie en ankerpunten stellen je in staat het uiterlijk nauwkeurig af te stemmen.  
- **Prestatie‑bewust** – ingebouwde feature‑gebaseerde labeling stelt je in staat de belangrijkste labels te prioriteren bij het renderen van grote datasets.  
- **Meerdere uitvoerformaten** – SVG, PNG, PDF, enz., met consistente labelresultaten.

## Vereisten
Zorg ervoor dat je het volgende hebt voordat je begint:

- Een werkende kennis van C# en het .NET-framework.  
- Aspose.GIS voor .NET geïnstalleerd. Je kunt het downloaden **[hier](https://releases.aspose.com/gis/net/)**.  
- Een GeoJSON‑bestand met puntgegevens (of een ander ondersteund vectorformaat).

## Namespaces importeren
Importeer in je C#‑code de benodigde namespaces:

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

We zullen nu verschillende labelscenario's doorlopen, elk voortbouwend op het vorige.

## Punten labelen – Hoe punten labelen
### Stap 1: Stel het pad in naar je documentenmap
```csharp
string dataDir = "Your Document Directory";
```

### Stap 2: Maak een kaart met een eenvoudig markersymbool
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Add a vector layer and apply labeling
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Render the map to an SVG file
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```

In dit eenvoudige voorbeeld **hoe we punten labelen** met behulp van het `name`‑attribuut uit het GeoJSON‑bestand.

## Punten labelen gestyled – Aangepaste labelstijl
Volg stap 1 en 2 van het vorige voorbeeld, en pas vervolgens de labelstijl aan:

```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Rest of the steps remain the same
```

De toegevoegde halo en cursieve lettertype geven de labels een **aangepaste labelstijl** die opvalt tegen drukke achtergronden.

## Punten labelen geplaatst – Geavanceerde plaatsingsopties
Begin opnieuw met stap 1 en 2 van het eerste voorbeeld, en pas vervolgens de plaatsing aan:

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
// Rest of the steps remain the same
```

Hier regelen we ankerpunten, offsets en rotatie, waardoor je fijnmazige controle krijgt over **hoe je punten labelt** in drukke kaartgebieden.

## Punten labelen op basis van features – Labelen van grote datasets
Bij het omgaan met veel punten wil je mogelijk labels prioriteren op basis van een attribuut zoals populatie. Volg stap 1 en 2 van het eerste voorbeeld, en implementeer vervolgens feature‑gebaseerde labeling:

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
        // Retrieve population from the feature.
        var population = feature.GetValue<int>("population");
        // Font size is computed and is based on the population.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // Priority of the label is also based on the population.
        // The greater the priority is, the more likely label will appear on the output image.
        labeling.Priority = population;
    }
};
// Rest of the steps remain the same
```

Deze **labelstrategie voor grote datasets** zorgt ervoor dat de belangrijkste steden (op basis van populatie) eerst worden weergegeven, terwijl minder kritieke punten kunnen worden weggelaten wanneer de ruimte beperkt is.

## Conclusie
Gefeliciteerd! Je kent nu meerdere manieren om **kaartfeatures te labelen** met Aspose.GIS voor .NET — van eenvoudige puntlabeling tot geavanceerde, feature‑gebaseerde styling voor grote datasets. Experimenteer met halos, rotaties en prioriteitsregels om kaarten te maken die precies overbrengen wat je publiek moet zien.

## Veelgestelde vragen

**Q: Kan ik features labelen met aangepaste lettertypen?**  
A: Ja. Stel `FontFamily` en `FontStyle` in de `SimpleLabeling`‑configuratie in om elk geïnstalleerd lettertype te gebruiken.

**Q: Is Aspose.GIS compatibel met andere GIS‑dataformaten?**  
A: Absoluut. Het ondersteunt GeoJSON, Shapefile, KML, GML en nog veel meer formaten.

**Q: Hoe kan ik grote datasets voor labeling verwerken?**  
A: Gebruik `FeatureBasedConfiguration` om prioriteiten toe te wijzen en dynamisch lettergroottes aan te passen op basis van attribuutwaarden, zoals getoond in het feature‑gebaseerde voorbeeld.

**Q: Zijn er geavanceerde opties voor labelplaatsing beschikbaar?**  
A: Ja. Je kunt de plaatsing fijn afstemmen met `PointLabelPlacement`, waarbij je ankerpunten, offsets en rotatie aanpast.

**Q: Kan ik labelgeneratie automatiseren in een batch‑proces?**  
A: Zeker. Plaats de kaartrendercode in een lus of een achtergrondservice om meerdere lagen of bestanden automatisch te verwerken.

---

**Laatst bijgewerkt:** 2026-01-15  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
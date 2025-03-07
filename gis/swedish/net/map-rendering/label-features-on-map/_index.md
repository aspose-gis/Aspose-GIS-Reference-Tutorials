---
title: Bemästra funktionsmärkning med Aspose.GIS för .NET
linktitle: Etikettfunktioner på kartan
second_title: Aspose.GIS .NET API
description: Utforska Aspose.GIS för .NET och bemästra konsten att märka funktioner på kartor. Förbättra dina geospatiala visualiseringar utan ansträngning. #Aspose #GIS
weight: 11
url: /sv/net/map-rendering/label-features-on-map/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bemästra funktionsmärkning med Aspose.GIS för .NET

## Introduktion
en värld av geospatial datavisualisering spelar märkning av funktioner på en karta en avgörande roll för att förmedla information effektivt. Aspose.GIS för .NET tillhandahåller en kraftfull verktygslåda för att uppnå detta sömlöst. I den här handledningen kommer vi att utforska olika metoder för att märka punkter på en karta med Aspose.GIS, vilket förbättrar dina kartvisualiseringar med informativa etiketter.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
- En praktisk kunskap om C# och .NET-ramverket.
-  Aspose.GIS för .NET installerat. Du kan ladda ner den[här](https://releases.aspose.com/gis/net/).
- En GeoJSON-fil som innehåller punktdata. Om du inte har en kan du använda en exempelfil för att testa.
## Importera namnområden
Se till att du importerar de nödvändiga namnrymden i din C#-kod för att arbeta med Aspose.GIS:
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
Låt oss nu dela upp varje exempel i flera steg i ett steg-för-steg-guideformat.
##  Punktmärkning

### Steg 1: Ställ in sökvägen till din dokumentkatalog:
```csharp
string dataDir = "Your Document Directory";
```
### Steg 2: Skapa en karta med en enkel markörsymbol:
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Lägg till ett vektorlager och använd märkning
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Gör kartan till en SVG-fil
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```
## Points Labeling Styled

Följ steg 1 och 2 från föregående exempel.

### Steg 1: Anpassa etikettstilen:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Resten av stegen förblir desamma
```
## Punktmärkning placerad

Följ steg 1 och 2 från det första exemplet.
### Steg 2: Anpassa etikettplaceringen:
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
// Resten av stegen förblir desamma
```
## Poängmärkning Funktionsbaserad

Följ steg 1 och 2 från det första exemplet.

### Steg 1: Implementera funktionsbaserad märkning:
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
        // Hämta population från funktionen.
        var population = feature.GetValue<int>("population");
        // Teckenstorleken beräknas och baseras på populationen.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // Prioriteten för märket baseras också på befolkningen.
        // Ju högre prioritet är, desto mer sannolikt kommer etiketten att visas på utdatabilden.
        labeling.Priority = population;
    }
};
// Resten av stegen förblir desamma
```
## Slutsats
Grattis! Du har lärt dig hur du förbättrar dina kartvisualiseringar genom att märka funktioner med Aspose.GIS för .NET. Experimentera med olika stilar och placeringar för att skapa övertygande kartor som är skräddarsydda för dina data.
## Vanliga frågor
### Kan jag märka funktioner med anpassade teckensnitt?
Ja, du kan anpassa teckensnittsstilen och storleken i etikettkonfigurationen.
### Är Aspose.GIS kompatibel med andra GIS-dataformat?
Aspose.GIS stöder olika geospatiala format, inklusive GeoJSON, Shapefile och mer.
### Hur kan jag hantera stora datamängder för märkning?
Aspose.GIS är optimerat för prestanda, men överväg att använda funktionsbaserade konfigurationer för att prioritera etiketter baserat på dataattribut.
### Finns det avancerade alternativ för etikettplacering?
Ja, du kan finjustera etikettplaceringen med hjälp av alternativ som rotation, ankarpunkter och förskjutningar.
### Kan jag automatisera etikettgenerering i en batchprocess?
Absolut, du kan integrera Aspose.GIS i dina automatiserade arbetsflöden för att skapa batchetiketter.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

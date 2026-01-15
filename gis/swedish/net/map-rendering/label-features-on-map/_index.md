---
date: 2026-01-15
description: Lär dig hur du märker kartfunktioner med Aspose.GIS för .NET, med anpassade
  etikettstilsalternativ för märkning av stora dataset.
linktitle: Label Features on Map
second_title: Aspose.GIS .NET API
title: Etikettera kartobjekt med Aspose.GIS för .NET
url: /sv/net/map-rendering/label-features-on-map/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Märk kartfunktioner med Aspose.GIS för .NET

## Introduktion
Att märka kartfunktioner är avgörande för att omvandla rå geospatial data till tydliga, användarvänliga visualiseringar. I den här handledningen kommer du att upptäcka **hur man märker kartfunktioner** (huvudnyckelordet) med Aspose.GIS för .NET, utforska anpassade etikettstilar och se tekniker som fungerar även med stora datamängder. I slutet kommer du att kunna lägga till informativ text direkt på dina kartor, vilket gör dem mer insiktsfulla för analytiker och slutanvändare.

## Snabba svar
- **Vad är huvudklassen för rendering?** `Map` (Aspose.Gis.Rendering)
- **Vilken märkningsklass lägger till enkel text?** `SimpleLabeling`
- **Kan jag styla etiketter (halo, teckensnitt, rotation)?** Ja – via egenskaper som `HaloSize`, `FontStyle` och `Placement`
- **Hur hanterar man stora datamängder?** Använd `FeatureBasedConfiguration` för att prioritera etiketter baserat på attributvärden
- **Behöver jag en licens?** En provversion fungerar för utveckling; en kommersiell licens krävs för produktion

## Vad är märkning av kartfunktioner?
`label map features` betyder att fästa läsbar text (såsom stadens namn, befolkningsantal eller anpassade identifierare) på geometriska objekt—punkter, linjer eller polygoner—så att kartan förmedlar både rumslig och attributinformation på ett ögonblick.

## Varför använda Aspose.GIS för märkning av kartfunktioner?
- **Inga externa beroenden** – rent .NET-bibliotek, inga inhemska GIS-binärer krävs.  
- **Rika stilalternativ** – halo, anpassade teckensnitt, rotation och ankarnpunkter låter dig finjustera utseendet.  
- **Prestandamedveten** – inbyggd funktionsbaserad märkning låter dig prioritera de viktigaste etiketterna vid rendering av stora datamängder.  
- **Flera utdataformat** – SVG, PNG, PDF osv., med konsekventa märkningsresultat.

## Förutsättningar
Innan du börjar, se till att du har:

- En fungerande kunskap om C# och .NET-ramverket.  
- Aspose.GIS för .NET installerat. Du kan ladda ner det **[here](https://releases.aspose.com/gis/net/)**.  
- En GeoJSON-fil som innehåller punktdata (eller något annat stödd vektorformat).  

## Importera namnrymder
I din C#-kod, importera de nödvändiga namnrymderna:

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

Nu kommer vi att gå igenom flera märkningsscenarier, där varje bygger på det föregående.

## Punktmärkning – Hur man märker punkter
### Steg 1: Ange sökvägen till din dokumentkatalog
```csharp
string dataDir = "Your Document Directory";
```

### Steg 2: Skapa en karta med en enkel markörsymbol
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

I detta grundläggande exempel **hur man märker punkter** med `name`-attributet från GeoJSON-filen.

## Punktmärkning stiliserad – Anpassad etikettstil
Följ steg 1 och 2 från föregående exempel, och anpassa sedan märkningsstilen:

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

Den tillagda haloen och den kursiva teckensnittet ger etiketterna en **anpassad etikettstil** som sticker ut mot röriga bakgrunder.

## Punktmärkning placerad – Avancerade placeringsalternativ
Börja återigen med steg 1 och 2 från det första exemplet, och justera sedan placeringen:

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

Här styr vi ankarnpunkter, förskjutningar och rotation, vilket ger dig finjusterad kontroll över **hur man märker punkter** i trånga kartområden.

## Punktmärkning funktionsbaserad – Märkning av stora datamängder
När du hanterar många punkter kan du vilja prioritera etiketter baserat på ett attribut som befolkning. Följ steg 1 och 2 från det första exemplet, och implementera sedan funktionsbaserad märkning:

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

Denna **strategi för märkning av stora datamängder** säkerställer att de viktigaste städerna (efter befolkning) visas först, medan mindre kritiska punkter kan utelämnas när utrymmet är begränsat.

## Slutsats
Grattis! Du känner nu till flera sätt att **märka kartfunktioner** med Aspose.GIS för .NET—från enkel punktmärkning till sofistikerad, funktionsbaserad stil för stora datamängder. Experimentera med halo, rotationer och prioriteringsregler för att skapa kartor som kommunicerar exakt det din publik behöver se.

## Vanliga frågor

**Q: Kan jag märka funktioner med anpassade teckensnitt?**  
A: Ja. Ställ in `FontFamily` och `FontStyle` i `SimpleLabeling`-konfigurationen för att använda vilket installerat teckensnitt som helst.

**Q: Är Aspose.GIS kompatibel med andra GIS‑dataformat?**  
A: Absolut. Den stödjer GeoJSON, Shapefile, KML, GML och många fler format.

**Q: Hur kan jag hantera stora datamängder för märkning?**  
A: Använd `FeatureBasedConfiguration` för att tilldela prioriteringar och dynamiskt justera teckenstorlekar baserat på attributvärden, som visas i det funktionsbaserade exemplet.

**Q: Finns det avancerade placeringsalternativ för etiketter?**  
A: Ja. Du kan finjustera placeringen med `PointLabelPlacement`, justera ankarnpunkter, förskjutningar och rotation.

**Q: Kan jag automatisera generering av etiketter i en batch‑process?**  
A: Självklart. Inslå kartrenderingskoden i en loop eller en bakgrundstjänst för att automatiskt bearbeta flera lager eller filer.

**Senast uppdaterad:** 2026-01-15  
**Testad med:** Aspose.GIS 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
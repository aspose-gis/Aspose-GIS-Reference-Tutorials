---
date: 2026-01-18
description: Lär dig hur du lägger till städer på kartan och genererar en SVG-karta
  med Aspose.GIS för .NET. Skapa imponerande visualiseringar snabbt.
linktitle: Render a Map
second_title: Aspose.GIS .NET API
title: Hur man lägger till städer på karta med Aspose.GIS för .NET
url: /sv/net/map-rendering/render-a-map/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man lägger till städer på kartan med Aspose.GIS för .NET

## Introduktion
Välkommen till den spännande världen av Aspose.GIS för .NET! I den här steg‑för‑steg‑guiden kommer du att lära dig **hur man lägger till städer på kartan** och generera en högkvalitativ SVG‑utdata. Oavsett om du bygger en skrivbordsdashboard eller en webbaserad GIS‑portal, visar denna handledning hur du ritar vektorlager, ställer in kartdimensioner och laddar en GeoJSON‑karta med lätthet.

## Snabba svar
- **Vad täcker den här handledningen?** Lägga till städer på en karta och exportera den som en SVG‑fil.  
- **Vilket bibliotek krävs?** Aspose.GIS för .NET.  
- **Behöver jag en licens?** En gratis provversion finns tillgänglig; en licens krävs för produktion.  
- **Kan jag använda detta i webbappar?** Ja – samma kod fungerar i ASP.NET, Blazor och andra .NET‑webbramverk.  
- **Vilket utdataformat produceras?** En SVG‑karta som kan visas i webbläsare eller redigeras vidare.

## Förutsättningar
Innan du dyker ner i handledningen, se till att du har följande förutsättningar på plats:
- Aspose.GIS för .NET‑biblioteket: Se till att du har Aspose.GIS för .NET‑biblioteket installerat. Du kan ladda ner det [here](https://releases.aspose.com/gis/net/).
- Datafiler: Förbered de nödvändiga shapefilerna och GeoJSON‑data för handledningen. Du kan hitta exempeldata i dokumentationen eller använda dina egna filer.
- Utvecklingsmiljö: Ha en .NET‑utvecklingsmiljö konfigurerad, inklusive en kodredigerare som Visual Studio.

## Importera namnrymder
För att börja, importera de nödvändiga namnrymderna i ditt .NET‑projekt. Dessa namnrymder är nödvändiga för att arbeta med Aspose.GIS‑funktioner.

```csharp
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.Drawing.Text;
using System.IO;
using System.Linq;
```

## Steg 1: Ställ in kartan (ange kartdimensioner)
```csharp
string dataDir = "Your Document Directory";
using (var map = new Map(800, 476))
{
    // Additional code for map setup can be added here.
}
```
I detta steg initierar vi en ny karta med en bredd på 800 pixlar och en höjd på 476 pixlar. Justera dimensionerna enligt dina designkrav.

## Steg 2: Lägg till en bas karta (rita vektorlager)
```csharp
var baseMapSymbolizer = new SimpleFill { FillColor = Color.Salmon, StrokeWidth = 0.75 };
map.Add(VectorLayer.Open(dataDir + "basemap.shp", Drivers.Shapefile), baseMapSymbolizer);
```
Här **ritar vi ett vektorlager** för bas kartan med en shapefile. Ändra gärna `SimpleFill`‑egenskaperna för att matcha din visuella stil.

## Steg 3: Lägg till städer på kartan (lägg till städer på kartan, ladda GeoJSON‑karta)
```csharp
var citiesSymbolizer = new SimpleMarker() { FillColor = Color.LightBlue };
citiesSymbolizer.FeatureBasedConfiguration = (feature, symbolizer) =>
{
    // Additional configuration logic can be added here.
};
map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), citiesSymbolizer);
```
Detta steg laddar en GeoJSON‑fil som innehåller punktdata för städer och **lägger till städer på kartan**. Du kan förbättra `FeatureBasedConfiguration`‑delegaten för att stilisera städer baserat på attribut som befolkning.

## Steg 4: Rendera kartan (exportera karta som SVG, generera SVG‑karta)
```csharp
map.Render(dataDir + "cities_out.svg", Renderers.Svg);
```
Till sist **exporterar vi kartan som en SVG**‑fil. Den resulterande `cities_out.svg` kan öppnas i vilken modern webbläsare som helst eller i en vektor‑grafikredigerare.

## Slutsats
Grattis! Du har framgångsrikt **lagt till städer på kartan** och genererat en SVG‑karta med Aspose.GIS för .NET. Denna handledning demonstrerade hur man ställer in kartdimensioner, ritar vektorlager, laddar GeoJSON‑data och exporterar resultatet som skalbar SVG – perfekt för både webb- och utskrifts scenarier.

## Vanliga frågor
### Kan jag använda Aspose.GIS för .NET i mina webbapplikationer?
Ja, Aspose.GIS för .NET är lämplig för både skrivbords- och webbapplikationer.

### Finns det en provversion tillgänglig?
Ja, du kan utforska den gratis provversionen [here](https://releases.aspose.com/).

### Var kan jag hitta support för Aspose.GIS för .NET?
Besök [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) för hjälp eller frågor.

### Kan jag köpa en tillfällig licens för korttidsprojekt?
Ja, en tillfällig licens finns tillgänglig [here](https://purchase.aspose.com/temporary-license/).

### Finns det ytterligare handledningar tillgängliga för Aspose.GIS för .NET?
Ja, kolla [documentation](https://reference.aspose.com/gis/net/) för omfattande handledningar och guider.

---

**Senast uppdaterad:** 2026-01-18  
**Testad med:** Aspose.GIS 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
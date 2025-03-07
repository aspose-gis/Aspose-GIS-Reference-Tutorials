---
title: Ställ in linjäriseringstolerans med Aspose.GIS för .NET
linktitle: Ställ in linjäriseringstolerans
second_title: Aspose.GIS .NET API
description: Master Aspose.GIS för .NET för att hantera geospatial data utan ansträngning. Följ denna steg-för-steg handledning och lås upp den fulla potentialen för GIS-utveckling i .NET.
weight: 17
url: /sv/net/geometry-processing/set-linearization-tolerance/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ställ in linjäriseringstolerans med Aspose.GIS för .NET

## Introduktion
en värld av Geographic Information Systems (GIS) utveckling framstår Aspose.GIS för .NET som en kraftfull verktygsuppsättning för att hantera rumslig data med lätthet och effektivitet. Oavsett om du är en erfaren GIS-utvecklare eller precis har börjat, kan behärskning av Aspose.GIS avsevärt förbättra din förmåga att arbeta med geospatial data i .NET-miljöer.
## Förutsättningar
Innan du börjar använda Aspose.GIS för .NET, se till att du har följande förutsättningar på plats:
### 1. Installera Visual Studio
Se till att du har Visual Studio installerat på ditt system. Aspose.GIS för .NET integreras sömlöst med Visual Studio, vilket ger en välbekant utvecklingsmiljö för .NET-utvecklare.
### 2. Skaffa Aspose.GIS-licens
För att låsa upp den fulla potentialen hos Aspose.GIS behöver du en giltig licens. Du kan skaffa en licens från Asposes webbplats eller välja en tillfällig licens för utvärderingssyften.
### 3. Ladda ner Aspose.GIS för .NET
Ladda ner Aspose.GIS för .NET-biblioteket från Asposes webbplats. Du hittar nedladdningslänken i resurserna nedan.
### 4. Bekantskap med C#
Grundläggande kunskaper i programmeringsspråket C# är avgörande för att förstå och implementera exemplen i denna handledning.

## Importera namnområden
Innan du börjar arbeta med Aspose.GIS för .NET, importera de nödvändiga namnrymden till ditt projekt:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
#Låt oss nu dela upp exemplet i flera steg:
## Steg 1: Ställ in linjäriseringstolerans
I det här steget ställer du in linjäriseringstoleransen för GeoJSON-alternativen:
```csharp
var options = new GeoJsonOptions
{
    // linjär geometri måste ligga inom 1e-4 från kurvgeometrin
    LinearizationTolerance = 1e-4,
};
```
## Steg 2: Ange utdatasökväg
Definiera sökvägen där du vill spara utdata-JSON-filen:
```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```
 Byta ut`"Your Document Directory"` med den faktiska katalogsökvägen där du vill spara filen.
## Steg 3: Skapa vektorlager
Skapa ett vektorlager med de angivna alternativen och utmatningsvägen:
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Din kod här
}
```
 Det här kodavsnittet säkerställer korrekt resursförfogande med hjälp av`using` påstående.
## Steg 4: Konstruera geometri
Konstruera en geometri (i det här fallet en cirkulär sträng) som du vill lägga till i lagret:
```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```
Ersätt geometridefinitionen med önskad geometri.
## Steg 5: Lägg till funktion till lager
Konstruera en egenskap och tilldela den geometrin, lägg sedan till egenskapen i vektorlagret:
```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

## Slutsats
Att behärska Aspose.GIS för .NET öppnar upp en värld av möjligheter inom geospatial databehandling och manipulation. Genom att följa denna handledning och utforska den omfattande dokumentationen och resurserna som tillhandahålls av Aspose, kan du lyfta dina GIS-utvecklingsfärdigheter till nya höjder.
## FAQ's
### Är Aspose.GIS för .NET kompatibelt med andra .NET-ramverk?
Ja, Aspose.GIS för .NET är kompatibelt med olika .NET-ramverk, inklusive .NET Core och .NET Standard.
### Kan jag använda Aspose.GIS för .NET i mina kommersiella projekt?
Absolut! Aspose.GIS för .NET erbjuder kommersiella licenser för användning i kommersiella projekt.
### Stöder Aspose.GIS för .NET olika GIS-dataformat?
Ja, Aspose.GIS för .NET stöder ett brett utbud av GIS-dataformat, inklusive GeoJSON, Shapefile, KML och många fler.
### Finns det en testversion tillgänglig för Aspose.GIS för .NET?
Ja, du kan ladda ner en gratis testversion av Aspose.GIS för .NET från Asposes webbplats.
### Var kan jag få support för Aspose.GIS för .NET?
Du kan få support för Aspose.GIS för .NET från Aspose-forumen. Besök supportlänken i resursavsnittet nedan.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

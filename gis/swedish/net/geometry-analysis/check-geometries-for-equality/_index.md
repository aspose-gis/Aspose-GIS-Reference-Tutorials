---
title: Kontrollera geometrier för jämlikhet
linktitle: Kontrollera geometrier för jämlikhet
second_title: Aspose.GIS .NET API
description: Lär dig hur du använder Aspose.GIS för .NET för att kontrollera geometrier för jämlikhet i dina .NET-applikationer med denna omfattande handledning.
weight: 10
url: /sv/net/geometry-analysis/check-geometries-for-equality/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kontrollera geometrier för jämlikhet

## Introduktion
Aspose.GIS för .NET är ett kraftfullt bibliotek som gör det möjligt för utvecklare att arbeta med geospatial data effektivt i sina .NET-applikationer. Oavsett om du bygger kartapplikationer, verktyg för rumslig analys eller integrerar geospatial funktionalitet i befintlig programvara, tillhandahåller Aspose.GIS de verktyg du behöver för att få jobbet gjort.
## Förutsättningar
Innan du börjar använda Aspose.GIS för .NET, se till att du har följande förutsättningar på plats:
### .NET Framework installerat
Se till att du har .NET Framework installerat på ditt system. Du kan ladda ner den från Microsofts webbplats.
### Aspose.GIS för .NET Library
 Ladda ner och installera Aspose.GIS for .NET-biblioteket från[nedladdningssida](https://releases.aspose.com/gis/net/). Följ installationsinstruktionerna i dokumentationen.
### Utvecklingsmiljö
Konfigurera din föredragna utvecklingsmiljö, som Visual Studio, för .NET-utveckling.

## Importera namnområden
I din .NET-applikation importerar du nödvändiga namnområden för att använda Aspose.GIS-funktionalitet:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Steg 1: Definiera geometrier
Definiera först de geometrier du vill jämföra. I det här exemplet har vi två geometrier:`geometry1` och`geometry2`.
```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```
## Steg 2: Kontrollera geometrier för jämlikhet
 Kontrollera nu om geometrierna är rymdmässigt lika med hjälp av`SpatiallyEquals` metod tillhandahållen av Aspose.GIS.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // Sann
```
 Detta kommer att skrivas ut`True` till konsolen sedan`geometry1` och`geometry2` är rumsligt lika.
## Steg 3: Ändra geometri
 Låt oss sedan ändra`geometry2` genom att lägga till en ny punkt.
```csharp
geometry2.AddPoint(3, 3);
```
## Steg 4: Kontrollera jämlikhet igen
Kontrollera nu likheten mellan geometrierna efter modifieringen.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // Falsk
```
 Den här gången blir utgången`False` eftersom geometrierna inte längre är spatialt lika på grund av den modifiering som gjorts till`geometry2`.

## Slutsats
Sammanfattningsvis erbjuder Aspose.GIS för .NET kraftfulla verktyg för att arbeta med geospatial data i .NET-applikationer. Genom att följa denna steg-för-steg-guide kan du enkelt kontrollera geometrier för jämlikhet med Aspose.GIS-metoder.
## FAQ's
### Kan jag använda Aspose.GIS för .NET med andra .NET-ramverk?
Ja, Aspose.GIS för .NET är kompatibelt med olika .NET-ramverk, inklusive .NET Core och .NET Standard.
### Finns det en gratis testversion tillgänglig för Aspose.GIS för .NET?
 Ja, du kan ladda ner en gratis testversion från[släpper sida](https://releases.aspose.com/).
### Var kan jag hitta dokumentation för Aspose.GIS för .NET?
 Du kan hitta detaljerad dokumentation på[Aspose.GIS dokumentationssida](https://reference.aspose.com/gis/net/).
### Hur kan jag få support för Aspose.GIS för .NET?
 Du kan få stöd från Aspose.GIS community forum[här](https://forum.aspose.com/c/gis/33).
### Kan jag köpa en tillfällig licens för Aspose.GIS för .NET?
 Ja, du kan köpa en tillfällig licens från[köpsidan](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

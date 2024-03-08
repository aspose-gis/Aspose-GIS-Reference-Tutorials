---
title: Kontrollera att geometrin innehåller en annan
linktitle: Kontrollera att geometrin innehåller en annan
second_title: Aspose.GIS .NET API
description: Utforska Aspose.GIS för .NET, ett robust bibliotek för sömlös integrering av geospatial data i dina .NET-applikationer.
type: docs
weight: 14
url: /sv/net/geometry-analysis/check-geometry-contains-another/
---
## Introduktion
Aspose.GIS för .NET är ett kraftfullt bibliotek som gör det möjligt för utvecklare att arbeta med geospatial data sömlöst i sina .NET-applikationer. Oavsett om du bygger en kartapplikation, utför geospatial analys eller integrerar platsbaserade funktioner i din programvara, förenklar Aspose.GIS processen genom att tillhandahålla intuitiva API:er och robust funktionalitet.
## Förutsättningar
Innan du börjar använda Aspose.GIS för .NET, se till att du har följande förutsättningar:
### 1. Installation av .NET-utvecklingsmiljö
Se till att du har en fungerande .NET-utvecklingsmiljö inställd på din dator. Detta inkluderar att ha .NET SDK installerat och konfigurerat på rätt sätt.
### 2. Aspose.GIS-installation
 Installera Aspose.GIS för .NET genom att ladda ner biblioteket från releasesidan[här](https://releases.aspose.com/gis/net/) . Följ installationsinstruktionerna i dokumentationen[här](https://reference.aspose.com/gis/net/)för att integrera Aspose.GIS i ditt projekt.
### 3. Grundläggande förståelse för C#
Bekanta dig med programmeringsspråket C# då Aspose.GIS för .NET främst används med C#.

## Importera namnområden
I ditt C#-projekt, importera de nödvändiga namnrymden för att använda Aspose.GIS-funktioner:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Steg 1: Definiera geometriobjekt
Definiera först geometriobjekten med Aspose.GIS-klasser:
```csharp
var geometry1 = new Polygon();
geometry1.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 4),
    new Point(4, 4),
    new Point(4, 0),
    new Point(0, 0),
});
geometry1.AddInteriorRing(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 3),
    new Point(3, 3),
    new Point(3, 1),
    new Point(1, 1),
}));
var geometry2 = new Point(2, 2);
```
## Steg 2: Kontrollera rumslig inneslutning
Kontrollera sedan om en geometri innehåller en annan:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry2)); // Falsk
```
## Steg 3: Definiera en annan geometri
Definiera ett annat geometriobjekt:
```csharp
var geometry3 = new Point(0.5, 0.5);
```
## Steg 4: Kontrollera rumslig inneslutning igen
Kontrollera om den nydefinierade geometrin finns inom den första geometrin:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry3)); // Sann
```
## Steg 5: Motsvarande funktionalitet
 Förstår det`a.SpatiallyContains(b)` är ekvivalent med`b.Within(a)`:
```csharp
Console.WriteLine(geometry3.Within(geometry1)); // Sann
```

## Slutsats
Sammanfattningsvis tillhandahåller Aspose.GIS för .NET kraftfulla verktyg för att hantera geospatial data i .NET-applikationer. Genom att följa den här guiden och använda det medföljande exemplet kan du effektivt utföra kontroller av rumslig inneslutning och utnyttja andra geospatiala funktioner i dina projekt.
## FAQ's
### F1: Är Aspose.GIS kompatibel med .NET Core?
S: Ja, Aspose.GIS stöder fullt ut .NET Core, vilket gör att du kan utveckla geospatiala applikationer över olika plattformar.
### F2: Kan jag utföra geospatial analys med Aspose.GIS?
S: Absolut, Aspose.GIS erbjuder olika funktioner för geospatial analys, inklusive rumsliga frågor, avståndsberäkningar och geometrimanipulationer.
### F3: Hur ofta släpps uppdateringar för Aspose.GIS?
S: Aspose.GIS släpper regelbundet uppdateringar för att förbättra prestanda, lägga till nya funktioner och åtgärda eventuella rapporterade problem. Du kan hålla dig uppdaterad genom att besöka releasesidan.
### F4: Finns det ett communityforum för Aspose.GIS-användare?
S: Ja, du kan gå med i Aspose.GIS-gemenskapsforumet[här](https://forum.aspose.com/c/gis/33) att få kontakt med andra användare, ställa frågor och dela dina erfarenheter.
### F5: Kan jag prova Aspose.GIS innan jag köper?
 S: Visst, du kan utforska Aspose.GIS genom att ladda ner den kostnadsfria testversionen från[här](https://releases.aspose.com/).
---
title: Räkna geometrier i geometri med Aspose.GIS
linktitle: Räkna geometrier i geometri
second_title: Aspose.GIS .NET API
description: Lär dig hur man räknar geometrier i en geometri med Aspose.GIS för .NET. Steg-för-steg handledning med kodexempel för utvecklare.
type: docs
weight: 23
url: /sv/net/geometry-creation/count-geometries-in-geometry/
---
## Introduktion
Aspose.GIS för .NET är ett kraftfullt verktyg för utvecklare som vill införliva geospatial funktionalitet i sina .NET-applikationer. Oavsett om du bygger kartprogram, platsbaserade tjänster eller rumsliga analysverktyg, tillhandahåller Aspose.GIS en omfattande uppsättning funktioner för att möta dina behov. I den här handledningen kommer vi att utforska hur man räknar geometrier inom en geometri med Aspose.GIS för .NET.
## Förutsättningar
Innan du dyker in i den här handledningen, se till att du har följande förutsättningar:
1. Visual Studio: Se till att du har Visual Studio installerat på ditt system.
2. Aspose.GIS för .NET: Ladda ner och installera Aspose.GIS för .NET från[nedladdningssida](https://releases.aspose.com/gis/net/).
3. Grundläggande kunskaper i C#: Bekanta dig med grunderna i programmeringsspråket i C#.

## Importera namnområden
Innan du börjar koda måste du importera de nödvändiga namnrymden för att komma åt Aspose.GIS-funktionalitet.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Steg 2: Skapa punktgeometri
```csharp
Point point = new Point(40.7128, -74.006);
```
 Här skapar vi en`Point` geometri med latitud 40.7128 och longitud -74.006.
## Steg 3: Skapa LineString Geometry
```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```
 Detta steg skapar en`LineString` geometri och lägger till två punkter till den.
## Steg 4: Skapa geometrisamling
```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```
 Vi skapar sedan en`GeometryCollection` och lägg till de tidigare skapade punkt- och linjegeometrierna till den.
## Steg 5: Räkna geometrier
```csharp
int geometriesCount = geometryCollection.Count;
```
 Detta steg räknar antalet geometrier inom`GeometryCollection`.
## Steg 6: Visa antalet
```csharp
Console.WriteLine(geometriesCount); // 2
```
 Slutligen skriver vi ut antalet geometrier, vilket i det här fallet är`2`.

## Slutsats
den här handledningen har vi lärt oss hur man räknar geometrier inom en geometri med Aspose.GIS för .NET. Genom att följa dessa steg kan du enkelt integrera geospatial funktionalitet i dina .NET-applikationer.
## FAQ's
### Är Aspose.GIS för .NET lämplig för både skrivbords- och webbapplikationer?
Ja, Aspose.GIS för .NET kan användas i både skrivbords- och webbapplikationer sömlöst.
### Kan jag utföra rumsliga frågor med Aspose.GIS för .NET?
Absolut, Aspose.GIS för .NET ger robust stöd för att utföra rumsliga frågor om geometrier.
### Stöder Aspose.GIS för .NET olika GIS-filformat?
Ja, Aspose.GIS för .NET stöder ett brett utbud av GIS-filformat inklusive SHP, KML och GeoJSON.
### Finns det en gratis testversion tillgänglig för Aspose.GIS för .NET?
 Ja, du kan ladda ner en gratis testversion från[hemsida](https://releases.aspose.com/).
### Var kan jag hitta support för Aspose.GIS för .NET?
 Du kan hitta support på[Aspose.GIS forum](https://forum.aspose.com/c/gis/33).
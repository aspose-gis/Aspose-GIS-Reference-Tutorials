---
title: Skapa polygon med hålgeometri med Aspose.GIS
linktitle: Skapa polygon med hålgeometri
second_title: Aspose.GIS .NET API
description: Lär dig hur du skapar polygon med hålgeometri med Aspose.GIS för .NET. Steg-för-steg handledning med kodexempel.
weight: 13
url: /sv/net/geometry-creation/create-polygon-with-hole-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa polygon med hålgeometri med Aspose.GIS

## Introduktion
I den här handledningen går vi igenom processen att skapa en polygon med en hålgeometri med Aspose.GIS för .NET. Aspose.GIS är ett kraftfullt bibliotek som gör det möjligt för utvecklare att arbeta med geospatial data i sina .NET-applikationer. 
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Aspose.GIS för .NET Library: Du kan ladda ner det från[här](https://releases.aspose.com/gis/net/).
2. Utvecklingsmiljö: Se till att du har en utvecklingsmiljö inställd med Visual Studio eller någon annan .NET IDE installerad.
## Importera namnområden
Först måste du importera de nödvändiga namnrymden för att arbeta med Aspose.GIS-funktioner. Så här gör du:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Låt oss nu fortsätta att skapa en polygon med en hålgeometri med Aspose.GIS för .NET.
## Steg 1: Skapa polygonobjekt
```csharp
Polygon polygon = new Polygon();
```
## Steg 2: Definiera yttre ring
```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```
## Steg 3: Definiera inre ring (hål)
```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```
## Steg 4: Tilldela yttre ring och lägg till inre ring till polygon
```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```
## Slutsats
Grattis! Du har framgångsrikt lärt dig hur man skapar en polygon med en hålgeometri med Aspose.GIS för .NET. Denna kunskap kommer att vara till nytta för olika geospatiala tillämpningar där sådana geometrier är väsentliga.
## FAQ's
### 1. Vad är Aspose.GIS?
Aspose.GIS är ett .NET-bibliotek som gör det möjligt för utvecklare att arbeta med geospatiala data, så att de kan skapa, läsa och manipulera olika geospatiala filformat.
### 2. Kan jag använda Aspose.GIS för kommersiella projekt?
 Ja, du kan använda Aspose.GIS för både personliga och kommersiella projekt genom att köpa en licens. Besök[här](https://purchase.aspose.com/buy) för mer detaljer.
### 3. Finns det en gratis testversion tillgänglig för Aspose.GIS?
 Ja, du kan använda en gratis provversion av Aspose.GIS från[här](https://releases.aspose.com/).
### 4. Var kan jag hitta support för Aspose.GIS?
 Du kan hitta support för Aspose.GIS på[Aspose.GIS forum](https://forum.aspose.com/c/gis/33).
### 5. Hur kan jag få en tillfällig licens för Aspose.GIS?
 Du kan få en tillfällig licens för Aspose.GIS från[här](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

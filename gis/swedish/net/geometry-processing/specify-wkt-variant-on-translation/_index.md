---
title: Ange WKT-variant på översättning med Aspose.GIS
linktitle: Ange WKT-variant på översättning
second_title: Aspose.GIS .NET API
description: Lär dig hur du specificerar WKT-varianter i Aspose.GIS för .NET för att effektivt kontrollera rumsliga datarepresentationsformat och precision.
weight: 19
url: /sv/net/geometry-processing/specify-wkt-variant-on-translation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ange WKT-variant på översättning med Aspose.GIS

## Introduktion
Aspose.GIS för .NET är ett kraftfullt bibliotek som låter utvecklare arbeta med GIS-data (geografiska informationssystem) i sina .NET-applikationer utan ansträngning. En av de väsentliga funktionerna som tillhandahålls av Aspose.GIS är möjligheten att specificera varianten Well-Known Text (WKT) under översättning, vilket gör det möjligt för användare att kontrollera formatet och precisionen för rumsliga datarepresentationer. I den här handledningen kommer vi att utforska hur man anger WKT-varianter steg för steg med Aspose.GIS för .NET.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar på plats:
1. Aspose.GIS för .NET: Ladda ner och installera Aspose.GIS för .NET från[nedladdningssida](https://releases.aspose.com/gis/net/).
2. Utvecklingsmiljö: Se till att du har en .NET-utvecklingsmiljö inrättad.
3. Grundläggande kunskaper: Kännedom om programmeringsspråket C# och .NET framework.

## Importera namnområden
Innan du använder Aspose.GIS-funktionalitet i din kod, importera de nödvändiga namnrymden:
```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```
## Steg 1: Skapa ett punktobjekt
 Skapa först en`Point` objekt med värden för latitud, longitud och valfritt mått (M):
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## Steg 2: Ställ in Spatial Reference System (SRS)
Tilldela ett rumsligt referenssystem (SRS) till punktobjektet. I det här exemplet använder vi det rumsliga referenssystemet WGS84:
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## Steg 3: Ange WKT-variant
 Ange nu WKT-varianten för översättning. Aspose.GIS stöder olika WKT-varianter, inklusive`Iso`, `SimpleFeatureAccessOutdated` , och`ExtendedPostGis`. Välj lämplig variant baserat på dina krav:
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // PUNKT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```
## Steg 4: Kontrollera numeriskt format
Du kan styra det numeriska formatet för koordinaterna i WKT-representationen. Aspose.GIS tillhandahåller alternativ för att ange decimalprecisionen:
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // PUNKT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // PUNKT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // PUNKT M (23,6 25,3 40,3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // PUNKT M (23.573 25.342 40.3)
```

## Slutsats
den här handledningen har vi lärt oss hur man specificerar WKT-varianter för översättning med Aspose.GIS för .NET. Genom att följa stegen som beskrivs ovan kan utvecklare effektivt kontrollera formatet och precisionen för rumsliga datarepresentationer i sina .NET-applikationer, vilket förbättrar flexibiliteten och användbarheten hos geografiska informationssystem.
## FAQ's
### Är Aspose.GIS kompatibel med alla versioner av .NET?
Ja, Aspose.GIS stöder .NET Framework 4.0 och högre.
### Kan jag använda Aspose.GIS för kommersiella projekt?
Ja, Aspose.GIS kan användas för både personliga och kommersiella projekt.
### Ger Aspose.GIS stöd för andra rumsliga dataformat?
Ja, Aspose.GIS stöder ett brett utbud av rumsliga dataformat, inklusive ESRI Shapefile, GeoJSON och KML.
### Finns det en gratis testversion tillgänglig för Aspose.GIS?
 Ja, du kan ladda ner en gratis testversion av Aspose.GIS från[här](https://releases.aspose.com/).
### Var kan jag få hjälp eller support för Aspose.GIS?
 Du kan skicka dina frågor eller söka hjälp från Aspose.GIS-gemenskapen på[forum](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

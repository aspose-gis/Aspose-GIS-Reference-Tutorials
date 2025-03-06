---
title: Ange objekt-ID och geometrifältnamn
linktitle: Ange objekt-ID och geometrifältnamn
second_title: Aspose.GIS .NET API
description: Utforska GIS-magi med Aspose.GIS för .NET! Hantera geospatial data utan ansträngning. Ladda ner nu och släpp lös kraften i rumslig intelligens.
weight: 20
url: /sv/net/layer-data-operations/specify-object-id-and-geometry-field-names/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ange objekt-ID och geometrifältnamn

## Introduktion
Att ge dig ut på en resa in i riket av Geographic Information Systems (GIS) med Aspose.GIS för .NET öppnar upp en värld av möjligheter för både utvecklare och entusiaster. Detta kraftfulla bibliotek ger dig möjlighet att hantera geospatial data utan ansträngning. I den här handledningen guidar vi dig genom processen att specificera objekt-ID och geometrifältnamn, vilket lägger grunden för dina GIS-strävanden.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
-  Aspose.GIS för .NET: Ladda ner och installera biblioteket från[här](https://releases.aspose.com/gis/net/).
- Dokumentkatalog: Skapa en katalog för dina dokument för att lagra geodatabaserna.
- .NET-miljö: Se till att du har en fungerande .NET-miljö.
## Importera namnområden
För att komma igång måste du importera de nödvändiga namnrymden till ditt projekt. Dessa namnområden tillhandahåller de väsentliga klasserna och metoderna för att interagera med Aspose.GIS för .NET.
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```
## Steg 1: Ange objekt-ID och geometrifältnamn
I det här steget lär du dig hur du ställer in objekt-ID och geometrifältnamn för dina GIS-data. Detta är avgörande för effektiv datahantering.
## Steg 1.1: Ställ in dokumentkatalog
Börja med att definiera sökvägen till din dokumentkatalog:
```csharp
string dataDir = "Your Document Directory";
```
## Steg 1.2: Skapa en GeoDatabas och definiera alternativ
Skapa en GeoDatabas med specificerat objekt-ID och geometrifältnamn:
```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Ange objekt-ID-fältnamnet
        GeometryFieldName = "POINT",       // Ange namnet på Geometrifältet
    };
```
## Steg 1.3: Skapa och lägg till ett lager
Skapa ett lager i GeoDatabasen och lägg till en funktion med en specifik geometri:
```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  //Ange geometrin (i det här fallet en punkt)
    layer.Add(feature);
}
```
## Steg 1.4: Öppna och hämta data från lagret
Öppna lagret och hämta data från det baserat på det angivna objekt-ID:t:
```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Utgång: 1
}
```
## Slutsats
Grattis! Du har framgångsrikt navigerat genom processen att ange objekt-ID och geometrifältnamn med Aspose.GIS för .NET. Detta lägger en solid grund för dina GIS-projekt, vilket gör att du enkelt kan hantera geospatial data.
## Vanliga frågor
### F: Kan jag använda Aspose.GIS för .NET i mina webbapplikationer?
S: Ja, Aspose.GIS för .NET är lämplig för både skrivbords- och webbapplikationer, vilket ger mångsidiga geospatiala möjligheter.
### F: Finns det en testversion innan köp?
 S: Ja, du kan utforska funktionerna i Aspose.GIS för .NET med en gratis testversion tillgänglig[här](https://releases.aspose.com/).
### F: Hur kan jag få en tillfällig licens för Aspose.GIS för .NET?
 S: Du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/) i utvärderingssyfte.
### F: Vilka rumsliga referenssystem stöder Aspose.GIS för .NET?
S: Aspose.GIS för .NET stöder olika rumsliga referenssystem, vilket ger flexibilitet för olika geografiska datamängder.
### F: Var kan jag söka hjälp eller diskutera Aspose.GIS-relaterade frågor?
 S: Besök Aspose.GIS-forumet[här](https://forum.aspose.com/c/gis/33) för stöd och diskussioner.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

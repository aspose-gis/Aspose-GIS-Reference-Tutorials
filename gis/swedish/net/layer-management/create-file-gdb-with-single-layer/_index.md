---
title: Skapa fil GDB med ett lager
linktitle: Skapa fil GDB med ett lager
second_title: Aspose.GIS .NET API
description: Lås upp potentialen för geospatial datahantering i .NET med Aspose.GIS. Lär dig hur du skapar filgeodatabaser och lager steg för steg. Ladda ner nu!
type: docs
weight: 11
url: /sv/net/layer-management/create-file-gdb-with-single-layer/
---
## Introduktion
Är du redo att lyfta dina geospatiala applikationer med robusta filgeodatabaser och lager? Leta inte längre än Aspose.GIS för .NET. I den här handledningen går vi igenom processen att skapa en filgeodatabas (GDB) med ett enda lager med Aspose.GIS för .NET. Utnyttja kraften i hantering och visualisering av rumslig data i dina .NET-applikationer utan ansträngning.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
1.  Aspose.GIS för .NET: Se till att du har Aspose.GIS-biblioteket installerat. Du kan ladda ner den från[Aspose.GIS för .NET nedladdningssida](https://releases.aspose.com/gis/net/).
2. Utvecklingsmiljö: Konfigurera en fungerande .NET-utvecklingsmiljö på din maskin.
3. Dokumentkatalog: Välj eller skapa en katalog på ditt system där du ska lagra dina geospatiala datafiler.
## Importera namnområden
För att komma igång måste du importera de nödvändiga namnrymden i ditt .NET-projekt. Dessa namnrymder ger åtkomst till Aspose.GIS-funktionerna. Lägg till följande rader i början av din kodfil:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```
## Steg 1: Konfigurera din dokumentkatalog
```csharp
string dataDir = "Your Document Directory";
```
Ersätt "Din dokumentkatalog" med sökvägen till den katalog där du vill lagra dina geospatiala datafiler.
## Steg 2: Skapa en filgeodatabas med ett enda lager
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Detta kodavsnitt skapar en filgeodatabas med ett enda lager och lägger till en linjefunktion till den.
## Steg 3: Öppna filgeodatabasen och hämta lagerinformation
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Utdata: Antal funktioner: 1
}
```
I det här steget öppnar vi den skapade filgeodatabasen, hämtar lagret som heter "lager" och skriver ut antalet funktioner i lagret.
## Slutsats
Grattis! Du har framgångsrikt skapat en filgeodatabas med ett enda lager med Aspose.GIS för .NET. Utforska de enorma funktionerna för hantering av rumslig data i dina applikationer med lätthet.
## Vanliga frågor
### Kan jag använda Aspose.GIS för .NET i mina befintliga .NET-projekt?
Ja, Aspose.GIS för .NET kan sömlöst integreras i dina befintliga .NET-projekt.
### Finns det en testversion tillgänglig för Aspose.GIS för .NET?
 Ja, du kan utforska funktionerna i Aspose.GIS för .NET genom att ladda ner[gratis testversion](https://releases.aspose.com/).
### Var kan jag hitta detaljerad dokumentation för Aspose.GIS för .NET?
 Referera till[dokumentation](https://reference.aspose.com/gis/net/) för omfattande information om Aspose.GIS för .NET.
### Hur kan jag få support för Aspose.GIS för .NET?
 Besök[Aspose.GIS forum](https://forum.aspose.com/c/gis/33) för samhällsstöd och hjälp.
### Finns tillfälliga licenser tillgängliga för Aspose.GIS för .NET?
 Ja, du kan få en[tillfällig licens](https://purchase.aspose.com/temporary-license/) för Aspose.GIS för .NET.
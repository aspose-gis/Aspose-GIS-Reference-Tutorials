---
title: Skapa vektorlager med SRS
linktitle: Skapa vektorlager med SRS
second_title: Aspose.GIS .NET API
description: Utforska Aspose.GIS för .NET - din nyckel till sömlös GIS-integration. Skapa vektorlager utan ansträngning med specificerade rumsliga referenssystem. Ladda ner nu!
weight: 13
url: /sv/net/layer-management/create-vector-layer-with-srs/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa vektorlager med SRS

## Introduktion
Aspose.GIS för .NET är ett kraftfullt bibliotek som gör det möjligt för utvecklare att arbeta med geografiska informationssystem (GIS) data sömlöst i .NET-applikationer. I den här handledningen kommer vi att fokusera på att skapa ett vektorlager med ett rumsligt referenssystem (SRS). I slutet av den här guiden kommer du att utan ansträngning kunna integrera GIS-funktioner i dina .NET-projekt.
## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:
- Grundläggande kunskap om C# och .NET utveckling.
-  Aspose.GIS för .NET-biblioteket installerat. Du kan ladda ner den[här](https://releases.aspose.com/gis/net/).
- En utvecklingsmiljö inrättad och redo.
## Importera namnområden
Se till att du har de nödvändiga namnrymden importerade i början av din C#-fil:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Steg 1: Konfigurera det projekterade spatiala referenssystemet
Låt oss skapa ett projicerat rumsligt referenssystem (SRS) med hjälp av World Mercator-projektionen som ett exempel. Följ dessa steg:
```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```
## Steg 2: Skapa ett vektorlager och lägg till funktioner
Låt oss nu skapa en shapefil och lägga till funktioner med den angivna SRS:
```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // Detta ger ett undantag eftersom geometrin har en annan SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## Steg 3: Verifiera det rumsliga referenssystemet
Slutligen, låt oss öppna lagret och verifiera dess rumsliga referenssystem:
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Bör returnera sant
}
```
Genom att följa dessa steg har du framgångsrikt skapat ett vektorlager med ett specificerat rumsligt referenssystem med Aspose.GIS för .NET.
## Slutsats
Att integrera GIS-funktionalitet i dina .NET-applikationer har aldrig varit enklare, tack vare Aspose.GIS. Med möjligheten att enkelt skapa vektorlager och hantera rumsliga referenssystem kan du förbättra dina projekt med kraftfulla geospatiala funktioner.
## Vanliga frågor
### Är Aspose.GIS kompatibel med alla GIS-filformat?
 Aspose.GIS stöder olika GIS-format, inklusive Shapefile, GeoJSON, KML och mer. Kolla[dokumentation](https://reference.aspose.com/gis/net/) för hela listan.
### Kan jag använda Aspose.GIS i en webbapplikation?
Absolut! Aspose.GIS för .NET är mångsidig och kan användas i webbapplikationer, stationära applikationer och till och med mobilappar.
### Var kan jag få support för Aspose.GIS?
 Du kan hitta en hjälpsam gemenskap på[Aspose.GIS forum](https://forum.aspose.com/c/gis/33) för alla frågor eller problem du kan stöta på.
### Finns det en gratis provperiod?
 Ja, du kan utforska funktionerna i Aspose.GIS genom att få en gratis provperiod[här](https://releases.aspose.com/).
### Hur kan jag köpa en licens för Aspose.GIS?
 För att köpa en licens, besök[köpsidan](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

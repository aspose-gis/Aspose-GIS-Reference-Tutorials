---
date: 2026-01-15
description: Utforska Aspose.GIS för .NET för att skapa ett vektorlager med ett rumsligt
  referenssystem. Lär dig hur du ställer in SRS, skapar lager och hanterar GIS‑data.
  Ladda ner nu!
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: Skapa vektorlager med SRS
url: /sv/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa vektorlager med SRS

## Introduktion
Aspose.GIS for .NET är ett kraftfullt bibliotek som gör det möjligt för utvecklare att **create vector layer** objekt och arbeta med geografiska informationssystem (GIS) data sömlöst i .NET-applikationer. I den här handledningen går vi igenom hur man skapar ett vektorlager med ett spatialt referenssystem (SRS), varför du vill ange en spatial referens och vilka fördelar detta ger för verkliga projekt. I slutet av guiden kommer du att kunna integrera GIS-funktioner i dina .NET-lösningar med förtroende.

## Snabba svar
- **Vad är huvudsyftet med den här handledningen?** Att visa hur man skapar ett vektorlager med ett specificerat SRS med hjälp av Aspose.GIS för .NET.  
- **Vilken projektion används i exemplet?** World Mercator (EPSG:3395).  
- **Behöver jag en licens för att köra koden?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Kan jag använda samma metod med andra GIS-format?** Ja, samma SRS‑hantering gäller för Shapefile, GeoJSON, KML osv.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Vad är ett vektorlager och varför ange dess spatiala referens?
Ett **vector layer** lagrar geometriska funktioner (punkter, linjer, polygoner) tillsammans med attributdata. Att tilldela en **spatial reference** (SRS) talar om för GIS‑programvaran hur dessa koordinater ska tolkas på jordens yta. Att ange rätt SRS säkerställer exakta mätningar, korrekt överlagring med andra lager och pålitliga kartvisualiseringar.

## Förutsättningar
- Grundläggande kunskap om C# och .NET‑utveckling.  
- Aspose.GIS för .NET‑biblioteket installerat. Du kan ladda ner det **[here](https://releases.aspose.com/gis/net/)**.  
- En utvecklingsmiljö (Visual Studio, VS Code eller någon C#‑IDE).  

## Importera namnrymder
Se till att du har de nödvändiga namnrymderna importerade högst upp i din C#‑fil:

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

## Så sätter du spatial reference (SRS) – Steg 1
Låt oss skapa ett **projected spatial reference system** med World Mercator-projektionen som exempel. Detta demonstrerar **how to set srs** för ett lager.

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

## Så skapar du lager – Steg 2
Nu kommer vi att **create a vector layer** (en Shapefile) och lägga till funktioner som använder det SRS vi just definierade. Denna del svarar på **how to create layer** med Aspose.GIS.

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
        layer.Add(feature); // This will throw an exception as the geometry has a different SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```

> **Pro tip:** Verifiera alltid att geometrins `SpatialReferenceSystem` matchar lagrets SRS innan du lägger till den. Mismatcherade SRS‑värden kastar ett `GisException`, som visas ovan.

## Verifiera Spatial Reference System – Steg 3
Slutligen, öppna lagret och bekräfta att SRS har tillämpats korrekt.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Om anropet `IsEquivalent` returnerar `true` har du framgångsrikt **create vector layer** med den önskade spatiala referensen.

## Vanliga problem & lösningar
| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| `GisException` när en funktion läggs till | Geometri använder ett annat SRS än lagret | Ställ in `feature.Geometry.SpatialReferenceSystem` till lagrets SRS innan du lägger till |
| Lagret visas tomt i GIS‑programvara | Shapefilen skapades utan en korrekt `.prj`‑fil | Se till att `projectedSrs`‑objektet skickas med när lagret skapas |
| Oväntade koordinatvärden | Fel projektionparametrar (t.ex. centralmeridianen) | Dubbelkolla parametrarna som skickas till `AddProjectionParameter` |

## Vanliga frågor
### Är Aspose.GIS kompatibel med alla GIS‑filformat?
Aspose.GIS stödjer olika GIS‑format, inklusive Shapefile, GeoJSON, KML och mer. Se **[documentation](https://reference.aspose.com/gis/net/)** för den kompletta listan.

### Kan jag använda Aspose.GIS i en webbapplikation?
Absolut! Aspose.GIS för .NET är mångsidigt och kan användas i webbapplikationer, skrivbordsapplikationer och även mobilappar.

### Var kan jag få support för Aspose.GIS?
Du kan hitta en hjälpsam community på **[Aspose.GIS forum](https://forum.aspose.com/c/gis/33)** för eventuella frågor eller problem du kan stöta på.

### Finns det en gratis provversion tillgänglig?
Ja, du kan utforska funktionerna i Aspose.GIS genom att skaffa en gratis provversion **[here](https://releases.aspose.com/)**.

### Hur kan jag köpa en licens för Aspose.GIS?
För att köpa en licens, besök **[purchase page](https://purchase.aspose.com/buy)**.

## Vanliga frågor (ytterligare)

**Q: Vad händer om jag försöker lägga till en geometri med ett annat SRS?**  
A: Aspose.GIS kastar ett `GisException`. Du måste antingen reprojicera geometrin eller säkerställa att den delar lagrets SRS.

**Q: Kan jag ändra SRS för ett befintligt lager?**  
A: Ja, du kan skapa ett nytt lager med önskad SRS och kopiera funktioner dit, reprojicera dem vid behov.

**Q: Är det möjligt att arbeta med 3D‑koordinater?**  
A: Aspose.GIS stödjer Z‑koordinater; använd bara geometrikonstruktörer som accepterar ett Z‑värde.

**Q: Hantera biblioteket datumtransformeringar automatiskt?**  
A: När du reprojicerar geometrier med `Geometry.Transform` utför Aspose.GIS den nödvändiga datumförskjutningen.

**Q: Vilka .NET‑versioner är officiellt testade?**  
A: Biblioteket är testat med .NET Framework 4.5+, .NET Core 3.1+, och .NET 5/6/7.

## Slutsats
Du har nu lärt dig hur man **create vector layer** med ett anpassat spatialt referenssystem med hjälp av Aspose.GIS för .NET. Genom att ange rätt SRS, hantera geometri konsekvent och verifiera lagrets metadata kan du bygga robusta GIS‑aktiverade applikationer som fungerar med all standard GIS‑programvara.

---

**Senast uppdaterad:** 2026-01-15  
**Testat med:** Aspose.GIS 24.11 för .NET (senaste vid skrivande stund)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
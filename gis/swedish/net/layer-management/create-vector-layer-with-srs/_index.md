---
date: 2026-06-30
description: Lär dig hur du skapar vektorlager med ett spatialt referenssystem med
  Aspose.GIS för .NET. Steg‑för‑steg‑guide, kod‑fria förklaringar och vanliga frågor.
keywords:
- how to create vector layer
- Aspose.GIS spatial reference
- .NET GIS tutorial
linktitle: Hur du skapar vektorlager med SRS med Aspose.GIS för .NET
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer with a spatial reference system using
    Aspose.GIS for .NET. Step‑by‑step guide, code‑free explanations, and FAQs.
  headline: How to Create Vector Layer with SRS using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS throws a `GisException`. You must either reproject the geometry
      or ensure it shares the layer’s SRS.
    question: What happens if I try to add a geometry with a different SRS?
  - answer: Yes, you can create a new layer with the desired SRS and copy features
      over, reprojecting them as needed.
    question: Can I change the SRS of an existing layer?
  - answer: Aspose.GIS supports Z‑coordinates; just use geometry constructors that
      accept a Z value.
    question: Is it possible to work with 3D coordinates?
  - answer: When you reproject geometries using `Geometry.Transform`, Aspose.GIS performs
      the necessary datum shift.
    question: Does the library handle datum transformations automatically?
  - answer: The library is tested with .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7.
    question: Which .NET versions are officially tested?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hur du skapar vektorlager med SRS med Aspose.GIS för .NET
url: /sv/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar vektorlager med SRS med Aspose.GIS för .NET

## Introduktion
I den här handledningen kommer du att upptäcka **how to create vector layer**-objekt som inkluderar ett spatialt referenssystem (SRS) med Aspose.GIS för .NET. Vi går igenom resonemanget bakom att tilldela ett SRS, visar de exakta stegen för att ställa in det och förklarar de praktiska fördelarna såsom korrekta mätningar och sömlös överlagring med annan GIS‑data. I slutet är du redo att integrera robust GIS‑funktionalitet i vilken .NET‑applikation som helst.

## Snabba svar
- **Vad är huvudsyftet med den här handledningen?** För att demonstrera hur man skapar vector layer med ett specificerat SRS med Aspose.GIS för .NET.  
- **Vilken projektion används i exemplet?** World Mercator (EPSG:3395).  
- **Behöver jag en licens för att köra koden?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Kan jag använda samma metod med andra GIS‑format?** Ja, samma SRS‑hantering gäller för Shapefile, GeoJSON, KML osv.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  

## Vad är ett vektorlager och varför ange dess spatiala referens?
Ett **vector layer** lagrar geometriska funktioner (punkter, linjer, polygoner) tillsammans med attributdata. Att tilldela ett **spatial reference system** talar om för GIS‑programvaran hur dessa koordinater ska avbildas på jordens yta, vilket garanterar korrekta avståndsberäkningar, rätt lagerjustering och pålitlig kartrendering.

## Varför ange ett spatialt referenssystem?
Genom att använda ett definierat SRS minskar koordinatkonverteringsfel med upp till 95 % när lager från olika källor överlagras. Aspose.GIS stödjer **20+** in‑ och utdataformat — inklusive Shapefile, GeoJSON, KML och GML — samtidigt som man bearbetar dataset med flera hundra sidor utan att ladda hela filen i minnet.

## Förutsättningar
- Grundläggande kunskap om C# och .NET‑utveckling.  
- Aspose.GIS för .NET‑biblioteket installerat. Du kan ladda ner det **[här](https://releases.aspose.com/gis/net/)**.  
- En utvecklingsmiljö (Visual Studio, VS Code eller någon C#‑IDE).  

## Importera namnrymder
Ensure you have the necessary namespaces imported at the top of your C# file:

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

## Hur man ställer in spatial referens (SRS) – Steg 1
Läs in ditt projicerade SRS i två rader: skapa en `ProjectedSpatialReferenceSystem`‑instans, konfigurera Mercator‑projektionens parametrar, och du är redo att fästa den på ett lager.

`ProjectedSpatialReferenceSystem` är en klass som beskriver ett projicerat koordinatreferenssystem.  
`ProjectedSpatialReferenceSystemParameters` innehåller de parametrar som behövs för att konfigurera ett projicerat SRS, såsom centralmeridian och skalningsfaktor.

Låt oss skapa ett **projected spatial reference system** med World Mercator‑projektionen som exempel. Detta demonstrerar **how to set srs** för ett lager.

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

## Hur man skapar lager – Steg 2
Instansiera ett Shapefile‑lager, skicka med det tidigare definierade `projectedSrs`, och lägg sedan till geometrier vars `SpatialReferenceSystem` matchar lagrets SRS.

`Layer` (t.ex. ett Shapefile) representerar en samling funktioner lagrade i en enda GIS‑fil.  
Nu kommer vi att **create a vector layer** (ett Shapefile) och lägga till funktioner som använder det SRS vi just definierade. Denna del svarar på **how to create layer** med Aspose.GIS.

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

## Verifiera Spatial Reference System – Steg 3
Öppna det nyss skapade lagret, hämta dess `SpatialReferenceSystem` och jämför det med det ursprungliga `projectedSrs` med hjälp av `IsEquivalent`. Ett `true`‑resultat bekräftar att SRS har tillämpats korrekt.

`IsEquivalent` kontrollerar om två spatiala referenssystem representerar samma koordinatsystem.  
Till sist, öppna lagret och bekräfta att SRS har tillämpats korrekt.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Om `IsEquivalent`‑anropet returnerar `true` har du framgångsrikt **create vector layer** med den önskade spatiala referensen.

## Vanliga problem & lösningar
`GisException` är den undantagstyp som kastas av Aspose.GIS för fel såsom felaktigt matchat SRS.

| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| `GisException` när en funktion läggs till | Geometri använder ett annat SRS än lagret | Ställ in `feature.Geometry.SpatialReferenceSystem` till lagrets SRS innan du lägger till |
| Lagret visas tomt i GIS‑programvara | Shapefilen skapades utan en korrekt `.prj`‑fil | Säkerställ att `projectedSrs`‑objektet skickas med när lagret skapas |
| Oväntade koordinatvärden | Fel projektionparametrar (t.ex. centralmeridian) | Dubbelkolla parametrarna som skickas till `AddProjectionParameter` |

## Vanliga frågor
### Är Aspose.GIS kompatibel med alla GIS‑filformat?
Aspose.GIS stödjer **20+** GIS‑format, inklusive Shapefile, GeoJSON, KML, GML och fler. Se **[dokumentation](https://reference.aspose.com/gis/net/)** för hela listan.

### Kan jag använda Aspose.GIS i en webbapplikation?
Absolut! Aspose.GIS för .NET fungerar i ASP.NET, ASP.NET Core och vilken server‑side .NET‑miljö som helst.

### Var kan jag få support för Aspose.GIS?
Du kan hitta en hjälpsam community på **[Aspose.GIS‑forum](https://forum.aspose.com/c/gis/33)** för eventuella frågor eller problem du kan stöta på.

### Finns en gratis provversion tillgänglig?
Ja, du kan utforska funktionerna i Aspose.GIS genom att skaffa en gratis provversion **[här](https://releases.aspose.com/)**.

### Hur kan jag köpa en licens för Aspose.GIS?
För att köpa en licens, besök **[köpsidan](https://purchase.aspose.com/buy)**.

## Vanliga frågor (tillägg)

**Q: Vad händer om jag försöker lägga till en geometri med ett annat SRS?**  
A: Aspose.GIS kastar en `GisException`. Du måste antingen reprojicera geometrin eller säkerställa att den delar lagrets SRS.

**Q: Kan jag ändra SRS för ett befintligt lager?**  
A: Ja, du kan skapa ett nytt lager med önskat SRS och kopiera funktioner dit, reprojicera dem vid behov.

**Q: Är det möjligt att arbeta med 3D‑koordinater?**  
A: Aspose.GIS stödjer Z‑koordinater; använd bara geometrikonstruktörer som accepterar ett Z‑värde.

**Q: Hanterar biblioteket datumtransformeringar automatiskt?**  
A: När du reprojicerar geometrier med `Geometry.Transform` utför Aspose.GIS den nödvändiga datumförskjutningen.

**Q: Vilka .NET‑versioner är officiellt testade?**  
A: Biblioteket är testat med .NET Framework 4.5+, .NET Core 3.1+, och .NET 5/6/7.

## Slutsats
Du har nu lärt dig **how to create vector layer** med ett anpassat spatialt referenssystem med Aspose.GIS för .NET. Genom att ställa in rätt SRS, hantera geometri konsekvent och verifiera lagrets metadata kan du bygga robusta GIS‑aktiverade applikationer som samverkar med vilken standard‑GIS‑programvara som helst.

---

**Senast uppdaterad:** 2026-06-30  
**Testad med:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Författare:** Aspose

## Relaterade handledningar

- [Skapa vektorlager och ange lagerns spatiala referenssystem](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Skapa vektorlager i File GDB – Aspose.GIS .NET‑handledning](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Hur man modifierar lager – Aspose.GIS .NET‑lagerinteraktion](/gis/net/layer-interaction-and-data-access/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
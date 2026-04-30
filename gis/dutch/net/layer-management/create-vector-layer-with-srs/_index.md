---
date: 2026-01-15
description: Ontdek Aspose.GIS voor .NET om een vectorlaag met een ruimtelijk referentiesysteem
  te maken. Leer hoe je SRS instelt, een laag maakt en GIS‑gegevens beheert. Download
  nu!
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: Vectorlaag maken met SRS
url: /nl/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vectorlaag maken met SRS

## Introduction
Aspose.GIS for .NET is een krachtige bibliotheek die ontwikkelaars in staat stelt **create vector layer** objecten te maken en naadloos te werken met geografische informatiesysteem (GIS) gegevens in .NET-toepassingen. In deze tutorial lopen we door hoe je een vectorlaag maakt met een ruimtelijk referentiesysteem (SRS), waarom je een ruimtelijke referentie zou willen instellen, en welke voordelen dit biedt voor projecten in de echte wereld. Aan het einde van deze gids kun je GIS-mogelijkheden integreren in je .NET-oplossingen met vertrouwen.

## Quick Answers
- **Wat is het primaire doel van deze tutorial?** Om te laten zien hoe je een vectorlaag maakt met een gespecificeerde SRS met behulp van Aspose.GIS voor .NET.  
- **Welke projectie wordt in het voorbeeld gebruikt?** World Mercator (EPSG:3395).  
- **Heb ik een licentie nodig om de code uit te voeren?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Kan ik dezelfde aanpak gebruiken met andere GIS-formaten?** Ja, dezelfde SRS-afhandeling geldt voor Shapefile, GeoJSON, KML, enz.  
- **Welke .NET-versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is a vector layer and why set its spatial reference?
Een **vector layer** slaat geometrische objecten (punten, lijnen, polygonen) op samen met attribuutgegevens. Het toewijzen van een **spatial reference** (SRS) vertelt GIS-software hoe die coördinaten op het aardoppervlak geïnterpreteerd moeten worden. Het instellen van de juiste SRS zorgt voor nauwkeurige metingen, correcte overlay met andere lagen en betrouwbare kaartvisualisaties.

## Prerequisites
Voordat we beginnen, zorg ervoor dat je het volgende hebt:

- Basiskennis van C# en .NET-ontwikkeling.  
- Aspose.GIS for .NET bibliotheek geïnstalleerd. Je kunt het downloaden **[here](https://releases.aspose.com/gis/net/)**.  
- Een ontwikkelomgeving (Visual Studio, VS Code, of een andere C# IDE).  

## Import Namespaces
Zorg ervoor dat je de benodigde namespaces bovenaan je C#-bestand hebt geïmporteerd:

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

## How to set spatial reference (SRS) – Step 1
Laten we een **projected spatial reference system** maken met de World Mercator-projectie als voorbeeld. Dit toont **how to set srs** voor een laag.

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

## How to create layer – Step 2
Nu gaan we een **create a vector layer** (een Shapefile) maken en functies toevoegen die de SRS gebruiken die we zojuist hebben gedefinieerd. Dit gedeelte beantwoordt **how to create layer** met Aspose.GIS.

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

> **Pro tip:** Controleer altijd dat de `SpatialReferenceSystem` van de geometrie overeenkomt met de SRS van de laag voordat je deze toevoegt. Niet-overeenkomende SRS-waarden veroorzaken een `GisException`, zoals hierboven getoond.

## Verify Spatial Reference System – Step 3
Open tenslotte de laag en bevestig dat de SRS correct is toegepast.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Als de `IsEquivalent`-aanroep `true` retourneert, heb je met succes **create vector layer** met de gewenste ruimtelijke referentie.

## Common Issues & Solutions
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| `GisException` bij het toevoegen van een feature | Geometrie gebruikt een andere SRS dan de laag | Stel `feature.Geometry.SpatialReferenceSystem` in op de SRS van de laag voordat je toevoegt |
| Laag lijkt leeg in GIS-software | Het shapefile werd aangemaakt zonder een correct `.prj`-bestand | Zorg ervoor dat het `projectedSrs`-object wordt doorgegeven bij het aanmaken van de laag |
| Onverwachte coördinaatwaarden | Verkeerde projectieparameters (bijv. centrale meridiaan) | Controleer de parameters die aan `AddProjectionParameter` zijn doorgegeven |

## FAQs
### Is Aspose.GIS compatible with all GIS file formats?
Aspose.GIS ondersteunt verschillende GIS-formaten, waaronder Shapefile, GeoJSON, KML en meer. Bekijk de **[documentation](https://reference.aspose.com/gis/net/)** voor de volledige lijst.

### Can I use Aspose.GIS in a web application?
Absoluut! Aspose.GIS voor .NET is veelzijdig en kan worden gebruikt in webapplicaties, desktopapplicaties en zelfs mobiele apps.

### Where can I get support for Aspose.GIS?
Je kunt een behulpzame community vinden op het **[Aspose.GIS forum](https://forum.aspose.com/c/gis/33)** voor eventuele vragen of problemen.

### Is there a free trial available?
Ja, je kunt de functies van Aspose.GIS verkennen door een gratis proefversie te verkrijgen **[here](https://releases.aspose.com/)**.

### How can I purchase a license for Aspose.GIS?
Om een licentie aan te schaffen, bezoek de **[purchase page](https://purchase.aspose.com/buy)**.

## Frequently Asked Questions (Additional)

**Q: Wat gebeurt er als ik een geometrie met een andere SRS probeer toe te voegen?**  
A: Aspose.GIS gooit een `GisException`. Je moet de geometrie opnieuw projecteren of ervoor zorgen dat deze dezelfde SRS als de laag heeft.

**Q: Kan ik de SRS van een bestaande laag wijzigen?**  
A: Ja, je kunt een nieuwe laag maken met de gewenste SRS en functies overzetten, waarbij je ze zo nodig reprojection.

**Q: Is het mogelijk om met 3D-coördinaten te werken?**  
A: Aspose.GIS ondersteunt Z‑coördinaten; gebruik gewoon geometry-constructors die een Z-waarde accepteren.

**Q: Handelt de bibliotheek datumtransformaties automatisch af?**  
A: Wanneer je geometrieën reprojecteert met `Geometry.Transform`, voert Aspose.GIS de benodigde datumverschuiving uit.

**Q: Welke .NET-versies zijn officieel getest?**  
A: De bibliotheek is getest met .NET Framework 4.5+, .NET Core 3.1+, en .NET 5/6/7.

## Conclusion
Je hebt nu geleerd hoe je een **create vector layer** maakt met een aangepast ruimtelijk referentiesysteem met behulp van Aspose.GIS voor .NET. Door de juiste SRS in te stellen, geometrie consistent te verwerken en de metadata van de laag te verifiëren, kun je robuuste GIS-ondersteunde applicaties bouwen die interopereren met elke standaard GIS-software.

---

**Last Updated:** 2026-01-15  
**Getest met:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Maak een vectorlaag met SRS
linktitle: Maak een vectorlaag met SRS
second_title: Aspose.GIS .NET-API
description: Ontdek Aspose.GIS voor .NET - uw sleutel tot naadloze GIS-integratie. Creëer moeiteloos vectorlagen met gespecificeerde ruimtelijke referentiesystemen. Download nu!
weight: 13
url: /nl/net/layer-management/create-vector-layer-with-srs/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak een vectorlaag met SRS

## Invoering
Aspose.GIS voor .NET is een krachtige bibliotheek waarmee ontwikkelaars naadloos kunnen werken met GIS-gegevens (geografisch informatiesysteem) in .NET-toepassingen. In deze zelfstudie concentreren we ons op het maken van een vectorlaag met een ruimtelijk referentiesysteem (SRS). Aan het einde van deze handleiding kunt u moeiteloos GIS-mogelijkheden integreren in uw .NET-projecten.
## Vereisten
Voordat we ingaan op de tutorial, zorg ervoor dat je aan de volgende vereisten voldoet:
- Basiskennis van C# en .NET-ontwikkeling.
-  Aspose.GIS voor .NET-bibliotheek geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/gis/net/).
- Een ontwikkelomgeving opgezet en klaar.
## Naamruimten importeren
Zorg ervoor dat u de benodigde naamruimten aan het begin van uw C#-bestand importeert:
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
## Stap 1: Stel het geprojecteerde ruimtelijke referentiesysteem in
Laten we een geprojecteerd ruimtelijk referentiesysteem (SRS) maken met de World Mercator-projectie als voorbeeld. Volg deze stappen:
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
## Stap 2: Maak een vectorlaag en voeg functies toe
Laten we nu een shapefile maken en functies toevoegen met de opgegeven SRS:
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
        layer.Add(feature); // Dit levert een uitzondering op omdat de geometrie een andere SRS heeft
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## Stap 3: Verifieer het ruimtelijke referentiesysteem
Laten we ten slotte de laag openen en het ruimtelijke referentiesysteem ervan verifiëren:
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / Wereld Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Zou waar moeten terugkeren
}
```
Door deze stappen te volgen, hebt u met succes een vectorlaag gemaakt met een gespecificeerd ruimtelijk referentiesysteem met behulp van Aspose.GIS voor .NET.
## Conclusie
GIS-functionaliteit integreren in uw .NET-applicaties is nog nooit zo eenvoudig geweest dankzij Aspose.GIS. Met de mogelijkheid om moeiteloos vectorlagen te creëren en ruimtelijke referentiesystemen te beheren, kunt u uw projecten uitbreiden met krachtige geospatiale mogelijkheden.
## Veelgestelde vragen
### Is Aspose.GIS compatibel met alle GIS-bestandsformaten?
 Aspose.GIS ondersteunt verschillende GIS-formaten, waaronder Shapefile, GeoJSON, KML en meer. Controleer de[documentatie](https://reference.aspose.com/gis/net/) voor de volledige lijst.
### Kan ik Aspose.GIS gebruiken in een webapplicatie?
Absoluut! Aspose.GIS voor .NET is veelzijdig en kan worden gebruikt in webapplicaties, desktopapplicaties en zelfs mobiele apps.
### Waar kan ik ondersteuning krijgen voor Aspose.GIS?
 Je kunt een behulpzame community vinden op de[Aspose.GIS-forum](https://forum.aspose.com/c/gis/33) voor eventuele vragen of problemen die u tegenkomt.
### Is er een gratis proefversie beschikbaar?
 Ja, u kunt de functies van Aspose.GIS verkennen door een gratis proefperiode aan te vragen[hier](https://releases.aspose.com/).
### Hoe kan ik een licentie voor Aspose.GIS aanschaffen?
 Als u een licentie wilt kopen, gaat u naar de[aankooppagina](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Stel het lagenruimtelijke referentiesysteem in
linktitle: Stel het lagenruimtelijke referentiesysteem in
second_title: Aspose.GIS .NET-API
description: Masterinstelling Layer Spatial Reference System met Aspose.GIS voor .NET. Verbeter uw GIS-projecten met deze stapsgewijze zelfstudie.
type: docs
weight: 19
url: /nl/net/layer-data-operations/set-layer-spatial-reference-system/
---
## Invoering
In het uitgestrekte landschap van geografische informatiesystemen (GIS) onderscheidt Aspose.GIS voor .NET zich als een robuust en veelzijdig hulpmiddel voor ontwikkelaars. Deze tutorial leidt u door het proces van het instellen van het Layer Spatial Reference System met behulp van Aspose.GIS voor .NET. Of u nu een doorgewinterde ontwikkelaar bent of een nieuwkomer in de GIS-ontwikkeling, deze stapsgewijze handleiding helpt u de kracht van Aspose.GIS te benutten om uw mogelijkheden voor de verwerking van ruimtelijke gegevens te verbeteren.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Een praktische kennis van .NET-programmering.
- Visual Studio is op uw systeem geïnstalleerd.
-  Aspose.GIS voor .NET-bibliotheek, die u kunt downloaden[hier](https://releases.aspose.com/gis/net/).
- Een basiskennis van ruimtelijke referentiesystemen in GIS.
## Naamruimten importeren
Begin in uw .NET-project met het importeren van de benodigde naamruimten om toegang te krijgen tot de functionaliteiten van Aspose.GIS. Gebruik het volgende codefragment:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```
## Stap 1: Geef de documentmap op
Begin met het opgeven van het pad naar uw documentmap. Dit is de locatie waar uw bestanden met ruimtelijke gegevens worden opgeslagen.
```csharp
string dataDir = "Your Document Directory";
```
## Stap 2: Creëer en stel een ruimtelijk referentiesysteem in
Definieer het pad voor het Shapefile en maak een nieuw ruimtelijk referentiesysteem met behulp van de EPSG-code (26918 in dit voorbeeld).
```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```
## Stap 3: Maak een vectorlaag
Gebruik Aspose.GIS om een vectorlaag te maken met het opgegeven Shapefile-pad, het stuurprogrammatype (Shapefile) en het ruimtelijke referentiesysteem.
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Hier vindt u uw code voor verdere bewerkingen op de laag
}
```
## Stap 4: Voeg object toe aan de laag
Construeer een nieuw object en stel de geometrie ervan in (in dit geval een punt met coördinaten 60, 24). Voeg het object toe aan de vectorlaag.
```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```
## Stap 5: Haal ruimtelijke referentiesysteeminformatie op
Open de vectorlaag en haal informatie op over het ruimtelijke referentiesysteem.
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```
Herhaal deze stappen afhankelijk van uw specifieke gebruikssituatie en u bent goed op weg om de kunst van het instellen van het Layer Spatial Reference System met Aspose.GIS voor .NET onder de knie te krijgen.
## Conclusie
In deze zelfstudie hebben we de essentiële stappen onderzocht om het Layer Spatial Reference System in te stellen met behulp van Aspose.GIS voor .NET. Met zijn intuïtieve API en krachtige functies stelt Aspose.GIS ontwikkelaars in staat naadloos met ruimtelijke gegevens om te gaan. Neem deze technieken op in uw GIS-projecten om uw capaciteiten voor de verwerking van ruimtelijke gegevens te verbeteren.
## Veel Gestelde Vragen
### Is Aspose.GIS compatibel met andere GIS-bibliotheken?
Ja, Aspose.GIS integreert goed met andere GIS-bibliotheken en kan in combinatie daarmee worden gebruikt.
### Kan ik Aspose.GIS gebruiken voor zowel desktop- als webapplicaties?
Absoluut! Aspose.GIS is veelzijdig en kan worden gebruikt in zowel desktop- als webgebaseerde applicaties.
### Zijn er licentieopties beschikbaar voor Aspose.GIS?
 Ja, u kunt licentieopties verkennen en een aankoop doen[hier](https://purchase.aspose.com/buy).
### Is er een gratis proefversie beschikbaar voor Aspose.GIS?
 Zeker! U kunt een gratis proefversie downloaden[hier](https://releases.aspose.com/).
### Waar kan ik ondersteuning zoeken voor Aspose.GIS-gerelateerde vragen?
 Voor ondersteuning of vragen kunt u terecht op de[Aspose.GIS-forum](https://forum.aspose.com/c/gis/33).
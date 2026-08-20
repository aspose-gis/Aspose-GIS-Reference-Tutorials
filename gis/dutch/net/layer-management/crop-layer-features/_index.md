---
date: 2026-07-05
description: Leer hoe u layer features kunt croppen met Aspose.GIS for .NET, inclusief
  hoe u raster kunt croppen met polygon, de raster cell size kunt extraheren en de
  raster extent kunt ophalen. Download nu uw free trial.
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: Hoe Crop layer features
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to crop layer features with Aspose.GIS for .NET, including
    how to crop raster with polygon, extract raster cell size, and retrieve raster
    extent. Download your free trial now.
  headline: How to Crop Layer Features with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for Aspose.GIS for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find comprehensive documentation for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support
      and community engagement.
    question: How can I seek support or connect with the community for Aspose.GIS
      for .NET?
  - answer: Yes, you can download a free trial [here](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.GIS for .NET?
  - answer: You can purchase the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hoe layer features bijsnijden met Aspose.GIS for .NET
url: /nl/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe laagfuncties bijsnijden

## Inleiding
In deze tutorial leer je **how to crop layer** functies te gebruiken met Aspose.GIS voor .NET, een krachtige bibliotheek die je **crop raster with polygon**, **extract raster cell size**, en **retrieve raster extent** laat uitvoeren voor nauwkeurige geospatiale analyse. Of je nu data voorbereidt voor een webkaart, satellietbeelden bijsnijdt, of een gebied van interesse isoleert, deze stap‑voor‑stap‑gids laat je precies zien hoe je de taak snel en betrouwbaar kunt voltooien.

## Snelle antwoorden
- **Wat betekent “crop layer”?** Het knipt een raster‑ of vectorlaag bij tot de grenzen van een opgegeven geometrie en verwijdert alles buiten deze grenzen.  
- **Welke geometrie wordt in dit voorbeeld gebruikt?** Een polygoon gedefinieerd in WKT‑formaat (Well‑Known Text).  
- **Kan ik de celgrootte extraheren na het bijsnijden?** Ja – de `CellSize`‑eigenschap geeft de breedte en hoogte van een rastercel terug.  
- **Heb ik een licentie nodig om de code uit te voeren?** Een tijdelijke licentie werkt voor evaluatie; een volledige licentie is vereist voor productiegebruik.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Wat is “how to crop layer”?
**Cropping a layer means restricting the dataset to a specific geographic area, discarding everything outside.** Deze bewerking verkleint de bestandsgrootte, versnelt vervolgverwerking en richt de analyse op het gebied dat voor jou van belang is. Door de data te beperken tot het interessegebied, vereenvoudig je ook downstream‑workflows zoals styling, analyse en publicatie, terwijl je het oorspronkelijke coördinatenreferentiesysteem en de metadata behoudt.

## Waarom Aspose.GIS gebruiken voor het bijsnijden?
**Aspose.GIS processes raster files up to 2 GB without loading the entire image into memory and supports more than 30 raster formats, including GeoTIFF, JPEG2000, and PNG.** De bibliotheek biedt een één‑regelige `Crop`‑aanroep, automatische CRS‑afhandeling en multi‑threaded prestaties die een 500‑MB GeoTIFF in minder dan een seconde kunnen bijsnijden op een typische server.

## Voorvereisten
Voordat je de magie van geospatiale manipulatie induikt, zorg ervoor dat je de volgende voorvereisten hebt:

- Aspose.GIS for .NET Library: Zorg ervoor dat je de Aspose.GIS‑bibliotheek hebt geïnstalleerd in je .NET‑project. Je kunt deze downloaden van [here](https://releases.aspose.com/gis/net/).  
- Document Directory: Richt een map in om je documenten op te slaan. Vervang `"Your Document Directory"` in de meegeleverde code door het daadwerkelijke pad naar jouw documentmap.

Nu duiken we in de stap‑voor‑stap‑gids.

## Importeren van namespaces
De `Aspose.Gis`‑namespace bevat alle kern‑typen voor raster‑ en vectorverwerking. Importeer deze om toegang te krijgen tot de `Layer`, `Geometry` en gerelateerde klassen.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Hoe knip ik een laag bij met een polygoon?
`Crop` is een methode van de `Layer`‑klasse die een raster‑subset extraheert dat door een geometrie wordt gedefinieerd.  
Laad het bronraster, definieer een polygoongeometrie en roep de `Crop`‑methode aan – de volledige bewerking wordt uitgevoerd in één regel code. De methode retourneert een nieuw raster dat alleen de pixels binnen de polygoon bevat, waarbij de oorspronkelijke ruimtelijke referentie automatisch behouden blijft.

## Stap 1: Open en knip de laag bij (crop raster with polygon)
`Layer` vertegenwoordigt een rasterdataset die kan worden geopend, bevraagd en bewerkt.  
De `Layer`‑klasse vertegenwoordigt een rasterdataset die kan worden geopend, bevraagd en bewerkt. Het openen van een GeoTIFF en deze bijsnijden met een polygoon is in slechts een paar statements mogelijk.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Stap 2: Haal rasterinformatie op (extract raster cell size & retrieve raster extent)
`CellSize` geeft de breedte en hoogte van elke rastercel in coördinaateenheden.  
`Extent` retourneert de geografische omhullende van het raster.  
De `CellSize`‑eigenschap geeft de breedte en hoogte van elke rastercel in coördinaateenheden, terwijl de `Extent`‑eigenschap de geografische omhullende van het bijgesneden raster retourneert. Beide stukken informatie zijn essentieel voor vervolg‑berekeningen zoals oppervlakte‑meting of herprojectie.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## Stap 3: Informatie weergeven
Print de geëxtraheerde informatie om de impact van het bijsnijdingsproces op je geospatiale data te begrijpen.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

Herhaal deze stappen indien nodig om je geospatiale data te verfijnen en af te stemmen op specifieke projectvereisten.

## Veelvoorkomende problemen en oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **Onjuiste polygoonorientatie** | Zorg ervoor dat de WKT‑polygoon de right‑hand rule volgt (tegen de klok in voor buitenranden). |
| **Ontbrekende ruimtelijke referentie** | Controleer of de bron‑GeoTiff een CRS bevat; stel anders handmatig een CRS in vóór het bijsnijden. |
| **Prestatievermindering bij enorme rasters** | Gebruik `layer.Crop` op een gedown‑samplede kopie of verwerk het raster in tegels. |

## Veelgestelde vragen
**Q: Is er een tijdelijke licentie beschikbaar voor Aspose.GIS voor .NET?**  
A: Ja, je kunt een tijdelijke licentie verkrijgen [here](https://purchase.aspose.com/temporary-license/).

**Q: Waar kan ik uitgebreide documentatie vinden voor Aspose.GIS voor .NET?**  
A: De documentatie is beschikbaar [here](https://reference.aspose.com/gis/net/).

**Q: Hoe kan ik ondersteuning zoeken of contact opnemen met de community voor Aspose.GIS voor .NET?**  
A: Bezoek het [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) voor ondersteuning en community‑betrokkenheid.

**Q: Kan ik een gratis proefversie van Aspose.GIS voor .NET downloaden?**  
A: Ja, je kunt een gratis proefversie downloaden [here](https://releases.aspose.com/).

**Q: Waar kan ik Aspose.GIS voor .NET aanschaffen?**  
A: Je kunt de bibliotheek aanschaffen [here](https://purchase.aspose.com/buy).

**Q: Kan ik meerdere lagen in één keer bijsnijden?**  
A: Ja—loop over elke laag en pas dezelfde `Crop`‑aanroep toe met de gewenste geometrie.

**Q: Ondersteunt de API andere rasterformaten (bijv. JPEG2000)?**  
A: Aspose.GIS ondersteunt alle formaten die door de onderliggende GDAL‑drivers worden blootgesteld, inclusief JPEG2000, PNG en meer.

## Conclusie
Door deze gids te volgen weet je nu **how to crop layer** functies efficiënt te gebruiken met Aspose.GIS voor .NET. Je kunt eenvoudig **crop raster with polygon**, **extract raster cell size**, en **retrieve raster extent** toepassen om aan de behoeften van elk project te voldoen. Verken verdere API’s voor herprojectie, raster‑styling en vectoranalyse om het volledige potentieel van je geospatiale workflows te benutten.

---

**Laatst bijgewerkt:** 2026-07-05  
**Getest met:** Aspose.GIS 24.10 for .NET  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Hoe polygongeometrie maken met Aspose.GIS voor .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Laagattributen ophalen – Laagattribuutinformatie ophalen met Aspose.GIS voor .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Polygongeometrie maken in C# en intersectie controleren met Aspose.GIS voor .NET](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
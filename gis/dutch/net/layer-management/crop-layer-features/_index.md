---
date: 2026-01-13
description: Leer hoe u laagfuncties kunt bijsnijden met Aspose.GIS voor .NET, inclusief
  hoe u raster kunt bijsnijden met een polygoon, de rastercelgrootte kunt extraheren
  en de rasterextent kunt ophalen. Download nu uw gratis proefversie.
linktitle: How to Crop Layer Features
second_title: Aspose.GIS .NET API
title: Hoe laagfuncties bijsnijden met Aspose.GIS voor .NET
url: /nl/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe laag‑kenmerken bijsnijden

## Introductie
In deze tutorial leer je **hoe je laag‑kenmerken kunt bijsnijden** met Aspose.GIS voor .NET, een krachtige aanpak waarmee je **raster bijsnijdt met een polygoon**, **de rastercelgrootte kunt extraheren**, en **de raster‑extent kunt ophalen** voor nauwkeurige geospatiale analyse. Of je nu data voorbereidt voor een webkaart, satellietbeelden bijsnijdt, of een interessegebied isoleert, deze stap‑voor‑stap‑gids laat je precies zien hoe je de klus klaart.

## Snelle antwoorden
- **Wat betekent “bijsnijden van laag”?** Het verkort een raster‑ of vectorlaag tot de grenzen van een opgegeven geometrie.  
- **Welke geometrie wordt in dit voorbeeld gebruikt?** Een polygoon gedefinieerd in WKT‑formaat.  
- **Kan ik de celgrootte extraheren na het bijsnijden?** Ja – de `CellSize`‑eigenschap levert die informatie.  
- **Heb ik een licentie nodig om de code uit te voeren?** Een tijdelijke licentie werkt voor evaluatie; een volledige licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Wat is “hoe laag bijsnijden”?
Een laag bijsnijden betekent dat de dataset wordt beperkt tot een specifiek geografisch gebied, waarbij alles buiten de gedefinieerde vorm wordt weggegooid. Dit verkleint de bestandsgrootte, versnelt de verwerking en richt de analyse op het gebied dat voor jou relevant is.

## Waarom Aspose.GIS gebruiken voor bijsnijden?
- **Hoge‑prestaties rasterverwerking** – ideaal voor grote GeoTiff‑bestanden.  
- **Eenvoudige API** – één‑regelige `Crop`‑aanroep met elke geometrie.  
- **Volledige .NET‑compatibiliteit** – werkt in desktop‑, server‑ en cloud‑apps.  
- **Nauwkeurige handling van ruimtelijke referenties** – behoudt CRS‑informatie automatisch.

## Voorvereisten
Voordat je de magie van geospatiale manipulatie induikt, zorg je dat de volgende zaken aanwezig zijn:

- Aspose.GIS voor .NET‑bibliotheek: Zorg ervoor dat de Aspose.GIS‑bibliotheek in je .NET‑project is geïnstalleerd. Je kunt deze downloaden van [hier](https://releases.aspose.com/gis/net/).  
- Documentdirectory: Maak een map aan om je documenten op te slaan. Vervang `"Your Document Directory"` in de meegeleverde code door het daadwerkelijke pad naar jouw documentdirectory.

Laten we nu de stap‑voor‑stap‑gids doorlopen.

## Namespaces importeren
Begin met het importeren van de benodigde namespaces om de volledige kracht van Aspose.GIS te benutten:

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Stap 1: De laag openen en bijsnijden (raster bijsnijden met polygoon)
Open de GeoTiff‑laag en snijd deze bij op basis van een gedefinieerde polygoon. Dit zorgt ervoor dat je geospatiale data wordt verfijnd tot een specifiek interessegebied.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Stap 2: Rasterinformatie ophalen (rastercelgrootte extraheren & raster‑extent ophalen)
Nadat de laag is bijgesneden, haal je essentiële informatie over de rasterdata op, zoals celgrootte, ruimtelijk referentiesysteem en grenzen.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## Stap 3: Informatie weergeven
Print de geëxtraheerde informatie om het effect van het bijsnijdingsproces op je geospatiale data te begrijpen.

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
| **Prestatie‑vertraging bij enorme rasters** | Gebruik `layer.Crop` op een gedown‑samplede kopie of verwerk het raster in tegels. |

## Veelgestelde vragen
### Q: Is er een tijdelijke licentie beschikbaar voor Aspose.GIS voor .NET?
A: Ja, je kunt een tijdelijke licentie verkrijgen [hier](https://purchase.aspose.com/temporary-license/).

### Q: Waar vind ik uitgebreide documentatie voor Aspose.GIS voor .NET?
A: De documentatie is beschikbaar [hier](https://reference.aspose.com/gis/net/).

### Q: Hoe kan ik ondersteuning krijgen of contact opnemen met de community voor Aspose.GIS voor .NET?
A: Bezoek het [Aspose.GIS‑forum](https://forum.aspose.com/c/gis/33) voor ondersteuning en community‑interactie.

### Q: Kan ik een gratis proefversie van Aspose.GIS voor .NET downloaden?
A: Ja, je kunt een gratis proefversie downloaden [hier](https://releases.aspose.com/).

### Q: Waar kan ik Aspose.GIS voor .NET aanschaffen?
A: Je kunt de bibliotheek kopen [hier](https://purchase.aspose.com/buy).

### Q: Kan ik meerdere lagen in één keer bijsnijden?
A: Ja—loop over elke laag en pas dezelfde `Crop`‑aanroep toe met de gewenste geometrie.

### Q: Ondersteunt de API andere rasterformaten (bijv. JPEG2000)?
A: Aspose.GIS ondersteunt alle formaten die de onderliggende GDAL‑drivers blootleggen, inclusief JPEG2000, PNG en meer.

## Conclusie
Door deze gids te volgen, weet je nu **hoe je laag‑kenmerken efficiënt kunt bijsnijden** met Aspose.GIS voor .NET. Je kunt eenvoudig **raster bijsnijden met een polygoon**, **de rastercelgrootte extraheren**, en **de raster‑extent ophalen** om aan de behoeften van elk project te voldoen. Verken verdere API’s voor herprojectie, raster‑styling en vectoranalyse om het volledige potentieel van je geospatiale workflows te benutten.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2026-01-13  
**Getest met:** Aspose.GIS 24.10 voor .NET  
**Auteur:** Aspose  

---
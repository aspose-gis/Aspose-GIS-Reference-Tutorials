---
date: 2025-12-31
description: Leer hoe u een vectorlaag maakt en het ruimtelijk referentiesysteem van
  de laag instelt met Aspose.GIS voor .NET. Beheers het definiëren van een ruimtelijke
  referentie, het toevoegen van een puntfeature en het ophalen van de EPSG‑code.
linktitle: Set Layer Spatial Reference System
second_title: Aspose.GIS .NET API
title: Vectorlaag maken en laag ruimtelijk referentiesysteem instellen
url: /nl/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak Vectorlaag en Stel Laag Ruimtelijk Referentiesysteem In

## Introductie
In het uitgestrekte landschap van Geographic Information Systems (GIS) onderscheidt **Aspose.GIS for .NET** zich als een robuust en veelzijdig hulpmiddel voor ontwikkelaars. In deze tutorial **maak je een vectorlaag**, definieer je de ruimtelijke referentie, voeg je een punt‑feature toe, en haal je de EPSG‑code op — alles met duidelijke, stap‑voor‑stap begeleiding. Of je nu een ervaren GIS‑engineer bent of net begint, deze technieken helpen je het coördinatensysteem van een shapefile correct in te stellen en de betrouwbaarheid van je ruimtelijke data‑workflows te vergroten.

## Snelle Antwoorden
- **Wat betekent “maak vectorlaag”?** Het maakt een nieuwe GIS‑laag (bijv. een Shapefile) die geometrieën zoals punten, lijnen of polygonen kan opslaan.  
- **Welke EPSG‑code wordt in het voorbeeld gebruikt?** EPSG 26918 (NAD83 / UTM zone 18N).  
- **Kan ik een punt‑feature toevoegen nadat de laag is aangemaakt?** Ja — gebruik `ConstructFeature()` en wijs een `Point`‑geometrie toe.  
- **Hoe haal ik het CRS van de laag op?** Lees `layer.SpatialReferenceSystem.EpsgCode` of `.Name`.  
- **Heb ik een licentie nodig voor Aspose.GIS?** Er is een gratis proefversie beschikbaar; een licentie is vereist voor productiegebruik.

## Vereisten
Voordat je aan de tutorial begint, zorg dat je de volgende zaken hebt:
- Een werkende kennis van .NET‑programmeren.  
- Visual Studio geïnstalleerd op je systeem.  
- Aspose.GIS for .NET‑bibliotheek, die je kunt downloaden [hier](https://releases.aspose.com/gis/net/).  
- Een basisbegrip van ruimtelijke referentiesystemen in GIS.

## Namespaces Importeren
Importeer in je .NET‑project de benodigde namespaces om toegang te krijgen tot de functionaliteiten van Aspose.GIS. Gebruik de volgende code‑snippet:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Stap 1: Specificeer de Documentmap
Geef het pad naar je documentmap op. Dit wordt de locatie waar je ruimtelijke data‑bestanden worden opgeslagen.

```csharp
string dataDir = "Your Document Directory";
```

## Stap 2: Definieer Ruimtelijke Referentie en Stel Shapefile‑Coördinatensysteem In
Definieer het pad voor de Shapefile en **definieer de ruimtelijke referentie** met de EPSG‑code (26918 in dit voorbeeld). Deze stap **stelt het shapefile‑coördinatensysteem** voor de laag in.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Stap 3: Maak Vectorlaag
Nu **maak je een vectorlaag** met het opgegeven Shapefile‑pad, driver‑type (Shapefile) en het ruimtelijke referentiesysteem dat je zojuist hebt gedefinieerd.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

## Stap 4: Voeg Punt‑Feature toe aan de Laag
Construeer een nieuwe feature en **voeg een punt‑feature toe** door de geometrie in te stellen (een `Point` met coördinaten 60, 24). Voeg vervolgens de feature toe aan de vectorlaag.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

## Stap 5: Haal Informatie over Ruimtelijk Referentiesysteem op (Haal EPSG‑Code op)
Open de Vectorlaag en haal informatie over het ruimtelijke referentiesysteem op, zoals de EPSG‑code en de mens‑leesbare naam. Dit laat zien hoe je **de EPSG‑code kunt ophalen** en **het laag‑CRS kunt instellen**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

Herhaal deze stappen volgens jouw specifieke gebruikssituatie, en je bent goed op weg om de kunst van het **maken van een vectorlaag** en het beheren van ruimtelijke referenties onder de knie te krijgen met Aspose.GIS for .NET.

## Veelvoorkomende Problemen en Oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| **Laag kan niet worden geopend** | Verkeerde driver of beschadigd bestandspad | Controleer `Drivers.Shapefile` en zorg dat `path` naar een bestaand `.shp`‑bestand wijst. |
| **Onjuist CRS weergegeven** | Verkeerde EPSG‑code gebruikt | Controleer de EPSG‑code bij een gezaghebbende bron (bijv. EPSG.io). |
| **Feature niet opgeslagen** | `layer.Add(feature)` niet aangeroepen binnen het `using`‑blok | Zorg dat de `Add`‑methode wordt uitgevoerd voordat de laag wordt vrijgegeven. |

## Veelgestelde Vragen
### Is Aspose.GIS compatibel met andere GIS‑bibliotheken?
Ja, Aspose.GIS integreert goed met andere GIS‑bibliotheken en kan in combinatie met hen worden gebruikt.

### Kan ik Aspose.GIS gebruiken voor zowel desktop‑ als webapplicaties?
Absoluut! Aspose.GIS is veelzijdig en kan zowel in desktop‑ als web‑gebaseerde applicaties worden ingezet.

### Zijn er licentie‑opties beschikbaar voor Aspose.GIS?
Ja, je kunt licentie‑opties verkennen en een aankoop doen [hier](https://purchase.aspose.com/buy).

### Is er een gratis proefversie beschikbaar voorose.GIS?
Zeker! Je kunt een gratis proefversie downloaden [hier](https://releases.aspose.com/).

### Waar kan ik ondersteuning vinden voor vragen over Aspose.GIS?
Voor ondersteuning of vragen, bezoek het [Aspose.GIS‑forum](https://forum.aspose.com/c/gis/33).

## Aanvullende Veelgestelde Vragen
**V: Hoe wijzig ik het CRS van een bestaande Shapefile?**  
A: Open de laag, maak een nieuw `SpatialReferenceSystem` met de gewenste EPSG‑code, en wijs dit toe aan `layer.SpatialReferenceSystem` voordat je opslaat.

**V: Kan ik andere geometrietypen (bijv. polygonen) toevoegen met dezelfde aanpak?**  
A: Ja — vervang `new Point(x, y)` door `new Polygon(...)` of `new LineString(...)` naar behoefte.

**V: Is het mogelijk om efficiënt met grote datasets te werken?**  
A: Gebruik streaming‑API’s (`VectorLayer.Create` met `FeatureCollection`) en maak lagen snel vrij om bronnen te besparen.

**V: Ondersteunt Aspose.GIS coördinatentransformatie?**  
A: Ja — gebruik `Geometry.Transform(targetSrs)` om geometrieën tussen verschillende ruimtelijke referenties te reprojeteren.

**V: Welke .NET‑versies worden ondersteund?**  
A: Aspose.GIS werkt met .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

## Conclusie
In deze tutorial hebben we onderzocht hoe je een **vectorlaag maakt**, de ruimtelijke referentie definieert, een **punt‑feature toevoegt**, en de **EPSG‑code ophaalt** met Aspose.GIS for .NET. Door deze stappen onder de knie te krijgen kun je het coördinatensysteem van een shapefile zelfverzekerd instellen, het laag‑CRS beheren, en betrouwbare GIS‑applicaties bouwen.

---

**Laatst bijgewerkt:** 2025-12-31  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
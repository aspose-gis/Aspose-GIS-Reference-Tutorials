---
date: 2025-12-28
description: Leer hoe u een raster instelt voor een File GDB‑laag met Aspose.GIS voor
  .NET, inclusief het toevoegen van objecten aan de laag en het valideren van het
  coördinatenbereik.
linktitle: Define Precision Grid for File GDB Layer
second_title: Aspose.GIS .NET API
title: Hoe een raster instellen voor File GDB-laag in Aspose.GIS
url: /nl/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een raster instellen voor een File GDB‑laag in Aspose.GIS

## Inleiding
In deze tutorial leer je **hoe je een raster instelt** voor een File Geodatabase (GDB)‑laag met Aspose.GIS voor .NET. Het instellen van een precisieraster helpt je **coördinatenbereik te valideren**, voorkomt out‑of‑range‑fouten en zorgt ervoor dat de gegevens die je **features aan een laag toevoegt** nauwkeurig en betrouwbaar blijven. We lopen elke stap door, leggen uit waarom de instellingen belangrijk zijn en laten zien hoe je veelvoorkomende valkuilen afhandelt.

## Snelle antwoorden
- **Wat betekent “raster instellen”?** Het definieert de coördinatenprecisie en het geldige bereik voor een GIS‑laag.  
- **Waarom een precisieraster gebruiken?** Het beschermt je gegevens tegen ongeldige coördinaten en verbetert de opslag‑efficiëntie.  
- **Welke bibliotheek biedt deze functionaliteit?** Aspose.GIS voor .NET.  
- **Heb ik een licentie nodig?** Er is een proefversie beschikbaar; een commerciële licentie is vereist voor productie.  
- **Kan ik dit gebruiken met .NET Core?** Ja, Aspose.GIS ondersteunt .NET Framework en .NET Core.

## Wat is een precisieraster en waarom instellen?
Een precisieraster is een set parameters (origin, scale, enz.) die de GIS‑engine vertelt hoe coördinatenwaarden afgerond en opgeslagen moeten worden. Door een raster te definiëren **valideer je automatisch het coördinatenbereik**, en elke poging om een punt buiten het raster in te voegen zal een uitzondering veroorzaken—wat je helpt **out‑of‑range‑scenario’s** vroegtijdig af te handelen.

## Vereisten
Zorg ervoor dat je het volgende geïnstalleerd hebt:

1. **Visual Studio** – elke recente versie (Community, Professional of Enterprise).  
2. **Aspose.GIS voor .NET** – download het van de [website](https://releases.aspose.com/gis/net/).  
3. **Basiskennis van C#** – je moet vertrouwd zijn met het maken van .NET‑consoleprojecten.

## Namespaces importeren
Importeer eerst de namespaces die nodig zijn voor het werken met Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## Hoe een raster instellen in een File GDB‑laag
Hieronder vind je een stap‑voor‑stap‑gids die precies laat zien hoe je het raster configureert, een laag maakt en veilig **features aan een laag toevoegt**.

### Stap 1: Een dataset maken
We beginnen met het aanmaken van een nieuwe File Geodatabase‑dataset. Hierin zal de laag worden opgeslagen.

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### Stap 2: Precisieraster‑opties definiëren
Hier specificeren we de rasterparameters. Pas de origins en scales aan zodat ze overeenkomen met het coördinatensysteem van je project.

```csharp
var options = new FileGdbOptions
{
    CoordinatePrecisionGrid = new FileGdbCoordinatePrecisionGrid
    {
        XOrigin = -400,
        YOrigin = -400,
        XYScale = 1e10,
        MOrigin = 0,
        MScale = 1e4,
    },
    EnsureValidCoordinatesRange = true,
};
```

*De vlag `EnsureValidCoordinatesRange = true` vertelt Aspose.GIS om **coördinatenbereik te valideren** voor elke feature die je toevoegt.*

### Stap 3: Een laag maken met het raster
Nu maken we een nieuwe laag binnen de dataset, waarbij we de rasteropties toepassen die we zojuist hebben gedefinieerd. We gebruiken het WGS84‑spatial reference system.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### Stap 4: Features aan de laag toevoegen
We construeren twee punt‑features. Het eerste punt ligt binnen het raster, terwijl het tweede opzettelijk buiten valt om **te laten zien hoe je out‑of‑range‑fouten** afhandelt.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### Stap 5: Uitzonderingen afhandelen bij het toevoegen van out‑of‑range‑features
Het proberen toe te voegen van de tweede feature zal een uitzondering veroorzaken omdat de X‑coördinaat (`-410`) buiten het gedefinieerde raster ligt. We vangen de uitzondering op en geven een duidelijke melding weer.

```csharp
try
{
    layer.Add(feature);
}
catch (GisException e)
{
    Console.WriteLine(e.Message); // X value -410 is out of valid range.
}
```

### Stap 6: Opruimen
De `using`‑statements sluiten en verwijderen de dataset en laag automatisch, waardoor alle resources worden vrijgegeven.

## Veelvoorkomende problemen en oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| **Exception: “X value … is out of valid range.”** | Coördinaten vallen buiten het precisieraster. | Pas `XOrigin`, `YOrigin` of `XYScale` aan zodat je gegevens binnen het bereik vallen, of zorg dat invoergegevens binnen het gedefinieerde bereik liggen. |
| **Features verschijnen niet in GIS‑viewer** | Laag niet opgeslagen of verkeerde spatial reference. | Controleer of `SpatialReferenceSystem.Wgs84` overeenkomt met de CRS van de viewer, en of `Dataset.Create` geslaagd is. |
| **M‑waarden worden genegeerd** | `MScale` staat op 0 of is te laag. | Stel een redelijke `MScale` in (bijv. `1e4`) om meetwaarden op te slaan. |

## Veelgestelde vragen

**V: Kan ik Aspose.GIS voor .NET gebruiken met andere GIS‑bestandsformaten?**  
A: Ja, Aspose.GIS ondersteunt Shapefile, GeoJSON, KML en nog veel meer formaten.

**V: Is Aspose.GIS voor .NET compatibel met .NET Core?**  
A: Absoluut. De bibliotheek werkt met .NET Framework, .NET Core en .NET 5/6+.

**V: Kan ik ruimtelijke bewerkingen uitvoeren zoals buffer of intersectie?**  
A: Ja, de API bevat methoden voor bufferen, intersecties en het berekenen van afstanden.

**V: Biedt Aspose.GIS mogelijkheden voor coördinatentransformatie?**  
A: Ja, je kunt geometrieën tussen verschillende spatial reference systems transformeren met de ingebouwde reprojection‑tools.

**V: Is er een proefversie beschikbaar?**  
A: Ja, je kunt een gratis proefversie downloaden van de [website](https://releases.aspose.com/gis/net/).

---

**Laatst bijgewerkt:** 2025-12-28  
**Getest met:** Aspose.GIS 24.11 voor .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
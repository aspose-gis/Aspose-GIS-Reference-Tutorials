---
date: 2025-12-28
description: Leer hoe u GeoJSON uit een stream kunt lezen met Aspose.GIS voor .NET.
  Deze C#‑handleiding voor het lezen van GeoJSON biedt een stapsgewijs voorbeeld voor
  het integreren van georuimtelijke gegevens.
linktitle: Read GeoJSON from Stream
second_title: Aspose.GIS .NET API
title: Hoe GeoJSON te lezen vanuit een stream met Aspose.GIS voor .NET
url: /nl/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe GeoJSON lezen uit een stream met Aspose.GIS voor .NET

## Introductie
Als je je afvraagt **hoe je geojson kunt lezen** in een .NET‑applicatie, ben je hier aan het juiste adres. In deze tutorial lopen we een volledige **c# geojson‑voorbeeld** door dat laat zien hoe je een GeoJSON‑string converteert, een GeoJSON‑laag opent vanuit een geheugen‑stream, en GeoJSON‑eigenschappen extraheert met Aspose.GIS. Aan het einde heb je een herbruikbaar patroon dat je in elk project kunt gebruiken dat met geografische data moet werken.

## Snelle antwoorden
- **Welke bibliotheek moet ik gebruiken?** Aspose.GIS voor .NET  
- **Kan ik GeoJSON direct uit een stream lezen?** Ja – gebruik `VectorLayer.Open` met `AbstractPath.FromStream`.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Is het extraheren van eigenschappen eenvoudig?** Ja – roep `GetValue<T>(columnName)` aan op een feature.

## Wat is “hoe je geojson leest”?
GeoJSON lezen betekent het parseren van het op JSON gebaseerde formaat dat geografische objecten (punten, lijnen, polygonen) beschrijft en die objecten beschikbaar maken als objecten die je kunt opvragen, bewerken of weergeven in je applicatie.

## Waarom Aspose.GIS gebruiken om **geojson‑laag te openen**?
Aspose.GIS verbergt de low‑level parsing‑details en biedt een consistente API voor veel GIS‑formaten. Het stelt je in staat om **geojson‑laag te openen** direct vanuit een stream, grote bestanden efficiënt te verwerken en attribuutwaarden van features te benaderen zonder eigen JSON‑parsers te schrijven.

## Voorvereisten
Voordat we beginnen, zorg dat je het volgende hebt:

1. **Basiskennis van C#** – je moet vertrouwd zijn met .NET‑syntaxis en de Visual Studio‑IDE.  
2. **Aspose.GIS geïnstalleerd** – download de bibliotheek van [hier](https://releases.aspose.com/gis/net/).  
3. **Een ontwikkelomgeving** – Visual Studio, Visual Studio Code of JetBrains Rider werken prima.  

## Namespaces importeren
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Stap 1: **GeoJSON‑string converteren** – een **c# geojson‑voorbeeld**
Eerst maken we een JSON‑string die een eenvoudige `FeatureCollection` vertegenwoordigt. Dit is het **convert geojson string**‑deel van de workflow.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Stap 2: **GeoJSON‑laag openen** vanuit een stream en **geojson‑eigenschappen extraheren**
Nu voeren we de string in een `MemoryStream`, openen deze als een GIS‑laag, en laten zien hoe je attribuutwaarden leest (de **extract geojson properties**‑stap).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **Pro tip:** `VectorLayer.Open` detecteert automatisch het GeoJSON‑formaat wanneer je `Drivers.GeoJson` opgeeft. Je kunt ook bestanden direct openen door een bestandspad op te geven in plaats van een stream.

## Veelvoorkomende problemen & oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **Ongeldig JSON‑formaat** | Controleer of de GeoJSON‑string correct is opgebouwd; gebruik een JSON‑validator. |
| **Coderingproblemen** | Zorg ervoor dat de stream UTF‑8 gebruikt (`Encoding.UTF8.GetBytes`). |
| **Ontbrekende eigenschappen** | Controleer of de eigenschapsnaam correct gespeld is (`"name"` in het voorbeeld). |
| **Licentie‑exception** | Gebruik een proeflicentie voor testen; pas een permanente licentie toe voor productie. |

## Veelgestelde vragen
### Is Aspose.GIS compatibel met andere GIS‑formaten?
Ja, Aspose.GIS ondersteunt GeoJSON, Shapefile, KML, GML en nog veel meer formaten.

### Kan ik Aspose.GIS uitproberen voordat ik koop?
Ja, je kunt een gratis proefversie van Aspose.GIS downloaden van [hier](https://releases.aspose.com/).

### Waar vind ik de documentatie voor Aspose.GIS?
De documentatie voor Aspose.GIS vind je [hier](https://reference.aspose.com/gis/net/).

### Hoe kan ik ondersteuning krijgen voor Aspose.GIS?
Je kunt ondersteuning krijgen voor Aspose.GIS op de Aspose‑forums [hier](https://forum.aspose.com/c/gis/33).

### Heb ik een tijdelijke licentie nodig om Aspose.GIS te gebruiken?
Je kunt een tijdelijke licentie voor Aspose.GIS verkrijgen via [hier](https://purchase.aspose.com/temporary-license/).

## Conclusie
In deze gids hebben we **hoe je geojson leest** vanuit een geheugen‑stream met Aspose.GIS voor .NET behandeld, een **c# read geojson**‑workflow gedemonstreerd, en laten zien hoe je **geojson‑eigenschappen kunt extraheren** uit de geopende laag. Met deze stappen kun je naadloos geospatiale data‑verwerking integreren in elke .NET‑applicatie.

---

**Laatst bijgewerkt:** 2025-12-28  
**Getest met:** Aspose.GIS 24.11 voor .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-04-24
description: Leer **hoe je geojson** uit een stream leest met Aspose.GIS voor .NET.
  Deze stapsgewijze handleiding laat je zien hoe je **geojson‑stream laadt**, deze
  parseert en eigenschappen extraheert in C#.
keywords:
- how to read geojson
- load geojson stream
- Aspose GIS GeoJSON
linktitle: GeoJSON lezen van stream
second_title: Aspose.GIS .NET API
title: Hoe GeoJSON uit een stream te lezen met Aspose.GIS voor .NET
url: /nl/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe GeoJSON te lezen vanuit een stream met Aspose.GIS voor .NET

## Introductie
Als je je afvraagt **hoe GeoJSON te lezen** in een .NET‑applicatie, ben je op de juiste plek. In deze tutorial lopen we een volledig **C# GeoJSON voorbeeld** door dat laat zien hoe je een GeoJSON‑string converteert, **geojson stream laden** in een memory‑stream, een GeoJSON‑laag opent, en GeoJSON‑eigenschappen extraheert met Aspose.GIS. Aan het einde heb je een herbruikbaar patroon dat je in elk project kunt gebruiken dat met geografische gegevens moet werken.

## Snelle antwoorden
- **Welke bibliotheek moet ik gebruiken?** Aspose.GIS voor .NET – het ondersteunt veel GIS‑formaten direct out‑of‑the‑box.  
- **Kan ik GeoJSON direct vanuit een stream lezen?** Ja – gebruik `VectorLayer.Open` met `AbstractPath.FromStream`.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een volledige licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Is het extraheren van eigenschappen eenvoudig?** Zeker – roep `GetValue<T>(columnName)` aan op een feature.

## Wat is “hoe GeoJSON te lezen”?
GeoJSON lezen betekent het parseren van het op JSON gebaseerde formaat dat geografische objecten (punten, lijnen, polygonen) beschrijft en die objecten omzetten in objecten die je kunt opvragen, bewerken of renderen in je applicatie.

## Waarom Aspose.GIS gebruiken om **geojson‑laag te openen**?
Aspose.GIS abstraheert de low‑level parse‑details en biedt je een consistente API voor veel GIS‑formaten. Het stelt je in staat om **geojson‑laag te openen** direct vanuit een stream, grote bestanden efficiënt te verwerken, en toegang te krijgen tot attribuut‑waarden van features zonder eigen JSON‑parsers te schrijven.

## Wanneer zou je **geojson‑stream laden**?
- Gegevens importeren van een webservice die GeoJSON retourneert in de respons‑body.  
- Gebruikers‑geüploade GeoJSON‑bestanden verwerken zonder ze eerst naar schijf te schrijven.  
- Werken met in‑memory data die on‑the‑fly wordt gegenereerd (bijv. vanuit een database of een andere API).  

## Voorvereisten
Voordat we beginnen, zorg ervoor dat je het volgende hebt:

1. **Basiskennis van C#** – je moet vertrouwd zijn met .NET‑syntaxis en de Visual Studio IDE.  
2. **Aspose.GIS geïnstalleerd** – download de bibliotheek van [here](https://releases.aspose.com/gis/net/).  
3. **Een ontwikkelomgeving** – Visual Studio, Visual Studio Code, of JetBrains Rider werkt prima.  

## Namespaces importeren
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Stap 1: **GeoJSON‑string converteren** – een **C# GeoJSON voorbeeld**
Eerst maken we een JSON‑string die een eenvoudige `FeatureCollection` vertegenwoordigt. Dit is het **geojson‑string converteren**‑deel van de workflow.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Stap 2: **GeoJSON‑stream laden** en **geojson‑eigenschappen extraheren**
Nu voeren we de string in een `MemoryStream`, openen deze als een GIS‑laag, en demonstreren we hoe attribuutwaarden gelezen kunnen worden (de **geojson‑eigenschappen extraheren** stap).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **Pro tip:** `VectorLayer.Open` detecteert automatisch het GeoJSON‑formaat wanneer je `Drivers.GeoJson` doorgeeft. Je kunt ook bestanden direct openen door een bestandspad op te geven in plaats van een stream.

## Veelvoorkomende problemen & oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **Ongeldig JSON‑formaat** | Controleer of de GeoJSON‑string goed gevormd is; gebruik een JSON‑validator. |
| **Coderingsproblemen** | Zorg ervoor dat de stream UTF‑8 gebruikt (`Encoding.UTF8.GetBytes`). |
| **Ontbrekende eigenschappen** | Controleer of de eigenschapsnaam correct gespeld is (`"name"` in het voorbeeld). |
| **Licentie‑uitzondering** | Gebruik een proeflicentie voor testen; pas een permanente licentie toe voor productie. |

## Veelgestelde vragen
### Is Aspose.GIS compatibel met andere GIS‑formaten?
Ja, Aspose.GIS ondersteunt GeoJSON, Shapefile, KML, GML en nog veel meer formaten.

### Kan ik Aspose.GIS uitproberen voordat ik het koop?
Ja, je kunt een gratis proefversie van Aspose.GIS downloaden van [here](https://releases.aspose.com/).

### Waar kan ik de documentatie voor Aspose.GIS vinden?
Je kunt de documentatie voor Aspose.GIS vinden [here](https://reference.aspose.com/gis/net/).

### Hoe kan ik ondersteuning krijgen voor Aspose.GIS?
Je kunt ondersteuning voor Aspose.GIS krijgen op de Aspose‑forums [here](https://forum.aspose.com/c/gis/33).

### Heb ik een tijdelijke licentie nodig om Aspose.GIS te gebruiken?
Je kunt een tijdelijke licentie voor Aspose.GIS verkrijgen via [here](https://purchase.aspose.com/temporary-license/).

## Conclusie
In deze gids hebben we **hoe GeoJSON te lezen** vanuit een memory‑stream met Aspose.GIS voor .NET behandeld, een **C# GeoJSON‑lezen** workflow gedemonstreerd, en laten zien hoe **geojson‑eigenschappen te extraheren** uit de geopende laag. Met deze stappen kun je naadloos geospatiale gegevensverwerking integreren in elke .NET‑applicatie.

---

**Laatst bijgewerkt:** 2026-04-24  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
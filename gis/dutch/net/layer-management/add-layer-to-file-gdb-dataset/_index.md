---
date: 2026-01-13
description: Leer hoe u een laag toevoegt aan een File GDB‑dataset met Aspose.GIS,
  met ondersteuning voor de ruimtelijke referentie WGS84. Volg deze stap‑voor‑stap‑gids
  om een laag toe te voegen aan GDB in .NET.
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: spatial reference wgs84 – Laag toevoegen aan GDB met Aspose.GIS
url: /nl/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# spatial reference wgs84 – Laag toevoegen aan GDB met Aspose.GIS

## Inleiding
Klaar om je GIS‑workflow te verbeteren met Aspose.GIS voor .NET? In deze tutorial leer je **hoe je een laag toevoegt aan een File GDB‑dataset** terwijl je werkt met het **spatial reference wgs84** coördinatensysteem. We lopen elke stap door, van het voorbereiden van je gegevensmap tot het valideren van de nieuw aangemaakte laag, zodat je zelfverzekerd geografische data kunt bewerken.

## Snelle antwoorden
- **Wat is het primaire coördinatensysteem?** spatial reference wgs84 (WGS 84)  
- **Welke bibliotheek levert de API?** Aspose.GIS voor .NET  
- **Heb ik een licentie nodig voor testen?** Ja – er is een tijdelijke Aspose‑licentie beschikbaar.  
- **Kan ik attributen toevoegen aan de nieuwe laag?** Absoluut, je kunt een willekeurig aantal feature‑attributen definiëren.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## Wat is spatial reference wgs84?
De spatial reference wgs84 (World Geodetic System 1984) is het meest gebruikte geografische coördinatensysteem. Het definieert breedte‑ en lengtegraad in graden en dient als de standaard‑CRS voor veel GIS‑datasets, inclusief degene die we in deze gids zullen maken.

## Waarom Aspose.GIS gebruiken om een laag toe te voegen?
- **Geen externe afhankelijkheden:** Werkt out‑of‑the‑box met pure .NET‑code.  
- **Volledige controle over schema:** Je kunt aangepaste attributen en geometrietypen definiëren.  
- **Cross‑platform:** Compatibel met Windows, Linux en macOS runtimes.  
- **Robuuste licensering:** Tijdelijke licenties laten je snel evalueren voordat je commit.

## Vereisten
Zorg ervoor dat je het volgende hebt voordat je begint:

- Aspose.GIS voor .NET Library: Download en installeer de bibliotheek vanaf de [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Documentmap: Maak een speciale map op je computer aan om GIS‑bestanden op te slaan.

## Namespaces importeren
Voeg de benodigde `using`‑statements toe aan je C#‑project zodat je toegang hebt tot Aspose.GIS‑klassen:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Stap 1: Map kopiëren
Dupliceer eerst de map die de originele GDB‑dataset bevat. Een kopie behouden beschermt de brondata terwijl je experimenteert.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Stap 2: Dataset openen en creatiemogelijkheid verifiëren
Open de nieuw gekopieerde dataset en bevestig dat er nieuwe lagen kunnen worden aangemaakt. De eigenschap `CanCreateLayers` moet **True** retourneren.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Stap 3: Nieuwe laag maken en vullen met spatial reference wgs84
Nu maken we een laag met de naam **data** en stellen we expliciet de spatial reference in op **Wgs84**. We voegen ook een eenvoudig attribuut **Name** toe en voegen één punt‑feature in.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## Stap 4: De toegevoegde laag openen en valideren
Tot slot open je de laag die je zojuist hebt aangemaakt en controleer je de inhoud. De console toont dat de laag één feature bevat en dat het **Name**‑attribuut overeenkomt met wat we hebben ingesteld.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Veelvoorkomende problemen & tips
- **Onjuist pad:** Zorg ervoor dat `dataDir` eindigt met een pad‑scheidingsteken (`/` of `\`) zodat de samengevoegde strings geldige bestands‑paden vormen.  
- **Licentiefouten:** Als je licentie‑waarschuwingen ziet, pas dan een tijdelijke licentie van het Aspose‑portaal toe voordat je de code uitvoert.  
- **CRS‑mismatch:** Wanneer je de laag later in een ander GIS‑tool opent, controleer dan of het gereedschap WGS 84 (EPSG:4326) herkent als coördinatensysteem.

## Veelgestelde vragen
### Q: Kan ik Aspose.GIS voor .NET gebruiken met andere GIS‑bibliotheken?
Aspose.GIS voor .NET is ontworpen om onafhankelijk te werken, maar kan worden geïntegreerd met andere bibliotheken voor uitgebreide functionaliteit.  

### Q: Is er een tijdelijke licentie beschikbaar voor testdoeleinden?
Ja, je kunt een tijdelijke licentie verkrijgen via [hier](https://purchase.aspose.com/temporary-license/) voor testen en evaluatie.  

### Q: Welke spatial reference‑systemen ondersteunt Aspose.GIS voor .NET?
Aspose.GIS voor .NET ondersteunt een breed scala aan spatial reference‑systemen, wat flexibiliteit biedt bij het verwerken van geografische data.  

### Q: Kan ik bijdragen aan de Aspose.GIS‑community?
Absoluut! Doe mee aan de discussies en deel je ervaringen op het [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).  

### Q: Waar vind ik gedetailleerde documentatie voor Aspose.GIS voor .NET?
Bekijk de uitgebreide documentatie [hier](https://reference.aspose.com/gis/net/) voor diepgaande informatie over Aspose.GIS voor .NET.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2026-01-13  
**Getest met:** Aspose.GIS voor .NET (nieuwste stabiele versie)  
**Auteur:** Aspose
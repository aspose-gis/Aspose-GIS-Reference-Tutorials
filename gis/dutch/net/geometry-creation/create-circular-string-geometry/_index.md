---
date: 2025-12-12
description: Leer hoe u een vectorlaag maakt en cirkelvormige stringgeometrie toevoegt
  met Aspose.GIS voor .NET – een snelle manier om GIS-toepassingen te bouwen.
linktitle: Create Circular String Geometry
second_title: Aspose.GIS .NET API
title: Vectorlaag en Circulaire String maken in Aspose.GIS voor .NET
url: /nl/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak Vectorlaag en Circulaire String Geometrie met Aspose.GIS voor .NET

## Introductie
Als je een GIS‑applicatie bouwt op het .NET‑platform, is de eerste stap vaak **een vector layer maken** objecten die je ruimtelijke kenmerken opslaan. Aspose.GIS voor .NET maakt dit proces eenvoudig en stelt je in staat die lagen te verrijken met geavanceerde geometrieën zoals circulaire strings. In deze tutorial leer je precies hoe je een vectorlaag maakt, een circulaire string‑geometrie toevoegt en het resultaat opslaat als een Shapefile — allemaal met nette, productie‑klare C#‑code.

## Snelle Antwoorden
- **Wat betekent “create vector layer”?** Het maakt een nieuwe container (laag) die ruimtelijke kenmerken zoals punten, lijnen of polygonen kan bevatten.  
- **Welke klasse vertegenwoordigt een circular string?** `CircularString` van `Aspose.Gis.Geometries`.  
- **Kan ik de laag opslaan als een Shapefile?** Ja – gebruik `Drivers.Shapefile` bij het maken van de laag.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een tijdelijke licentie werkt voor evaluatie; een volledige licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Wat is “create vector layer”?
Een vectorlaag is een logische groepering van vectorfeatures (punten, lijnen, polygonen) die in één gegevensbron worden opgeslagen. In Aspose.GIS maak je een laag aan door `VectorLayer.Create` aan te roepen, waarbij je het doel‑bestandspad en de gewenste driver (bijv. Shapefile) opgeeft. Zodra de laag bestaat, kun je features toevoegen, geometrieën toewijzen en ruimtelijke bewerkingen uitvoeren.

## Waarom een circular string toevoegen?
Circular strings zijn een type **lineaire geometrie** dat boogsegmenten benadert met een reeks punten. Ze zijn nuttig voor het weergeven van gebogen wegen, rivierbochten, of elk kenmerk waarbij een vloeiende curve nodig is zonder veel kleine lijnsegmenten te gebruiken.

## Voorvereisten
- **.NET Framework of .NET Core** geïnstalleerd op je machine.  
- **Aspose.GIS for .NET** bibliotheek – download deze van de officiële site **[hier](https://releases.aspose.com/gis/net/)**.  
- Een IDE zoals **Visual Studio** of **JetBrains Rider**.  
- Basiskennis van **C#** programmeren.

## Namespaces importeren
Add the required namespaces to your C# file:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Stapsgewijze gids

### Stap 1: Definieer het uitvoer‑bestandspad
Stel de locatie in waar de Shapefile wordt weggeschreven.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

Vervang `"Your Document Directory"` door het daadwerkelijke mappad op je systeem.

### Stap 2: **Vectorlaag maken**
Open een `VectorLayer` met de `Create`‑methode. Dit is de kern van de **vectorlaag maken** bewerking.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### Stap 3: Maak een nieuw feature
Een feature vertegenwoordigt een enkel ruimtelijk record binnen de laag.

```csharp
    var feature = layer.ConstructFeature();
```

### Stap 4: Bouw de circular string‑geometrie
Voeg de punten toe die de gebogen vorm definiëren. De reeks punten creëert een boog die op dezelfde locatie begint en eindigt, waardoor een gesloten circular string ontstaat.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### Stap 5: Wijs de geometrie toe en voeg de feature toe aan de laag
Koppel de geometrie aan de feature en sla deze op in de laag.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

Wanneer het `using`‑blok eindigt, wordt de laag automatisch weggeschreven naar de Shapefile op schijf.

## Veelvoorkomende problemen & oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **Bestandspad ongeldig** | Zorg ervoor dat de map bestaat en dat je schrijfrechten hebt. |
| **CircularString verschijnt als een rechte lijn** | Controleer of de punten in de juiste volgorde zijn toegevoegd; het eerste en laatste punt moeten identiek zijn voor een gesloten vorm. |
| **Licentie‑exception** | Pas een tijdelijke licentie toe tijdens ontwikkeling of koop een volledige licentie voor productiegebruik. |

## Veelgestelde vragen

### Is Aspose.GIS for .NET compatibel met alle versies van het .NET Framework?
Ja, Aspose.GIS voor .NET is ontworpen om te werken met een breed scala aan .NET‑versies, van Framework 4.5 tot de nieuwste .NET 8‑releases.

### Kan ik Aspose.GIS for .NET integreren met andere GIS‑bibliotheken?
Absoluut! Je kunt data lezen met andere bibliotheken, deze manipuleren met Aspose.GIS, en vervolgens weer opslaan, dankzij de flexibele API.

### Ondersteunt Aspose.GIS for .NET visualisatie van ruimtelijke data?
Ja, de bibliotheek bevat renderings‑hulpmiddelen waarmee je kaarten en visuele weergaven van je geometrieën kunt genereren.

### Is er een community‑forum waar ik hulp kan zoeken voor Aspose.GIS for .NET?
Ja, je kunt het Aspose.GIS‑forum **[hier](https://forum.aspose.com/c/gis/33)** bezoeken om vragen te stellen en ervaringen te delen.

### Kan ik een tijdelijke licentie verkrijgen om Aspose.GIS for .NET te evalueren?
Natuurlijk! Een tijdelijke evaluatielicentie is beschikbaar **[hier](https://purchase.aspose.com/temporary-license/)**.

### Hoe voeg ik complexere geometrieën (bijv. MultiLineString) toe aan dezelfde laag?
Maak het juiste geometrie‑object (bijv. `MultiLineString`), vul het met individuele `LineString`‑objecten, wijs het toe aan `feature.Geometry` en voeg de feature toe zoals we deden met de circular string.

## Conclusie
Door deze stappen te volgen weet je nu hoe je **vectorlagen** objecten maakt en verrijkt met een circular string‑geometrie met behulp van Aspose.GIS voor .NET. Deze basis stelt je in staat rijkere GIS‑oplossingen te bouwen — nu transportnetwerken in kaart brengt, milieugegevens visualiseert, of aangepaste ruimtelijke analysetools ontwikkelt.

---

**Laatst bijgewerkt:** 2025-12-12  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
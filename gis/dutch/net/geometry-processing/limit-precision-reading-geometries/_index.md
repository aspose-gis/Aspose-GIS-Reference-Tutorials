---
date: 2026-04-03
description: Leer hoe u een vectorlaag maakt en de precisie beperkt bij het lezen
  van geometrieën met Aspose.GIS voor .NET. Stapsgewijze gids voor optimale verwerking
  van georuimtelijke gegevens.
keywords:
- create vector layer
- reduce shapefile size
- set precision model
linktitle: Beperk precisie bij het lezen van geometrieën
second_title: Aspose.GIS .NET API
title: Vectorlaag maken, nauwkeurigheid beperken met Aspose.GIS voor .NET
url: /nl/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak Vectorlaag, Beperk Precisie met Aspose.GIS voor .NET

## Inleiding
Bij het werken met georuimtelijke gegevens moet je vaak **vectorlaag maken** objecten en bepalen hoeveel decimalen van coördinatendetail je echt nodig hebt. Het beperken van precisie versnelt niet alleen de verwerking, maar kan ook **shapefile-grootte verminderen**, waardoor opslag en overdracht efficiënter worden. In deze tutorial lopen we door het maken van een vectorlaag, het schrijven van een eenvoudige puntgeometrie, en vervolgens het teruglezen ervan met zowel exacte als afgeronde precisiemodellen. Aan het einde begrijp je hoe je **precision model instellen** opties kunt instellen die passen bij de nauwkeurigheidseisen van je toepassing.

## Snelle Antwoorden
- **Wat betekent “limit precision”?** Het rondt coördinatiewaarden af tot een gedefinieerd aantal decimalen.  
- **Waarom eerst een vectorlaag maken?** Een vectorlaag is de container die geometrieën zoals punten, lijnen en polygonen opslaat.  
- **Welke precisiemodellen zijn beschikbaar?** `PrecisionModel.Exact` (geen afronding) en `PrecisionModel.Rounding(n)` (afronden op *n* decimalen).  
- **Heb ik een licentie nodig om dit te proberen?** Een gratis proefversie is beschikbaar op de releases-pagina.  
- **Welke .NET-versies worden ondersteund?** .NET Framework 4.5+, .NET Core, en .NET 5/6+.

## Waarom precisie beperken en hoe helpt dat?
- **Performance boost** – Minder cijfers betekenen minder gegevens om te parseren en te serialiseren.  
- **Smaller files** – Afgeronde coördinaten kunnen een shapefile merkbaar verkleinen, vooral bij grote datasets.  
- **Sufficient accuracy** – Veel GIS-analyses vereisen geen sub‑millimeter precisie, dus afronden op 2‑3 decimalen is vaak voldoende.

## Vereisten
Voordat we aan deze reis beginnen, zorg ervoor dat je de volgende vereisten hebt:
1. **Installation** – Aspose.GIS for .NET library should be installed in your development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).
2. **Familiarity with .NET** – Basic knowledge of C# and the .NET framework is necessary to understand and implement the provided code examples.
3. **Development Environment** – A working .NET development environment, such as Visual Studio, is required.
4. **Document Directory** – Have a directory set up where you can store and access the shapefile generated during the process.

## Import Namespaces
Voordat we beginnen met het implementeren van de functionaliteit om precisie te beperken bij het lezen van geometrieën, laten we ervoor zorgen dat we de benodigde namespaces importeren:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Hoe maak je een vectorlaag
De eerste stap is om een **vectorlaag** te maken die onze geometrie zal bevatten. Deze laag wordt opgeslagen als een Shapefile zodat we later kunnen heropenen met verschillende precisie‑instellingen.
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Instellen van precisie‑opties
Vervolgens moeten we opties definiëren voor het lezen van geometrieën, waarbij we het gewenste precisiemodel opgeven. We kunnen beginnen met exacte precisie:
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Geometrieën lezen met exacte precisie
Laten we nu de vectorlaag openen met de opgegeven opties om geometrieën te lezen met exacte precisie:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Precisie afkappen
Als we de precisie willen afkappen tot een specifiek aantal decimalen, kunnen we het precisiemodel dienovereenkomstig aanpassen:
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Hoe precisiemodel instellen voor verschillende scenario's
Je vraagt je misschien af wanneer je `Exact` versus `Rounding` moet gebruiken. Hier zijn twee veelvoorkomende scenario's:

| Scenario | Aanbevolen model | Reden |
|----------|-------------------|--------|
| Wetenschappelijke analyse met hoge precisie | `PrecisionModel.Exact` | Geen verlies van coördinatendetail |
| Web‑mapping tegels of mobiele apps | `PrecisionModel.Rounding(2)` | Vermindert bestandsgrootte en versnelt rendering |

Het kiezen van het juiste model is onderdeel van het **precision model instellen** besluitvormingsproces dat nauwkeurigheid afweegt tegen prestaties.

## Veelvoorkomende problemen en oplossingen
- **Unexpected coordinate values** – Zorg ervoor dat je `options.XYPrecisionModel` *vóór* het openen van de laag instelt. Wijzigen na het openen heeft geen effect.  
- **File not found** – Controleer of de variabele `path` naar een geldige map wijst en of de Shapefile succesvol is aangemaakt in de vorige stap.  
- **Incorrect geometry type** – Het voorbeeld gebruikt een `Point`. Voor andere geometrietypen (bijv. `LineString`) moet de cast overeenkomen met het daadwerkelijke type.  

## Tips om Shapefile-grootte te verkleinen
- Gebruik `PrecisionModel.Rounding` met het kleinste aantal decimalen dat nog aan je nauwkeurigheidseisen voldoet.  
- Verwijder onnodige attribuutvelden voordat je de laag schrijft.  
- Comprimeer de resulterende `.shp`, `.shx` en `.dbf` bestanden met standaard ZIP-hulpmiddelen als je ze moet overdragen.

## Conclusie
Samenvattend is het beheren van precisie bij het lezen van geometrieën een cruciaal aspect van georuimtelijke gegevensmanipulatie. Aspose.GIS for .NET biedt robuuste functionaliteiten om dit efficiënt te realiseren. Door de bovenstaande stappen te volgen kun je naadloos **vectorlaag maken** objecten, **precision model instellen**, en zelfs **shapefile-grootte verminderen** wanneer dat passend is, waardoor optimale gegevensverwerking in je toepassingen wordt gegarandeerd.

## Veelgestelde vragen
### Kan ik Aspose.GIS voor .NET gebruiken met andere .NET-frameworks zoals .NET Core of .NET Standard?
Ja, Aspose.GIS for .NET is compatible with various .NET frameworks, including .NET Core and .NET Standard.  
### Is er een proefversie beschikbaar voor Aspose.GIS voor .NET?
Ja, je kunt een gratis proefversie verkrijgen van de [releases page](https://releases.aspose.com/).  
### Waar kan ik uitgebreide documentatie vinden voor Aspose.GIS voor .NET?
Je kunt de [documentation](https://reference.aspose.com/gis/net/) raadplegen voor gedetailleerde informatie en voorbeelden.  
### Hoe kan ik tijdelijke licenties verkrijgen voor Aspose.GIS voor .NET?
Tijdelijke licenties kunnen worden verkregen via de [purchase page](https://purchase.aspose.com/temporary-license/) voor Aspose.GIS.  
### Waar kan ik hulp of ondersteuning zoeken voor Aspose.GIS voor .NET?
Je kunt het Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) bezoeken voor vragen, discussies of ondersteuning.

## Veelgestelde vragen
**Q: Heeft het beperken van precisie invloed op de originele shapefile?**  
A: Nee. Precisie wordt alleen toegepast bij het lezen van de geometrie; het bronbestand blijft ongewijzigd.  

**Q: Kan ik een ander precisiemodel gebruiken voor X- en Y-coördinaten?**  
A: Aspose.GIS past momenteel hetzelfde `XYPrecisionModel` toe op beide assen.  

**Q: Is het mogelijk om een aangepaste afrondingsfunctie in te stellen?**  
A: De API ondersteunt alleen de ingebouwde `PrecisionModel.Rounding(int)` methode. Voor aangepaste logica moet je de coördinaten na het lezen post‑processen.  

---
**Laatst bijgewerkt:** 2026-04-03  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
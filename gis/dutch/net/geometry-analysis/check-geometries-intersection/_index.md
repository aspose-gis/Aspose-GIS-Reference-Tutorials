---
date: 2025-12-03
description: Leer hoe je polygon-geometry in C# maakt en overlappende polygonen detecteert
  met de Intersects-methode van Aspose.GIS voor .NET.
language: nl
linktitle: Create Polygon Geometry C#
second_title: Aspose.GIS .NET API
title: Polygongeometrie maken in C# en intersectie controleren met Aspose.GIS voor
  .NET
url: /net/geometry-analysis/check-geometries-intersection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Polygongeometrie maken in C# en intersectie controleren met Aspose.GIS voor .NET

## Inleiding
Als je **polygongeometrie C#** wilt maken en snel wilt bepalen of twee vormen elkaar overlappen, biedt Aspose.GIS voor .NET een nette, high‑performance API. In deze gids lopen we het volledige proces door — van het installeren van de bibliotheek tot het gebruik van de `Intersects`‑methode om **overlappende polygonen** te detecteren. Aan het einde kun je polygon‑intersectiecontroles integreren in elke .NET‑applicatie met slechts een paar regels code.

## Snelle antwoorden
- **Wat doet de Intersects‑methode?** Het retourneert `true` wanneer twee geometrieën een gemeenschappelijk gebied delen.  
- **Welke namespace bevat polygonkl?** `Aspose.Gis.Geometries`.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Kan ik dit gebruiken met .NET Core / .NET 6+?** Ja, Aspose.GIS ondersteunt alle moderne .NET‑runtimes.  
- **Hoe lang duurt het om het voorbeeld uit te voeren?** Minder dan een seconde op een typische ontwikkelmachine.

## Wat is “polygongeometrie maken in C#”?
Een polygongeometrie maken in C# betekent het instantieren van de `Polygon`‑klasse (of andere geometrische types) die door Aspose.GIS worden geleverd en het leveren van een gesloten ring van `Point`‑objecten die de hoekpunten van definiëren. Eenmaal gebouwd kan de geometrie deelnemen aan ruimtelijke bewerkingen zoals intersectie, containment en afstandsberekeningen.

## Waarom Aspose.GIS gebruiken om overlappende polygonen te detecteren?
- **Geen externe afhankelijkheden** – pure .NET bibliotheek, geen native GIS‑installaties.  
- **Rijke ruimtelijke bewerkingen** – `Intersects`, `Disjoint`, `Contains`, enz., direct klaar voor gebruik.  
- **Hoge nauwkeurigheid** – robuuste afhandeling van randgevallen zoals gedeelde randen of hoekpunten.  
- **Cross‑platform** – werkt op Windows, Linux en macOS met .NET Core/5/6.

## Voorvereisten
Voordat je begint, zorg dat je het volgende hebt:

1. **Aspose.GIS for .NET** geïnstalleerd (zie de stappen hieronder).  
2. Een .NET ontwikkelomgeving (Visual Studio, VS Code of Rider).  
3. .NET Framework 4.6+ of .NET Core 3.1+.

### Installing Aspose.GIS for .NET
1. Navigeer naar de downloadpagina: Bezoek [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/) om de nieuwste versie van de toolkit te verkrijgen.  
2. Download de toolkit: Selecteer de juiste versie die compatibel is met uw ontwikkelomgeving en download de toolkit.  
3. Installeer de toolkit: Volg de meegeleverde installatie‑instructies om Aspose.GIS for .NET op uw ontwikkelmachine te installeren.

## Namespaces importeren
Om met Aspose.GIS for .NET te werken, moet je de benodigde namespaces in je project importeren.

1. Referenties toevoegen: Voeg in uw project referenties toe aan de Aspose.GIS‑assembly.  
2. Namespaces importeren: Importeer de benodigde namespaces in uw code‑bestand. Voor het gegeven voorbeeld, zorg ervoor dat u de volgende namespaces importeert:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Hoe polygongeometrie maken in C# met Aspose.GIS?
Nu de omgeving klaar is, laten we twee eenvoudige polygongeometrieën maken die we later op overlapping gaan testen.

### Stap 1: Geometrieën definiëren
In deze stap maak je polygonen die twee rechthoekige gebieden vertegenwoordigen. De hoekpunten worden gedefinieerd in een klokrichting, en het eerste punt wordt aan het einde herhaald om de ring te sluiten.

```csharp
var geometry1 = new Polygon(new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 3),
    new Point(3, 3),
    new Point(3, 0),
    new Point(0, 0),
}));
var geometry2 = new Polygon(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 4),
    new Point(4, 4),
    new Point(4, 1),
    new Point(1, 1),
}));
```

### Stap 2: De Intersects‑methode gebruiken om overlappende polygonen te detecteren
Met de geometrieën gedefinieerd, kunnen we nu de `Intersects`‑methode aanroepen. Deze methode **gebruikt het Intersects‑algoritme** om te controleren of een deel van de twee polygonen dezelfde ruimte deelt.

```csharp
Console.WriteLine(geometry1.Intersects(geometry2)); // True
Console.WriteLine(geometry2.Intersects(geometry1)); // True
```

### Stap 3: Controleren op gescheiden geometrieën (het tegenovergestelde van intersectie)
Als je moet bevestigen dat twee vormen **niet** overlappen, biedt de `Disjoint`‑methode het inverse resultaat.

```csharp
// 'Disjoint' is opposite to 'Intersects'
Console.WriteLine(geometry1.Disjoint(geometry2)); // False
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|----------|
| **Altijd `false`** | De polygonen zijn niet gesloten (eerste punt ≠ laatste punt). | Zorg ervoor dat het eerste punt wordt herhaald aan het einde van de coördinatenarray. |
| **Onverwacht `true` voor aangrenzende randen** | `Intersects` beschouwt gedeelde randen als intersectie. | Gebruik de `Touches`‑methode als u alleen randdetectie nodig heeft. |
| **Prestatie‑vertraging bij veel polygonen** | Elke oproep controleert elk vertex‑paar. | Batchverwerking met `GeometryCollection` of ruimtelijke indexering (R‑tree) indien ondersteund. |

## Veelgestelde vragen

**Q: Kan ik Aspose.GIS for .NET gebruiken met andere .NET‑frameworks?**  
A: Ja, Aspose.GIS for .NET is compatibel met diverse .NET‑frameworks, inclusief .NET Core en .NET Framework.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.GIS for .NET?**  
A: Ja, je kunt een gratis proefversie van Aspose.GIS for .NET verkrijgen via [hier](https://releases.aspose.com/).

**Q: Waar kan ik ondersteuning vinden voor Aspose.GIS for .NET?**  
A: Je kunt hulp zoeken en contact opnemen met de community op het [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

**Q: Kan ik een tijdelijke licentie verkrijgen voor Aspose.GIS for .NET?**  
A: Ja, je kunt een tijdelijke licentie verkrijgen via [hier](https://purchase.aspose.com/temporary-license/).

**Q: Waar kan ik een gelicentieerde versie van Aspose.GIS for .NET kopen?**  
A: Je kunt een gelicentieerde versie van Aspose.GIS for .NET kopen via [hier](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2025-12-03  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose
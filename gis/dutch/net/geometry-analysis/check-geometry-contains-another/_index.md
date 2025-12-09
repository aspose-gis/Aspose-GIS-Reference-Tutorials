---
date: 2025-12-04
description: Leer hoe u kunt bepalen of een punt binnen een polygoon ligt met C#.
  Deze Aspose.GIS .NET‑tutorial behandelt controles of een geometrie een punt bevat,
  geospatiale analyse‑technieken in .NET en best practices met Aspose GIS .NET.
linktitle: point inside polygon c# – Check Geometry Contains Another
second_title: Aspose.GIS .NET API
title: punt binnen veelhoek c# – Controleer of geometrie een andere bevat
url: /nl/net/geometry-analysis/check-geometry-contains-another/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# punt binnen veelhoek c# – Controleer of geometrie een andere bevat

## Introductie
Als je werkt aan **geospatial analysis .net** projecten, is een van de meest voorkomende taken om te bepalen of een specifieke locatie (een punt) binnen een gedefinieerd gebied (een veelhoek) valt. In deze tutorial laten we je stap‑voor‑stap zien hoe je een **point inside polygon c#** controle uitvoert met de **Aspose.GIS .NET** bibliotheek. Of je nu een kaartapplicatie, een locatie‑gebaseerde service, of een andere oplossing bouwt die ruimtelijke containlogica nodig heeft, de code‑fragmenten hieronder helpen je binnen enkele minuten op gang te komen.

## Snelle antwoorden
- **Wat betekent “point inside polygon c#”?** Het is een ruimtelijke query die true retourneert wanneer een puntgeometrie volledig binnen een veelhoekgeometrie ligt.  
- **Welke bibliotheek behandelt dit in .NET?** Aspose.GIS for .NET biedt de `SpatiallyContains` en `Within` methoden.  
- **Heb ik een licentie nodig?** Een gratis proefversie is beschikbaar; een commerciële licentie is vereist voor productiegebruik.  
- **Is het compatibel met .NET Core / .NET 6+?** Ja – Aspose.GIS ondersteunt volledig moderne .NET runtimes.  
- **Hoe lang duurt de implementatie?** Ongeveer 10 minuten om de code te kopiëren en het voorbeeld uit te voeren.

## Wat is point inside polygon c#?
Een *point inside polygon* test controleert of de coördinaten van een `Point`‑object zich binnen de grenzen van een `Polygon`‑object bevinden. In C# wordt dit doorgaans bereikt via geometriebibliotheken die de **Ray Casting**‑ of **Winding Number**‑algoritmen implementeren. Aspose.GIS abstraheert die details en biedt een eenvoudige API: `polygon.SpatiallyContains(point)`.

## Waarom Aspose.GIS .NET gebruiken voor geometry contains point‑controles?
- **Rijk geometrie‑model** – Ondersteunt polygonen, multipolygonen, lineaire ringen en meer.  
- **Hoge‑prestaties ruimtelijke bewerkingen** – Geoptimaliseerd voor grote datasets.  
- **Cross‑platform** – Werkt op .NET Framework, .NET Core en .NET 5/6+.  
- **Uitgebreide documentatie** – Veel voorbeelden voor geospatial analysis .net scenario’s.

## Voorvereisten
Voordat je begint, zorg ervoor dat je het volgende hebt:

1. **.NET‑ontwikkelomgeving** – .NET 6 SDK (of later) geïnstalleerd.  
2. **Aspose.GIS for .NET** – Download van de officiële release‑pagina en voeg het NuGet‑pakket toe aan je project.  
3. **Basis C#‑kennis** – Vertrouwd met klassen, objecten en console‑applicaties.

### 1. .NET‑ontwikkelomgeving configureren
Zorg ervoor dat je een werkende .NET‑ontwikkelomgeving op je machine hebt ingesteld. Dit omvat dat de .NET SDK geïnstalleerd en correct geconfigureerd is.

### 2. Aspose.GIS‑installatie
Installeer Aspose.GIS for .NET door de bibliotheek te downloaden van de release‑pagina [here](https://releases.aspose.com/gis/net/). Volg de installatie‑instructies in de documentatie [here](https://reference.aspose.com/gis/net/) om Aspose.GIS in je project te integreren.

### 3. Basisbegrip van C#
Maak jezelf vertrouwd met de programmeertaal C# aangezien Aspose.GIS for .NET voornamelijk met C# wordt gebruikt.

## Namespaces importeren
Importeer in je C#‑project de benodigde namespaces om de functionaliteiten van Aspose.GIS te gebruiken:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Stap 1: Definieer geometrie‑objecten
Eerst definieer je de geometrie‑objecten met behulp van Aspose.GIS‑klassen. Hier maken we een veelhoek met een buitenste ring en een binnenste ring (een gat), vervolgens een punt dat we zullen testen op containement.
```csharp
var geometry1 = new Polygon();
geometry1.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 4),
    new Point(4, 4),
    new Point(4, 0),
    new Point(0, 0),
});
geometry1.AddInteriorRing(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 3),
    new Point(3, 3),
    new Point(3, 1),
    new Point(1, 1),
}));
var geometry2 = new Point(2, 2);
```

## Stap 2: Controleer ruimtelijke containement
Vervolgens controleer je of de veelhoek **geometry1** het punt **geometry2** bevat. De `SpatiallyContains`‑methode retourneert `false` omdat het punt zich binnen de binnenste ring (het gat) bevindt.
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry2)); // False
```

## Stap 3: Definieer een andere geometrie
Nu definiëren we een tweede punt dat zich in de buitenste ring bevindt maar buiten de binnenste ring.
```csharp
var geometry3 = new Point(0.5, 0.5);
```

## Stap 4: Controleer ruimtelijke containement opnieuw
Het uitvoeren van dezelfde containement‑check met het nieuwe punt retourneert `true`, wat bevestigt dat het punt inderdaad binnen de buitenste grens van de veelhoek ligt.
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry3)); // True
```

## Stap 5: Equivalente functionaliteit
Aspose.GIS biedt ook de inverse methode `Within`. De volgende regel toont aan dat `geometry3.Within(geometry1)` hetzelfde resultaat oplevert als `geometry1.SpatiallyContains(geometry3)`.
```csharp
Console.WriteLine(geometry3.Within(geometry1)); // True
```

## Veelvoorkomende problemen en oplossingen
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **Onverwacht `false` resultaat** | Punt ligt binnen een gat (interne ring) van de veelhoek. | Zorg ervoor dat je test tegen de juiste veelhoek of gebruik `geometry1.ExteriorRing` voor eenvoudige polygonen zonder gaten. |
| **NullReferenceException** | Geometrie‑objecten zijn niet geïnitialiseerd vóór het aanroepen van `SpatiallyContains`. | Instantieer zowel de veelhoek‑ als punt‑objecten voordat je ruimtelijke methoden aanroept. |
| **Prestatie‑vertraging bij grote datasets** | Herhaaldelijk geometrie‑objecten aanmaken binnen lussen. | Herbruik geometrie‑instanties of verwerk in batches met `GeometryCollection`. |

## Veelgestelde vragen

**Q: Is Aspose.GIS compatibel met .NET Core?**  
A: Ja, Aspose.GIS ondersteunt volledig .NET Core, waardoor je geospatiale applicaties kunt ontwikkelen op verschillende platforms.

**Q: Kan ik geospatial analysis uitvoeren met Aspose.GIS?**  
A: Absoluut, Aspose.GIS biedt diverse functionaliteiten voor geospatial analysis, waaronder ruimtelijke queries, afstandsberekeningen en geometrie‑manipulaties.

**Q: Hoe vaak worden updates uitgebracht voor Aspose.GIS?**  
A: Aspose.GIS brengt regelmatig updates uit om de prestaties te verbeteren, nieuwe functies toe te voegen en eventuele gemelde problemen op te lossen. Je kunt op de hoogte blijven door de release‑pagina te bezoeken.

**Q: Is er een community‑forum voor Aspose.GIS‑gebruikers?**  
A: Ja, je kunt lid worden van het Aspose.GIS community‑forum [here](https://forum.aspose.com/c/gis/33) om in contact te komen met andere gebruikers, vragen te stellen en je ervaringen te delen.

**Q: Kan ik Aspose.GIS uitproberen voordat ik het koop?**  
A: Zeker, je kunt Aspose.GIS verkennen door de gratis proefversie te downloaden via [here](https://releases.aspose.com/).

## Conclusie
In deze gids hebben we een praktische **point inside polygon c#** oplossing gedemonstreerd met Aspose.GIS voor .NET. Door je geometrieën te definiëren en de `SpatiallyContains` (of `Within`) methode te gebruiken, kun je snel ruimtelijke containement‑vragen beantwoorden — een essentieel onderdeel van elke **geospatial analysis .net** workflow. Voel je vrij om te experimenteren met grotere datasets, verschillende geometrie‑typen, en deze controles te combineren met andere Aspose.GIS‑mogelijkheden zoals afstandsberekeningen of ruimtelijke indexering.

---

**Laatst bijgewerkt:** 2025-12-04  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
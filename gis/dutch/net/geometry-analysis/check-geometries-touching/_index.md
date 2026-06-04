---
date: 2026-02-08
description: Leer hoe u een netwerkrouteringscontrole uitvoert door aangrenzende geometrieën
  te detecteren met Aspose.GIS voor .NET, een krachtige bibliotheek voor het verwerken
  van ruimtelijke gegevens en het mogelijk maken van ruimtelijke analyse.
linktitle: How to Check Touching Geometries
second_title: Aspose.GIS .NET API
title: 'Netwerkrouteringscontrole: Aanrakende geometrieën met Aspose.GIS'
url: /nl/net/geometry-analysis/check-geometries-touching/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Netwerkrouteringscontrole: Aanrakende geometrieën met Aspose.GIS voor .NET

## Introductie
Wanneer u een **netwerkrouteringscontrole** moet uitvoeren tussen twee ruimtelijke objecten, biedt Aspose.GIS voor .NET een nette, type‑veilige API die de taak triviaal maakt. In deze tutorial ziet u hoe u lijnstrings, punten maakt en vervolgens de `Touches`‑methode gebruikt om te bepalen of de geometrieën alleen een grens delen. Deze bewerking is een hoeksteen van veel **spatial analysis .NET**‑scenario's, zoals routevalidatie, kaart‑overlay‑verificatie en nabijheids‑query's.

## Snelle antwoorden
- **Wat betekent “touching”?** Twee geometrieën delen minstens één grenspunt, maar hun interieurs snijden elkaar niet.  
- **Welke methode controleert dit?** `Geometry.Touches(otherGeometry)`.  
- **Heb ik een licentie nodig voor deze functie?** Een proefversie werkt voor ontwikkeling; een permanente licentie is vereist voor productie.  
- **Ondersteunde .NET‑versies?** .NET Framework, .NET Core, .NET 5/6/7 – allemaal gedekt door Aspose.GIS.  
- **Hoe lang duurt de implementatie?** Ongeveer 5‑10 minuten voor een basisvoorbeeld.  

## Hoe een netwerkrouteringscontrole uit te voeren met behulp van aanrakende geometrieën
Hieronder lopen we de exacte stappen door die u nodig heeft om **aanrakende** geometrieën te controleren en het resultaat in een routerings‑validatieworkflow te integreren.

### Wat is “Touching” in ruimtelijke analyse?
In GIS‑terminologie beschrijft *touching* een ruimtelijke relatie waarbij twee geometrieën elkaar aan hun randen ontmoeten, maar niet overlappen. Het verschilt van *intersects* (dat ook overlappende interieurs omvat) en wordt vaak gebruikt wanneer u moet valideren dat objecten alleen aan een grens samenkomen — bijvoorbeeld wegsegmenten die op een kruising aansluiten zonder elkaar te kruisen.

## Waarom Aspose.GIS gebruiken voor ruimtelijke analyse .NET?
Aspose.GIS biedt een volledig beheerde .NET‑bibliotheek waarmee u **spatial data** kunt verwerken zonder native GIS‑installaties. Het ondersteunt een breed scala aan formaten (Shapefile, GeoJSON, KML, enz.) en biedt high‑performance geometrie‑operaties zoals `Touches`, `Intersects`, `Contains` en meer. Omdat het pure .NET is, kunt u het direct in webservices, desktop‑apps of cloud‑functies embedden.

## Voorvereisten
Voordat u begint, zorg dat u het volgende heeft:

1. **Visual Studio** (een recente versie) geïnstalleerd op uw machine.  
2. **Aspose.GIS for .NET** – download het nieuwste pakket van de [official download page](https://releases.aspose.com/gis/net/).  
3. **Een geldige licentie** (of een gratis proefversie) – verkrijg deze van [here](https://releases.aspose.com/).  

### Instellen van uw omgeving
1. Installeer Visual Studio als u dat nog niet heeft gedaan.  
2. Download Aspose.GIS for .NET via de bovenstaande link en voeg het NuGet‑pakket toe aan uw project.  
3. Pas uw licentiebestand toe in de code (of gebruik een tijdelijke licentie voor testen).

## Namespaces importeren
Om de API te gebruiken, importeert u de benodigde namespaces:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Stap 1: Maak lijnstrings (en een punt) aan
Hieronder **maken we lijnstring**‑objecten en een punt die worden gebruikt om de aanrakende relatie te testen.

```csharp
var geometry1 = new LineString();
geometry1.AddPoint(0, 0);
geometry1.AddPoint(2, 2);
var geometry2 = new LineString();
geometry2.AddPoint(2, 2);
geometry2.AddPoint(3, 3);
var geometry3 = new Point(2, 2);
var geometry4 = new LineString();
geometry4.AddPoint(1, 1);
geometry4.AddPoint(4, 4);
```

*Uitleg*:  
- `geometry1` en `geometry2` delen het eindpunt `(2, 2)`.  
- `geometry3` is een punt dat precies op dat gedeelde eindpunt ligt.  
- `geometry4` kruist hetzelfde gebied maar **deelt geen** grens met `geometry1`.

## Stap 2: Controleer aanrakende relaties
Nu roepen we de `Touches`‑methode aan om te zien welke paren als aanrakend worden beschouwd.

```csharp
Console.WriteLine(geometry1.Touches(geometry2)); // True
Console.WriteLine(geometry2.Touches(geometry1)); // True
Console.WriteLine(geometry1.Touches(geometry3)); // True
Console.WriteLine(geometry1.Touches(geometry4)); // False
```

*Resultaat*:  
- De eerste drie controles geven **True** omdat de geometrieën op één enkel punt samenkomen zonder interior overlap.  
- De laatste controle geeft **False** omdat de twee lijnstrings over een lijnsegment overlappen, niet alleen op een grenspunt.

## Veelvoorkomende problemen & tips
- **Precisieproblemen** – GIS‑berekeningen zijn gebaseerd op floating‑point. Als u onverwachte `False`‑resultaten krijgt, overweeg dan de coördinaten te normaliseren of een tolerantie te gebruiken met `Geometry.EqualsExact(other, tolerance)`.  
- **Gemengde geometrietypen** – `Touches` werkt met punten, lijnen en polygonen, maar de semantiek verschilt; controleer altijd de verwachte relatie voor uw datamodel.  
- **Prestaties** – Voor grote datasets, batch de controles of gebruik ruimtelijke indexen (bijv. R‑tree) die door Aspose.GIS worden geleverd om O(N²)-vergelijkingen te vermijden.

## Veelgestelde vragen

**Q: Is Aspose.GIS compatibel met alle .NET‑frameworks?**  
A: Ja. Het ondersteunt .NET Framework, .NET Core, .NET 5+, en .NET 6+, waardoor u flexibiliteit heeft voor desktop‑, web‑ en cloud‑projecten.

**Q: Kan ik Aspose.GIS uitproberen voordat ik een licentie koop?**  
A: Absoluut. U kunt een gratis proefversie verkrijgen via de Aspose‑website [here](https://purchase.aspose.com/temporary-license/) om alle functies, inclusief de `Touches`‑operatie, te verkennen.

**Q: Waar vind ik ondersteuning voor Aspose.GIS‑gerelateerde vragen?**  
A: Bezoek het officiële [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) om vragen te stellen, voorbeelden te delen en hulp te krijgen van zowel de community als Aspose‑engineers.

**Q: Hoe vaak worden updates uitgebracht voor Aspose.GIS?**  
A: Aspose brengt regelmatig updates uit die nieuwe formatondersteuning, prestatie‑verbeteringen en bug‑fixes toevoegen, zodat compatibiliteit met de nieuwste .NET‑releases gewaarborgd blijft.

**Q: Kan ik een tijdelijke licentie voor Aspose.GIS verkrijgen?**  
A: Ja, een tijdelijke licentie is beschikbaar [here](https://purchase.aspose.com/temporary-license/) voor evaluatiedoeleinden.

**Q: Hoe helpt de `Touches`‑methode bij een netwerkrouteringscontrole?**  
A: Door te bevestigen dat wegsegmenten alleen op gedeelde eindpunten (touch) elkaar ontmoeten, kunt u valideren dat een routeringsnetwerk correct is verbonden zonder ongewenste overlappen.

---

**Laatst bijgewerkt:** 2026-02-08  
**Getest met:** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
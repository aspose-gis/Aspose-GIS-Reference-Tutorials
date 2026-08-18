---
date: 2026-06-05
description: Leer hoe je een line string ASP.NET maakt en een netwerkrouteringscontrole
  uitvoert door aangrenzende geometrieën te detecteren met Aspose.GIS for .NET, een
  krachtige bibliotheek voor het verwerken en analyseren van ruimtelijke gegevens.
keywords:
- create line string asp.net
- touching geometries
- Aspose.GIS spatial analysis
linktitle: Hoe aangrenzende geometrieën te controleren
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create line string ASP.NET and perform a network routing
    check by detecting touching geometries with Aspose.GIS for .NET, a powerful library
    for spatial data handling and analysis.
  headline: Create line string ASP.NET – Touching Geometries Check with Aspose.GIS
  type: TechArticle
- description: Learn how to create line string ASP.NET and perform a network routing
    check by detecting touching geometries with Aspose.GIS for .NET, a powerful library
    for spatial data handling and analysis.
  name: Create line string ASP.NET – Touching Geometries Check with Aspose.GIS
  steps:
  - name: '**Visual Studio** (any recent version).'
    text: '**Visual Studio** (any recent version).'
  - name: '**Aspose.GIS for .NET** – download the latest package from the [official
      download page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS for .NET** – download the latest package from the [official
      download page](https://releases.aspose.com/gis/net/).'
  - name: '**A valid license** (or a free trial) – obtain it from [here](https://purchase.aspose.com/temporary-license/)
      or view all releases at [here](https://releases.aspose.com/).'
    text: '**A valid license** (or a free trial) – obtain it from [here](https://purchase.aspose.com/temporary-license/)
      or view all releases at [here](https://releases.aspose.com/).'
  - name: Install Visual Studio if you haven’t already.
    text: Install Visual Studio if you haven’t already.
  - name: Add the Aspose.GIS NuGet package to your project (e.g., `Install-Package
      Aspose.GIS`).
    text: Add the Aspose.GIS NuGet package to your project (e.g., `Install-Package
      Aspose.GIS`).
  - name: Apply your license file in code (or use a temporary license for testing).
    text: Apply your license file in code (or use a temporary license for testing).
  type: HowTo
- questions:
  - answer: Yes. It supports .NET Framework, .NET Core, .NET 5+, and .NET 6+, giving
      you flexibility across desktop, web, and cloud projects.
    question: Is Aspose.GIS compatible with all .NET frameworks?
  - answer: Absolutely. You can obtain a free trial from the Aspose website [here](https://purchase.aspose.com/temporary-license/)
      to explore all features, including the `Touches` operation.
    question: Can I try Aspose.GIS before purchasing a license?
  - answer: Visit the official [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      to ask questions, share examples, and get help from both the community and Aspose
      engineers.
    question: Where can I find support for Aspose.GIS‑related queries?
  - answer: Aspose releases regular updates that add new format support, performance
      improvements, and bug fixes, ensuring compatibility with the latest .NET releases.
    question: How often are updates released for Aspose.GIS?
  - answer: By confirming that road segments only meet at shared endpoints (touch),
      you can validate that a routing network is correctly connected without unintended
      overlaps.
    question: How does the `Touches` method help with a network routing check?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Maak line string ASP.NET – Controle op aangrenzende geometrieën met Aspose.GIS
url: /nl/net/geometry-analysis/check-geometries-touching/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak lijnstring ASP.NET – Controle van raakliggende geometrieën met Aspose.GIS

## Introductie
Wanneer u een **netwerkrouteringscontrole** tussen twee ruimtelijke objecten moet uitvoeren, is de eerste stap om **line string ASP.NET**‑objecten te maken die uw wegsegmenten modelleren. Aspose.GIS voor .NET biedt een nette, type‑veilige API die deze bewerking triviaal maakt, zodat u zich kunt concentreren op de bedrijfslogica in plaats van op lage‑niveau geometrische berekeningen. In deze tutorial lopen we door het maken van lijnstrings, het toevoegen van een punt, en het gebruik van de `Touches`‑methode om te verifiëren dat geometrieën alleen op hun grenzen elkaar raken – een belangrijke vereiste voor routevalidatie, kaartoverlay‑verificatie en nabijheidsquery's.

## Snelle antwoorden
- **Wat betekent “touching”?** Twee geometrieën delen ten minste één grenspunt, maar hun interieurs overlappen niet.  
- **Welke methode controleert dit?** `Geometry.Touches(otherGeometry)`.  
- **Heb ik een licentie nodig voor deze functie?** Een proefversie werkt voor ontwikkeling; een permanente licentie is vereist voor productie.  
- **Ondersteunde .NET-versies?** .NET Framework, .NET Core, .NET 5/6/7 – allemaal gedekt door Aspose.GIS.  
- **Hoe lang duurt de implementatie?** Ongeveer 5‑10 minuten voor een basisvoorbeeld.  

## Wat is “Touching” in ruimtelijke analyse?
**Touching** beschrijft een ruimtelijke relatie waarbij twee geometrieën elkaar ontmoeten op hun randen zonder overlappende interieurs. Dit verschilt van *intersects*, dat ook interior overlap omvat, en is essentieel wanneer u moet bevestigen dat wegsegmenten alleen op kruispunten verbonden zijn.  
De `Touches`‑methode retourneert **true** wanneer de geometrieën een grenspunt delen maar geen interior‑punten, waardoor deze ideaal is voor het valideren van netwerkconnectiviteit zonder ongewenste kruisingen.

## Waarom Aspose.GIS gebruiken voor ruimtelijke analyse .NET?
Aspose.GIS ondersteunt **30+ invoer- en uitvoerformaten** (inclusief Shapefile, GeoJSON, KML en GML) en kan bestanden tot **2 GB** verwerken zonder het volledige document in het geheugen te laden, dankzij de streaming‑architectuur. De bibliotheek biedt high‑performance geometrie‑operaties—`Touches`, `Intersects`, `Contains`, `Distance`—die volledig beheerd worden in .NET, zodat u ruimtelijke analyse direct kunt integreren in webservices, desktop‑applicaties of Azure Functions zonder externe GIS‑installaties.

## Voorvereisten
Zorg ervoor dat u het volgende heeft voordat u begint:

1. **Visual Studio** (een recente versie).  
2. **Aspose.GIS for .NET** – download het nieuwste pakket van de [officiële downloadpagina](https://releases.aspose.com/gis/net/).  
3. **Een geldige licentie** (of een gratis proefversie) – verkrijg deze via [hier](https://purchase.aspose.com/temporary-license/) of bekijk alle releases op [hier](https://releases.aspose.com/).  

### Instellen van uw omgeving
1. Installeer Visual Studio als u dat nog niet heeft gedaan.  
2. Voeg het Aspose.GIS NuGet‑pakket toe aan uw project (bijv. `Install-Package Aspose.GIS`).  
3. Pas uw licentiebestand toe in code (of gebruik een tijdelijke licentie voor testen).

## Namespaces importeren
Om de API te gebruiken, importeer de benodigde namespaces:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Hoe controleer je raakliggende geometrieën in Aspose.GIS?
`Touches` is een methode die true retourneert wanneer twee geometrieën alleen een grenspunt delen en geen interior‑punten.  
Laad of maak de geometrieën, roep vervolgens `Touches` aan om de relatie te evalueren. De methode retourneert een Boolean die aangeeft of de twee vormen alleen een grenspunt delen. Deze één‑regelige controle is voldoende voor de meeste routerings‑validatiescenario's en kan in een strakke lus worden uitgevoerd voor grote netwerken.

## Stap 1: Lijnstrings maken (en een punt)
`LineString` is een geometrie‑type dat een reeks verbonden lijnsegmenten vertegenwoordigt, gedefinieerd door geordende punten.  

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
- `geometry4` kruist hetzelfde gebied maar deelt **niet** een grens met `geometry1`.

## Stap 2: Raakrelaties controleren
Nu roepen we de `Touches`‑methode aan om te zien welke paren als raak worden beschouwd.

```csharp
Console.WriteLine(geometry1.Touches(geometry2)); // True
Console.WriteLine(geometry2.Touches(geometry1)); // True
Console.WriteLine(geometry1.Touches(geometry3)); // True
Console.WriteLine(geometry1.Touches(geometry4)); // False
```

*Resultaat*:  
- De eerste drie controles geven **True** terug omdat de geometrieën op één punt elkaar ontmoeten zonder interior‑overlap.  
- De laatste controle geeft **False** terug omdat de twee lijnstrings over een lijnsegment overlappen, niet alleen op een grenspunt.

## Veelvoorkomende problemen & tips
- **Precisieproblemen** – GIS‑berekeningen zijn gebaseerd op floating‑point. Als u onverwachte `False`‑resultaten tegenkomt, overweeg dan om coördinaten te normaliseren of een tolerantie te gebruiken met `Geometry.EqualsExact(other, tolerance)`.  
- **Gemengde geometrietypen** – `Touches` werkt met punten, lijnen en polygonen, maar de semantiek verschilt; controleer altijd de verwachte relatie voor uw datamodel.  
- **Prestaties** – Voor grote datasets, batch de controles of gebruik ruimtelijke indexen (bijv. R‑tree) die door Aspose.GIS worden geleverd om O(N²)-vergelijkingen te vermijden.

## Veelgestelde vragen

**V: Is Aspose.GIS compatibel met alle .NET‑frameworks?**  
A: Ja. Het ondersteunt .NET Framework, .NET Core, .NET 5+, en .NET 6+, waardoor u flexibiliteit heeft voor desktop-, web- en cloudprojecten.

**V: Kan ik Aspose.GIS uitproberen voordat ik een licentie koop?**  
A: Absoluut. U kunt een gratis proefversie verkrijgen via de Aspose‑website [hier](https://purchase.aspose.com/temporary-license/) om alle functies te verkennen, inclusief de `Touches`‑operatie.

**V: Waar vind ik ondersteuning voor Aspose.GIS‑gerelateerde vragen?**  
A: Bezoek het officiële [Aspose.GIS‑forum](https://forum.aspose.com/c/gis/33) om vragen te stellen, voorbeelden te delen en hulp te krijgen van zowel de community als Aspose‑engineers.

**V: Hoe vaak worden updates uitgebracht voor Aspose.GIS?**  
A: Aspose brengt regelmatig updates uit die nieuwe formatondersteuning, prestatieverbeteringen en bugfixes toevoegen, zodat compatibiliteit met de nieuwste .NET‑releases gewaarborgd blijft.

**V: Hoe helpt de `Touches`‑methode bij een netwerkrouteringscontrole?**  
A: Door te bevestigen dat wegsegmenten alleen op gedeelde eindpunten (touch) elkaar ontmoeten, kunt u valideren dat een routeringsnetwerk correct verbonden is zonder ongewenste overlappingen.

**Laatst bijgewerkt:** 2026-06-05  
**Getest met:** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Geospatial Data Handling with Aspose.GIS for .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Create Polygon Geometry C# and Check Intersection with Aspose.GIS for .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [How to Calculate Length of Geometry in .NET with Aspose.GIS](/gis/net/geometry-analysis/get-geometry-length/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
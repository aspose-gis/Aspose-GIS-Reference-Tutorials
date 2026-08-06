---
date: 2026-08-03
description: Leer hoe u een linestring c# maakt met Aspose.GIS voor .NET, punten aan
  een linestring toevoegt en een punt‑op‑lijn‑controle uitvoert met de covers‑methode.
keywords:
- create linestring c#
- point on line check
- add points to linestring
- use covers method
lastmod: 2026-08-03
linktitle: Maak linestring c# – Controleer of geometrie een andere dekt
og_description: Maak linestring c# en verifieer een punt op een lijn met de Aspose.GIS
  covers‑methode. Leer nauwkeurige geometriecontroles voor .NET‑toepassingen. (150‑160
  chars)
og_image_alt: Developer guide showing linestring creation and covers check in C# with
  Aspose.GIS
og_title: Maak linestring c# – Controleer of geometrie een andere dekt (50‑60 chars)
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  headline: Create linestring c# – Check geometry covers another
  type: TechArticle
- description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  name: Create linestring c# – Check geometry covers another
  steps:
  - name: create a linestring object
    text: The `LineString` class represents a sequence of points connected by straight
      line segments in a two‑dimensional plane. Here, we instantiate a new `LineString`
      object, which represents a sequence of connected line segments in a two‑dimensional
      space.
  - name: add points to linestring
    text: '`AddPoint` appends a coordinate pair to the end of the `LineString` collection,
      preserving the order of insertion. We **add points to linestring** using the
      `AddPoint` method. In this example, we add two points: (0, 0) and (1, 1), forming
      a simple diagonal line segment.'
  - name: create a point object
    text: The `Point` class models a single location in a two‑dimensional coordinate
      system. Instantiate a `Point` object representing a single point in a two‑dimensional
      space. Here, we create a point at coordinates (0, 0).
  - name: perform a point on line check – does the line cover the point?
    text: '`Covers` determines whether the first geometry completely contains the
      second geometry, returning true only when every point of the second geometry
      lies inside the first. Use the `Covers` method to check if the line covers the
      point. In this case, it returns `True` because the point (0, 0) lies exac'
  - name: verify the reverse relationship – is the point covered by the line?
    text: '`CoveredBy` is the inverse of `Covers`; it returns true when the invoking
      geometry is entirely inside the target geometry. Similarly, use the `CoveredBy`
      method to check if the point is covered by the line. Since the point (0, 0)
      lies on the line, it also returns `True`.'
  type: HowTo
- questions:
  - answer: Yes, you can use Aspose.GIS for .NET in both commercial and non‑commercial
      projects after obtaining the appropriate license.
    question: Can I use Aspose.GIS for .NET in my commercial projects?
  - answer: Yes, Aspose.GIS for .NET is compatible with both .NET Framework and .NET
      Core environments.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Yes, Aspose.GIS for .NET supports a wide range of GIS formats including
      Shapefile, GeoJSON, KML, and more.
    question: Does Aspose.GIS for .NET support various GIS formats?
  - answer: Aspose.GIS for .NET is a proprietary library developed by Aspose, so external
      contributions are not accepted. However, you can provide feedback and suggestions
      to improve the library.
    question: Can I contribute to the development of Aspose.GIS for .NET?
  - answer: Updates for Aspose.GIS for .NET are released regularly to introduce new
      features, enhancements, and bug fixes. Check the [website](https://releases.aspose.com/gis/net/)
      for the latest releases.
    question: How often are updates released for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create linestring
- Aspose.GIS
- C# geometry analysis
title: Maak linestring c# – Controleer of geometrie een andere dekt
url: /nl/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Controleer of geometrie een andere bedekt

## Introductie
In deze tutorial leer je **hoe je een linestring c#** maakt met Aspose.GIS voor .NET, punten toevoegt aan een linestring, en een betrouwbare **punt‑op‑lijn controle** uitvoert met de `Covers` en `CoveredBy` methoden. Of je nu een kaarttool bouwt, ruimtelijke analyses uitvoert, of simpelweg geometrische relaties moet verifiëren, het beheersen van deze bewerkingen geeft je applicatie de precisie die ze nodig heeft.

## Snelle antwoorden
- **Wat betekent “create linestring c#”?** Het betekent het instantieren van een `LineString` geometrie‑object en het vullen ervan met coördinaten.  
- **Welke methode controleert of een punt op een lijn ligt?** Gebruik de `Covers`‑methode op de `LineString` of `CoveredBy` op de `Point`.  
- **Heb ik een licentie nodig om het voorbeeld uit te voeren?** Een tijdelijke licentie werkt voor evaluatie; een volledige licentie is vereist voor productie.  
- **Kan dit worden gebruikt met .NET Core?** Ja, Aspose.GIS ondersteunt .NET Framework en .NET Core.  
- **Hoeveel punten kan ik toevoegen aan een linestring?** Er is geen harde limiet; je kunt zoveel punten toevoegen als nodig is voor je ruimtelijke analyse.

## Wat is create linestring c#?
Een `LineString` is een geometrische vorm die bestaat uit een geordende lijst van punten die met rechte lijnsegmenten verbonden zijn. In C# maak je deze door de `LineString`‑klasse uit de `Aspose.Gis.Geometries` namespace te instantieren en vervolgens **punten toe te voegen aan linestring** met de `AddPoint`‑methode. Dit object dient als basis voor elke lineaire ruimtelijke analyse, zoals route‑mapping of netwerktracering.

## Waarom Aspose.GIS gebruiken voor een punt‑op‑lijn controle?
`Covers` is een ruimtelijke predicaat‑methode die true retourneert wanneer de eerste geometrie de tweede geometrie volledig bevat.  
Aspose.GIS biedt een deterministische, hoge‑precisie implementatie van ruimtelijke predicaten. Het ondersteunt meer dan 50 invoer‑ en uitvoer‑GIS‑formaten, kan netwerken van honderden kilometers aan lijnsegmenten verwerken zonder de volledige dataset in het geheugen te laden, en draait op .NET Framework, .NET Core en .NET 5/6+. Het gebruik van de `Covers`‑methode garandeert dat afrondingsfouten van floating‑point worden meegenomen, waardoor betrouwbare punt‑op‑lijn resultaten worden geleverd, zelfs in veeleisende enterprise‑scenario's.

## Vereisten
Voordat je begint met het gebruiken van Aspose.GIS voor .NET, zorg ervoor dat je de volgende vereisten hebt ingesteld:

### 1. Installeer Visual Studio
Zorg ervoor dat Visual Studio op je systeem is geïnstalleerd. Aspose.GIS voor .NET integreert naadloos met Visual Studio en biedt een soepele ontwikkelervaring.

### 2. Verkrijg Aspose.GIS voor .NET
Download de Aspose.GIS voor .NET bibliotheek van de [website](https://releases.aspose.com/gis/net/). Je kunt de bibliotheek direct downloaden of een pakketbeheerder zoals NuGet gebruiken om deze in je project te installeren.

### 3. Vertrouwdheid met .NET Framework
Basiskennis van het .NET‑framework en de programmeertaal C# is essentieel om Aspose.GIS voor .NET effectief te gebruiken.

### 4. Toegang tot documentatie en ondersteuning
Raadpleeg de [documentatie](https://reference.aspose.com/gis/net/) voor gedetailleerde informatie over Aspose.GIS API's en functionaliteiten. Als je problemen tegenkomt of vragen hebt, gebruik dan het [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) voor hulp.

### 5. Optioneel: tijdelijke licentie
Als je Aspose.GIS voor .NET verkent, kun je een tijdelijke licentie verkrijgen via de [tijdelijke licentiepagina](https://purchase.aspose.com/temporary-license/) om de functies van de bibliotheek te evalueren.

## Importeer namespaces
Voordat je Aspose.GIS voor .NET in je project gebruikt, moet je de benodigde namespaces importeren:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Laten we nu het voorbeeld opsplitsen in meerdere stappen om te begrijpen hoe je **controleert of een geometrie een andere bedekt** met Aspose.GIS voor .NET.

## Hoe maak je linestring c# – stapsgewijze handleiding
Laad je project, importeer de vereiste namespaces, en volg vervolgens de vijf beknopte stappen hieronder. In slechts een paar code‑regels heb je een `LineString`‑object, een `Point`‑object, en twee booleaanse controles die aangeven of de lijn het punt bedekt en of het punt door de lijn wordt gedekt.

### Stap 1: maak een linestring‑object
De `LineString`‑klasse vertegenwoordigt een reeks punten die met rechte lijnsegmenten in een tweedimensionaal vlak verbonden zijn.  
```csharp
var line = new LineString();
```
Hier instantieren we een nieuw `LineString`‑object, dat een reeks verbonden lijnsegmenten in een tweedimensionale ruimte vertegenwoordigt.

### Stap 2: voeg punten toe aan linestring
`AddPoint` voegt een coördinaatpaar toe aan het einde van de `LineString`‑collectie, waarbij de volgorde van invoeging behouden blijft.  
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
We **voegen punten toe aan linestring** met de `AddPoint`‑methode. In dit voorbeeld voegen we twee punten toe: (0, 0) en (1, 1), waardoor een eenvoudig diagonaal lijnsegment ontstaat.

### Stap 3: maak een punt‑object
De `Point`‑klasse modelleert een enkele locatie in een tweedimensionaal coördinatensysteem.  
```csharp
var point = new Point(0, 0);
```
Instantieer een `Point`‑object dat een enkel punt in een tweedimensionale ruimte vertegenwoordigt. Hier creëren we een punt op coördinaten (0, 0).

### Stap 4: voer een punt‑op‑lijn controle uit – dekt de lijn het punt?
`Covers` bepaalt of de eerste geometrie de tweede geometrie volledig bevat, en retourneert true alleen wanneer elk punt van de tweede geometrie binnen de eerste ligt.  
```csharp
Console.WriteLine(line.Covers(point));    // True
```
Gebruik de `Covers`‑methode om te controleren of de lijn het punt bedekt. In dit geval retourneert deze `True` omdat het punt (0, 0) precies op de lijn ligt.

### Stap 5: controleer de omgekeerde relatie – wordt het punt door de lijn gedekt?
`CoveredBy` is het inverse van `Covers`; het retourneert true wanneer de aanroepende geometrie volledig binnen de doelgeometrie ligt.  
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
Gebruik op dezelfde manier de `CoveredBy`‑methode om te controleren of het punt door de lijn wordt gedekt. Aangezien het punt (0, 0) op de lijn ligt, retourneert deze ook `True`.

## Veelvoorkomende problemen en oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|----------|
| `line.Covers(point)` retourneert `False` hoewel het punt op de lijn lijkt | De puntcoördinaten zijn niet exact hetzelfde door floating‑point precisie. | Gebruik `Math.Round` op coördinaten of pas een tolerantiebasis controle toe met `line.Distance(point) < epsilon`. |
| Ontbrekende `using Aspose.Gis.Geometries;` | Namespace niet geïmporteerd, waardoor compileerfouten ontstaan. | Zorg ervoor dat de importverklaring aanwezig is (zie de sectie **Importeer namespaces**). |
| Licentie‑exception tijdens runtime | Geen geldige licentie geladen voor productie. | Laad een tijdelijke of volledige licentie met `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Veelgestelde vragen

**Q: Kan ik Aspose.GIS voor .NET gebruiken in mijn commerciële projecten?**  
A: Ja, je kunt Aspose.GIS voor .NET gebruiken in zowel commerciële als niet‑commerciële projecten na het verkrijgen van de juiste licentie.

**Q: Is Aspose.GIS voor .NET compatibel met .NET Core?**  
A: Ja, Aspose.GIS voor .NET is compatibel met zowel .NET Framework als .NET Core omgevingen.

**Q: Ondersteunt Aspose.GIS voor .NET verschillende GIS-formaten?**  
A: Ja, Aspose.GIS voor .NET ondersteunt een breed scala aan GIS-formaten, waaronder Shapefile, GeoJSON, KML en meer.

**Q: Kan ik bijdragen aan de ontwikkeling van Aspose.GIS voor .NET?**  
A: Aspose.GIS voor .NET is een propriëtaire bibliotheek ontwikkeld door Aspose, dus externe bijdragen worden niet geaccepteerd. Je kunt echter feedback en suggesties geven om de bibliotheek te verbeteren.

**Q: Hoe vaak worden updates uitgebracht voor Aspose.GIS voor .NET?**  
A: Updates voor Aspose.GIS voor .NET worden regelmatig uitgebracht om nieuwe functies, verbeteringen en bugfixes toe te voegen. Bekijk de [website](https://releases.aspose.com/gis/net/) voor de nieuwste releases.

## Conclusie
Door de bovenstaande stappen te volgen, weet je nu hoe je **linestring c#** maakt, **punten toevoegt aan linestring**, en een betrouwbare **punt‑op‑lijn controle** uitvoert met de `Covers` en `CoveredBy` methoden. Deze mogelijkheid verbetert de ruimtelijke analysefuncties van je software en opent de deur naar meer geavanceerde GIS‑operaties zoals route‑validatie, netwerktopologie‑controles en nabijheids‑queries.

---

**Last Updated:** 2026-08-03  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Leer hoe je LineString-geomtrie maakt met Aspose.GIS voor .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Hoe je een punt toevoegt aan LineString en geometrie converteert naar bewerkbaar formaat met Aspose.GIS](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [punt binnen polygon c# – Controleer of geometrie een andere bevat](/gis/net/geometry-analysis/check-geometry-contains-another/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
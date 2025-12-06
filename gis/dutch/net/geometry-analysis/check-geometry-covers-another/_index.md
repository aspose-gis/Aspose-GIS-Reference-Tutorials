---
date: 2025-12-06
description: Leer hoe je een LineString maakt in C# met Aspose.GIS voor .NET, punten
  aan een LineString toevoegt en controleert of een geometrie een andere bedekt.
language: nl
linktitle: Create LineString C# – Check Geometry Covers Another
second_title: Aspose.GIS .NET API
title: LineString maken in C# – Controleer of geometrie een andere bedekt
url: /net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Controleer of geometrie een andere bedekt

## Introductie
Aspose.GIS for .NET is een krachtige bibliotheek die ontwikkelaars tools biedt om efficiënt met geografische gegevens te werken binnen hun .NET‑applicaties. Of je nu een kaartapplicatie bouwt, ruimtelijke gegevens analyseert, of geografische functies in je software integreert, Aspose.GIS biedt een uitgebreide set functionaliteiten om je ontwikkelingsproces te stroomlijnen. In deze tutorial leer je **hoe je een LineString in C# maakt**, punten aan de lijn toevoegt, en een **punt‑op‑lijn controle** uitvoert met behulp van de `Covers`‑ en `CoveredBy`‑methoden.

## Snelle Antwoorden
- **Wat betekent “create LineString in C#”?** Het betekent het instantieren van een `LineString`‑geometrieobject en het vullen ervan met coördinatenpunten.  
- **Welke methode controleert of een punt op een lijn ligt?** Gebruik de `Covers`‑methode op de `LineString` of `CoveredBy` op de `Point`.  
- **Heb ik een licentie nodig om het voorbeeld uit te voeren?** Een tijdelijke licentie werkt voor evaluatie; een volledige licentie is vereist voor productie.  
- **Kan dit worden gebruikt met .NET Core?** Ja, Aspose.GIS ondersteunt .NET Framework en .NET Core.  
- **Hoeveel punten kan ik toevoegen aan een LineString?** Er is geen harde limiet; je kunt zoveel punten toevoegen als nodig is voor je ruimtelijke analyse.

## Wat is **create LineString C#**?
Een `LineString` is een geometrische vorm die bestaat uit een geordende lijst van punten verbonden door rechte lijnsegmenten. In C# maak je deze door de `LineString`‑klasse uit de `Aspose.Gis.Geometries`‑namespace te instantieren en vervolgens **punten aan de LineString toe te voegen** met de `AddPoint`‑methode.

## Waarom Aspose.GIS gebruiken voor een punt‑op‑lijn controle?
- **Precisie** – Handelt zwevende‑komma‑berekeningen en ruimtelijke predicaten nauwkeurig af.  
- **Cross‑platform** – Werkt met .NET Framework, .NET Core en .NET 5/6+.  
- **Rijke API** – Biedt een volledige reeks methoden voor ruimtelijke relaties (`Covers`, `CoveredBy`, `Intersects`, enz.).

## Vereisten
Voordat je begint met het gebruiken van Aspose.GIS voor .NET, zorg ervoor dat je de volgende vereisten hebt ingesteld:

### 1. Installeer Visual Studio
Zorg ervoor dat Visual Studio op je systeem is geïnstalleerd. Aspose.GIS for .NET integreert naadloos met Visual Studio en biedt een soepele ontwikkelervaring.

### 2. Verkrijg Aspose.GIS voor .NET
Download de Aspose.GIS for .NET‑bibliotheek van de [website](https://releases.aspose.com/gis/net/). Je kunt de bibliotheek direct downloaden of een pakketbeheerder zoals NuGet gebruiken om deze in je project te installeren.

### 3. Vertrouwdheid met .NET Framework
Basiskennis van het .NET‑framework en de programmeertaal C# is essentieel om Aspose.GIS for .NET effectief te kunnen gebruiken.

### 4. Toegang tot Documentatie en Ondersteuning
Raadpleeg de [documentatie](https://reference.aspose.com/gis/net/) voor gedetailleerde informatie over Aspose.GIS‑API’s en functionaliteiten. Als je problemen tegenkomt of vragen hebt, gebruik dan het [Aspose.GIS‑forum](https://forum.aspose.com/c/gis/33) voor hulp.

### 5. Optioneel: Tijdelijke Licentie
Als je Aspose.GIS for .NET verkent, kun je een tijdelijke licentie verkrijgen via [hier](https://purchase.aspose.com/temporary-license/) om de functies van de bibliotheek te evalueren.

## Namespaces importeren
Voordat je Aspose.GIS for .NET in je project gebruikt, moet je de benodigde namespaces importeren:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Laten we nu het gegeven voorbeeld in meerdere stappen opsplitsen om te begrijpen hoe je **controleert of één geometrie een andere bedekt** met behulp van Aspose.GIS for .NET.

## Hoe **create LineString C#** – Stapsgewijze gids

### Stap 1: Maak een LineString‑object
```csharp
var line = new LineString();
```
Hier instantieren we een nieuw `LineString`‑object, dat een reeks verbonden lijnsegmenten in een tweedimensionale ruimte vertegenwoordigt.

### Stap 2: **Punten aan LineString toevoegen**
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
We **voegen punten toe aan de LineString** met de `AddPoint`‑methode. In dit voorbeeld voegen we twee punten toe: (0, 0) en (1, 1), waardoor een eenvoudige diagonale lijnsegment ontstaat.

### Stap 3: Maak een Point‑object
```csharp
var point = new Point(0, 0);
```
Instantieer een `Point`‑object dat een enkel punt in een tweedimensionale ruimte vertegenwoordigt. Hier maken we een punt op coördinaten (0, 0).

### Stap 4: Voer een **punt‑op‑lijn controle** uit – Bedekt de lijn het punt?
```csharp
Console.WriteLine(line.Covers(point));    // True
```
Gebruik de `Covers`‑methode om te controleren of de lijn het punt bedekt. In dit geval geeft het `True` terug omdat het punt (0, 0) precies op de lijn ligt.

### Stap 5: Controleer de omgekeerde relatie – Wordt het punt door de lijn gedekt?
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
Gebruik op dezelfde manier de `CoveredBy`‑methode om te controleren of het punt door de lijn wordt gedekt. Aangezien het punt (0, 0) op de lijn ligt, geeft het ook `True` terug.

## Veelvoorkomende Problemen en Oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| `line.Covers(point)` retourneert `False` hoewel het punt op de lijn lijkt te liggen | De puntcoördinaten zijn niet exact hetzelfde door floating‑point‑precisie. | Gebruik `Math.Round` op de coördinaten of pas een tolerantieberekening toe met `line.Distance(point) < epsilon`. |
| Ontbrekende `using Aspose.Gis.Geometries;` | Namespace niet geïmporteerd, wat compileerfouten veroorzaakt. | Zorg ervoor dat de importverklaring aanwezig is (zie de sectie **Namespaces importeren**). |
| Licentie‑exception tijdens uitvoering | Geen geldige licentie geladen voor productie. | Laad een tijdelijke of volledige licentie met `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Veelgestelde Vragen

**Q: Kan ik Aspose.GIS for .NET gebruiken in mijn commerciële projecten?**  
A: Ja, je kunt Aspose.GIS for .NET gebruiken in zowel commerciële als niet‑commerciële projecten nadat je de juiste licentie hebt verkregen.

**Q: Is Aspose.GIS for .NET compatibel met .NET Core?**  
A: Ja, Aspose.GIS for .NET is compatibel met zowel .NET Framework als .NET Core omgevingen.

**Q: Ondersteunt Aspose.GIS for .NET verschillende GIS‑formaten?**  
A: Ja, Aspose.GIS for .NET ondersteunt een breed scala aan GIS‑formaten, waaronder Shapefile, GeoJSON, KML en meer.

**Q: Kan ik bijdragen aan de ontwikkeling van Aspose.GIS for .NET?**  
A: Aspose.GIS for .NET is een propriëtaire bibliotheek ontwikkeld door Aspose, dus externe bijdragen worden niet geaccepteerd. Je kunt echter feedback en suggesties geven om de bibliotheek te verbeteren.

**Q: Hoe vaak worden updates uitgebracht voor Aspose.GIS for .NET?**  
A: Updates voor Aspose.GIS for .NET worden regelmatig uitgebracht om nieuwe functies, verbeteringen en bugfixes toe te voegen. Bekijk de [website](https://releases.aspose.com/gis/net/) voor de nieuwste releases.

## Conclusie
Samengevat biedt Aspose.GIS for .NET krachtige tools voor het werken met geografische gegevens in .NET‑applicaties. Door de bovenstaande stappen te volgen, kun je efficiënt **een LineString in C# maken**, **punten aan de linestring toevoegen**, en een **punt‑op‑lijn controle** uitvoeren om te bepalen of één geometrie een andere bedekt. Deze mogelijkheid verbetert de ruimtelijke analysefuncties van je software en opent de deur naar meer geavanceerde GIS‑bewerkingen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-06  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose
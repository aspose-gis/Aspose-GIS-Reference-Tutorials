---
date: 2026-02-08
description: Leer hoe je een linestring in C# maakt met Aspose.GIS voor .NET, punten
  toevoegt aan een linestring en een punt‑op‑lijn‑controle uitvoert met de covers‑methode.
linktitle: Create LineString C# – Check Geometry Covers Another
second_title: Aspose.GIS .NET API
title: Maak LineString C# – Controleer of geometrie een andere bedekt
url: /nl/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Controleer of geometrie een andere bedekt

## Inleiding
In deze tutorial leer je **hoe je een linestring c# maakt** met Aspose.GIS voor .NET, voeg je punten toe aan een linestring, en voer je een betrouwbare **point on line check** uit met de `Covers` en `CoveredBy` methoden. Of je nu een kaarttool bouwt, ruimtelijke analyses uitvoert, of simpelweg geometrische relaties moet verifiëren, het beheersen van deze bewerkingen geeft je applicatie de precisie die ze nodig heeft.

## Snelle antwoorden
- **Wat betekent “create linestring c#”?** Het betekent het instantieren van een `LineString` geometrie‑object en het vullen ervan met coördinatenpunten.  
- **Welke methode controleert of een punt op een lijn ligt?** Gebruik de `Covers`‑methode op de `LineString` of `CoveredBy` op de `Point`.  
- **Heb ik een licentie nodig om het voorbeeld uit te voeren?** Een tijdelijke licentie werkt voor evaluatie; een volledige licentie is vereist voor productie.  
- **Kan dit worden gebruikt met .NET Core?** Ja, Aspose.GIS ondersteunt .NET Framework en .NET Core.  
- **Hoeveel punten kan ik aan een linestring toevoegen?** Er is geen harde limiet; je kunt zoveel punten toevoegen als nodig is voor je ruimtelijke analyse.

## Wat is **create linestring c#**?
Een `LineString` is een geometrische vorm die bestaat uit een geordende lijst van punten die verbonden zijn door rechte lijnsegmenten. In C# maak je deze aan door de `LineString`‑klasse uit de `Aspose.Gis.Geometries`‑namespace te instantieren en vervolgens **punten toe te voegen aan linestring** met de `AddPoint`‑methode.

## Waarom Aspose.GIS gebruiken voor een point on line check?
- **Precisie** – Handelt zwevende‑komma berekeningen en ruimtelijke predicaten nauwkeurig af, waardoor je een **precision point on line** resultaat krijgt.  
- **Cross‑platform** – Werkt met .NET Framework, .NET Core en .NET 5/6+.  
- **Rijke API** – Biedt een volledige reeks ruimtelijke relatie‑methoden (`Covers`, `CoveredBy`, `Intersects`, enz.).

## Vereisten
Voordat je begint met het gebruiken van Aspose.GIS voor .NET, zorg ervoor dat je de volgende vereisten hebt ingesteld:

### 1. Installeer Visual Studio
Zorg ervoor dat Visual Studio op je systeem is geïnstalleerd. Aspose.GIS voor .NET integreert naadloos met Visual Studio, wat een soepele ontwikkelervaring biedt.

### 2. Verkrijg Aspose.GIS voor .NET
Download de Aspose.GIS voor .NET bibliotheek van de [website](https://releases.aspose.com/gis/net/). Je kunt de bibliotheek direct downloaden of een pakketbeheerder zoals NuGet gebruiken om deze in je project te installeren.

### 3. Basiskennis van .NET Framework
Basiskennis van het .NET‑framework en de programmeertaal C# is essentieel om Aspose.GIS voor .NET effectief te kunnen gebruiken.

### 4. Toegang tot documentatie en ondersteuning
Raadpleeg de [documentatie](https://reference.aspose.com/gis/net/) voor gedetailleerde informatie over Aspose.GIS API's en functionaliteiten. Als je problemen ondervindt of vragen hebt, maak gebruik van het [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) voor ondersteuning.

### 5. Optioneel: Tijdelijke licentie
Als je Aspose.GIS voor .NET verkent, kun je een tijdelijke licentie verkrijgen via [hier](https://purchase.aspose.com/temporary-license/) om de functies van de bibliotheek te evalueren.

## Importeren van namespaces
Voordat je Aspose.GIS voor .NET in je project gebruikt, moet je de benodigde namespaces importeren:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Laten we nu het gegeven voorbeeld opsplitsen in meerdere stappen om te begrijpen hoe je **controleert of één geometrie een andere bedekt** met Aspose.GIS voor .NET.

## Hoe maak je een linestring c# – Stapsgewijze handleiding

### Stap 1: Maak een LineString‑object
```csharp
var line = new LineString();
```
Hier instantieren we een nieuw `LineString`‑object, dat een reeks verbonden lijnsegmenten in een tweedimensionale ruimte vertegenwoordigt.

### Stap 2: **Punten toevoegen aan LineString**
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
We **voegen punten toe aan linestring** met de `AddPoint`‑methode. In dit voorbeeld voegen we twee punten toe: (0, 0) en (1, 1), waardoor een eenvoudige diagonale lijnsegment ontstaat.

### Stap 3: Maak een Point‑object
```csharp
var point = new Point(0, 0);
```
Instantieer een `Point`‑object dat een enkel punt in een tweedimensionale ruimte vertegenwoordigt. Hier maken we een punt aan op coördinaten (0, 0).

### Stap 4: Voer een **point on line check** uit – Bedekt de lijn het punt?
```csharp
Console.WriteLine(line.Covers(point));    // True
```
Gebruik de `Covers`‑methode om te controleren of de lijn het punt bedekt. In dit geval retourneert deze `True` omdat het punt (0, 0) precies op de lijn ligt.

### Stap 5: Verifieer de omgekeerde relatie – Wordt het punt door de lijn gedekt?
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
Gebruik op dezelfde manier de `CoveredBy`‑methode om te controleren of het punt door de lijn wordt gedekt. Aangezien het punt (0, 0) op de lijn ligt, retourneert deze ook `True`.

## Veelvoorkomende problemen en oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| `line.Covers(point)` retourneert `False` hoewel het punt op de lijn lijkt | De puntcoördinaten zijn niet exact gelijk vanwege zwevende‑komma precisie. | Gebruik `Math.Round` op de coördinaten of voer een tolerantieberekening uit met `line.Distance(point) < epsilon`. |
| Ontbrekende `using Aspose.Gis.Geometries;` | Namespace niet geïmporteerd, waardoor compileerfouten ontstaan. | Zorg ervoor dat de importverklaring aanwezig is (zie de sectie **Importeren van namespaces**). |
| Licentie‑exceptie tijdens runtime | Geen geldige licentie geladen voor productie. | Laad een tijdelijke of volledige licentie met `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Veelgestelde vragen

**V: Kan ik Aspose.GIS voor .NET gebruiken in mijn commerciële projecten?**  
A: Ja, je kunt Aspose.GIS voor .NET gebruiken in zowel commerciële als niet‑commerciële projecten na het verkrijgen van de juiste licentie.

**V: Is Aspose.GIS voor .NET compatibel met .NET Core?**  
A: Ja, Aspose.GIS voor .NET is compatibel met zowel .NET Framework als .NET Core omgevingen.

**V: Ondersteunt Aspose.GIS voor .NET verschillende GIS‑formaten?**  
A: Ja, Aspose.GIS voor .NET ondersteunt een breed scala aan GIS‑formaten, waaronder Shapefile, GeoJSON, KML en meer.

**V: Kan ik bijdragen aan de ontwikkeling van Aspose.GIS voor .NET?**  
A: Aspose.GIS voor .NET is een propriëtaire bibliotheek ontwikkeld door Aspose, dus externe bijdragen worden niet geaccepteerd. Je kunt echter feedback en suggesties geven om de bibliotheek te verbeteren.

**V: Hoe vaak worden updates uitgebracht voor Aspose.GIS voor .NET?**  
A: Updates voor Aspose.GIS voor .NET worden regelmatig uitgebracht om nieuwe functies, verbeteringen en bugfixes toe te voegen. Bekijk de [website](https://releases.aspose.com/gis/net/) voor de nieuwste releases.

## Conclusie
Door de bovenstaande stappen te volgen, weet je nu hoe je **linestring c# maakt**, **punten toevoegt aan linestring**, en een betrouwbare **point on line check** uitvoert met de `Covers` en `CoveredBy` methoden. Deze mogelijkheid verbetert de ruimtelijke analyse‑functies van je software en opent de deur naar meer geavanceerde GIS‑operaties.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2026-02-08  
**Getest met:** Aspose.GIS for .NET (latest release)  
**Auteur:** Aspose
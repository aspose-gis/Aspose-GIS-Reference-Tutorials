---
date: 2025-12-02
description: Leer hoe u de afstand tussen geometrieën kunt berekenen met Aspose.GIS
  voor .NET. Deze stapsgewijze gids laat zien hoe u Aspose.GIS gebruikt, de afstand
  tot een geometrie verkrijgt en afstandsberekeningen in uw toepassingen integreert.
linktitle: How to Calculate Distance Between Geometries
second_title: Aspose.GIS .NET API
title: Hoe de afstand tussen geometrieën te berekenen met Aspose.GIS
url: /nl/net/geometry-analysis/calculate-distance-between-geometries/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe afstand tussen geometrieën te berekenen met Aspose.GIS

## Inleiding
Als je ooit hebt moeten weten **hoe afstand te berekenen** tussen twee ruimtelijke objecten—of het nu een wegennet, bezorgzones of milieukenmerken betreft—dan is deze gids voor jou. In .NET maakt Aspose.GIS afstandsberekeningen eenvoudig, nauwkeurig en performant. We lopen een praktijkvoorbeeld door dat laat zien **hoe Aspose.GIS te gebruiken**, eenvoudige geometrieën te maken, en de **GetDistanceTo**‑methode aan te roepen om de afstand daartussen te verkrijgen.

## Snelle antwoorden
- **Wat betekent “afstand berekenen” in GIS?** Het retourneert de kortste (Euclidische) afstand tussen twee geometrieën.  
- **Welke Aspose.GIS‑klasse levert de berekening?** `Geometry.GetDistanceTo(Geometry other)`.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een licentie is vereist voor productie.  
- **Kan ik afstand berekenen voor 3‑D‑geometrieën?** Ja, Aspose.GIS ondersteunt 2‑D‑ en 3‑D‑berekeningen.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

## Wat is afstandsberekening in geospatiale programmering?
Afstandsberekening meet de kortste lijn die twee geometrieën met elkaar verbindt. Het is een kernoperatie voor taken zoals nabijheidsanalyse, routering, clustering en ruimtelijke indexering.

## Waarom Aspose.GIS gebruiken om afstand te berekenen?
- **Hoge precisie** – Gebruikt double‑precision rekenkunde.  
- **Zero‑dependency** – Geen native GIS‑bibliotheken nodig.  
- **Cross‑platform** – Werkt op Windows, Linux en macOS met .NET Core/5+.  
- **Rijk geometrisch model** – Ondersteunt punten, lijnen, polygonen en multi‑geometrieën direct uit de doos.

## Vereisten
- **Aspose.GIS for .NET** geïnstalleerd (download van de [Aspose.GIS for .NET releases page](https://releases.aspose.com/gis/net/)).  
- Basiskennis van C# en .NET‑projectstructuur.  
- Een ontwikkelomgeving zoals Visual Studio 2022 of VS Code.

## Namespaces importeren
Voordat je Aspose.GIS kunt gebruiken, voeg je de benodigde namespaces toe aan je C#‑bestand:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Stap 1: Maak een Polygon-geometrie
```csharp
var polygon = new Polygon();
```
We beginnen met een lege polygon die later een rechthoekig gebied zal vertegenwoordigen.

### Stap 2: Definieer de buitenring van de Polygon
```csharp
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(1, 0),
    new Point(0, 0),
});
```
De buitenring is een gesloten lus van punten die de grens van de polygon definieert. In dit voorbeeld maken we een 1 × 1‑vierkant.

### Stap 3: Maak een LineString-geometrie
```csharp
var line = new LineString();
```
Een `LineString` is een reeks verbonden lijnsegmenten. We gebruiken het om een weg of pad te vertegenwoordigen.

### Stap 4: Voeg punten toe aan de LineString
```csharp
line.AddPoint(2, 0);
line.AddPoint(1, 3);
```
Deze twee punten geven de lijn een schuine vorm die de polygon niet snijdt, waardoor de afstandsberekening interessant wordt.

### Stap 5: Bereken de afstand
```csharp
double distance = polygon.GetDistanceTo(line);
```
Hier **krijgen we afstand tot geometrie** door `GetDistanceTo` aan te roepen. Aspose.GIS berekent de kortste afstand tussen de rand van de polygon en de lijn.

### Stap 6: Resultaat weergeven
```csharp
Console.WriteLine(distance.ToString("F")); // 0.63
```
Het resultaat wordt afgedrukt met twee decimalen (`0.63`). Deze waarde vertegenwoordigt de minimale Euclidische afstand tussen het vierkant en de lijn.

## Veelvoorkomende gebruikssituaties
- **Logistiek:** Vind het dichtstbijzijnde depot voor een bezorgroute.  
- **Milieumonitoring:** Meet hoe ver een verontreinigingspluim van een beschermd gebied ligt.  
- **Stedelijke planning:** Bepaal de afstand tussen voorgestelde infrastructuur en bestaande herkenningspunten.

## Probleemoplossing & Tips
- **Coördinatensysteem is belangrijk:** Zorg ervoor dat beide geometrieën hetzelfde CRS (coordinate reference system) gebruiken voordat je de afstand berekent.  
- **Prestaties:** Overweeg bij grote datasets ruimtelijke indexering (R‑tree) om O(N²)-vergelijkingen te vermijden.  
- **Precisie:** Als je geodetische (great‑circle) afstanden nodig hebt, transformeer dan eerst de coördinaten naar een geschikte projectie.

## Veelgestelde vragen
### Is Aspose.GIS voor .NET compatibel met alle .NET-frameworks?
Ja, Aspose.GIS for .NET is compatibel met .NET Framework 4.6 en hoger.

### Kan ik Aspose.GIS voor .NET gebruiken voor complexe ruimtelijke analyses?
Absoluut! Aspose.GIS for .NET biedt een breed scala aan functionaliteiten voor geavanceerde ruimtelijke analyse‑taken.

### Ondersteunt Aspose.GIS voor .NET zowel 2D- als 3D-geometrieën?
Ja, je kunt zowel 2D- als 3D-geometrieën gebruiken met Aspose.GIS for .NET.

### Kan ik Aspose.GIS voor .NET integreren met andere GIS-bibliotheken?
Aspose.GIS for .NET biedt interoperabiliteit met andere GIS‑bibliotheken, zodat je extra functionaliteiten kunt benutten.

### Is technische ondersteuning beschikbaar voor Aspose.GIS voor .NET-gebruikers?
Ja, gebruikers van Aspose.GIS for .NET kunnen technische ondersteuning krijgen via de Aspose [forums](https://forum.aspose.com/c/gis/33).

## Veelgestelde vragen

**Q: Hoe nauwkeurig is de afstand die `GetDistanceTo` retourneert?**  
A: De methode gebruikt double‑precision rekenkunde en volgt de OGC Simple Features Specification, waardoor sub‑meter nauwkeurigheid wordt geboden voor typische vlakke coördinaten.

**Q: Kan ik afstand berekenen tussen een `Point` en een `Polygon`?**  
A: Ja—roep simpelweg `point.GetDistanceTo(polygon)` (of omgekeerd) aan en Aspose.GIS retourneert de kortste afstand van het punt tot de rand van de polygon.

**Q: Ondersteunt de API batch‑afstandsberekeningen?**  
A: Hoewel er geen enkele batch‑methode bestaat, kun je over collecties van geometrieën itereren en dezelfde `GetDistanceTo`‑aanroep efficiënt hergebruiken.

**Q: Wat gebeurt er als de geometrieën elkaar snijden?**  
A: De methode retourneert `0.0` omdat de kortste afstand tussen snijdende geometrieën nul is.

**Q: Is er een manier om de dichtstbijzijnde punten op elke geometrie te krijgen?**  
A: Ja—gebruik `Geometry.GetNearestPoints(Geometry other)` die een tuple retourneert met de dichtstbijzijnde punten op beide geometrieën.

## Conclusie
Afstand berekenen tussen geometrieën is een fundamentele bewerking in elke GIS‑enabled .NET‑applicatie. Door de bovenstaande stappen te volgen, weet je nu **hoe afstand te berekenen** met Aspose.GIS, hoe je **Aspose** kunt gebruiken om geometrieën te maken en te manipuleren, en hoe je de **afstand tot geometrie** met één methode‑aanroep kunt ophalen. Experimenteer met verschillende vormen, coördinatensystemen en grotere datasets om te zien hoe deze mogelijkheid je volgende ruimtelijke‑analyseproject kan versterken.

---

**Laatst bijgewerkt:** 2025-12-02  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
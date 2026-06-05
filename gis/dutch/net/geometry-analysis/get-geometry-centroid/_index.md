---
date: 2026-02-10
description: Leer hoe u de centroid van een geometrie berekent met Aspose.GIS voor
  .NET, het middelpunt van een polygoon opvraagt en de centroid van een multipolygon
  berekent voor ruimtelijke analyse.
linktitle: Get Geometry Centroid
second_title: Aspose.GIS .NET API
title: Hoe de centroid van een geometrie te berekenen met Aspose.GIS voor .NET
url: /nl/net/geometry-analysis/get-geometry-centroid/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe het centroid van een geometrie te berekenen met Aspose.GIS voor .NET

## Introductie
Als je werkt aan **C# spatial analysis** en moet weten **hoe je centroid berekent** van een willekeurige vorm, ben je hier op de juiste plek. In deze tutorial lopen we door het gebruik van Aspose.GIS voor .NET om **polygon centroid te berekenen**, dat centroid op te halen, en te zien hoe dit kleine stukje geometrie krachtige **integrated spatial analysis** scenario's kan ontsluiten, zoals labelplaatsing, clustering en afstandsberekeningen.

## Snelle antwoorden
- **Wat is de primaire methode?** `GetCentroid()` op een `IGeometry` object.  
- **Welke bibliotheek levert dit?** Aspose.GIS voor .NET.  
- **Hoeveel regels code?** Minder dan 15 regels totaal (exclusief using‑statements).  
- **Heb ik een licentie nodig?** Een tijdelijke licentie werkt voor testen; een volledige licentie is vereist voor productie.  
- **Kan het draaien op .NET 6+?** Ja – de API is volledig compatibel met .NET Core en .NET 5/6.  

## Wat is een centroid en waarom is het belangrijk?
Een centroid is het geometrische midden van een vorm – denk aan het “balanspunt”. Voor polygonen wordt het centroid (of **center point of polygon**) vaak gebruikt om labels te plaatsen, gemiddelde locaties te berekenen, of als referentiepunt in ruimtelijke queries te dienen. Weten **hoe je centroid berekent** snel stelt je in staat om ruimtelijke analyse‑functies te integreren zonder zelf complexe wiskunde te schrijven.

## Waarom het centroid van een multipolygon berekenen?
Wanneer je werkt met verzamelingen van polygonen (bijv. landsgrenzen bestaande uit eilanden), moet je mogelijk **centroid van multipolygon** objecten berekenen. Aspose.GIS laat je `GetCentroid()` aanroepen op een `MultiPolygon` en retourneert het centroid van de gecombineerde vorm, waardoor batch‑processing en kaart‑visualisatietaken worden vereenvoudigd.

## Voorvereisten
Voordat we beginnen, zorg dat je het volgende hebt:

### 1. Aspose.GIS voor .NET installeren
Download de bibliotheek van de [Aspose.GIS for .NET website](https://releases.aspose.com/gis/net/). Volg de installatie‑instructies om het NuGet‑pakket aan je project toe te voegen.

### 2. Vertrouwdheid met C# programmeren
Je moet comfortabel zijn met het schrijven van basis C#‑code. Als je nieuw bent, overweeg dan een snelle opfrisser over variabelen, klassen en console‑output.

### 3. Basisbegrip van geografische concepten
Hoewel niet verplicht, helpt kennis van het verschil tussen punten, lijnen en polygonen je de voorbeelden gemakkelijker te volgen.

## Importeren van namespaces
We moeten de Aspose.GIS‑klassen in scope brengen. Voeg de volgende `using`‑directieven toe aan de bovenkant van je C#‑bestand:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Deze namespaces geven je toegang tot geometry‑types, de `GetCentroid()`‑methode en standaard .NET‑hulpmiddelen.

## Hoe het centroid van een geometrie te berekenen
Hieronder vind je een stap‑voor‑stap‑gids die laat zien hoe je **polygon geometry maakt**, het centroid berekent en het resultaat weergeeft.

### Stap 1: Definieer een polygon
Eerst **maken we polygon geometry** door de hoekpunten op te geven. Dit voorbeeld bouwt een eenvoudige, niet‑zelf‑snijdende polygon:

```csharp
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(1, 0),
    new Point(2, 2),
    new Point(0, 4),
    new Point(5, 5),
    new Point(6, 1),
    new Point(1, 0),
});
```

### Stap 2: Haal het polygon centroid op (center point of polygon)
Zodra de polygon is gedefinieerd, roep je `GetCentroid()` aan om **polygon centroid op te halen**:

```csharp
IPoint centroid = polygon.GetCentroid();
```

### Stap 3: Toon centroidcoördinaten
Tot slot geef je de X‑ en Y‑coördinaten van het centroid weer. De opmaak‑string rondt de waarden af op twee decimalen:

```csharp
Console.WriteLine("{0:F} {1:F}", centroid.X, centroid.Y); // Output: 3.33 2.58
```

Het uitvoeren van het programma zal de centroidcoördinaten naar de console schrijven, waarmee wordt bevestigd dat de geometrie correct is verwerkt.

## Veelvoorkomende valkuilen & pro‑tips
- **Valkuil:** Het leveren van een zelf‑snijdende polygon kan een onverwacht centroid opleveren.  
  **Tip:** Valideer je polygon (bijv. met `IsValid` indien beschikbaar) voordat je `GetCentroid()` aanroept.
- **Valkuil:** Vergeten de ring te sluiten (het eerste en laatste punt moeten identiek zijn).  
  **Tip:** Herhaal altijd het eerste punt als laatste punt bij het construeren van een `LinearRing`.
- **Pro‑tip:** Voor grote datasets, bereken centroiden parallel met `Parallel.ForEach` om batch‑verwerking te versnellen.
- **Pro‑tip:** Werk je met een `MultiPolygon`, roep dan `GetCentroid()` direct op de collectie aan om **centroid van multipolygon** in één oproep te berekenen.

## Veelgestelde vragen

### Q: Is Aspose.GIS voor .NET compatibel met alle versies van .NET Framework?
A: Aspose.GIS voor .NET is compatibel met .NET Framework 4.6 en hoger, wat brede compatibiliteit over verschillende versies garandeert.

### Q: Kan ik tijdelijke licenties verkrijgen voor Aspose.GIS voor .NET?
A: Ja, tijdelijke licenties voor Aspose.GIS voor .NET zijn beschikbaar voor testdoeleinden. Je kunt ze verkrijgen via de [temporary license page](https://purchase.aspose.com/temporary-license/).

### Q: Is Aspose.GIS voor .NET geschikt voor zowel desktop‑ als webapplicaties?
A: Absoluut! Aspose.GIS voor .NET kan naadloos worden geïntegreerd in zowel desktop‑ als webapplicaties, waardoor flexibiliteit in ontwikkeling wordt geboden.

### Q: Biedt Aspose.GIS voor .NET uitgebreide documentatie?
A: Ja, uitgebreide documentatie voor Aspose.GIS voor .NET is beschikbaar op de [documentation page](https://reference.aspose.com/gis/net/), met gedetailleerde inzichten in het gebruik en de functionaliteiten.

### Q: Hoe kan ik hulp zoeken of contact opnemen met de community over Aspose.GIS voor .NET?
A: Voor vragen, ondersteuning of community‑betrokkenheid kun je het toegewijde Aspose.GIS‑forum bezoeken [hier](https://forum.aspose.com/c/gis/33).

## Veelgestelde vragen

**Q: Kan ik het centroid van een MultiPolygon berekenen?**  
A: Ja. Roep `GetCentroid()` aan op elk individueel polygon of op het `MultiPolygon`‑object; de API retourneert het centroid van de gecombineerde vorm.

**Q: Houdt de centroidberekening rekening met de kromming van de aarde?**  
A: De ingebouwde `GetCentroid()` werkt in de coördinatenruimte van de geometrie (planar). Voor geodetische data, reprojecteer naar een geschikt planair CRS voordat je het centroid berekent.

**Q: Is er een manier om het centroid van een geometrieverzameling in één oproep te krijgen?**  
A: Je kunt over de collectie itereren en centroiden afzonderlijk berekenen, of de `GeometryFactory` gebruiken om geometrieën te combineren en vervolgens `GetCentroid()` op het samengevoegde resultaat aanroepen.

**Q: Hoe nauwkeurig is het centroid voor zeer grote polygonen?**  
A: Nauwkeurigheid hangt af van de coördinatenprecisie en projectie. Voor extreem grote of complexe polygonen, overweeg de geometrie eerst te vereenvoudigen om de prestaties te verbeteren.

**Q: Kan ik de centroidoutput formatteren als GeoJSON?**  
A: Ja. Nadat je de `IPoint` hebt verkregen, kun je deze serialiseren met Aspose.GIS’s `GeoJsonWriter` of een andere JSON‑serializer naar keuze.

---

**Last Updated:** 2026-02-10  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
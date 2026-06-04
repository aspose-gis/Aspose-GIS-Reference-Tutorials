---
date: 2026-02-08
description: Leer hoe je geometrie kunt bufferen met Aspose.GIS voor .NET en ruimtelijke
  analyse‑buffers kunt uitvoeren, inclusief installatie, namespace‑importen en containment‑controles.
linktitle: How to Create Buffer Using Aspose.GIS for .NET
second_title: Aspose.GIS .NET API
title: Hoe geometrie te bufferen met Aspose.GIS voor .NET
url: /nl/net/geometry-analysis/create-geometry-buffer/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe geometrie bufferen met Aspose.GIS voor .NET

## Introductie
Als je werkt met regionale gegevens in een .NET‑omgeving, is het weten **hoe je geometrie moet bufferen** essentieel voor nabijheidsanalyse, zone‑indeling en generalisatie van objecten. In deze tutorial lopen we stap voor stap het volledige proces door met Aspose.GIS voor .NET—beginnend met installatie, het importeren van de benodigde naamruimten, het genereren van buffers voor lijn‑ en polygoongeometrieën, en uiteindelijk het controleren van ruimtelijke containment. Aan het einde kun je **ruimtelijke analysebuffers** toepassen in je eigen applicaties.

## Snelle antwoorden
- **Wat is een geometriebuffer?** Een polygoon die alle punten omsluit die zich binnen een synthetische afstand van een bron‑geometrie bevinden.
- **Waarom Aspose.GIS gebruiken voor buffering?** Het biedt een eenvoudige, krachtige API die werkt op .NET Framework, .NET Core en .NET 5/6+.
- **Hoe installeer je Aspose.GIS?** Download de bibliotheek van de officiële site en voeg deze toe als referentie in Visual Studio.
- **Hoe controleren je containment?** Gebruik de `SpatiallyContains`-methode om te testen of een punt binnen de geproduceerde buffer ligt.
- **Kan ik ruimtelijke analyse uitvoeren naast buffering?** Ja—bewerkingen zoals intersect, union en afstandsberekeningen worden ook ondersteund.

## Wat is een geometriebuffer?
Een geometriebuffer onmogelijk een zone rond een object (punt, lijn of polygoon) op een door de gebruiker bedoelde afstand. Deze zone is nuttig voor het gelijktijdige van nabije objecten, het creëren van impactgebieden, of het vereenvoudigen van complexe vormen.

## Geometrie bufferen met Aspose.GIS
### Waarom Aspose.GIS gebruiken voor buffers voor ruimtelijke analyse?
- **Cross‑platform ondersteuning:** Werkt op Windows, Linux en macOS.
- **Geen externe afhankelijkheden:** Geen verplichte voor native GIS‑bibliotheken.
- **Rijke API:** Bevat buffering, ruimtelijke predicaten en transformaties van coördinatensystemen.
- **Prestaties onbekende:** Verwerkt grote datasets efficiënt, waardoor het ideaal is voor intensieve ruimtelijke analysebuffers.

## Vereisten
Voordat we beginnen, zorg dat je de volgende hebt:

- **Visual Studio 2019 of later** (of een compatibele .NET‑IDE).
- **.NET 6 SDK** (van .NET Core 3.1+).
- **Aspose.GIS voor .NET‑bibliotheek** – zie de installatie‑stappen hieronder.

### Aspose.GIS voor .NET installeren
1. Download de Aspose.GIS voor .NET‑bibliotheek van de [downloadlink](https://releases.aspose.com/gis/net/).
2. Klik in Visual Studio met de tijdelijke op je project → **Toevoegen** → **Referentie…** → blader naar de gedownloade DLL en voeg deze toe.
3. Verkrijg een licentie via [Aspose](https://purchase.aspose.com/buy) of gebruik een [tijdelijke licentie](https://purchase.aspose.com/temporary-license/) voor evaluatie.

## Naamruimten importeren
Om de API te gebruiken, importeer je de benodigde naamruimten in je C#‑bestand.

### Aspose.GIS importeren
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Laten we nu het proces voor het maken van buffers stap voor stap analyseren.

## Stap-voor-stap handleiding

### Stap 1: Maak een geometriebuffer
In eerste instantie we een eenvoudige `LineString`‑geometrie die dient als bron voor onze buffer.

```csharp
// Define a LineString geometry
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(3, 3);
```

In dit fragment maken we een `LineString` en voegen twee punten toe, waardoor een diagonale lijn ontstaat van (0,0) tot (3,3).

### Stap 2: Genereer buffer voor LineString
Vervolgens genereren we een buffer rond de lijn met een **positieve afstand** van 1 eenheid.

```csharp
// Generate a buffer for the LineString with a positive distance
var lineBuffer = line.GetBuffer(distance: 1);
```

De `GetBuffer`‑methode retourneert een polygoon die elk punt omvat dat zich binnen 1 eenheid van de oorspronkelijke lijn bevindt.

### Stap 3: Controleer de ruimtelijke begrenzing
Nu demonstreren we **hoe je containment controleert** door te testen of specifieke punten binnen de buffer vallen.

```csharp
// Check spatial containment of points within the buffer
Console.WriteLine(lineBuffer.SpatiallyContains(new Point(1, 2)));     // True
Console.WriteLine(lineBuffer.SpatiallyContains(new Point(3.1, 3.1))); // True
```

De `SpatiallyContains`‑predicate retourneert `true` als het punt binnen de buffer‑polygoon ligt.

### Stap 4: Definieer een polygoongeometrie
We maken ook een `Polygon`‑geometrie om buffering met een **negatieve afstand** te illustreren, waardoor de vorm wordt verkleind.

```csharp
// Define a Polygon geometry
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 3),
    new Point(3, 3),
    new Point(3, 0),
    new Point(0, 0),
});
```

De polygoon stelt een vierkant voor met hoekpunten op (0,0), (0,3), (3,3) en (3,0).

### Stap 5: Genereer een buffer voor de polygoon
Het toepassen van een negatieve afstand van –1 eenheid krimpt de polygoon naar binnen.

```csharp
// Generate a buffer for the Polygon with a negative distance
var polygonBuffer = (IPolygon)polygon.GetBuffer(distance: -1);
```

De resulterende `polygonBuffer` is een kleiner vierkant, nuttig voor het creëren van binnenzones.

### Stap 6: Toegang tot de buitenste ringpunten van de buffer
Tenslotte halen we de coördinaten van de buitenring van de buffer op en tonen deze.

```csharp
// Access points of the exterior ring of the buffer Polygon
var ring = polygonBuffer.ExteriorRing;
for (int i = 0; i < ring.Count; ++i)
{
    Console.WriteLine("[{0}] = ({1} {2})", i, ring[i].X, ring[i].Y);
}
```

Deze lus print elke vertex van de verkleinde polygoon, waarmee de buffergeometrie wordt bevestigd.

## Veelvoorkomende problemen en oplossingen
| Uitgave | Oplossing |
|-------|----------|
| **Buffer retourneert `null`** | Zorg ervoor dat de afstandswaarde geschikt is voor het coördinatensysteem van de geometrie. |
| **`SpatiallyContains` retourneert altijd `false`** | Controleer of beide geometrieën gelijke ruimtelijke referentie (CRS) delen. |
| **Prestatievertraging bij grote datasets** | Verwerk geometrieën in batches en hergebruik gelijktijdig `GeometryFactory`‑instantie. |

## Veelgestelde vragen

**V: Is Aspose.GIS voor .NET compatibel met andere .NET-frameworks?**
A: Ja, het werkt met .NET Framework, .NET Core, .NET 5 en .NET 6.

**V: Kan ik ruimtelijke analyses uitvoeren met Aspose.GIS voor .NET?**
A: Absoluut. De bibliotheek ondersteunt buffering, intersectie, afstandsberekeningen en meer.

**V: Zijn er limieten voor de grootte van de dataset?**
A: De API is identiek voor grote datasets, maar het geheugenverbruik hangt af van de grootte van de geometrieën die je laadt.

**V: Ondersteunt Aspose.GIS verschillende ruimtelijke referentiesystemen?**
A: Ja, het ondersteunt een scala aan coördinatensystemen en staat on-the-fly transformaties toe.

**V: Waar kan ik technische ondersteuning krijgen?**
A: Bezoek het Aspose.GIS‑communityforum op [https://forum.aspose.com/c/gis/33](https://forum.aspose.com/c/gis/33) voor hulp.

---

**Laatst bijgewerkt:** 08-02-2026
**Getest voldaan:** Aspose.GIS voor .NET (nieuwste versie)
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
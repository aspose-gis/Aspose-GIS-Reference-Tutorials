---
date: 2026-05-31
description: Leer hoe je een polygoon maakt met Aspose.GIS voor .NET. Stapsgewijze
  handleiding voor .NET-ontwikkelaars om polygoongeometrie te bouwen en een polygoon‑shapefile
  te exporteren.
keywords:
- how to create polygon
- export polygon shapefile
- add vertices polygon
- build polygon coordinates
linktitle: Polygoongeometrie maken
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create polygon using Aspose.GIS for .NET. Step‑by‑step
    guide for .NET developers to build polygon geometry and export polygon shapefile.
  headline: How to Create Polygon Geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create polygon using Aspose.GIS for .NET. Step‑by‑step
    guide for .NET developers to build polygon geometry and export polygon shapefile.
  name: How to Create Polygon Geometry with Aspose.GIS for .NET
  steps:
  - name: Create a Polygon Object
    text: The `Polygon` class is the top‑level container that represents a single
      polygon geometry. **The `Polygon` class represents a closed geometric shape
      consisting of an exterior ring and optional interior rings.**
  - name: Define Exterior Ring
    text: A `LinearRing` holds the sequence of points that form the outer boundary.
      **The `LinearRing` class stores an ordered list of coordinate pairs that must
      form a closed loop.**
  - name: Add Points to the Exterior Ring
    text: Now we **add vertices polygon** by feeding latitude‑longitude pairs (or
      any coordinate system you prefer) into the ring. The points must form a closed
      loop, so the first and last coordinates are identical. **`LinearRing.AddPoint(x,
      y)` adds a single vertex to the ring; repeat for each coordinate.**
  - name: Set Exterior Ring on the Polygon
    text: Finally, assign the prepared ring to the polygon’s `ExteriorRing` property.
      The polygon is now a complete, valid geometry object. **The `ExteriorRing` property
      links the constructed `LinearRing` to the `Polygon` instance, finalizing the
      shape.** Congratulations! You have just **created polygon geome
  type: HowTo
- questions:
  - answer: Yes – simply iterate through your coordinate collection and call `ring.AddPoint(x,
      y)` for each item.
    question: Can I create a polygon from an existing list of coordinates?
  - answer: Create another `LinearRing`, add points, and assign it to `polygon.InteriorRings.Add(yourRing);`.
    question: How do I add an interior ring (hole) to the polygon?
  - answer: Use `polygon.IsValid` property; it returns `true` if the geometry complies
      with OGC standards.
    question: Is there a way to validate the polygon after creation?
  - answer: Absolutely. Use `FeatureWriter` with `GeoJson` format to write the polygon
      to a file, or choose `Shapefile` to **export polygon shapefile**.
    question: Can I export the polygon directly to GeoJSON?
  - answer: The library currently focuses on 2‑D geometries; for 3‑D you’ll need to
      manage Z‑values manually or use another specialized library.
    question: Does Aspose.GIS support 3‑D polygons?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hoe polygoongeometrie te maken met Aspose.GIS voor .NET
url: /nl/net/geometry-creation/create-polygon-geometry/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe maak je polygon geometrie met Aspose.GIS voor .NET

## Introductie  
Als je op zoek bent naar een duidelijke, praktische gids over **hoe je polygon** geometrie in een .NET‑omgeving maakt, ben je hier aan het juiste adres. In deze tutorial lopen we het volledige proces door met Aspose.GIS voor .NET – van het opzetten van het project tot het toevoegen van punten en het afronden van de polygon. Aan het einde begrijp je waarom deze bibliotheek een solide keuze is voor het werken met ruimtelijke data‑polygonstructuren en heb je een herbruikbaar **polygon geometry example** klaar voor je eigen GIS‑toepassingen. Je zult ook zien hoe je **export polygon shapefile** en andere veelvoorkomende formaten kunt exporteren.

## Snelle antwoorden
`Polygon` is de klasse die polygon‑geometrieën vertegenwoordigt in Aspose.GIS. `LinearRing.AddPoint` voegt een vertex toe aan een lineaire ring.  

- **Wat is de primaire klasse voor polygonen?** `Polygon` from `Aspose.Gis.Geometries`.  
- **Welke methode voegt vertices toe?** `LinearRing.AddPoint(x, y)` – het voegt polygon‑vertices één voor één toe.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een licentie is vereist voor productie.  
- **Ondersteunde .NET‑versies?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6+.  
- **Kan ik de polygon exporteren naar een bestand?** Ja – gebruik `FeatureWriter` om Shapefile, GeoJSON, enz. te schrijven, en gemakkelijk **export polygon shapefile**.

## Wat is een polygon‑geometrie?  
Een polygon is een gesloten vorm die bestaat uit een buitenring (de buitenste grens) en optioneel een of meer binnenringen (gaten). In GIS modelleren polygonen reële gebieden zoals meren, percelen of administratieve grenzen. Aspose.GIS biedt een schoon objectmodel waarmee je **build polygon coordinates** met slechts een paar regels C# kunt maken.

## Waarom Aspose.GIS gebruiken om polygon geometrie te maken?  
Aspose.GIS stelt je in staat om polygon geometrie snel te creëren terwijl het enterprise‑grade prestaties levert. Het ondersteunt **50+ input and output formats**, kan datasets van honderden pagina's verwerken zonder het volledige bestand in het geheugen te laden, en draait op .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6+. Dit betekent dat je **export polygon shapefile**, GeoJSON, KML en vele andere formaten direct vanuit code kunt exporteren, waardoor het gebruik van converters van derden overbodig wordt.

## Vereisten  
1. **Kennis van C# programmeren** – basiskennis van klassen en methoden.  
2. **Installatie van Aspose.GIS voor .NET** – je kunt het downloaden van [here](https://releases.aspose.com/gis/net/).  
3. **Ontwikkelomgeving configuratie** – Visual Studio, Rider, of elke IDE die .NET ondersteunt.  

## Namespaces importeren  
We moeten de GIS‑klassen in scope brengen. De `using`‑directieven hieronder zijn alles wat je nodig hebt voor dit voorbeeld.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Hoe polygon geometrie te maken in Aspose.GIS  

Laad je project, voeg de benodigde namespaces toe, instantieer een `Polygon`‑object, bouw de buitenring, voeg polygon‑vertices toe, en wijs ten slotte de ring toe — allemaal in een paar eenvoudige stappen. Deze aanpak werkt op alle ondersteunde .NET‑runtimes en produceert een geldige OGC‑conforme polygon die klaar is voor export.

### Stap 1: Maak een Polygon‑object  
De `Polygon`‑klasse is de top‑level container die een enkele polygon‑geometrie vertegenwoordigt.  
**De `Polygon`‑klasse vertegenwoordigt een gesloten geometrische vorm bestaande uit een buitenring en optionele binnenringen.**  
```csharp
Polygon polygon = new Polygon();
```

### Stap 2: Definieer de buitenring  
Een `LinearRing` bevat de reeks punten die de buitenste grens vormen.  
**De `LinearRing`‑klasse slaat een geordende lijst van coördinaatparen op die een gesloten lus moeten vormen.**  
```csharp
LinearRing ring = new LinearRing();
```

### Stap 3: Voeg punten toe aan de buitenring  
Nu **add vertices polygon** door latitude‑longitude‑paren (of elk gewenst coördinatensysteem) in de ring te voeren. De punten moeten een gesloten lus vormen, dus de eerste en laatste coördinaten zijn identiek.  
**`LinearRing.AddPoint(x, y)` voegt een enkele vertex toe aan de ring; herhaal voor elke coördinaat.**  
```csharp
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

### Stap 4: Stel de buitenring in op de Polygon  
Ten slotte wijs je de voorbereide ring toe aan de `ExteriorRing`‑eigenschap van de polygon. De polygon is nu een compleet, geldig geometrie‑object.  
**De `ExteriorRing`‑eigenschap koppelt de geconstrueerde `LinearRing` aan de `Polygon`‑instantie, waardoor de vorm wordt voltooid.**  
```csharp
polygon.ExteriorRing = ring;
```

Gefeliciteerd! Je hebt zojuist **created polygon geometry** met Aspose.GIS voor .NET. Vanaf hier kun je de polygon aan een feature koppelen, naar een bestand schrijven, of ruimtelijke analyses uitvoeren.

## Veelvoorkomende problemen & tips  

| Probleem | Waarom het gebeurt | Oplossing |
|-------|----------------|-----|
| **Ring not closed** | De eerste en laatste punten verschillen, waardoor de geometrie ongeldig is. | Herhaal de eerste coördinaat als laatste punt (zoals hierboven getoond). |
| **Wrong coordinate order** | GIS‑bibliotheken verwachten X (longitude) dan Y (latitude). | Zorg ervoor dat je `(longitude, latitude)` doorgeeft aan `AddPoint`. |
| **Missing license** | Proefmodus kan bepaalde bewerkingen beperken. | Pas een gratis proeflicentie toe voor testen; gebruik een betaalde licentie voor productie. |

## Veelgestelde vragen  

**Q: Kan ik een polygon maken van een bestaande lijst met coördinaten?**  
A: Ja – loop simpelweg door je coördinatenverzameling en roep `ring.AddPoint(x, y)` aan voor elk item.

**Q: Hoe voeg ik een binnenring (gat) toe aan de polygon?**  
A: Maak een andere `LinearRing`, voeg punten toe, en wijs deze toe aan `polygon.InteriorRings.Add(yourRing);`.

**Q: Is er een manier om de polygon te valideren na creatie?**  
A: Gebruik de `polygon.IsValid`‑eigenschap; deze retourneert `true` als de geometrie voldoet aan de OGC‑normen.

**Q: Kan ik de polygon direct exporteren naar GeoJSON?**  
A: Absoluut. Gebruik `FeatureWriter` met het `GeoJson`‑formaat om de polygon naar een bestand te schrijven, of kies `Shapefile` om **export polygon shapefile**.

**Q: Ondersteunt Aspose.GIS 3‑D polygonen?**  
A: De bibliotheek richt zich momenteel op 2‑D geometrieën; voor 3‑D moet je Z‑waarden handmatig beheren of een andere gespecialiseerde bibliotheek gebruiken.

---

**Laatst bijgewerkt:** 2026-05-31  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Polygon maken met gatgeometrie met Aspose.GIS](/gis/net/geometry-creation/create-polygon-with-hole-geometry/)
- [Polygon geometrie C# maken en intersectie controleren met Aspose.GIS voor .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Hoe buffer maken met Aspose.GIS voor .NET](/gis/net/geometry-analysis/create-geometry-buffer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
date: 2025-12-04
description: Leer hoe u raakliggende geometrieën kunt controleren met Aspose.GIS voor
  .NET, een krachtige bibliotheek om ruimtelijke gegevens te verwerken en ruimtelijke
  analyses uit te voeren.
language: nl
linktitle: How to Check Touching Geometries
second_title: Aspose.GIS .NET API
title: Hoe raakliggende geometrieën te controleren met Aspose.GIS voor .NET
url: /net/geometry-analysis/check-geometries-touching/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe raakliggende geometrieën te controleren

## Inleiding
Als je **hoe je raakliggend controleert** tussen twee ruimtelijke objecten, biedt Aspose.GIS voor .NET een schone, type‑veilige API die het werk triviaal maakt. In deze tutorial zie je hoe je line strings en punten maakt, en vervolgens de `Touches`‑methode gebruikt om te bepalen of de geometrieën alleen een grens delen. Dit is een kernoperatie in veel .NET‑scenario's voor ruimtelijke analyse, zoals netwerkroutering, kaartoverlay‑validatie en nabijheidscontroles.

## Snelle antwoorden
- **Wat betekent “touching”?** Twee geometrieën delen minstens één grenspunt, maar hun interieurs snijden elkaar niet.  
- **Welke methode controleert dit?** `Geometry.Touches(otherGeometry)`.  
- **Heb ik een licentie nodig voor deze functie?** Een proefversie werkt voor ontwikkeling; een permanente licentie is vereist voor productie.  
- **Ondersteunde .NET‑versies?** .NET Framework, .NET Core, .NET 5/6/7 – allemaal ondersteund door Aspose.GIS.  
- **Hoe lang duurt de implementatie?** Ongeveer 5‑10 minuten voor een basisvoorbeeld.

## Wat is “Touching” in ruimtelijke analyse?
In GIS‑terminologie beschrijft *touching* een ruimtelijke relatie waarbij twee geometrieën elkaar aan hun randen raken maar niet overlappen. Het verschilt van *intersects* (dat ook overlappende interieurs omvat) en wordt vaak gebruikt wanneer je moet valideren dat objecten alleen op een grens elkaar ontmoeten — bijvoorbeeld wegsegmenten die op een kruising aansluiten zonder elkaar te kruisen.

## Waarom Aspose.GIS gebruiken voor ruimtelijke analyse .NET?
Aspose.GIS biedt een volledig beheerde .NET‑bibliotheek waarmee je **ruimtelijke gegevens** kunt verwerken zonder native GIS‑installaties. Het ondersteunt een breed scala aan formaten (Shapefile, GeoJSON, KML, enz.) en biedt high‑performance geometrie‑bewerkingen zoals `Touches`, `Intersects`, `Contains` en meer. Omdat het pure .NET is, kun je het direct in webservices, desktop‑applicaties of cloud‑functies integreren.

## Voorvereisten
Zorg ervoor dat je het volgende hebt voordat je begint:

1. **Visual Studio** (een recente versie) geïnstalleerd op je machine.  
2. **Aspose.GIS for .NET** – download het nieuwste pakket van de [officiële downloadpagina](https://releases.aspose.com/gis/net/).  
3. **Een geldige licentie** (of een gratis proefversie) – verkrijg deze via [hier](https://releases.aspose.com/).  

### Instellen van je omgeving
1. Installeer Visual Studio als je dat nog niet hebt gedaan.  
2. Download Aspose.GIS for .NET via de bovenstaande link en voeg het NuGet‑pakket toe aan je project.  
3. Pas je licentiebestand toe in de code (of gebruik een tijdelijke licentie voor testen).

## Namespaces importeren
Om de API te gebruiken, importeer je de benodigde namespaces:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Stap 1: Maak line strings (en een punt)
Hieronder **maken we line‑string**‑objecten en een punt die worden gebruikt om de raakliggend‑relatie te testen.

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

## Stap 2: Controleer raakliggend relaties
Nu roepen we de `Touches`‑methode aan om te zien welke paren als raakliggend worden beschouwd.

```csharp
Console.WriteLine(geometry1.Touches(geometry2)); // True
Console.WriteLine(geometry2.Touches(geometry1)); // True
Console.WriteLine(geometry1.Touches(geometry3)); // True
Console.WriteLine(geometry1.Touches(geometry4)); // False
```

*Resultaat*:  
- De eerste drie controles geven **True** terug omdat de geometrieën op één enkel punt elkaar raken zonder interieur‑overlap.  
- De laatste controle geeft **False** terug omdat de twee line strings over een lijnsegment overlappen, niet alleen op een grenspunt.

## Veelvoorkomende problemen & tips
- **Precisieproblemen** – GIS‑berekeningen zijn gebaseerd op floating‑point. Als je onverwachte `False`‑resultaten krijgt, overweeg dan om coördinaten te normaliseren of een tolerantie te gebruiken met `Geometry.EqualsExact(other, tolerance)`.  
- **Gemengde geometrietypen** – `Touches` werkt met punten, lijnen en polygonen, maar de semantiek verschilt; controleer altijd de verwachte relatie voor je datamodel.  
- **Prestaties** – Voor grote datasets kun je de controles in batches uitvoeren of ruimtelijke indexen (bijv. R‑tree) gebruiken die door Aspose.GIS worden geleverd om O(N²)‑vergelijkingen te vermijden.

## Veelgestelde vragen

**V: Is Aspose.GIS compatibel met alle .NET‑frameworks?**  
Ja. Het ondersteunt .NET Framework, .NET Core, .NET 5+ en .NET 6+, waardoor je flexibiliteit hebt voor desktop-, web- en cloud‑projecten.

**V: Kan ik Aspose.GIS uitproberen voordat ik een licentie koop?**  
Absoluut. Je kunt een gratis proefversie verkrijgen via de Aspose‑website **[hier](https://purchase.aspose.com/temporary-license/)** om alle functies te verkennen, inclusief de `Touches`‑operatie.

**V: Waar kan ik ondersteuning vinden voor Aspose.GIS‑gerelateerde vragen?**  
Bezoek het officiële **[Aspose.GIS‑forum](https://forum.aspose.com/c/gis/33)** om vragen te stellen, voorbeelden te delen en hulp te krijgen van zowel de community als Aspose‑engineers.

**V: Hoe vaak worden updates voor Aspose.GIS uitgebracht?**  
Aspose brengt regelmatig updates uit die nieuwe formaatondersteuning, prestatieverbeteringen en bugfixes toevoegen, waardoor compatibiliteit met de nieuwste .NET‑releases wordt gegarandeerd.

**V: Kan ik een tijdelijke licentie voor Aspose.GIS verkrijgen?**  
Ja, een tijdelijke licentie is beschikbaar **[hier](https://purchase.aspose.com/temporary-license/)** voor evaluatiedoeleinden.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2025-12-04  
**Getest met:** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**Auteur:** Aspose  

---
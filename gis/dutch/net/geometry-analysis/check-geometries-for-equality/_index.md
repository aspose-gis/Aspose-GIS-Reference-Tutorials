---
date: 2026-06-05
description: Leer hoe u geometrieën in .NET kunt vergelijken met Aspose.GIS, dubbele
  geometrieën kunt detecteren en de gelijkheid van geometrieën in uw toepassingen
  kunt controleren.
keywords:
- how to compare geometries
- detect duplicate geometries
- Aspose.GIS geometry equality
linktitle: Hoe geometrieën op gelijkheid vergelijken
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to compare geometries in .NET using Aspose.GIS, detect duplicate
    geometries, and check geometry equality in your applications.
  headline: How to Compare Geometries for Equality using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard
      projects.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. Download a trial from the [Aspose.GIS releases page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Detailed docs are on the [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).
    question: Where can I find the full API documentation?
  - answer: Post your question on the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How do I get help if I run into an issue?
  - answer: Yes, temporary licenses are available on the [purchase page](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hoe geometrieën op gelijkheid vergelijken met Aspose.GIS voor .NET
url: /nl/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe geometrieën te vergelijken op gelijkheid met Aspose.GIS for .NET

## Inleiding
In deze tutorial leer je **hoe je geometrieën kunt vergelijken** met Aspose.GIS for .NET, een taak die essentieel is wanneer je dubbele geometrieën moet detecteren, ruimtelijke gegevens moet valideren of topologische regels moet afdwingen. Of je nu een kaartservice bouwt, batch‑ruimtelijke analyses uitvoert, of simpelweg controleert of twee vormen dezelfde locatie innemen, deze gids leidt je door het maken, wijzigen en testen van geometrie‑gelijkheid met nette, productie‑klare C#‑code.

## Snelle antwoorden
- **What does “compare geometries” mean?** Het controleert of twee geometrische objecten dezelfde ruimte innemen, ongeacht hoe ze zijn geconstrueerd.  
- **Which method is used?** `SpatiallyEquals` van de Aspose.GIS API.  
- **Do I need a license for development?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Supported .NET versions?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Typical implementation time?** Ongeveer 5‑10 minuten voor een basisgelijkheidscontrole.

## Wat is geometrie‑gelijkheid?
Geometrie‑gelijkheid, ook wel ruimtelijke gelijkheid genoemd, betekent dat twee geometrieën exact dezelfde set punten op het aardoppervlak vertegenwoordigen. Zelfs als de ene geometrie is opgebouwd als een `MultiLineString` en de andere als een enkele `LineString`, worden ze als gelijk beschouwd wanneer elke coördinaat binnen de gedefinieerde tolerantie overeenkomt. Deze definitie stelt ontwikkelaars in staat om betrouwbaar dubbele geometrieën te detecteren over heterogene gegevensbronnen.

## Waarom Aspose.GIS gebruiken om geometrieën te vergelijken?
Aspose.GIS biedt een high‑performance, offline geometrie‑engine die de noodzaak voor externe services elimineert. Het **ondersteunt meer dan 30 vector‑ en rasterformaten** (inclusief WKT, GeoJSON, Shapefile, KML, GML) en kan bestanden verwerken met **honderdduizenden vertices** terwijl het geheugenverbruik onder de 50 MB blijft. De `SpatiallyEquals`‑methode van de bibliotheek is precisiebewust en levert deterministische resultaten, zelfs bij floating‑point coördinaten.

### Waarom dit belangrijk is voor ontwikkelaars
Wanneer je **dubbele geometrieën** moet detecteren in batchprocessen, real‑time validatie‑pijplijnen of GIS‑datamigraties, verwijdert een bewezen bibliotheek giswerk en garandeert consistente resultaten over verschillende gegevensleveranciers.

## Vereisten
Voordat je begint, zorg dat je het volgende hebt:

- **.NET Framework of .NET Core geïnstalleerd** – elke versie die door Aspose.GIS wordt ondersteund.  
- **Aspose.GIS for .NET bibliotheek** – download van de [Aspose.GIS downloadpagina](https://releases.aspose.com/gis/net/).  
- **Een ontwikkel‑IDE** – Visual Studio, Rider, of VS Code met C#‑extensies.

## Namespaces importeren
In je .NET‑project voeg je de benodigde `using`‑statements toe zodat de compiler weet waar de GIS‑klassen te vinden zijn:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Stap 1: Definieer de geometrieën
`MultiLineString` vertegenwoordigt een verzameling lijncomponenten, terwijl `LineString` een enkele doorlopende lijn definieert. Beide klassen erven van het basistype `Geometry`.

Eerst maken we twee geometrieën die we gaan vergelijken. In dit voorbeeld is `geometry1` een `MultiLineString` bestaande uit twee lijnsegmenten, terwijl `geometry2` een enkele `LineString` is die dezelfde begin‑ en eindpunten beslaat.

```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```

## Stap 2: Controleer geometrieën op gelijkheid
`SpatiallyEquals` evalueert of twee geometrieën dezelfde set punten innemen, met optionele tolerantie voor floating‑point onnauwkeurigheid.

Nu gebruiken we de `SpatiallyEquals`‑methode om te zien of de twee vormen als gelijk worden beschouwd door de GIS‑engine.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

De console geeft `True` weer omdat, ondanks de verschillende constructie, beide geometrieën dezelfde lijn van (0,0) tot (2,2) bestrijken.

## Stap 3: Wijzig één geometrie
Om te illustreren hoe een wijziging de gelijkheid beïnvloedt, voegen we een extra punt toe aan `geometry2`.

```csharp
geometry2.AddPoint(3, 3);
```

## Stap 4: Controleer gelijkheid opnieuw na wijziging
Na de wijziging zijn de geometrieën niet meer gelijk, dus `SpatiallyEquals` retourneert `False`.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

De uitvoer `False` bevestigt dat het extra punt de ruimtelijke gelijkheid heeft verbroken.

## Hoe dubbele geometrieën te detecteren?
Laad elke geometrie, roep `SpatiallyEquals` aan met een geschikte tolerantie, en filter de geometrieën die `True` retourneren. Dit patroon schaalt goed met LINQ, waardoor je dubbele vormen in grote collecties kunt identificeren met slechts een paar regels code. Je kunt het ook combineren met `GroupBy` om identieke geometrieën te aggregeren en opslagkosten te verlagen.

## Veelvoorkomende problemen & tips
- **Precision problems** – Als je werkt met zeer hoge precisie‑coördinaten, overweeg dan afronding of gebruik de tolerantie‑overload van `SpatiallyEquals`.  
- **Different SRIDs** – Zorg ervoor dat beide geometrieën dezelfde Spatial Reference System Identifier (SRID) delen voordat je vergelijkt.  
- **Performance** – Voor grote collecties kunnen batch‑vergelijkingen met LINQ of parallelle lussen de overhead aanzienlijk verminderen.

## Veelgestelde vragen
**Q: Kan ik Aspose.GIS for .NET gebruiken met andere .NET‑frameworks?**  
A: Ja, Aspose.GIS werkt met .NET Framework, .NET Core en .NET Standard‑projecten.

**Q: Is er een gratis proefversie beschikbaar?**  
A: Absoluut. Download een proefversie vanaf de [Aspose.GIS releases‑pagina](https://releases.aspose.com/).

**Q: Waar kan ik de volledige API‑documentatie vinden?**  
A: Gedetailleerde documentatie staat op de [Aspose.GIS documentatiepagina](https://reference.aspose.com/gis/net/).

**Q: Hoe krijg ik hulp als ik een probleem tegenkom?**  
A: Plaats je vraag op het Aspose.GIS community‑forum [hier](https://forum.aspose.com/c/gis/33).

**Q: Kan ik een tijdelijke licentie aanschaffen voor evaluatie?**  
A: Ja, tijdelijke licenties zijn beschikbaar op de [aankoop‑pagina](https://purchase.aspose.com/temporary-license/).

## Conclusie
Je weet nu **hoe je geometrieën kunt vergelijken** met Aspose.GIS for .NET, van het maken van de objecten tot het controleren van ruimtelijke gelijkheid en het afhandelen van wijzigingen. Deze mogelijkheid is een bouwsteen voor meer geavanceerde ruimtelijke analyses zoals topologie‑validatie, detectie van duplicaten en geometrie‑gebaseerde filtering.

---

**Laatst bijgewerkt:** 2026-06-05  
**Getest met:** Aspose.GIS for .NET 24.11  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Polygon-geometrie maken in C# en intersectie controleren met Aspose.GIS for .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Hoe ruimtelijke overlap‑analyse van geometrieën uit te voeren met Aspose.GIS for .NET](/gis/net/geometry-analysis/check-geometries-overlap/)
- [Netwerk‑routering controle: aangrenzende geometrieën met Aspose.GIS](/gis/net/geometry-analysis/check-geometries-touching/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
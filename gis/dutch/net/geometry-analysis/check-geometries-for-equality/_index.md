---
date: 2026-02-05
description: Leer hoe u geometrieën in .NET kunt vergelijken met Aspose.GIS en de
  gelijkheid van geometrieën in uw toepassingen kunt controleren.
linktitle: How to Compare Geometries for Equality
second_title: Aspose.GIS .NET API
title: Hoe geometrieën vergelijken op gelijkheid met Aspose.GIS voor .NET
url: /nl/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe geometrieën op gelijkheid te vergelijken met Aspose.GIS voor .NET

## Inleiding
In deze tutorial ontdek je **hoe je geometrieën kunt vergelijken** met Aspose.GIS voor .NET. Of je nu een mappingservice bouwt, ruimtelijke analyse uitvoert, of simpelweg moet verifiëren dat twee vormen dezelfde locatie vertegenwoordigen, weten hoe je geometrieën kunt vergelijken is essentieel. We lopen een volledig, end‑to‑end voorbeeld door dat laat zien hoe je geometrieën maakt, wijzigt en test op gelijkheid in slechts een paar regels C# code.

## Snelle antwoorden
- **Wat betekent “compare geometries”?** Het controleert of twee geometrische objecten dezelfde ruimte innemen, ongeacht hoe ze zijn geconstrueerd.  
- **Welke methode wordt gebruikt?** `SpatiallyEquals` van de Aspose.GIS API.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Ondersteunde .NET‑versies?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Typische implementatietijd?** Ongeveer 5‑10 minuten voor een basisgelijkheidscontrole.

## Wat is geometrie‑gelijkheid?
Geometrie‑gelijkheid (vaak spatial equality genoemd) betekent dat twee geometrieën exact dezelfde verzameling punten op het aardoppervlak vertegenwoordigen. Twee vormen kunnen verschillend worden opgebouwd — een MultiLineString versus een enkele LineString — maar toch spatially equal zijn.

## Waarom Aspose.GIS gebruiken om geometrieën te vergelijken?
Aspose.GIS biedt een robuuste, high‑performance geometrie‑engine die:
- Een breed scala aan vectorformaten ondersteunt (WKT, GeoJSON, Shapefile, enz.).
- Precisie‑bewuste vergelijkingsmethoden biedt zoals `SpatiallyEquals`.
- Offline werkt, zonder externe services, waardoor het ideaal is voor veilige of geïsoleerde omgevingen.

### Waarom dit belangrijk is voor ontwikkelaars
Wanneer je **hoe je geometrieën kunt vergelijken** nodig hebt in batchprocessen, duplicate‑detectieroutines of realtime‑validatie, verwijdert een betrouwbare bibliotheek het giswerk en garandeert consistente resultaten over verschillende gegevensbronnen heen.

## Voorvereisten
Voordat je begint, zorg dat je het volgende hebt:

- **.NET Framework of .NET Core geïnstalleerd** – elke versie ondersteund door Aspose.GIS.  
- **Aspose.GIS for .NET bibliotheek** – download van de [Aspose.GIS downloadpagina](https://releases.aspose.com/gis/net/).  
- **Een ontwikkel‑IDE** – Visual Studio, Rider, of VS Code met C#‑extensies.

## Namespaces importeren
Voeg in je .NET‑project de benodigde `using`‑statements toe zodat de compiler weet waar de GIS‑klassen te vinden zijn:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Stap 1: Definieer de geometrieën
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
Nu gebruiken we de `SpatiallyEquals`‑methode om te zien of de twee vormen door de GIS‑engine als gelijk worden beschouwd.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

De console print `True` omdat, ondanks de verschillende constructie, beide geometrieën dezelfde lijn van (0,0) tot (2,2) bestrijken.

## Stap 3: Wijzig één geometrie
Om te illustreren hoe een wijziging de gelijkheid beïnvloedt, voegen we een extra punt toe aan `geometry2`.

```csharp
geometry2.AddPoint(3, 3);
```

## Stap 4: Controleer gelijkheid opnieuw na wijziging
Na de wijziging zijn de geometrieën niet langer gelijk, dus `SpatiallyEquals` retourneert `False`.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

De uitvoer `False` bevestigt dat het extra punt de spatial equality heeft verbroken.

## Veelvoorkomende problemen & tips
- **Precisieproblemen** – Als je werkt met zeer hoge precisie coördinaten, overweeg afronding of het gebruik van een tolerantietoevoeging van `SpatiallyEquals`.  
- **Verschillende SRID's** – Zorg ervoor dat beide geometrieën dezelfde Spatial Reference System Identifier (SRID) hebben vóór het vergelijken.  
- **Prestaties** – Voor grote collecties kunnen batch‑vergelijkingen met LINQ de overhead verminderen.

## Veelgestelde vragen
**V: Kan ik Aspose.GIS voor .NET gebruiken met andere .NET‑frameworks?**  
A: Ja, Aspose.GIS werkt met .NET Framework, .NET Core en .NET Standard‑projecten.

**V: Is er een gratis proefversie beschikbaar?**  
A: Zeker. Download een proefversie van de [Aspose.GIS releases‑pagina](https://releases.aspose.com/).

**V: Waar kan ik de volledige API‑documentatie vinden?**  
A: Gedetailleerde documentatie staat op de [Aspose.GIS documentatiepagina](https://reference.aspose.com/gis/net/).

**V: Hoe krijg ik hulp als ik een probleem tegenkom?**  
A: Plaats je vraag op het Aspose.GIS community‑forum [hier](https://forum.aspose.com/c/gis/33).

**V: Kan ik een tijdelijke licentie kopen voor evaluatie?**  
A: Ja, tijdelijke licenties zijn beschikbaar op de [aankooppagina](https://purchase.aspose.com/temporary-license/).

## Conclusie
Je weet nu **hoe je geometrieën kunt vergelijken** met Aspose.GIS voor .NET, van het maken van de objecten tot het controleren van spatial equality en het verwerken van wijzigingen. Deze mogelijkheid is een bouwsteen voor meer geavanceerde ruimtelijke analyses zoals topologie‑validatie, duplicaatdetectie en geometrie‑gebaseerde filtering.

---

**Laatst bijgewerkt:** 2026-02-05  
**Getest met:** Aspose.GIS for .NET 24.11  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
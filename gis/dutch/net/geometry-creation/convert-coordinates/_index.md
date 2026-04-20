---
date: 2026-02-13
description: Leer hoe u coördinaten naar DMS kunt converteren met Aspose.GIS voor
  .NET. Deze stap‑voor‑stap C#‑gids laat zien hoe u latitude en longitude, decimale
  graden naar DMS kunt omzetten en meer.
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: Hoe coördinaten omzetten naar DMS met Aspose.GIS voor .NET
url: /nl/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe coördinaten om te zetten naar DMS met Aspose.GIS

## Inleiding
In deze tutorial leer je **hoe je coördinaten** naar DMS (graden, minuten, seconden) te converteren met de krachtige Aspose.GIS bibliotheek voor .NET. Of je nu **c# lat long wilt converteren**, menselijk leesbare locatieteksten wilt genereren, of gewoon verschillende coördinatenformaten wilt verkennen, deze gids leidt je stap voor stap met duidelijke uitleg en kant‑klaar C#‑code.

## Snelle antwoorden
- **Wat betekent “convert coordinates to DMS”?** Het zet numerieke breedte‑/lengtegraadwaarden om naar de traditionele notatie graden‑minuten‑seconden.  
- **Welke bibliotheek verzorgt de conversie?** Aspose.GIS voor .NET levert de `GeoConvert`‑klasse met ingebouwde formatondersteuning.  
- **Heb ik een licentie nodig om het te proberen?** Er is een gratis proefversie beschikbaar; een commerciële licentie is vereist voor productiegebruik.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+ en .NET 5/6+.  
- **Kan ik dezelfde code gebruiken voor andere formaten?** Ja—verander simpelweg de `PointFormats`‑enumwaarde (bijv. `DecimalDegrees`, `GeoRef`).  

## Hoe coördinaten om te zetten naar DMS
Voordat we in de code duiken, laten we verduidelijken waarom DMS nog steeds waardevol is. Cartografen, piloten en veel GIS‑dataleveranciers vertrouwen op DMS omdat het mens‑vriendelijk is en aansluit bij traditionele kaarten. Aspose.GIS verwijdert de noodzaak voor handmatige berekeningen, zodat je je kunt concentreren op de logica van je applicatie.

## Wat is coördinatenconversie naar DMS?
Het omzetten van coördinaten naar DMS herschrijft decimale breedte‑ en lengtegraadwaarden naar een formaat zoals `25°30'00"N 45°30'00"E`. Deze weergave wordt veel gebruikt in cartografie, navigatie en GIS‑gegevensuitwisseling.

## Waarom Aspose.GIS gebruiken voor coördinatenconversie?
- **All‑in‑one API** – Geen externe bibliotheken of complexe wiskunde; Aspose.GIS verwerkt parsing en formattering intern.  
- **Hoge nauwkeurigheid** – Precieze afhandeling van randgevallen zoals negatieve waarden en hemisfeer‑aanduidingen.  
- **Cross‑platform** – Werkt hetzelfde op Windows, Linux en macOS .NET‑runtime.  
- **Uitbreidbaar** – Gemakkelijk schakelen tussen DMS, decimale graden, graad‑decimale‑minuten en GeoRef‑formaten.  

## Voorvereisten
Voordat je begint, zorg dat je het volgende hebt:

1. **Basiskennis van C#** – Vertrouwd met variabelen, methode‑aanroepen en console‑output.  
2. **Aspose.GIS geïnstalleerd** – Download het nieuwste pakket van de [Aspose.GIS website](https://releases.aspose.com/gis/net/).  

## Namespaces importeren
Importeer eerst de namespaces die nodig zijn voor GIS‑bewerkingen:

```csharp
using System;
using Aspose.Gis;
```

## Stapsgewijze handleiding

### Stap 1: Het conversieproces starten
We printen een vriendelijk bericht zodat je weet dat de demo is begonnen.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Stap 2: Omzetten naar decimale graden  
Hoewel het einddoel DMS is, beginnen we met het tonen van de oorspronkelijke decimale weergave. Dit demonstreert ook het **decimal degrees to dms**‑pad dat je later volgt.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Stap 3: Omzetten naar graad‑decimale‑minuten  
Dit formaat (`DD°MM.m'`) is een veelvoorkomende tussenstap wanneer je *convert lat long degree minutes* nodig hebt.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Stap 4: Omzetten naar graad‑minuten‑seconden (DMS)  
Hier is de kern van onze tutorial—**convert coordinates to DMS**.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### Stap 5: Omzetten naar GeoRef  
Voor de volledigheid laten we ook het `GeoRef`‑formaat zien, nuttig in remote‑sensing‑werkstromen.

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Veelvoorkomende problemen en oplossingen
- **Onjuiste hemisfeer‑letters** – Zorg ervoor dat je positieve waarden doorgeeft voor noord/oost en negatieve voor zuid/west; de API voegt automatisch het juiste achtervoegsel toe.  
- **Onverwachte lege uitvoer** – Controleer of de `Aspose.Gis`‑assembly correct is gerefereerd en of het project een ondersteunde .NET‑versie target.  
- **Licentie niet gevonden** – Plaats je licentiebestand in de applicatiewortel of stel het programmatisch in met `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.  

## Veelgestelde vragen

**Q: Is Aspose.GIS compatibel met andere programmeertalen?**  
A: Aspose.GIS richt zich voornamelijk op .NET‑ontwikkelaars, maar er is ook een Java‑versie beschikbaar.

**Q: Kan ik Aspose.GIS proberen voordat ik het koop?**  
A: Ja, je kunt een gratis proefversie van Aspose.GIS krijgen via de [website](https://releases.aspose.com/).

**Q: Hoe kan ik ondersteuning krijgen voor Aspose.GIS?**  
A: Je kunt hulp zoeken op het Aspose.GIS‑community‑forum [hier](https://forum.aspose.com/c/gis/33).

**Q: Zijn tijdelijke licenties beschikbaar voor Aspose.GIS?**  
A: Ja, tijdelijke licenties zijn verkrijgbaar via de [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Waar kan ik Aspose.GIS kopen?**  
A: Je kunt Aspose.GIS aanschaffen via de [purchase page](https://purchase.aspose.com/buy).

## Conclusie
Door deze stappen te volgen, weet je nu hoe je **coördinaten kunt omzetten naar DMS** en andere gangbare GIS‑formaten met Aspose.GIS voor .NET. Deze mogelijkheid stelt je in staat om menselijk leesbare locatieteksten naadloos te integreren in kaart‑applicaties, rapporten of elke workflow met ruimtelijke gegevens. Voel je vrij om te experimenteren met verschillende breedte‑/lengtegraadwaarden en de andere formaten te verkennen die de `GeoConvert`‑klasse biedt.

---

**Laatst bijgewerkt:** 2026-02-13  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
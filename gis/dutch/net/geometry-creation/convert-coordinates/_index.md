---
date: 2025-12-11
description: Leer hoe u coördinaten naar DMS kunt converteren met Aspose.GIS voor
  .NET. Inclusief C#‑voorbeelden, c# converteer breedte‑ en lengtegraad, en een stapsgewijze
  handleiding.
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: Coördinaten converteren naar DMS met Aspose.GIS voor .NET
url: /nl/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Coördinaten converteren naar DMS met Aspose.GIS

## Introduction
In deze tutorial ontdek je hoe je **coördinaten kunt converteren naar DMS** (degrees, minutes, seconds) met de krachtige Aspose.GIS‑bibliotheek voor .NET. Of je nu latitude longitude moet c# converteren voor kaarttoepassingen, mens‑leesbare locatieteksten wilt genereren, of simpelweg verschillende coördinatenformaten wilt verkennen, deze gids leidt je stap voor stap met duidelijke uitleg en kant‑klaar C#‑code.

## Quick Answers
- **Wat betekent “coördinaten converteren naar DMS”?** Het zet numerieke latitude/longitude‑waarden om naar de traditionele notatie graden‑minuten‑seconden.  
- **Welke bibliotheek voert de conversie uit?** Aspose.GIS voor .NET biedt de `GeoConvert`‑klasse met ingebouwde formatondersteuning.  
- **Heb ik een licentie nodig om het uit te proberen?** Er is een gratis proefversie beschikbaar; een commerciële licentie is vereist voor productiegebruik.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+ en .NET 5/6+.  
- **Kan ik dezelfde code voor andere formaten gebruiken?** Ja – wijzig eenvoudig de `PointFormats`‑enumwaarde (bijv. `DecimalDegrees`, `GeoRef`).  

## What is coordinate conversion to DMS?
Het converteren van coördinaten naar DMS herschrijft decimale latitude‑ en longitude‑waarden naar een formaat zoals `25°30'00"N 45°30'00"E`. Deze weergave wordt veel gebruikt in cartografie, navigatie en GIS‑gegevensuitwisseling.

## Why use Aspose.GIS for coordinate conversion?
- **All‑in‑one API** – Geen externe bibliotheken of complexe wiskunde; Aspose.GIS verwerkt parsing en formattering intern.  
- **Hoge nauwkeurigheid** – Precieze afhandeling van randgevallen zoals negatieve waarden en hemisfeer‑aanduidingen.  
- **Cross‑platform** – Werkt hetzelfde op Windows, Linux en macOS .NET‑runtime.  
- **Uitbreidbaar** – Gemakkelijk schakelen tussen DMS, decimal degrees, degree‑decimal‑minutes en GeoRef‑formaten.

## Prerequisites
Zorg ervoor dat je het volgende hebt voordat je begint:

1. **Basiskennis van C#** – Vertrouwd met variabelen, methode‑aanroepen en console‑output.  
2. **Aspose.GIS geïnstalleerd** – Download het nieuwste pakket van de [Aspose.GIS‑website](https://releases.aspose.com/gis/net/).

## Import Namespaces
First, import the namespaces required for GIS operations:

```csharp
using System;
using Aspose.Gis;
```

## Step‑by‑step guide

### Step 1: Start the conversion process
We print a friendly message so you know the demo has begun.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Step 2: Convert to Decimal Degrees  
Even though the final goal is DMS, we start by showing the original decimal representation.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Step 3: Convert to Degree Decimal Minutes  
This format (`DD°MM.m'`) is a common intermediate step when you need *convert lat long degree minutes*.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Step 4: Convert to Degree Minutes Seconds (DMS)  
Here’s the core of our tutorial—**convert coordinates to DMS**.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### Step 5: Convert to GeoRef  
For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing workflows.

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Common Issues and Solutions
- **Onjuiste hemisfeer‑letters** – Zorg ervoor dat je positieve waarden doorgeeft voor noord/oost en negatieve voor zuid/west; de API voegt automatisch het juiste achtervoegsel toe.  
- **Onverwachte lege output** – Controleer of de `Aspose.Gis`‑assembly correct is gerefereerd en of het project een ondersteunde .NET‑versie target.  
- **Licentie niet gevonden** – Plaats je licentiebestand in de applicatiemap of stel het programmatically in met `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.

## Frequently Asked Questions

**Q: Is Aspose.GIS compatible with other programming languages?**  
A: Aspose.GIS richt zich voornamelijk op .NET‑ontwikkelaars, maar er is ook een Java‑versie beschikbaar.

**Q: Kan ik Aspose.GIS uitproberen voordat ik het koop?**  
A: Ja, je kunt een gratis proefversie van Aspose.GIS verkrijgen via de [website](https://releases.aspose.com/).

**Q: Hoe kan ik ondersteuning krijgen voor Aspose.GIS?**  
A: Je kunt hulp zoeken op het Aspose.GIS‑communityforum [hier](https://forum.aspose.com/c/gis/33).

**Q: Zijn tijdelijke licenties beschikbaar voor Aspose.GIS?**  
A: Ja, tijdelijke licenties zijn verkrijgbaar via de [tijdelijke licentiepagina](https://purchase.aspose.com/temporary-license/).

**Q: Waar kan ik Aspose.GIS kopen?**  
A: Je kunt Aspose.GIS aanschaffen via de [aankooppagina](https://purchase.aspose.com/buy).

## Conclusion
Door deze stappen te volgen, weet je nu hoe je **coördinaten kunt converteren naar DMS** en andere gangbare GIS‑formaten kunt gebruiken met Aspose.GIS voor .NET. Deze mogelijkheid stelt je in staat om mens‑leesbare locatieteksten naadloos te integreren in kaarttoepassingen, rapporten of elke workflow met ruimtelijke gegevens. Voel je vrij om te experimenteren met verschillende latitude/longitude‑waarden en de andere formaten te verkennen die de `GeoConvert`‑klasse biedt.

---

**Laatst bijgewerkt:** 2025-12-11  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-08-18
description: Decimal degrees omzetten naar dms met Aspose.GIS for .NET. Deze stapsgewijze
  C#-gids laat zien hoe latitude/longitude, decimal degrees naar dms en meer te converteren.
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: Coördinaten converteren
og_description: decimal degrees naar dms conversie eenvoudig gemaakt met Aspose.GIS
  for .NET. Leer latitude‑longitude waarden omzetten naar DMS-formaat in minutes.
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: Hoe decimal degrees naar dms converteren met Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  headline: How to convert decimal degrees to dms with Aspose.GIS for .NET
  type: TechArticle
- description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  name: How to convert decimal degrees to dms with Aspose.GIS for .NET
  steps:
  - name: start the conversion process
    text: We print a friendly message so you know the demo has begun.
  - name: convert to decimal degrees
    text: Even though the final goal is DMS, we start by showing the original decimal
      representation. This also demonstrates the **decimal degrees to dms** path you’ll
      later follow.
  - name: convert to degree decimal minutes
    text: This format (`DD°MM.m'`) is a common intermediate step when you need to
      **convert lat long degree minutes**.
  - name: convert to degree minutes seconds (dms)
    text: Here’s the core of our tutorial—**convert coordinates to dms**.
  - name: convert to GeoRef
    text: For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing
      workflows.
  type: HowTo
- questions:
  - answer: Aspose.GIS primarily targets .NET developers, but a Java version is also
      available.
    question: Is Aspose.GIS compatible with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.GIS before purchasing?
  - answer: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  - answer: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert coordinates
- Aspose.GIS
- .NET GIS processing
title: Hoe decimal degrees naar dms converteren met Aspose.GIS for .NET
url: /nl/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe decimale graden om te zetten naar dms met Aspose.GIS

## Introductie
In deze tutorial leer je **hoe je decimale graden naar dms kunt omzetten** met behulp van de krachtige Aspose.GIS bibliotheek voor .NET. Of je nu **c# convert lat long** moet uitvoeren, menselijk leesbare locatieteksten voor rapporten wilt genereren, of gewoon verschillende coördinaatformaten wilt verkennen, deze gids leidt je door elke stap met duidelijke uitleg en kant‑klaar C#‑fragmenten.

## Snelle antwoorden
- **Wat betekent “convert coordinates to dms”?** Het transformeert numerieke breedte‑/lengtegraadwaarden naar de traditionele graden‑minuten‑seconden notatie.  
- **Welke bibliotheek verwerkt de conversie?** Aspose.GIS voor .NET biedt de `GeoConvert`‑klasse met ingebouwde formatondersteuning.  
- **Heb ik een licentie nodig om het te proberen?** Een gratis proefversie is beschikbaar; een commerciële licentie is vereist voor productiegebruik.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+ en .NET 5/6+.  
- **Kan ik dezelfde code voor andere formaten gebruiken?** Ja—verander eenvoudig de `PointFormats`‑enumwaarde (bijv. `DecimalDegrees`, `GeoRef`).  

## Wat is coördinaatconversie naar dms?
Het omzetten van coördinaten naar DMS herschrijft decimale breedte‑ en lengtegraadwaarden naar een formaat zoals `25°30'00"N 45°30'00"E`. Het proces splitst elke decimale graad in hele graden, minuten (een zestigste van een graad) en seconden (een zestigste van een minuut), en voegt vervolgens de juiste hemisfeer‑indicator toe (N, S, E, W). Deze menselijk leesbare vorm is essentieel voor veel legacy‑datasets en voor het communiceren van precieze locaties zonder gebruik te maken van decimale notatie.

## Waarom Aspose.GIS gebruiken voor coördinaatconversie?
Aspose.GIS ondersteunt **meer dan 50 invoer‑ en uitvoerformaten** en kan multi‑honderd‑pagina GIS‑bestanden verwerken zonder de volledige dataset in het geheugen te laden. De API levert sub‑millimeter nauwkeurigheid voor randgevallen zoals negatieve waarden en hemisfeer‑aanduidingen, en draait consistent op Windows, Linux en macOS .NET‑runtime.

## Vereisten
Voordat je begint, zorg ervoor dat je het volgende hebt:

1. **Basiskennis van C#** – vertrouwd met variabelen, methode‑aanroepen en console‑output.  
2. **Aspose.GIS geïnstalleerd** – download het nieuwste pakket van de [Aspose.GIS website](https://releases.aspose.com/gis/net/). Je kunt ook de hoofd‑Aspose‑releasesite verkennen op de [Aspose releases website](https://releases.aspose.com/).  

## Namespaces importeren
Importeer eerst de namespaces die nodig zijn voor GIS‑operaties:

Import Namespaces placeholder blijft ongewijzigd.

## Stapsgewijze handleiding

### Wat is de GeoConvert-klasse?
De `GeoConvert`‑klasse biedt statische methoden voor het converteren tussen coördinaatformaten zoals decimale graden, DMS en GeoRef. Het bevat overloads die ruwe numerieke waarden of `Point`‑objecten accepteren en retourneert geformatteerde strings of nieuwe `Point`‑instanties. Door randgevallen zoals negatieve coördinaten en afronding af te handelen, garandeert de klasse dat de output voldoet aan de standaard GIS‑specificaties, waardoor integratie in elke .NET‑mappingtoepassing wordt vereenvoudigd.

### Stap 1: start het conversieproces
We printen een vriendelijke boodschap zodat je weet dat de demo is gestart.

```csharp
using System;
using Aspose.Gis;
```

### Stap 2: omzetten naar decimale graden
Hoewel het uiteindelijke doel DMS is, beginnen we met het tonen van de oorspronkelijke decimale weergave. Dit demonstreert ook het **decimal degrees to dms** pad dat je later zult volgen.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Stap 3: omzetten naar graad decimale minuten
Dit formaat (`DD°MM.m'`) is een veelvoorkomende tussenstap wanneer je **convert lat long degree minutes** moet uitvoeren.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Stap 4: omzetten naar graad minuten seconden (dms)
Hier is de kern van onze tutorial—**convert coordinates to dms**.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Stap 5: omzetten naar GeoRef
Voor de volledigheid demonstreren we ook het `GeoRef`‑formaat, nuttig in remote‑sensing‑werkstromen.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## Veelvoorkomende problemen en oplossingen
- **Onjuiste hemisfeer‑letters** – Zorg ervoor dat je positieve waarden doorgeeft voor noord/oost en negatieve voor zuid/west; de API voegt automatisch het juiste achtervoegsel toe.  
- **Onverwachte lege output** – Controleer of de `Aspose.Gis`‑assembly correct is gerefereerd en dat het project een ondersteunde .NET‑versie target.  
- **Licentie niet gevonden** – Plaats je licentiebestand in de toepassings‑root of stel het programmatically in met `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.

## Veelgestelde vragen

**Q: Is Aspose.GIS compatibel met andere programmeertalen?**  
A: Aspose.GIS richt zich voornamelijk op .NET‑ontwikkelaars, maar er is ook een Java‑versie beschikbaar.

**Q: Kan ik Aspose.GIS uitproberen voordat ik het koop?**  
A: Ja, je kunt een gratis proefversie van Aspose.GIS krijgen via de [website](https://releases.aspose.com/).

**Q: Hoe kan ik ondersteuning krijgen voor Aspose.GIS?**  
A: Je kunt hulp zoeken op het Aspose.GIS community‑forum [hier](https://forum.aspose.com/c/gis/33).

**Q: Zijn tijdelijke licenties beschikbaar voor Aspose.GIS?**  
A: Ja, tijdelijke licenties kunnen verkregen worden via de [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Waar kan ik Aspose.GIS kopen?**  
A: Je kunt Aspose.GIS aanschaffen via de [purchase page](https://purchase.aspose.com/buy).

## Conclusie
Door deze stappen te volgen, weet je nu hoe je **convert decimal degrees to dms** en andere veelvoorkomende GIS‑formaten kunt gebruiken met Aspose.GIS voor .NET. Deze mogelijkheid stelt je in staat om menselijk leesbare locatieteksten naadloos te integreren in mapping‑applicaties, rapporten of elke workflow voor ruimtelijke data. Voel je vrij om te experimenteren met verschillende breedte‑/lengtegraadwaarden en de andere formaten te verkennen die de `GeoConvert`‑klasse biedt.

---

**Last Updated:** 2026-08-18  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Gerelateerde tutorials

- [Hoe puntgeometrie te maken en geometrie‑type op te halen met Aspose.GIS voor .NET](/gis/net/geometry-analysis/get-geometry-type/)
- [Hoe GeoJSON te converteren – Aspose.GIS voor .NET](/gis/net/geo-data-conversion/)
- [MultiPoint‑geometrie maken .NET met Aspose.GIS](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
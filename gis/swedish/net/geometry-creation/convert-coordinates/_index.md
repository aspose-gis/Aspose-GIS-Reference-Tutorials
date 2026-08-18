---
date: 2026-08-18
description: Konvertera decimal degrees till dms med Aspose.GIS for .NET. Denna steg‑för‑steg
  C#‑guide visar hur man konverterar latitude/longitude, decimal degrees till dms
  och mer.
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: Konvertera koordinater
og_description: decimal degrees till dms konvertering gjort enkelt med Aspose.GIS
  for .NET. Lär dig att omvandla latitude‑longitude‑värden till DMS-format i minutes.
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: Konvertera decimal degrees till dms med Aspose.GIS for .NET
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
title: Hur man konverterar decimal degrees till dms med Aspose.GIS for .NET
url: /sv/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man konverterar decimalgrader till dms med Aspose.GIS

## Introduktion
I den här handledningen kommer du att lära dig **hur man konverterar decimalgrader till dms** med det kraftfulla Aspose.GIS‑biblioteket för .NET. Oavsett om du behöver **c# konvertera lat long**, generera människoläsbara positionssträngar för rapporter, eller helt enkelt utforska olika koordinatformat, så guidar den här guiden dig genom varje steg med tydliga förklaringar och färdiga C#‑kodsnuttar.

## Snabba svar
- **Vad betyder “convert coordinates to dms”?** Det omvandlar numeriska latitud-/longitudvärden till den traditionella grader‑minuter‑sekunder‑notationen.  
- **Vilket bibliotek hanterar konverteringen?** Aspose.GIS för .NET tillhandahåller `GeoConvert`‑klassen med inbyggt formatstöd.  
- **Behöver jag en licens för att prova det?** En gratis provversion finns tillgänglig; en kommersiell licens krävs för produktionsanvändning.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+ och .NET 5/6+.  
- **Kan jag använda samma kod för andra format?** Ja—byt helt enkelt `PointFormats`‑enum‑värdet (t.ex. `DecimalDegrees`, `GeoRef`).  

## Vad är koordinatkonvertering till dms?
Att konvertera koordinater till DMS omskriver decimal latitud- och longitudvärden till ett format som `25°30'00"N 45°30'00"E`. Processen delar varje decimalgrad i hela grader, minuter (en sextio del av en grad) och sekunder (en sextio del av en minut), och lägger sedan till rätt hemisfärsindikator (N, S, E, W). Denna människoläsbara form är viktig för många äldre dataset och för att kommunicera exakta platser utan att förlita sig på decimalnotation.

## Varför använda Aspose.GIS för koordinatkonvertering?
Aspose.GIS stödjer **50+ in‑ och utdataformat** och kan bearbeta GIS‑filer med hundratals sidor utan att ladda hela datasetet i minnet. API:t levererar sub‑millimeternoggrannhet för kantfall som negativa värden och hemisfärsdesignatorer, och det körs konsekvent på Windows, Linux och macOS .NET‑runtime‑miljöer.

## Förutsättningar
Innan du börjar, se till att du har:

1. **Grundläggande kunskap om C#** – bekantskap med variabler, metodanrop och konsolutskrift.  
2. **Aspose.GIS installerat** – ladda ner det senaste paketet från den [Aspose.GIS‑webbplatsen](https://releases.aspose.com/gis/net/). Du kan också utforska Asposes huvudsakliga releases‑sida på den [Aspose releases‑webbplatsen](https://releases.aspose.com/).  

## Importera namnrymder
First, import the namespaces required for GIS operations:

Import Namespaces‑platshållaren förblir oförändrad.

## Steg‑för‑steg‑guide

### Vad är GeoConvert‑klassen?
`GeoConvert`‑klassen tillhandahåller statiska metoder för att konvertera mellan koordinatformat såsom decimalgrader, DMS och GeoRef. Den inkluderar överlagringar som accepterar råa numeriska värden eller `Point`‑objekt och returnerar formaterade strängar eller nya `Point`‑instanser. Genom att hantera kantfall som negativa koordinater och avrundning garanterar klassen att utdata följer standard GIS‑specifikationer, vilket förenklar integration i vilken .NET‑kartapplikation som helst.

### Steg 1: starta konverteringsprocessen
Vi skriver ut ett vänligt meddelande så att du vet att demonstrationen har startat.

```csharp
using System;
using Aspose.Gis;
```

### Steg 2: konvertera till decimalgrader
Även om det slutgiltiga målet är DMS börjar vi med att visa den ursprungliga decimalrepresentationen. Detta demonstrerar också **decimal degrees to dms**‑vägen som du senare kommer att följa.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Steg 3: konvertera till grad decimal minuter
Detta format (`DD°MM.m'`) är ett vanligt mellansteg när du behöver **convert lat long degree minutes**.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Steg 4: konvertera till grader minuter sekunder (dms)
Här är kärnan i vår handledning—**convert coordinates to dms**.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Steg 5: konvertera till GeoRef
För fullständighetens skull demonstrerar vi också `GeoRef`‑formatet, som är användbart i fjärranalys‑arbetsflöden.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## Vanliga problem och lösningar
- **Felaktiga hemisfärsbokstäver** – Se till att skicka positiva värden för norr/öster och negativa för söder/väst; API:t lägger automatiskt till rätt suffix.  
- **Oväntad tom output** – Verifiera att `Aspose.Gis`‑assemblyn refereras korrekt och att projektet riktar sig mot en stödd .NET‑version.  
- **Licens ej hittad** – Placera din licensfil i applikationens rot eller ställ in den programatiskt med `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.

## Vanliga frågor

**Q: Är Aspose.GIS kompatibel med andra programmeringsspråk?**  
A: Aspose.GIS riktar sig främst till .NET‑utvecklare, men en Java‑version finns också tillgänglig.

**Q: Kan jag prova Aspose.GIS innan jag köper?**  
A: Ja, du kan få åtkomst till en gratis provversion av Aspose.GIS från [webbplatsen](https://releases.aspose.com/).

**Q: Hur kan jag få support för Aspose.GIS?**  
A: Du kan söka hjälp i Aspose.GIS‑community‑forumet [här](https://forum.aspose.com/c/gis/33).

**Q: Finns tillfälliga licenser tillgängliga för Aspose.GIS?**  
A: Ja, tillfälliga licenser kan erhållas från [sidan för tillfälliga licenser](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag köpa Aspose.GIS?**  
A: Du kan köpa Aspose.GIS från [köpsidan](https://purchase.aspose.com/buy).

## Slutsats
Genom att följa dessa steg vet du nu hur du **convert decimal degrees to dms** och andra vanliga GIS‑format med Aspose.GIS för .NET. Denna funktion låter dig sömlöst integrera människoläsbara positionssträngar i kartapplikationer, rapporter eller något spatialt dataflöde. Känn dig fri att experimentera med olika latitud‑/longitudvärden och utforska de andra format som `GeoConvert`‑klassen erbjuder.

---

**Last Updated:** 2026-08-18  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Relaterade handledningar

- [Hur man skapar punktgeometri och får geometri‑typ med Aspose.GIS för .NET](/gis/net/geometry-analysis/get-geometry-type/)
- [Hur man konverterar GeoJSON – Aspose.GIS för .NET](/gis/net/geo-data-conversion/)
- [Skapa MultiPoint‑geometri .NET med Aspose.GIS](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2025-12-23
description: Lär dig hur du konverterar geometri till WKT med olika alternativ, ställer
  in numeriskt format och justerar decimalprecision med Aspose.GIS för .NET.
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: Konvertera geometri till WKT-variantalternativ med Aspose.GIS
url: /sv/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konvertera geometri till WKT-variantalternativ med Aspose.GIS

## Introduktion
I moderna .NET‑applikationer är **konvertering av geometri till WKT** ett vanligt steg när du behöver utbyta rumsliga data med andra system eller lagra dem i ett textbaserat format. Aspose.GIS för .NET gör denna konvertering enkel samtidigt som du får full kontroll över WKT‑varianten, numeriskt format och decimalprecision. I den här handledningen kommer du att lära dig hur du konverterar geometri till WKT, väljer rätt variant och finjusterar resultatet för att möta ditt projekts exakta krav.

## Snabba svar
- **Vad betyder “convert geometry to WKT”?** Det omvandlar geometriska objekt (punkter, linjer, polygoner) till Well‑Known Text‑representationen.  
- **Vilka WKT‑varianter stöds?** `Iso`, `SimpleFeatureAccessOutdated` och `ExtendedPostGis`.  
- **Hur kan jag kontrollera decimalprecision?** Använd `NumericFormat`‑alternativen såsom `General`, `RoundTrip` eller `Flat`.  
- **Behöver jag en licens för produktion?** Ja, en kommersiell licens krävs för icke‑testanvändning.  
- **Vilka .NET‑versioner är kompatibla?** .NET Framework 4.0+ och .NET 5/6/7.

## Vad är “convert geometry to WKT”?
Att konvertera geometri till WKT genererar en mänskligt läsbar sträng som beskriver rumsliga objekt. Detta format accepteras brett av GIS‑verktyg, databaser och webbtjänster, vilket gör det idealiskt för datautbyte.

## Varför använda Aspose.GIS för denna konvertering?
- **Precisionkontroll** – Välj hur många decimaler som skrivs ut.  
- **Variantflexibilitet** – Matcha exakt WKT‑dialekt som ditt efterföljande system kräver.  
- **Inga externa beroenden** – Ren .NET‑bibliotek, inga inhemska binärer.

## Förutsättningar
1. **Aspose.GIS för .NET** – Ladda ner och installera det från [nedladdningssidan](https://releases.aspose.com/gis/net/).  
2. **Utvecklingsmiljö** – Vilken som helst nyare version av Visual Studio eller VS Code med .NET SDK.  
3. **Grundläggande C#‑kunskaper** – Bekantskap med klasser, objekt och .NET‑ramverket.

## Importera namnrymder
Först, importera de nödvändiga namnrymderna:

```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```

## Steg 1: Skapa ett Point‑objekt
Skapa ett `Point` som du senare **konverterar geometri till WKT**. Punkten innehåller latitud, longitud och ett valfritt mått (M)-värde:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Steg 2: Ange Spatialt referenssystem (SRS)
Tilldela ett spatialt referenssystem så att WKT‑utdata vet vilket koordinatsystem som ska refereras. Här använder vi det vanliga WGS84‑systemet:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Steg 3: Specificera WKT‑variant
Välj rätt WKT‑variant när du **konverterar geometri till WKT**. Varje variant formaterar utdata något annorlunda:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Steg 4: Kontrollera numeriskt format (Ställ in numeriskt format & justera decimalprecision)
Finjustera den numeriska representationen av koordinater. Klassen `NumericFormat` låter dig **ställa in numeriskt format** och **justera decimalprecision** efter dina behov:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## Vanliga problem & tips
- **Saknad M‑värde** – Om du inte behöver ett mått, utelämna `M`‑egenskapen; ISO‑varianten kommer att ta bort den automatiskt.  
- **Oväntad precision** – Dubbelkolla att du använder rätt `NumericFormat`; `General` bevarar full dubbelprecision, medan `Flat` avrundar till det angivna antalet decimaler.  
- **SRID visas inte** – Endast `ExtendedPostGis`‑varianten prefixar utdata med `SRID=`. Välj denna variant när ditt målsystem förväntar sig ett SRID.

## Slutsats
Genom att följa dessa steg vet du nu hur du **konverterar geometri till WKT**, väljer rätt variant och exakt kontrollerar den numeriska utdata. Detta ger dig flexibiliteten att integrera Aspose.GIS med vilket GIS‑arbetsflöde, databas eller webbtjänst som helst som konsumerar WKT.

## Vanliga frågor
### Är Aspose.GIS kompatibel med alla versioner av .NET?
Ja, Aspose.GIS stödjer .NET Framework 4.0 och högre.  

### Kan jag använda Aspose.GIS för kommersiella projekt?
Ja, Aspose.GIS kan användas både för personliga och kommersiella projekt.  

### Ger Aspose.GIS stöd för andra rumsliga dataformat?
Ja, Aspose.GIS stödjer ett brett spektrum av rumsliga dataformat, inklusive ESRI Shapefile, GeoJSON och KML.  

### Finns det en gratis provversion av Aspose.GIS?
Ja, du kan ladda ner en gratis provversion av Aspose.GIS från [här](https://releases.aspose.com/).  

### Var kan jag få hjälp eller support för Aspose.GIS?
Du kan posta dina frågor eller söka hjälp från Aspose.GIS‑gemenskapen på [forumet](https://forum.aspose.com/c/gis/33).

## Vanligt förekommande frågor
**Q: Hur exporterar jag en Geometry‑samling till en enda WKT‑sträng?**  
A: Iterera över varje geometri i samlingen och konkatenera deras `AsText`‑resultat, eventuellt separerade med kommatecken eller radbrytningar.

**Q: Kan jag ändra SRID utan att ändra koordinaterna?**  
A: Ja, sätt `SpatialReferenceSystem`‑egenskapen till önskat SRID; koordinatvärdena förblir oförändrade.

**Q: Vad händer om jag använder en ej stödd WKT‑variant?**  
A: Aspose.GIS kastar ett `ArgumentException`. Validera alltid varianten mot `WktVariant`‑enum‑värden.

---

**Senast uppdaterad:** 2025-12-23  
**Testad med:** Aspose.GIS 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
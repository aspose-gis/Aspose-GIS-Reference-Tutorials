---
description: Lär dig hur du använder dynamisk typkonvertering med Aspose.GIS för .NET
  för att hämta attributvärden från en shapefil. Inkluderar exempel på explicit typkonvertering.
linktitle: Get Feature Attribute Value using Dynamic Type Casting
second_title: Aspose.GIS .NET API
title: Hämta funktionsattributvärde med dynamisk typkonvertering
url: /sv/net/layer-interaction-and-data-access/get-feature-attribute-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hämta funktionsattributvärde med dynamisk typkonvertering

## Introduktion
Välkommen till världen av Aspose.GIS för .NET, ett kraftfullt bibliotek som ger .NET‑utvecklare möjlighet att sömlöst arbeta med geografiska informationssystem (GIS)‑data. I den här handledningen kommer du att upptäcka hur **dynamic type casting** förenklar processen att hämta funktionsattributvärden från en shapefile, samtidigt som vi även går igenom den klassiska **explicit type casting**‑metoden. Oavsett om du läser en shapefile‑.NET‑applikation eller behöver **fetch attribute values** för analys, kommer dessa tekniker att göra din kod renare och mer flexibel.

## Snabba svar
- **What is dynamic type casting?** Ett sätt vid körning att hämta attributvärden utan att specificera måltypen i förväg.  
- **Why use Aspose.GIS?** Det erbjuder ett enhetligt API för att läsa shapefile‑.NET‑data och stödjer båda konverteringsmetoderna.  
- **Do I need a license?** En gratis provversion finns; en kommersiell licens krävs för produktion.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 och senare.  
- **Can I fetch attribute values from large files?** Ja—iterera över funktioner effektivt som visas i exemplen.

## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:
- Grundläggande förståelse för .NET‑utveckling.  
- Visual Studio installerat på din maskin.  
- Aspose.GIS för .NET‑biblioteket, som du kan ladda ner från [download link](https://releases.aspose.com/gis/net/).  
- Bekantskap med GIS‑koncept och terminologi.

## Importera namnrymder
För att kickstarta ditt projekt, se till att du importerar de nödvändiga namnrymderna. Detta steg är avgörande för att få åtkomst till funktionaliteten som tillhandahålls av Aspose.GIS för .NET. Inkludera följande namnrymder i din kod:
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Hur man använder dynamisk typkonvertering för att hämta attributvärden
Nedan följer en steg‑för‑steg‑guide som visar hur du sätter upp projektet, öppnar en shapefile och hämtar attributvärden med både **explicit type casting** och **dynamic type casting**.

### Steg 1: Skapa ditt projekt
Skapa ett nytt .NET‑projekt i Visual Studio och referera Aspose.GIS‑biblioteket.

### Steg 2: Definiera din dokumentkatalog
Ange sökvägen till din dokumentkatalog. Här ligger din shapefile (`InputShapeFile.shp`).
```csharp
string dataDir = "Your Document Directory";
```

### Steg 3: Öppna vektorlager
Öppna vektorlageret med Aspose.GIS. Se till att ange drivrutinen, i detta fall Shapefile‑drivrutinen.
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the vector layer goes here
}
```

### Steg 4: Hämta funktionsattributvärden
Nu loopar du igenom varje funktion i lagret och hämtar attributvärden. Aspose.GIS erbjuder olika sätt att **fetch attribute values**.

#### Fall 1: Explicit typkonvertering
```csharp
for (int i = 0; i < layer.Count; i++)
{
    Feature feature = layer[i];
    Console.WriteLine("Entry {0} information\n ========================", i);
    string nameValue = feature.GetValue<string>("name"); // attribute name is case-sensitive
    int ageValue = feature.GetValue<int>("age");
    string dobValue = feature.GetValue<DateTime>("dob").ToString();
    Console.WriteLine("Attribute value for feature #{0} is: {1}, {2}", nameValue, ageValue, dobValue);
}
```

#### Fall 2: Dynamisk typkonvertering
```csharp
for (int i = 0; i < layer.Count; i++)
{
    Feature feature = layer[i];
    Console.WriteLine("Entry {0} information\n ========================", i);
    var objName = feature.GetValue("name"); // attribute name is case-sensitive
    var objAge = feature.GetValue("age");
    var objDob = feature.GetValue("dob");
    Console.WriteLine("Attribute object for feature #{0} is: {1}, {2}", objName, objAge, objDob);
}
```

> **Pro tip:** Använd dynamisk typkonvertering när du är osäker på den exakta datatypen för ett attribut eller när du vill skriva generisk kod som fungerar över flera shapefiles. Byt till explicit typkonvertering när du behöver typ‑säkerhet vid kompilering.

## Vanliga problem och lösningar
- **Attribute name mismatch:** GIS‑attributnamn är skiftlägeskänsliga. Dubbelkolla den exakta stavningen i shapefile‑schemat.  
- **Null values:** `GetValue` returnerar `null` för saknade attribut; hantera detta på ett smidigt sätt för att undvika `NullReferenceException`.  
- **Large datasets:** Iterera med `foreach` eller paginering för att minska minnesanvändning.

## Vanliga frågor

### Fråga: Är Aspose.GIS lämplig för både nybörjare och erfarna utvecklare?
**Svar:** Absolut! Aspose.GIS riktar sig till utvecklare på alla kunskapsnivåer och erbjuder ett intuitivt API för GIS‑datamanipulation.

### Fråga: Kan jag använda Aspose.GIS i mina kommersiella projekt?
**Svar:** Ja, Aspose.GIS är en kommersiell produkt. Du kan hitta licensinformation på [purchase page](https://purchase.aspose.com/buy).

### Fråga: Finns tillfälliga licenser för teständamål?
**Svar:** Ja, du kan erhålla en tillfällig licens för testning från [here](https://purchase.aspose.com/temporary-license/).

### Fråga: Var kan jag hitta community‑support för Aspose.GIS?
**Svar:** Gå med i diskussionen på [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) för att söka hjälp och knyta kontakt med andra användare.

### Fråga: Finns det en gratis provversion av Aspose.GIS?
**Svar:** Självklart! Du kan utforska funktionerna i Aspose.GIS genom att ladda ner den fria provversionen från [here](https://releases.aspose.com/).

### Fråga: Hur får jag shapefile‑attributvärden utan att känna till deras typer?
**Svar:** Använd den dynamiska typkonverteringsmetoden (`feature.GetValue("attributeName")`) som returnerar värdet som ett `object` som du kan kasta vid körning.

### Fråga: Kan jag läsa shapefile‑.NET‑data i en .NET Core‑applikation?
**Svar:** Ja, Aspose.GIS för .NET stödjer fullt ut .NET Core, .NET 5 och senare versioner.

## Slutsats
Grattis! Du har nu lärt dig hur du använder Aspose.GIS för .NET för att hämta funktionsattributvärden med både **explicit type casting** och **dynamic type casting**. Dessa tekniker ger dig möjlighet att **get shapefile attribute**‑data effektivt, oavsett om du bygger ett desktop‑GIS‑verktyg eller integrerar rumslig analys i en webbtjänst.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-05  
**Tested With:** Aspose.GIS för .NET (senaste)  
**Author:** Aspose
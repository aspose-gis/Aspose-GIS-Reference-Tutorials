---
date: 2025-12-06
description: Lär dig hur du konverterar GeoJSON till TopoJSON med gruppering, ställer
  in objektets namn‑attribut och grupperar GeoJSON‑funktioner med Aspose.GIS för .NET.
language: sv
linktitle: How to Convert GeoJSON to TopoJSON with Grouping using Aspose.GIS
second_title: Aspose.GIS .NET API
title: Hur man konverterar GeoJSON till TopoJSON med gruppering med Aspose.GIS
url: /net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man konverterar GeoJSON till TopoJSON med gruppering med Aspose.GIS

## Introduktion

I den här steg‑för‑steg‑handledningen kommer du att lära dig **hur man konverterar GeoJSON**‑filer till TopoJSON samtidigt som du grupperar funktioner baserat på ett valt attribut. Att använda Aspose.GIS .NET‑API gör konverteringen snabb, pålitlig och fullt kontrollerbar från din C#‑kod. Oavsett om du bygger en ASP.NET GeoJSON‑konverteringstjänst eller ett skrivbords‑GIS‑verktyg, visar den här guiden exakt vad du behöver göra.

## Snabba svar
- **Vilket bibliotek hanterar konverteringen?** Aspose.GIS for .NET  
- **Hur lång tid tar implementeringen?** Vanligtvis 5‑10 minuter för en grundläggande installation  
- **Behöver jag en licens för produktion?** Ja, en kommersiell licens krävs (gratis provversion finns tillgänglig)  
- **Kan jag gruppera funktioner efter vilket attribut som helst?** Ja – ange `ObjectNameAttribute` till det fält du vill gruppera efter  
- **Stöds .NET Core?** Absolut – API:et fungerar med .NET Core, .NET 5/6 och den klassiska .NET‑ramverket  

## Vad är GeoJSON och TopoJSON?

GeoJSON är ett allmänt använt JSON‑format för att koda geografiska funktioner såsom punkter, linjer och polygoner. TopoJSON utökar GeoJSON genom att lagra topologi (delade linjesegment) vilket minskar filstorleken och förbättrar renderingsprestanda för komplexa kartor. Att konvertera mellan dem är ett vanligt steg när du behöver kompakt kartdata för webbvisualiseringar.

## Varför gruppera GeoJSON‑funktioner?

Gruppering (`group geojson features`) låter dig organisera relaterade geometrier under ett enda namngivet objekt i den resulterande TopoJSON. Detta är särskilt användbart när:

- Du vill skapa separata lager för olika administrativa regioner.  
- Ditt front‑end‑kartbibliotek förväntar sig namngivna objekt för styling eller interaktion.  
- Du behöver minska duplicering genom att dela gränser mellan intilliggande funktioner.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar:

1. **Aspose.GIS for .NET** – ladda ner och installera från den officiella webbplatsen [here](https://releases.aspose.com/gis/net/).  
2. **Utvecklingsmiljö** – Visual Studio, Visual Studio Code, eller någon IDE som stödjer C#.  
3. **Exempel‑GeoJSON‑fil** – en fil som innehåller de funktioner du vill konvertera.  

## Importera namnrymder

Först, inkludera de nödvändiga namnrymderna i ditt projekt:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```

## Steg‑för‑steg‑guide

### Steg 1: Definiera filsökvägar

Ange var käll‑GeoJSON‑filen finns och var TopoJSON‑filen ska skrivas:

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

> **Proffstips:** Använd `Path.Combine` för plattformsoberoende sökvägsbyggnad om du riktar dig mot .NET Core.

### Steg 2: Konfigurera konverteringsalternativ (Ange Object Name Attribute)

Skapa en `ConversionOptions`‑instans och tala om för Aspose.GIS hur funktionerna ska grupperas:

```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // Specify the attribute in GeoJSON layer by which we are going to group into objects
        ObjectNameAttribute = "group",
        // Specify the default object name for features with unknown attribute values
        DefaultObjectName = "unnamed",
    }
};
```

Byt ut `"group"` mot det faktiska egenskapsnamnet i din GeoJSON som du vill använda för **geojson‑funktiongruppering**. `DefaultObjectName` säkerställer att varje funktion hamnar i ett TopoJSON‑objekt, även om attributet saknas.

### Steg 3: Utför konverteringen (Konvertera GeoJSON till TopoJSON)

Kör konverteringen med ett enda API‑anrop:

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

Efter körning kommer `convertedSampleWithGrouping_out.topojson` att innehålla TopoJSON‑representationen, med funktioner grupperade enligt det attribut du angav.

## Vanliga problem och felsökning

| Symptom | Trolig orsak | Åtgärd |
|---------|--------------|-----|
| **Alla funktioner hamnar i “unnamed”** | `ObjectNameAttribute` matchar ingen egenskap i GeoJSON | Verifiera det exakta egenskapsnamnet (skiftlägeskänsligt) och uppdatera alternativet |
| **Utdatafilen är tom** | Felaktig filsökväg eller saknade läsbehörigheter | Använd absoluta sökvägar eller säkerställ att appen har åtkomst till filsystemet |
| **Konverteringen kastar `NotSupportedException`** | Försök att konvertera en GeoJSON med geometrytyper som inte stöds (t.ex. GeometryCollection) | Förenkla källdata eller uppgradera till den senaste versionen av Aspose.GIS |

## Vanliga frågor

**Q: Kan jag gruppera funktioner baserat på flera attribut?**  
A: Ja, du kan konkatenera flera fält till ett enda virtuellt attribut eller köra flera konverteringspass med olika `ObjectNameAttribute`‑värden.

**Q: Är Aspose.GIS kompatibel med ASP.NET Core?**  
A: Absolut – biblioteket fungerar med ASP.NET Core, .NET 5, .NET 6 och det klassiska .NET‑ramverket.

**Q: Kan jag konvertera andra geografiska format än GeoJSON?**  
A: Ja, Aspose.GIS stödjer Shapefile, KML, GML, CSV och många fler format för både import och export.

**Q: Erbjuder Aspose.GIS en gratis provversion?**  
A: Ja, du kan få en gratis provversion av Aspose.GIS från [here](https://releases.aspose.com/).

**Q: Var kan jag få support för Aspose.GIS?**  
A: Du kan få support från Aspose.GIS‑community‑forumet [here](https://forum.aspose.com/c/gis/33).

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Senast uppdaterad:** 2025-12-06  
**Testad med:** Aspose.GIS for .NET (latest release)  
**Författare:** Aspose  

---
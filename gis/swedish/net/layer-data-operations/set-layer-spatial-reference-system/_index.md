---
date: 2025-12-31
description: Lär dig hur du skapar ett vektorlager och ställer in lagrets rumsliga
  referenssystem med Aspose.GIS för .NET. Behärska att definiera rumslig referens,
  lägga till punktfunktion och hämta EPSG‑kod.
linktitle: Set Layer Spatial Reference System
second_title: Aspose.GIS .NET API
title: Skapa vektorlager och ange lagerns spatiala referenssystem
url: /sv/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa vektorlager och ange lagrets rumsliga referenssystem

## Introduktion
I det stora landskapet av Geographic Information Systems (GIS) framträder **Aspose.GIS for .NET** som ett robust och mångsidigt verktyg för utvecklare. I den här handledningen kommer du att **skapa vektorlager**, definiera dess rumsliga referens, lägga till en punktfunktion och hämta EPSG‑koden – allt med tydlig, steg‑för‑steg‑vägledning. Oavsett om du är en erfaren GIS‑ingenjör eller precis har börjat, kommer dessa tekniker att hjälpa dig att korrekt ange shapefilens koordinatsystem och öka tillförlitligheten i dina spatiala data‑arbetsflöden.

## Snabba svar
- **Vad betyder “skapa vektorlager”?** Det skapar ett nytt GIS‑lager (t.ex. en Shapefile) som kan lagra geometrier såsom punkter, linjer eller polygoner.  
- **Vilken EPSG‑kod används i exemplet?** EPSG 26918 (NAD83 / UTM‑zon 18N).  
- **Kan jag lägga till en punktfunktion efter att lagret skapats?** Ja – använd `ConstructFeature()` och tilldela en `Point`‑geometri.  
- **Hur hämtar jag lagrets CRS?** Läs `layer.SpatialReferenceSystem.EpsgCode` eller `.Name`.  
- **Behöver jag en licens för Aspose.GIS?** En gratis provversion finns tillgänglig; en licens krävs för produktionsbruk.

## Förutsättningar
Innan du dyker ner i handledningen, se till att du har följande förutsättningar på plats:
- Grundläggande kunskaper i .NET‑programmering.  
- Visual Studio installerat på ditt system.  
- Aspose.GIS for .NET‑biblioteket, som du kan ladda ner [här](https://releases.aspose.com/gis/net/).  
- En grundläggande förståelse för rumsliga referenssystem i GIS.

## Importera namnrymder
I ditt .NET‑projekt, börja med att importera de nödvändiga namnrymderna för att få åtkomst till funktionerna som tillhandahålls av Aspose.GIS. Använd följande kodsnutt:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Steg 1: Ange dokumentkatalogen
Börja med att ange sökvägen till din dokumentkatalog. Detta blir platsen där dina spatiala data‑filer lagras.

```csharp
string dataDir = "Your Document Directory";
```

## Steg 2: Definiera rumslig referens och ange shapefilens koordinatsystem
Definiera sökvägen för Shapefile och **definiera rumslig referens** med hjälp av EPSG‑koden (26918 i detta exempel). Detta steg **anger shapefilens koordinatsystem** för lagret.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Steg 3: Skapa vektorlager
Nu **skapar du vektorlager** med den angivna Shapefile‑sökvägen, drivrutinstypen (Shapefile) och det rumsliga referenssystem du just definierat.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

## Steg 4: Lägg till punktfunktion i lagret
Konstruera en ny funktion och **lägg till punktfunktion** genom att sätta dess geometri (en `Point` med koordinaterna 60, 24). Lägg sedan till funktionen i vektorlager.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

## Steg 5: Hämta information om rumsligt referenssystem (hämta EPSG‑kod)
Öppna vektorlager och hämta information om det rumsliga referenssystemet, såsom EPSG‑kod och det mänskligt läsbara namnet. Detta demonstrerar hur man **hämtar EPSG‑kod** och **anger lagrets CRS**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

Upprepa dessa steg enligt ditt specifika användningsfall, så är du väl på väg att bemästra konsten att **skapa vektorlager** och hantera rumsliga referenser med Aspose.GIS for .NET.

## Vanliga problem och lösningar
| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| **Lagret går inte att öppna** | Fel drivrutin eller korrupt filsökväg | Verifiera `Drivers.Shapefile` och säkerställ att `path` pekar på en befintlig `.shp`‑fil. |
| **Fel CRS visas** | Fel EPSG‑kod används | Dubbelkolla EPSG‑koden mot en auktoritativ källa (t.ex. EPSG.io). |
| **Funktionen sparas inte** | `layer.Add(feature)` anropas inte inom `using`‑blocket | Säkerställ att `Add`‑metoden körs innan lagret tas bort. |

## Vanliga frågor
### Är Aspose.GIS kompatibel med andra GIS‑bibliotek?
Ja, Aspose.GIS integreras väl med andra GIS‑bibliotek och kan användas i kombination med dem.

### Kan jag använda Aspose.GIS för både skrivbords‑ och webbapplikationer?
Absolut! Aspose.GIS är mångsidigt och kan utnyttjas i både skrivbords‑ och webb‑baserade applikationer.

### Finns det licensalternativ för Aspose.GIS?
Ja, du kan utforska licensalternativ och göra ett köp [här](https://purchase.aspose.com/buy).

### Finns det en gratis provversion av Aspose.GIS?
Självklart! Du kan ladda ner en gratis provversion [här](https://releases.aspose.com/).

### Var kan jag få support för frågor relaterade till Aspose.GIS?
För support eller frågor, besök [Aspose.GIS‑forumet](https://forum.aspose.com/c/gis/33).

## Ytterligare vanliga frågor
**Q: Hur ändrar jag CRS för en befintlig Shapefile?**  
A: Öppna lagret, skapa ett nytt `SpatialReferenceSystem` med önskad EPSG‑kod och tilldela det till `layer.SpatialReferenceSystem` innan du sparar.

**Q: Kan jag lägga till andra geometri‑typer (t.ex. polygoner) med samma metod?**  
A: Ja – ersätt `new Point(x, y)` med `new Polygon(...)` eller `new LineString(...)` efter behov.

**Q: Är det möjligt att arbeta med stora datamängder effektivt?**  
A: Använd streaming‑API:er (`VectorLayer.Create` med `FeatureCollection`) och frigör lager omedelbart för att spara resurser.

**Q: Stöder Aspose.GIS koordinattransformation?**  
A: Ja – använd `Geometry.Transform(targetSrs)` för att projicera geometrier mellan olika rumsliga referenser.

**Q: Vilka .NET‑versioner stöds?**  
A: Aspose.GIS fungerar med .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

## Slutsats
I den här handledningen har vi gått igenom hur man **skapar vektorlager**, definierar dess rumsliga referens, **lägger till punktfunktion** och **hämtar EPSG‑kod** med Aspose.GIS for .NET. Genom att behärska dessa steg kan du tryggt ange shapefilens koordinatsystem, hantera lagrets CRS och bygga pålitliga GIS‑applikationer.

---

**Last Updated:** 2025-12-31  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-05-31
description: Lär dig hur du skapar polygon med Aspose.GIS för .NET. Steg‑för‑steg‑guide
  för .NET‑utvecklare för att bygga polygongeometri och exportera polygon‑shapefile.
keywords:
- how to create polygon
- export polygon shapefile
- add vertices polygon
- build polygon coordinates
linktitle: Skapa polygongeometri
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create polygon using Aspose.GIS for .NET. Step‑by‑step
    guide for .NET developers to build polygon geometry and export polygon shapefile.
  headline: How to Create Polygon Geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create polygon using Aspose.GIS for .NET. Step‑by‑step
    guide for .NET developers to build polygon geometry and export polygon shapefile.
  name: How to Create Polygon Geometry with Aspose.GIS for .NET
  steps:
  - name: Create a Polygon Object
    text: The `Polygon` class is the top‑level container that represents a single
      polygon geometry. **The `Polygon` class represents a closed geometric shape
      consisting of an exterior ring and optional interior rings.**
  - name: Define Exterior Ring
    text: A `LinearRing` holds the sequence of points that form the outer boundary.
      **The `LinearRing` class stores an ordered list of coordinate pairs that must
      form a closed loop.**
  - name: Add Points to the Exterior Ring
    text: Now we **add vertices polygon** by feeding latitude‑longitude pairs (or
      any coordinate system you prefer) into the ring. The points must form a closed
      loop, so the first and last coordinates are identical. **`LinearRing.AddPoint(x,
      y)` adds a single vertex to the ring; repeat for each coordinate.**
  - name: Set Exterior Ring on the Polygon
    text: Finally, assign the prepared ring to the polygon’s `ExteriorRing` property.
      The polygon is now a complete, valid geometry object. **The `ExteriorRing` property
      links the constructed `LinearRing` to the `Polygon` instance, finalizing the
      shape.** Congratulations! You have just **created polygon geome
  type: HowTo
- questions:
  - answer: Yes – simply iterate through your coordinate collection and call `ring.AddPoint(x,
      y)` for each item.
    question: Can I create a polygon from an existing list of coordinates?
  - answer: Create another `LinearRing`, add points, and assign it to `polygon.InteriorRings.Add(yourRing);`.
    question: How do I add an interior ring (hole) to the polygon?
  - answer: Use `polygon.IsValid` property; it returns `true` if the geometry complies
      with OGC standards.
    question: Is there a way to validate the polygon after creation?
  - answer: Absolutely. Use `FeatureWriter` with `GeoJson` format to write the polygon
      to a file, or choose `Shapefile` to **export polygon shapefile**.
    question: Can I export the polygon directly to GeoJSON?
  - answer: The library currently focuses on 2‑D geometries; for 3‑D you’ll need to
      manage Z‑values manually or use another specialized library.
    question: Does Aspose.GIS support 3‑D polygons?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hur man skapar polygongeometri med Aspose.GIS för .NET
url: /sv/net/geometry-creation/create-polygon-geometry/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar polygongeometri med Aspose.GIS för .NET

## Introduktion  
Om du letar efter en tydlig, praktisk guide om **hur man skapar polygon** geometri i en .NET-miljö, har du kommit till rätt ställe. I den här handledningen går vi igenom hela processen med Aspose.GIS för .NET – från att sätta upp projektet till att lägga till punkter och slutföra polygonen. I slutet kommer du att förstå varför detta bibliotek är ett solidt val för att arbeta med spatiala datapolygonstrukturer och du kommer att ha ett återanvändbart **exempel på polygongeometri** redo för dina egna GIS-applikationer. Du kommer också att se hur man **exporterar polygon shapefile** och andra vanliga format.

## Snabba svar
`Polygon` är klassen som representerar polygongeometrier i Aspose.GIS. `LinearRing.AddPoint` lägger till en vertex i en linjär ring.  

- **Vad är den primära klassen för polygoner?** `Polygon` från `Aspose.Gis.Geometries`.  
- **Vilken metod lägger till vertices?** `LinearRing.AddPoint(x, y)` – den lägger till polygonens vertices en efter en.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en licens krävs för produktion.  
- **Vilka .NET-versioner stöds?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6+.  
- **Kan jag exportera polygonen till en fil?** Ja – använd `FeatureWriter` för att skriva Shapefile, GeoJSON, etc., och enkelt **exportera polygon shapefile**.

## Vad är en polygongeometri?  
En polygon är en sluten form bestående av en yttre ring (den yttre gränsen) och eventuellt en eller flera inre ringar (hål). I GIS modellerar polygoner verkliga områden såsom sjöar, tomter eller administrativa gränser. Aspose.GIS tillhandahåller en ren objektmodell som låter dig **bygga polygonkoordinater** med bara några få rader C#.

## Varför använda Aspose.GIS för att skapa polygongeometri?  
Aspose.GIS låter dig skapa polygongeometri snabbt samtidigt som det levererar prestanda på företagsnivå. Det stöder **50+ in- och utdataformat**, kan bearbeta dataset med flera hundra sidor utan att ladda hela filen i minnet, och kör på .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6+. Detta innebär att du kan **exportera polygon shapefile**, GeoJSON, KML och många andra format direkt från kod, vilket eliminerar behovet av tredjepartsomvandlare.

## Förutsättningar  
1. **Kunskap om C#-programmering** – grundläggande förtrogenhet med klasser och metoder.  
2. **Installation av Aspose.GIS för .NET** – du kan ladda ner det från [här](https://releases.aspose.com/gis/net/).  
3. **Inställning av utvecklingsmiljö** – Visual Studio, Rider eller någon IDE som stöder .NET.  

## Importera namnrymder  
Vi behöver importera GIS-klasserna i scopet. `using`-direktiven nedan är allt du behöver för detta exempel.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Hur man skapar polygongeometri i Aspose.GIS  

Läs in ditt projekt, lägg till de nödvändiga namnrymderna, skapa ett `Polygon`-objekt, bygg dess yttre ring, lägg till polygonens vertices och till sist tilldela ringen – allt i några enkla steg. Detta tillvägagångssätt fungerar på alla stödda .NET‑runtime och producerar en giltig OGC‑kompatibel polygon redo för export.

### Steg 1: Skapa ett Polygon‑objekt  
`Polygon`-klassen är den översta behållaren som representerar en enskild polygongeometri.  
**`Polygon`-klassen representerar en sluten geometrisk form bestående av en yttre ring och valfria inre ringar.**  
```csharp
Polygon polygon = new Polygon();
```

### Steg 2: Definiera yttre ring  
En `LinearRing` innehåller sekvensen av punkter som bildar den yttre gränsen.  
**`LinearRing`-klassen lagrar en ordnad lista av koordinatpar som måste bilda en sluten slinga.**  
```csharp
LinearRing ring = new LinearRing();
```

### Steg 3: Lägg till punkter i den yttre ringen  
Nu **lägger vi till polygonens vertices** genom att mata in latitud‑longitud‑par (eller vilket koordinatsystem du föredrar) i ringen. Punkten måste bilda en sluten slinga, så den första och sista koordinaten är identiska.  
**`LinearRing.AddPoint(x, y)` lägger till en enskild vertex i ringen; upprepa för varje koordinat.**  
```csharp
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

### Steg 4: Tilldela yttre ring till polygonen  
Till sist, tilldela den förberedda ringen till polygonens `ExteriorRing`-egenskap. Polygonen är nu ett komplett, giltigt geometriskt objekt.  
**`ExteriorRing`-egenskapen länkar den konstruerade `LinearRing` till `Polygon`‑instansen och slutför formen.**  
```csharp
polygon.ExteriorRing = ring;
```

Grattis! Du har just **skapat polygongeometri** med Aspose.GIS för .NET. Härifrån kan du bifoga polygonen till ett objekt, skriva den till en fil eller utföra rumslig analys.

## Vanliga problem & tips  

| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| **Ringen är inte sluten** | Den första och sista punkten skiljer sig, vilket gör geometrin ogiltig. | Upprepa den första koordinaten som den sista punkten (som visat ovan). |
| **Fel koordinatordning** | GIS‑bibliotek förväntar sig X (longitude) sedan Y (latitude). | Se till att du skickar `(longitude, latitude)` till `AddPoint`. |
| **Saknad licens** | Provläget kan begränsa vissa operationer. | Använd en gratis provlicens för testning; använd en betald licens för produktion. |

## Vanliga frågor  

**Q: Kan jag skapa en polygon från en befintlig lista med koordinater?**  
A: Ja – iterera helt enkelt genom din koordinatsamling och anropa `ring.AddPoint(x, y)` för varje element.

**Q: Hur lägger jag till en inre ring (hål) i polygonen?**  
A: Skapa en annan `LinearRing`, lägg till punkter och tilldela den till `polygon.InteriorRings.Add(yourRing);`.

**Q: Finns det ett sätt att validera polygonen efter skapandet?**  
A: Använd egenskapen `polygon.IsValid`; den returnerar `true` om geometrin följer OGC‑standarderna.

**Q: Kan jag exportera polygonen direkt till GeoJSON?**  
A: Absolut. Använd `FeatureWriter` med `GeoJson`-format för att skriva polygonen till en fil, eller välj `Shapefile` för att **exportera polygon shapefile**.

**Q: Stöder Aspose.GIS 3‑D‑polygoner?**  
A: Biblioteket fokuserar för närvarande på 2‑D‑geometrier; för 3‑D måste du hantera Z‑värden manuellt eller använda ett annat specialiserat bibliotek.

---

**Senast uppdaterad:** 2026-05-31  
**Testat med:** Aspose.GIS 24.11 för .NET  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Skapa polygon med hålgeometri med Aspose.GIS](/gis/net/geometry-creation/create-polygon-with-hole-geometry/)
- [Skapa polygongeometri C# och kontrollera skärning med Aspose.GIS för .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Hur man skapar buffert med Aspose.GIS för .NET](/gis/net/geometry-analysis/create-geometry-buffer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
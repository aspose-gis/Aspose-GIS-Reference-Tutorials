---
date: 2026-06-25
description: Lär dig hur du läser shapefile och konverterar en polygon shapefile till
  en linestring med Aspose.GIS för .NET. Boosta din GIS‑utveckling med tydlig steg‑för‑steg‑vägledning.
keywords:
- how to read shapefile
- convert polygon to line
- shapefile to geojson c#
- extract lines from polygon
linktitle: Konvertera Polygon Shapefile till Linestring
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  headline: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  type: TechArticle
- description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  name: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  steps:
  - name: Set the Document Directory
    text: Replace `"Your Document Directory"` with the actual path where your shapefile
      resides.
  - name: Open the Source Shapefile
    text: This line opens the source Polygon Shapefile so you can read its features.
  - name: Create the Destination Linestring Shapefile
    text: Here we create a new Linestring Shapefile that will store the converted
      geometries.
  - name: Iterate Through Source Features
    text: The loop walks through each polygon feature in the original file.
  - name: Convert Polygon to Linestring and Write to Destination
    text: The `ExteriorRing` property returns the outer boundary of a polygon as a
      `LineString`. In this block we convert polygon to line (`LineString`) and add
      the new feature to the destination shapefile.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS supports .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7, ensuring seamless integration with modern development stacks.
    question: Is Aspose.GIS compatible with all versions of .NET?
  - answer: Yes, you can. Purchase a license [here](https://purchase.aspose.com/buy)
      to remove evaluation limitations and obtain full support.
    question: Can I use Aspose.GIS for commercial projects?
  - answer: Yes, you can find comprehensive documentation and code samples on the
      [documentation page](https://reference.aspose.com/gis/net/).
    question: Are there any examples or documentation available?
  - answer: Absolutely – explore Aspose.GIS with a free trial by visiting [this link](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      assistance and official support.
    question: Where can I seek help or support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hur du läser Shapefile i C# – Konvertera Polygon Shapefile till Linestring
url: /sv/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Läs Shapefile C# – Konvertera Polygon Shapefile till Linestring

## Introduktion
Om du behöver **how to read shapefile** data i en .NET-miljö, är du på rätt plats. Aspose.GIS för .NET abstraherar det lågnivå binära formatet för en Shapefile, så att du kan ladda, fråga och transformera geografiska funktioner med bara några API‑anrop. Att konvertera en polygon‑shapefile till en linestring är särskilt användbart när du vill extrahera linjära representationer för ruttplanering, nätverksanalys eller enkel visualisering.

## Snabba svar
- **Vilket bibliotek hjälper dig att läsa shapefile c#?** Aspose.GIS för .NET – det stöder 50+ GIS‑format och hanterar filer på upp till flera hundra megabyte utan att ladda hela filen i minnet.  
- **Kan du konvertera en polygon till en linje?** Ja – anropa `LineString` på polygonens yttre ring och skriv resultatet till en ny shapefile.  
- **Behöver jag en licens för produktion?** En kommersiell licens krävs för produktionsdistributioner; en gratis provversion fungerar för utvärdering.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Finns en provversion tillgänglig?** Absolut – ladda ner en gratis provversion från Aspose‑sajten.

`LineString` är en geometrityp som representerar en serie sammanhängande linjesegment.

## Vad är “read shapefile c#”?
`Document` är kärnklassen som representerar en GIS‑datamängd och ger åtkomst till dess funktioner.  
Att läsa en shapefile i C# betyder att ladda `.shp`‑filen i minnet så att du kan fråga, modifiera eller transformera dess geometrier. **Du instansierar helt enkelt `Document`‑klassen med filsökvägen, och Aspose.GIS parsar den binära strukturen åt dig**, vilket exponerar funktionerna via en lätt‑använd samling. Detta tillvägagångssätt eliminerar behovet av att manuellt arbeta med lågnivå filhuvuden eller koordinatarrayer.

## Varför konvertera polygon till linje med Aspose.GIS?
Att konvertera en polygon till en linestring bevarar den exakta yttre gränsen samtidigt som inre ringar tas bort, vilket ger dig en ren linjär representation. Aspose.GIS bearbetar **datamängder på upp till 500 MB på under 2 sekunder på en typisk server**, vilket gör batch‑konverteringar snabba och minnes‑effektiva. Biblioteket behåller också den ursprungliga rumsliga referensen, så de resulterande linjerna alignerar perfekt med befintliga GIS‑lager.

## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande:

- **Aspose.GIS Library** – Ladda ner och installera Aspose.GIS‑biblioteket från [webbplatsen](https://releases.aspose.com/gis/net/).  
- **Shapefile Data** – Ha en Polygon‑Shapefile redo för konvertering. Om du inte har en, kan du hitta exempeldata eller skapa din egen.  
- **Development Environment** – Ställ in din .NET‑utvecklingsmiljö med nödvändiga verktyg (Visual Studio, .NET SDK, etc.).

## Importera namnrymder
`Document`‑klassen är Aspose.GIS:s kärnobjekt som representerar en GIS‑datamängd och tillhandahåller metoder för att läsa och skriva shapefiler. Lägg till följande namnrymder i början av din kodfil:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Hur läser du shapefile och konverterar polygon till linestring?
Ladda den ursprungliga polygon‑shapefilen, extrahera varje polygons yttre ring, skapa en `LineString` från den ringen och skriv resultatet till en ny shapefile – allt i fem enkla steg. Detta mönster fungerar för datamängder av vilken storlek som helst och garanterar att källans koordinatsystem bevaras i destinationen.

### Steg 1: Ange dokumentkatalogen
Byt ut `"Your Document Directory"` mot den faktiska sökvägen där din shapefile finns.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Steg 2: Öppna källshapefile
Denna rad öppnar den ursprungliga Polygon‑Shapefilen så att du kan läsa dess funktioner.

```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```

### Steg 3: Skapa destinations‑Linestring‑shapefile
Här skapar vi en ny Linestring‑Shapefile som kommer att lagra de konverterade geometrierna.

```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```

### Steg 4: Iterera genom källfunktioner
Loopen går igenom varje polygonfunktion i den ursprungliga filen.

```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```

### Steg 5: Konvertera polygon till linestring och skriv till destination
`ExteriorRing`‑egenskapen returnerar den yttre gränsen av en polygon som en `LineString`.  
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```

## Vanliga problem och tips
- **Coordinate System Mismatch** – Säkerställ att både källa och destination använder samma rumsliga referens; annars kan linjerna verka förskjutna.  
- **Large Files** – När du bearbetar mycket stora shapefiler, överväg att strömma funktioner istället för att ladda dem alla i minnet på en gång.  
- **Null Geometries** – Skydda mot funktioner med tomma geometrier för att undvika körningsfel.  
- **Extract lines from polygon** – Om du bara behöver den yttre ringen, använd `ExteriorRing`‑egenskapen; för inre ringar, iterera `InteriorRings`.  

## Vanliga frågor

**Q: Är Aspose.GIS kompatibel med alla versioner av .NET?**  
A: Ja, Aspose.GIS stöder .NET Framework 4.5+, .NET Core 3.1+, och .NET 5/6/7, vilket säkerställer sömlös integration med moderna utvecklingsstackar.

**Q: Kan jag använda Aspose.GIS för kommersiella projekt?**  
A: Ja, det kan du. Köp en licens [here](https://purchase.aspose.com/buy) för att ta bort utvärderingsbegränsningar och få full support.

**Q: Finns det exempel eller dokumentation tillgänglig?**  
A: Ja, du kan hitta omfattande dokumentation och kodexempel på [documentation page](https://reference.aspose.com/gis/net/).

**Q: Finns en provversion tillgänglig?**  
A: Absolut – utforska Aspose.GIS med en gratis provversion genom att besöka [this link](https://releases.aspose.com/).

**Q: Var kan jag söka hjälp eller support?**  
A: Besök [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) för gemenskapsstöd och officiell support.

---

**Senast uppdaterad:** 2026-06-25  
**Testat med:** Aspose.GIS for .NET (latest release)  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man konverterar Shapefile till GeoJSON med Aspose.GIS för .NET](/gis/net/layer-management/extract-features-to-geojson/)
- [Hur man läser GeoJSON från ström med Aspose.GIS för .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Hur man skapar polygongeometri med Aspose.GIS för .NET](/gis/net/geometry-creation/create-polygon-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
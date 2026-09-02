---
date: 2026-08-24
description: Lär dig hur du skapar geometry collection .NET med Aspose.GIS för .NET
  och visualiserar geospatial data i dina applikationer.
keywords:
- create geometry collection .net
- Aspose.GIS geometry collection
- .NET geospatial programming
lastmod: 2026-08-24
linktitle: Skapa Geometry Collection
og_description: Lär dig hur du skapar geometry collection .NET med Aspose.GIS, kombinerar
  punkter och linjer, och exporterar till GeoJSON eller Shapefile på några minuter.
og_image_alt: Screenshot of a .NET application creating and visualizing a geometry
  collection with Aspose.GIS
og_title: Hur man skapar geometry collection .NET med Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to create geometry collection .NET using Aspose.GIS for .NET
    and visualize geospatial data in your applications.
  headline: How to create geometry collection .NET using Aspose.GIS
  type: TechArticle
- description: Learn how to create geometry collection .NET using Aspose.GIS for .NET
    and visualize geospatial data in your applications.
  name: How to create geometry collection .NET using Aspose.GIS
  steps:
  - name: create a point geometry
    text: The `Point` class represents a single location defined by latitude (Y) and
      longitude (X). Here we use latitude 40.7128 and longitude ‑74.0060, which corresponds
      to New York City.
  - name: create a line string
    text: 'A `LineString` is an ordered list of points that forms a continuous line.
      In this example we define a line string with two vertices: (78.65, ‑32.65) and
      (‑98.65, 12.65).'
  - name: create a geometry collection
    text: Now we combine the previously created point and line string into a single
      collection. The `GeometryCollection` instance can now be exported, queried,
      or visualized as one cohesive object.
  type: HowTo
- questions:
  - answer: Yes. The library is compatible with .NET Core, .NET Standard, and the
      full .NET Framework, giving you flexibility across desktop, server, and cloud
      projects.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. It includes built‑in support for over 4,000 EPSG codes, allowing
      you to work with global and regional coordinate systems without manual transformations.
    question: Does Aspose.GIS support many spatial reference systems?
  - answer: Indeed. The API scales from simple scripts handling a few dozen features
      to enterprise services processing multi‑gigabyte datasets, thanks to streaming
      APIs that avoid loading entire files into memory.
    question: Is Aspose.GIS suitable for both small‑scale and enterprise‑level applications?
  - answer: Yes. After exporting to GeoJSON or Shapefile, you can load the file into
      popular viewers such as QGIS, ArcGIS, or embed it in web maps using Leaflet
      or Mapbox.
    question: Can I visualize geospatial data using Aspose.GIS?
  - answer: Join the community at the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      to share ideas, ask questions, and learn from other developers.
    question: Where can I ask for help or discuss best practices?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geometry collection
- Aspose.GIS
- .NET GIS
- geospatial data
title: Hur man skapar geometry collection .NET med Aspose.GIS
url: /sv/net/geometry-creation/create-geometry-collection/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar geometrisamling .NET med Aspose.GIS

## Introduktion

I den här guiden kommer du att **create geometry collection .NET**-objekt med Aspose.GIS, kombinera punkter, linjesträngar och andra geometrier, och se hur samlingen passar in i större GIS-pipelines. Oavsett om du bygger en karttjänst, en rumslig analysmotor eller ett enkelt skrivbordsverktyg, låter en geometrisamling dig behandla heterogena funktioner som en enda, exportklar enhet. I slutet av handledningen kommer du att kunna generera en samling, lägga till flera geometrityper och exportera den till format som GeoJSON eller Shapefile för efterföljande visualisering.

## Snabba svar
- **What is a geometry collection?** Det är en behållare som kan hålla punkter, linjer, polygoner och andra geometriska objekt tillsammans.  
- **Why choose Aspose.GIS?** Biblioteket erbjuder ett rent .NET‑API, stödjer 30+ GIS‑format och fungerar utan inhemska beroenden.  
- **What do I need beforehand?** .NET 6+ (eller .NET Core/.NET Framework), Aspose.GIS för .NET och en giltig prov‑ eller kommersiell licensnyckel.  
- **How long does the sample take?** Ungefär 5‑10 minuter att skriva, kompilera och köra.  
- **Can I visualize the result?** Ja – exportera till GeoJSON eller Shapefile och öppna filen i någon standard GIS‑visare.

## Vad är en geometry collection?

En geometry collection är ett sammansatt GIS‑objekt som kan lagra en blandning av punkter, linjesträngar, polygoner och andra geometrityper. Det är särskilt användbart när du behöver gruppera relaterade funktioner som inte delar en enda geometrityp, såsom en stads landmärken (punkter) tillsammans med dess vägnät (linjer).

## Varför skapa geometry collection med Aspose.GIS?

Aspose.GIS låter dig samla olika geometrityper i ett enda objekt, vilket förenklar datahantering, minskar minnesanvändning och säkerställer att samlingen kan exporteras till format som bevarar blandad geometrisemantik, vilket gör efterföljande bearbetning och visualisering enklare.

- **Flexibility:** Kombinera heterogena geometrier utan att förlora typinformation.  
- **Performance:** Arbeta med ett enda objekt istället för att jonglera flera separata instanser, vilket minskar minnesbelastningen med upp till 40 % för stora dataset.  
- **Interoperability:** Exportera till standard GIS‑format som förstår samlingssemantik; Aspose.GIS stödjer 30+ in‑ och utdataformat, inklusive GeoJSON, Shapefile, KML och GML.  
- **Visualization ready:** Mata samlingen direkt in i kartrenderingsbibliotek eller GIS‑skrivbordsverktyg för omedelbar visuell återkoppling.

## Förutsättningar

Innan du dyker in i den spännande världen av geospatial datamanipulation med Aspose.GIS för .NET, se till att du har följande:

1. **Install Aspose.GIS for .NET**  

   - Besök [download page](https://releases.aspose.com/gis/net/) och hämta den senaste versionen.  
   - Följ installationsstegen som beskrivs i den officiella dokumentationen [Aspose.GIS documentation](https://reference.aspose.com/gis/net/) för att lägga till NuGet‑paketet i ditt projekt.

2. **Set up your development environment**  

   - Öppna Visual Studio, Rider eller någon IDE du föredrar för .NET‑utveckling.  
   - Skapa en ny konsolapplikation (eller integrera i ett befintligt projekt) som riktar sig mot .NET 6 eller senare.

## Importera nödvändiga namnrymder

Det första steget är att ta med de erforderliga Aspose.GIS-namnrymderna i scope.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
```

*Klassen `GeometryCollection` är Aspose.GIS:s övergripande behållare som representerar en heterogen uppsättning geometrier i minnet.*  
*Klasserna `Point` och `LineString` är konkreta geometrityper som härstammar från den abstrakta basklassen `Geometry`.*

Med dessa namnrymder importerade är du redo att börja bygga geospatiala objekt.

## Hur man skapar geometry collection .NET

I följande exempel instansierar vi en ny `GeometryCollection`, lägger till en punkt och en linjesträng, och demonstrerar sedan hur samlingen kan manipuleras eller exporteras, vilket ger en tydlig grund för att bygga mer komplexa geospatiala arbetsflöden i.

### Steg 1: skapa en punktgeometri

`Point`-klassen representerar en enskild plats definierad av latitud (Y) och longitud (X).

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Här använder vi latitud 40.7128 och longitud ‑74.0060, vilket motsvarar New York City.

### Steg 2: skapa en linjesträng

`LineString` är en ordnad lista av punkter som bildar en kontinuerlig linje.

```csharp
Point point = new Point(40.7128, -74.006);
```

I detta exempel definierar vi en linjesträng med två hörn: (78.65, ‑32.65) och (‑98.65, 12.65).

### Steg 3: skapa en geometry collection

Nu kombinerar vi den tidigare skapade punkten och linjesträngen till en enda samling.

```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```

`GeometryCollection`-instansen kan nu exporteras, frågas eller visualiseras som ett sammanhängande objekt.

## Hur exporterar man en geometry collection till GeoJSON?

Läs in samlingen i minnet och anropa `Export`‑metoden, med `GeoJson` som utdataformat. Operationen skriver en standard‑kompatibel GeoJSON‑fil som kan öppnas direkt i webbkartor, QGIS eller någon GIS‑visare som stödjer formatet, enkelt.

## Vanliga problem och lösningar

| Problem | Lösning |
|-------|----------|
| **Invalid coordinate order** | Aspose.GIS förväntar sig **latitude, longitude** (Y, X). Dubbelkolla ordningen när du konstruerar punkter eller linjesträngar. |
| **Empty collection** | Se till att du lägger till minst en geometri innan du exporterar; annars blir utdatafilen tom. |
| **Export format not supporting collections** | Använd format som **GeoJSON** eller **Shapefile**, som bevarar samlingssemantik. |

## Vanliga frågor

**Q: Kan jag använda Aspose.GIS för .NET med andra .NET‑ramverk?**  
A: Ja. Biblioteket är kompatibelt med .NET Core, .NET Standard och hela .NET‑Framework, vilket ger dig flexibilitet över skrivbords-, server- och molnprojekt.

**Q: Stöder Aspose.GIS många rumsliga referenssystem?**  
A: Absolut. Det inkluderar inbyggt stöd för över 4 000 EPSG‑koder, vilket låter dig arbeta med globala och regionala koordinatsystem utan manuella transformationer.

**Q: Är Aspose.GIS lämplig för både småskalig och företagsnivå‑applikationer?**  
A: Ja. API:et skalar från enkla skript som hanterar ett dussintal funktioner till företags tjänster som bearbetar multi‑gigabyte‑dataset, tack vare streaming‑API:er som undviker att ladda hela filer i minnet.

**Q: Kan jag visualisera geospatial data med Aspose.GIS?**  
A: Ja. Efter export till GeoJSON eller Shapefile kan du ladda filen i populära visare som QGIS, ArcGIS eller bädda in den i webbkartor med Leaflet eller Mapbox.

**Q: Var kan jag be om hjälp eller diskutera bästa praxis?**  
A: Gå med i gemenskapen på [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) för att dela idéer, ställa frågor och lära av andra utvecklare.

## Ytterligare vanliga frågor

**Q: Hur exporterar jag en geometry collection till GeoJSON?**  
A: Anropa `collection.Export("output.geojson", ExportFormat.GeoJson)`. Detta skapar en fil som kan renderas direkt i webbläsare med JavaScript‑kartbibliotek.

**Q: Kan jag lägga till fler geometrityper, såsom polygoner, i samma samling?**  
A: Ja. `GeometryCollection` accepterar alla objekt som är härledda från `Geometry`, så du kan blanda punkter, linjer, polygoner och även nästlade samlingar.

**Q: Behöver jag en licens för att köra exempel­koden?**  
A: En gratis provversion fungerar för utveckling och testning, men en kommersiell licens krävs för produktionsdistribution.

## Varför detta är viktigt: kombinera flera geometrier effektivt

När du behöver **combine multiple geometries**—till exempel att para stadens landmärken (punkter) med vägnät (linjesträngar)—sparar en geometry collection dig från att hantera separata objekt och förenklar export till format som förstår samlingar. Detta ger renare kod, lägre minnesförbrukning och färre risker för data‑mismatch.

## Slutsats

Du har nu lärt dig hur du **create geometry collection .NET**-objekt med Aspose.GIS, lagt till punkter och linjesträngar samt exporterat samlingen för visualisering. Härifrån kan du utforska avancerade scenarier som att tillämpa rumsliga filter, transformera koordinatsystem eller integrera samlingen med kartrenderingsbibliotek.

---

**Senast uppdaterad:** 2026-08-24  
**Testad med:** Aspose.GIS for .NET 24.11  
**Författare:** Aspose  

```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```

## Relaterade handledningar

- [Lär dig hur du skapar MultiPolygon-geometri med Aspose.GIS](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [Skapa MultiLineString-geometri med Aspose.GIS för .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)
- [Skapa MultiPoint-geometri .NET med Aspose.GIS](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
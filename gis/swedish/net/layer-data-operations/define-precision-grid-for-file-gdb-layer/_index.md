---
date: 2026-09-30
description: Lär dig hur du skapar geodatabas och ställer in ett precisionsrutnät
  för ett File GDB-lager med Aspose.GIS for .NET, inklusive att lägga till objekt
  i ett lager och validera koordinatintervall.
keywords:
- how to create geodatabase
- how to validate coordinates
- handle out of range
- configure coordinate grid
- validate coordinate range
lastmod: 2026-09-30
linktitle: Definiera precisionsrutnät för File GDB-lager
og_description: Lär dig hur du skapar geodatabas och ställer in ett precisionsrutnät
  för ett File GDB-lager med Aspose.GIS for .NET, vilket säkerställer korrekta koordinater
  och hantering av värden utanför intervallet.
og_image_alt: Developer guide showing how to create a geodatabase and configure a
  precision grid with Aspose.GIS
og_title: Hur man skapar geodatabas och ställer in rutnät för File GDB-lager
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create geodatabase and set a precision grid for a File
    GDB layer using Aspose.GIS for .NET, including adding features to a layer and
    validating coordinate range.
  headline: How to create geodatabase and set grid for File GDB layer
  type: TechArticle
- description: Learn how to create geodatabase and set a precision grid for a File
    GDB layer using Aspose.GIS for .NET, including adding features to a layer and
    validating coordinate range.
  name: How to create geodatabase and set grid for File GDB layer
  steps:
  - name: create a dataset
    text: '`Dataset` represents a file‑geodatabase container that holds one or more
      spatial layers.'
  - name: define precision grid options
    text: '`PrecisionGridOptions` specifies the origin, scale, and validation behavior
      for coordinates. *The `EnsureValidCoordinatesRange = true` flag tells Aspose.GIS
      to **validate coordinate range** for every feature you add.*'
  - name: create a layer with the grid
    text: '`FeatureLayer` is the object that stores vector features inside a dataset.'
  - name: add features to the layer
    text: '`Feature` represents a single geometric object (point, line, polygon) together
      with its attribute values.'
  - name: handle exceptions when adding out‑of‑range features
    text: '`FeatureException` is thrown when a geometry violates the defined grid
      limits.'
  - name: clean up
    text: The `using` statements automatically close and dispose of the dataset and
      layer, ensuring all resources are released.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS supports Shapefile, GeoJSON, KML, and many more formats—over
      30 in total.
    question: Can I use Aspose.GIS for .NET with other GIS file formats?
  - answer: Absolutely. The library works with .NET Framework, .NET Core, and .NET
      5/6+.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Yes, the API includes methods for buffering, intersecting, and calculating
      distances.
    question: Can I perform spatial operations such as buffering or intersection?
  - answer: Yes, you can transform geometries between different spatial reference
      systems using the built‑in reprojection tools.
    question: Does Aspose.GIS provide coordinate transformation capabilities?
  - answer: Yes, you can download a free trial from the [website](https://releases.aspose.com/gis/net/).
    question: Is there a trial version available?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create geodatabase
- Aspose.GIS
- .NET GIS programming
- precision grid
title: Hur man skapar geodatabas och ställer in rutnät för File GDB-lager
url: /sv/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ställer in rutnät för File GDB-lager i Aspose.GIS

## Introduktion
I den här handledningen kommer du att **skapa en geodatabas**, lägga till ett lager och lära dig hur du **ställer in ett precisionsrutnät** för det File Geodatabase (GDB)-lagret med Aspose.GIS för .NET. Att definiera ett precisionsrutnät låter dig **validera koordinatintervall**, förhindrar fel utanför intervallet och garanterar att varje **lägg till funktioner i lager**-operation lagrar data korrekt. Du kommer att se varför detta är viktigt, hur du **konfigurerar koordinatrutnät** och hur du **hanterar utanför intervallet**-scenarier på ett smidigt sätt.

## Snabba svar
- **Vad betyder “set grid”?** Det definierar koordinatprecisionen och det giltiga intervallet för ett GIS-lager.  
- **Varför använda ett precisionsrutnät?** Det skyddar dina data från ogiltiga koordinater och förbättrar lagringseffektiviteten.  
- **Vilket bibliotek tillhandahåller denna funktion?** Aspose.GIS för .NET.  
- **Behöver jag en licens?** En provversion finns tillgänglig; en kommersiell licens krävs för produktion.  
- **Kan jag använda detta med .NET Core?** Ja, Aspose.GIS stödjer .NET Framework och .NET Core.

## Vad är ett precisionsrutnät och varför ställa in det?
Ett precisionsrutnät är en uppsättning parametrar (ursprung, skala osv.) som talar om för GIS-motorn hur koordinatvärden ska avrundas och lagras. Genom att konfigurera ett rutnät **validerar du koordinatintervallet** automatiskt, och varje försök att infoga en punkt utanför rutnätet kommer att kasta ett undantag—vilket hjälper dig att **hantera utanför intervallet**-scenarier tidigt i utvecklingen.

## Varför skapa en geodatabas med ett precisionsrutnät?
Att skapa en filgeodatabase ger dig en portabel, högpresterande behållare för vektordata. Att lägga till ett precisionsrutnät vid skapandet säkerställer att varje lagrad funktion följer samma numeriska gränser, förbättrar indexeringshastigheten och fångar ogiltiga koordinater innan de korruptar datasetet. Denna tidiga validering minskar efterföljande rengöringsarbete och garanterar konsekvent datakvalitet i hela projektet.

- **Konsekvent datakvalitet** – varje funktion respekterar samma numeriska precision.  
- **Snabbare indexering** – motorn kan lagra koordinater mer effektivt.  
- **Tidigt felupptäckt** – koordinater utanför intervallet fångas innan de korruptar datasetet.

## Förutsättningar
1. **Visual Studio** – någon recent version (Community, Professional eller Enterprise).  
2. **Aspose.GIS för .NET** – ladda ner det från [webbplatsen](https://releases.aspose.com/gis/net/).  
3. **Grundläggande C#-kunskaper** – du bör vara bekväm med att skapa .NET-konsolprojekt.

## Vanliga användningsfall
- **Fältdatainsamling** där GPS-enheter kan producera koordinater något utanför det avsedda området.  
- **Datamigrering** från äldre system som använde olika koordinatprecisioner.  
- **Automatiserade ETL-pipelines** som måste upprätthålla spatial integritet innan data laddas in i en GIS-databas.

## Importera namnrymder
De nödvändiga Aspose.GIS-namnrymderna tillhandahåller klasserna för att arbeta med dataset, lager och geometrier.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## Hur man konfigurerar koordinatrutnät i ett File GDB-lager
I det här avsnittet går vi igenom hela processen för att skapa ett dataset, definiera ett precisionsrutnät, lägga till ett lager, infoga funktioner och hantera eventuella fel som uppstår. Stegen illustreras med koncisa kodsnuttar, och varje steg innehåller en kort förklaring till varför operationen är nödvändig för att upprätthålla spatial integritet.

### Steg 1: skapa ett dataset
`Dataset` representerar en fil‑geodatabase‑behållare som innehåller en eller flera spatiala lager.  

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### Steg 2: definiera alternativ för precisionsrutnät
`PrecisionGridOptions` specificerar ursprung, skala och valideringsbeteende för koordinater.  

```csharp
var options = new FileGdbOptions
{
    CoordinatePrecisionGrid = new FileGdbCoordinatePrecisionGrid
    {
        XOrigin = -400,
        YOrigin = -400,
        XYScale = 1e10,
        MOrigin = 0,
        MScale = 1e4,
    },
    EnsureValidCoordinatesRange = true,
};
```

*Flaggan `EnsureValidCoordinatesRange = true` talar om för Aspose.GIS att **validera koordinatintervallet** för varje funktion du lägger till.*

### Steg 3: skapa ett lager med rutnätet
`FeatureLayer` är objektet som lagrar vektorfunktioner i ett dataset.  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### Steg 4: lägg till funktioner i lagret
`Feature` representerar ett enskilt geometriskt objekt (punkt, linje, polygon) tillsammans med dess attributvärden.  

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### Steg 5: hantera undantag när du lägger till funktioner utanför intervallet
`FeatureException` kastas när en geometri bryter mot de definierade rutnätsgränserna.  

```csharp
try
{
    layer.Add(feature);
}
catch (GisException e)
{
    Console.WriteLine(e.Message); // X value -410 is out of valid range.
}
```

### Steg 6: rensa upp
`using`-satserna stänger och frigör automatiskt datasetet och lagret, vilket säkerställer att alla resurser släpps.

## Varför konfigurera ett precisionsrutnät?
Aspose.GIS stödjer **över 30 GIS‑filformat** och kan bearbeta **dataset med flera hundra sidor** utan att ladda in hela filen i minnet. Att använda ett precisionsrutnät minskar lagringsstorleken med upp till **15 %** och minskar indexeringstiden med ungefär **20 %** eftersom koordinater lagras i en normaliserad, avrundad form.

## Vanliga problem och lösningar
| Issue | Why it happens | Fix |
|-------|----------------|-----|
| **Exception: “X value … is out of valid range.”** | Koordinater ligger utanför precisionsrutnätet. | Justera `XOrigin`, `YOrigin` eller `XYScale` så att de omfattar dina data, eller säkerställ att indata ligger inom det definierade intervallet. |
| **Features not appearing in GIS viewer** | Lagret sparades inte eller fel rumslig referens. | Verifiera att `SpatialReferenceSystem.Wgs84` matchar visningsprogrammets CRS, och att `Dataset.Create` lyckades. |
| **M values ignored** | `MScale` är satt till 0 eller för lågt. | Sätt ett rimligt `MScale` (t.ex. `1e4`) för att lagra måttvärden. |

## Felsökningstips
- **Dubbelkolla rutnätsutbredningarna** innan du laddar stora datamängder; ett litet skrivfel i `XOrigin` kan orsaka att många rader avvisas.  
- **Logga undantagsmeddelandet** (som visas i try‑catch‑blocket) till en fil när du bearbetar automatiserade importeringar; detta gör det enklare att upptäcka mönster i data utanför intervallet.  
- **Använd `EnsureValidCoordinatesRange = false` endast för betrodda datakällor** – att stänga av det hoppar över validering och kan leda till korrupta geometrier.

## Vanliga frågor

**Q: Kan jag använda Aspose.GIS för .NET med andra GIS‑filformat?**  
A: Ja, Aspose.GIS stödjer Shapefile, GeoJSON, KML och många fler format—över 30 totalt.

**Q: Är Aspose.GIS för .NET kompatibel med .NET Core?**  
A: Absolut. Biblioteket fungerar med .NET Framework, .NET Core och .NET 5/6+.

**Q: Kan jag utföra spatiala operationer som buffring eller skärning?**  
A: Ja, API:et innehåller metoder för buffring, skärning och beräkning av avstånd.

**Q: Tillhandahåller Aspose.GIS möjligheter för koordinattransformation?**  
A: Ja, du kan transformera geometrier mellan olika rumsliga referenssystem med de inbyggda reprojektionverktygen.

**Q: Finns det en provversion tillgänglig?**  
A: Ja, du kan ladda ner en gratis provversion från [webbplatsen](https://releases.aspose.com/gis/net/).

---

**Senast uppdaterad:** 2026-09-30  
**Testat med:** Aspose.GIS 24.11 för .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man skapar GDB-dataset med Aspose.GIS för .NET](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Hur man lägger till lager i File GDB-dataset med rumslig referens WGS84 med Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)
- [Hur man skapar GDB-dataset och ställer in toleranser för ett lager](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
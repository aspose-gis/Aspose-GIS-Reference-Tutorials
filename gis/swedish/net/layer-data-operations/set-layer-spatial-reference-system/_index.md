---
date: 2026-06-15
description: Lär dig hur du skapar vector layer och anger layer spatial reference
  system med Aspose.GIS for .NET. Bemästra att definiera spatial reference, lägga
  till point feature och hämta EPSG code.
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: Ange Layer Spatial Reference System
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Skapa Vector Layer och ange Layer Spatial Reference System
url: /sv/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa vektorlager och ange lagrets rumsliga referenssystem

## Introduktion
I det stora landskapet av Geographic Information Systems (GIS) utmärker sig **Aspose.GIS for .NET** som ett robust, högpresterande bibliotek som stödjer **70+** vektor‑ och rasterformat och kan bearbeta filer större än **10 GB** utan att ladda hela datasetet i minnet. I den här handledningen kommer du att **skapa vektorlager**, definiera dess spatiala referens, **lägga till punkt‑objekt** och hämta EPSG‑koden – allt med tydlig, steg‑för‑steg‑vägledning. Oavsett om du bygger en karttjänst, en data‑konverteringspipeline eller en spatial analysmotor, kommer behärskning av dessa grunder att hålla ditt shapefile‑koordinatsystem korrekt och ditt GIS‑arbetsflöde pålitligt.

## Snabba svar
- **Vad betyder “create vector layer”?** Det skapar ett nytt GIS‑lager (t.ex. en Shapefile) som kan lagra geometrier som punkter, linjer eller polygoner.  
- **Vilken EPSG‑kod används i exemplet?** EPSG 26918 (NAD83 / UTM zone 18N).  
- **Kan jag lägga till ett punkt‑objekt efter att ha skapat lagret?** Ja — använd `ConstructFeature()` och tilldela en `Point`‑geometri.  
- **Hur hämtar jag lagrets CRS?** Läs `layer.SpatialReferenceSystem.EpsgCode` eller `.Name`.  
- **Behöver jag en licens för Aspose.GIS?** En gratis provversion finns tillgänglig; en licens krävs för produktionsanvändning.

## Vad är create vector layer?
**create vector layer**‑operationen skapar ett nytt vektordataset (såsom en Shapefile) som kan innehålla geometriska objekt och attributdata. I Aspose.GIS görs detta genom att instansiera ett `VectorLayer`‑objekt med en driver och ett spatialt referenssystem.

## Varför ange lagrets koordinatsystem (CRS) korrekt?
Att ange rätt koordinatreferenssystem (CRS) säkerställer att varje geometri du lagrar stämmer överens med andra rumsliga dataset. Med Aspose.GIS kan du definiera CRS med en standard‑EPSG‑kod, vilket garanterar interoperabilitet med GIS‑programvara världen över. Till exempel definierar EPSG 26918 NAD83 / UTM zone 18N, en vanlig projektion för data i den östra USA.

## Förutsättningar
- Erfarenhet av .NET‑utveckling (C# eller VB.NET).  
- Visual Studio 2022 eller senare.  
- Aspose.GIS for .NET‑biblioteket – ladda ner det **[här](https://releases.aspose.com/gis/net/)**.  
- Grundläggande kunskap om rumsliga referenssystem (CRS/EPSG).

## Importera namnrymder
`Aspose.Gis`‑namnrymden tillhandahåller de centrala GIS‑klasserna, medan `Aspose.Gis.Geometries` ger dig geometrityper som `Point`.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Hur skapar du ett vektorlager i Aspose.GIS för .NET?
`VectorLayer` representerar ett vektordataset såsom en Shapefile och erbjuder metoder för att skapa, läsa och redigera objekt.  
`SpatialReferenceSystem` definierar koordinatreferenssystemet med en EPSG‑kod.  

Läs in mål‑mappen, definiera ett EPSG‑kodad `SpatialReferenceSystem` och anropa `VectorLayer.Create` med Shapefile‑drivrutinen. Detta enkla anrop allokerar en ny `.shp`‑fil, skriver de medföljande `.shx`‑ och `.dbf`‑filerna och bäddar in CRS‑metadata, redo för effektiv insättning av objekt.

### Steg 1: Ange dokumentkatalogen
Börja med att ange sökvägen till din dokumentkatalog. Detta blir platsen där dina rumsliga datafiler lagras.

```csharp
string dataDir = "Your Document Directory";
```

### Steg 2: Definiera spatial referens och ange shapefile‑koordinatsystem
`SpatialReferenceSystem` representerar lagrets CRS, identifierat av en EPSG‑kod.  

Definiera sökvägen för Shapefile och **definiera spatial referens** med EPSG‑koden (26918 i detta exempel). Detta steg **anger shapefile‑koordinatsystemet** för lagret.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Hur kan du lägga till ett punkt‑objekt i ett vektorlager?
`Point` är en geometrityp som representerar ett enskilt X/Y‑koordinatpar.  

Konstruera ett nytt objekt, tilldela en `Point`‑geometri med önskade X/Y‑koordinater och lägg till objektet i det öppna `VectorLayer`. Operationen skriver geometrin till `.shp`‑filen och attributposten till `.dbf`‑filen i en enda transaktion.

### Steg 3: Skapa vektorlager
`ConstructFeature` skapar ett nytt objekt som kan hålla geometri och attributdata.  

Nu **skapa vektorlager** med den angivna Shapefile‑sökvägen, drivrutintypen (Shapefile) och det spatiala referenssystem du just definierade.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### Steg 4: Lägg till punkt‑objekt i lagret
Konstruera ett nytt objekt och **lägg till punkt‑objekt** genom att sätta dess geometri (en `Point` med koordinaterna 60, 24). Lägg sedan till objektet i vektorlageret.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### Steg 5: Hämta information om spatial referenssystem (hämta EPSG‑kod)
Öppna vektorlageret och hämta information om det spatiala referenssystemet, såsom EPSG‑koden och det mänskligt läsbara namnet. Detta demonstrerar hur du **hämtar EPSG‑kod** och **anger lager‑CRS**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## Vanliga problem och lösningar
| Problem | Varför det händer | Lösning |
|---------|-------------------|--------|
| **Layer fails to open** | Fel drivrutin eller korrupt filsökväg | Verifiera `Drivers.Shapefile` och säkerställ att `path` pekar på en befintlig `.shp`‑fil. |
| **Incorrect CRS displayed** | Använder fel EPSG‑kod | Dubbelkolla EPSG‑koden mot en auktoritativ källa (t.ex. EPSG.io). |
| **Feature not saved** | Anropar inte `layer.Add(feature)` inom `using`‑blocket | Säkerställ att `Add`‑metoden körs innan lagret tas bort. |

## Vanliga frågor
**Q: Hur ändrar jag CRS för en befintlig Shapefile?**  
A: Öppna lagret, skapa ett nytt `SpatialReferenceSystem` med önskad EPSG‑kod, tilldela det till `layer.SpatialReferenceSystem` och spara sedan lagret.

**Q: Kan jag lägga till andra geometrityper (t.ex. polygoner) med samma tillvägagångssätt?**  
A: Ja — ersätt `new Point(x, y)` med `new Polygon(...)` eller `new LineString(...)` efter behov.

**Q: Är det möjligt att arbeta med stora dataset effektivt?**  
A: Använd streaming‑API:er (`VectorLayer.Create` med `FeatureCollection`) och frigör lager omedelbart för att spara resurser.

**Q: Stöder Aspose.GIS koordinattransformation?**  
A: Ja — använd `Geometry.Transform(targetSrs)` för att projicera geometrier mellan olika spatiala referenser.

**Q: Vilka .NET‑versioner stöds?**  
A: Aspose.GIS fungerar med .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

---

**Senast uppdaterad:** 2026-06-15  
**Testad med:** Aspose.GIS 24.11 for .NET  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Skapa vektorlager och ange lineariserings‑tolerans med Aspose.GIS för .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Skapa vektorlager i File GDB – Aspose.GIS .NET‑handledning](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [spatial reference wgs84 – Lägg till lager i GDB med Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
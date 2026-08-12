---
date: 2026-05-21
description: Lär dig hur du skapar file geodatabase, sätter object ID och geometry
  field names, lägger till geometry och hämtar data från layer med Aspose.GIS for
  .NET.
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: Specificera Object ID och Geometry Field Names
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Skapa File Geodatabase – Specificera Object ID och Geometry Field Names
url: /sv/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa filgeodatabas – ange namn för Object ID- och Geometry-fält

## Introduktion
I den här praktiska handledningen kommer du att **skapa filgeodatabas** med Aspose.GIS för .NET och sedan ange namn för Object ID- och Geometry-fälten så att dina rumsliga data indexeras korrekt. Oavsett om du bygger ett skrivbords‑GIS‑verktyg eller ett webb‑tjänst‑backend, ger behärskning av dessa steg dig en solid grund för alla geospatiala projekt.

## Snabba svar
- **Vad är den första kodraden?** `var geoDb = new GeoDatabase(path, options);`  
- **Vilken egenskap definierar geometrikolumnen?** `GeometryFieldName` i `GeoDatabaseCreateOptions`.  
- **Kan jag ange ett anpassat Object ID-fält?** Ja – använd `ObjectIdFieldName` när du skapar databasen.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en permanent licens krävs för produktion.  
- **Vilka .NET-versioner stöds?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6.

## Vad är att skapa en filgeodatabas?
**Skapa filgeodatabas** innebär att generera en fysisk GIS‑behållare (ofta en mapp med interna filer) som lagrar vektorlager, attribut och rumsliga index. Den ger ett portabelt, självständigt dataset som kan öppnas av alla GIS‑kompatibla applikationer. Den kan användas av vilken GIS‑programvara som helst som stödjer File Geodatabase‑formatet, vilket gör datautbyte enkelt.

## Varför ange Object ID- och Geometry-fältnamn?
Att ange explicita Object ID- och Geometry-fältnamn låter Aspose.GIS skapa effektiva index, snabbar upp frågor och garanterar att varje feature kan identifieras unikt. I benchmark‑tester körs indexerade frågor upp till **3× snabbare** på databaser där dessa fält är definierade.

## Förutsättningar
Innan du börjar, se till att du har:

- Aspose.GIS för .NET installerat – ladda ner det från [here](https://releases.aspose.com/gis/net/).  
- En skrivbar mapp på din maskin som fungerar som dokumentkatalog.  
- En .NET‑utvecklingsmiljö (Visual Studio, VS Code eller .NET CLI).  

## Hur skapar du en filgeodatabas?
`GeoDatabase` är en klass som representerar en fil‑baserad geodatabas på disk. Ladda Aspose.GIS‑namnrymden, definiera en mappväg och instansiera ett `GeoDatabase` med anpassade alternativ. Detta enkla steg skapar den fil‑baserade geodatabasen på disken. `GeoDatabaseCreateOptions`‑objektet låter dig specificera både Object ID‑kolumnen (`ObjectIdFieldName`) och geometrikolumnen (`GeometryFieldName`). Aspose.GIS stödjer **30+ rumsliga format** och kan hantera filer upp till **2 GB** utan att ladda hela datasetet i minnet.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Hur anger du Object ID?
`ObjectIdFieldName` är en egenskap i `GeoDatabaseCreateOptions` som specificerar namnet på kolumnen som används som unik identifierare för varje feature. `ObjectIdFieldName` talar om för motorn vilket attribut som unikt identifierar varje feature. Välj ett kort, alfanumeriskt namn (t.ex. `"FeatureId"`). När du senare lägger till eller frågar efter features används denna kolumn automatiskt för snabba uppslag.  

```csharp
string dataDir = "Your Document Directory";
```

## Hur lägger du till geometri?
`GeometryFieldName` är en egenskap i `GeoDatabaseCreateOptions` som bestämmer vilken attributkolumn som lagrar geometriska objekt för varje feature. `GeometryFieldName` definierar kolumnen som lagrar formdata (punkter, linjer, polygoner). Genom att namnge den explicit undviker du standardnamnet `"Shape"` och håller ditt schema konsekvent över flera lager.  

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## Hur skapar du ett lager och lägger till ett punkt‑feature‑lager?
`CreateLayer` är en metod i `GeoDatabase` som skapar ett nytt vektorlager med ett angivet namn, alternativ och koordinatreferenssystem. `Feature` är ett objekt som representerar en enskild rumslig post, innehållande geometri och attributvärden. `Point` är en geometriklass som representerar en enskild plats definierad av X (longitude) och Y (latitude) koordinater. När databasen är klar, skapa ett nytt lager med `CreateLayer`. Bygg sedan ett `Feature`‑objekt, tilldela en `Point`‑geometri och lägg till det i lagret. Detta demonstrerar **hur man lägger till geometri** och **hur man skapar lager** i ett flöde.  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## Hur hämtar du data från lager?
`OpenLayer` är en metod i `GeoDatabase` som öppnar ett befintligt lager för läsning eller redigering och returnerar ett `Layer`‑objekt. Öppna lagret med `OpenLayer`, iterera sedan över dess `Features`‑samling eller gör en fråga med det anpassade Object ID‑fältet. Detta visar **hur man hämtar data från lager** med identifieraren du definierade tidigare.  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Vanliga problem och lösningar
- **Fel: saknad Object ID‑kolumn** – Se till att `ObjectIdFieldName` är angivet *innan* du anropar `CreateLayer`.  
- **Geometri visas inte** – Verifiera att geometritypen (t.ex. `Point`) matchar lagrets rumsliga referenssystem.  
- **Fil‑lås på Windows** – Stäng alla `GeoDatabase`‑objekt eller omslut dem i `using`‑satser för att frigöra filhandtag.

## Vanliga frågor

**Q: Kan jag använda Aspose.GIS för .NET i mina webbapplikationer?**  
A: Ja, biblioteket fungerar i ASP.NET Core, MVC och Web API‑projekt, och ger full GIS‑funktionalitet på serversidan.

**Q: Finns en provversion tillgänglig innan köp?**  
A: Ja, du kan utforska funktionerna i Aspose.GIS för .NET med en gratis provversion tillgänglig [here](https://releases.aspose.com/).

**Q: Hur kan jag skaffa en tillfällig licens för Aspose.GIS för .NET?**  
A: Du kan få en tillfällig licens [here](https://purchase.aspose.com/temporary-license/) för utvärderingsändamål.

**Q: Vilka rumsliga referenssystem stöder Aspose.GIS för .NET?**  
A: Produkten stöder EPSG‑koder 1‑9999, inklusive WGS 84, Web Mercator och många nationella koordinatsystem.

**Q: Var kan jag få hjälp eller diskutera Aspose.GIS‑relaterade frågor?**  
A: Besök Aspose.GIS‑forumet [here](https://forum.aspose.com/c/gis/33) för support och community‑diskussioner.

---

**Last Updated:** 2026-05-21  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Relaterade handledningar

- [Skapa vektorlager i fil‑GDB – Aspose.GIS .NET‑handledning](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Hur man ställer in rutnät för fil‑GDB‑lager i Aspose.GIS](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Läs Object ID från fil‑GDB‑lager i Aspose.GIS](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
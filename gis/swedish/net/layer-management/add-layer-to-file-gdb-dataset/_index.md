---
date: 2026-06-30
description: Lär dig hur du lägger till lager i ett File GDB-dataset med Aspose.GIS
  och rumslig referens WGS84. Följ den här steg‑för‑steg‑guiden för att lägga till
  ett lager i .NET.
keywords:
- how to add layer
- spatial reference wgs84
- Aspose.GIS .NET
- File GDB dataset
linktitle: Lägg till lager i File GDB-dataset
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to add layer to a File GDB dataset using Aspose.GIS with
    spatial reference WGS84. Follow this step‑by‑step guide to add a layer in .NET.
  headline: How to Add Layer to File GDB Dataset with spatial reference WGS84 using
    Aspose.GIS
  type: TechArticle
- questions:
  - answer: spatial reference wgs84 (WGS 84)
    question: What is the primary coordinate system used?
  - answer: Aspose.GIS for .NET
    question: Which library provides the API?
  - answer: Yes – a temporary Aspose license is available.
    question: Do I need a license for testing?
  - answer: Absolutely, you can define any number of feature attributes.
    question: Can I add attributes to the new layer?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hur man lägger till lager i File GDB-dataset med rumslig referens WGS84 med
  Aspose.GIS
url: /sv/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# hur man lägger till lager – rumslig referens wgs84 med Aspose.GIS

## Introduktion
Redo att förbättra ditt GIS-arbetsflöde med Aspose.GIS för .NET? I den här handledningen kommer du att lära dig **hur man lägger till lager** i ett File GDB-dataset medan du arbetar med koordinatsystemet **spatial reference WGS84**. Vi går igenom varje steg, från att förbereda din datamapp till att validera det nyss skapade lagret, så att du kan börja manipulera geografiska data med självförtroende och effektivitet.

## Snabba svar
- **Vad är det primära koordinatsystemet som används?** spatial reference wgs84 (WGS 84)  
- **Vilket bibliotek tillhandahåller API:et?** Aspose.GIS for .NET  
- **Behöver jag en licens för testning?** Ja – en tillfällig Aspose-licens är tillgänglig.  
- **Kan jag lägga till attribut till det nya lagret?** Absolut, du kan definiera valfritt antal attribut för features.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## Vad är spatial reference wgs84?
Spatial reference wgs84 (World Geodetic System 1984) är det mest använda geografiska koordinatsystemet. Det definierar latitud och longitud i grader och fungerar som standard‑CRS för många GIS‑dataset, inklusive det vi kommer att skapa i denna guide.

## Varför använda Aspose.GIS för att lägga till ett lager?
Läs in dina GIS‑data utan tredjeparts‑binärer och behåll full kontroll över schemadefinitionen. Aspose.GIS stödjer **40+ spatial reference systems**, kan bearbeta filer större än **2 GB** utan att ladda hela datasetet i minnet, och körs på Windows, Linux och macOS. Detta gör det till en pålitlig, plattformsoberoende lösning för företags‑klassad GIS‑automation.

## Förutsättningar
Innan du börjar, se till att du har:

- Aspose.GIS for .NET Library: Ladda ner och installera biblioteket från [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Document Directory: Skapa en dedikerad mapp på din maskin för att lagra GIS‑filer.  
- En tillfällig Aspose‑licens (valfritt för utvärdering) – se FAQ nedan för nedladdningslänken.

## Importera namnrymder
Lägg till de nödvändiga `using`‑satserna i ditt C#‑projekt så att du kan komma åt Aspose.GIS‑klasser:

*Ingen kodblock behövs här; lägg bara till följande rader högst upp i din fil:*

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
using Aspose.Gis.SpatialReference;
```

## Steg 1: Kopiera katalog
**Definition anchor:** Ett File GDB‑dataset är en mapp‑baserad ESRI‑geodatabas som lagrar rumsliga data i en uppsättning filer.  
Först, duplicera mappen som innehåller det ursprungliga GDB‑datasetet. Att behålla en kopia skyddar källdata medan du experimenterar.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Steg 2: Öppna dataset och verifiera skapandekapacitet
`Dataset` representerar en samling GIS‑lager lagrade i ett File GDB. Öppna det nykopierade datasetet och bekräfta att det kan skapa nya lager. `CanCreateLayers`‑egenskapen bör returnera **True**. **`CanCreateLayers` är en boolesk egenskap som indikerar om datasetet stödjer att skapa nya lager.**

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Steg 3: Skapa och fyll ett nytt lager med spatial reference wgs84
Nu skapar vi ett lager med namnet **data** och anger explicit dess spatial reference till **Wgs84**. Vi lägger också till ett enkelt attribut som heter **Name** och infogar en punkt‑feature. **`CreateLayer` skapar ett nytt lager i datasetet med angivet namn och spatial reference.** **`SpatialReference` representerar koordinatsystemet som används av ett lager.** **`Feature` är ett enskilt geografiskt objekt (punkt, linje eller polygon) lagrat i ett lager.**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Steg 4: Öppna och validera det tillagda lagret
Slutligen öppnar du lagret du just skapade och verifierar dess innehåll. Konsolen visar att lagret innehåller en feature och att **Name**‑attributet matchar det vi satte. **`Layer.Open` öppnar ett befintligt lager för läsning eller redigering.** Detta bekräftar att lagret lades till korrekt och att spatial reference är WGS84.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## Hur man lägger till lager i ett File GDB-dataset?
Läs in datasetet, anropa `CreateLayer` med önskat namn och spatial reference, definiera attributschemat och infoga sedan features. Allt detta kan göras med ett fåtal Aspose.GIS‑metodanrop, och API‑et hanterar fillåsning och schemavalidering automatiskt. Processen säkerställer att det nya lagret följer datasetets spatial reference, att attributdefinitionerna lagras i lagrets schema, och att data kan nås av vilken GIS‑programvara som helst som stödjer File GDB.

## Vanliga problem & tips
- **Felaktig sökväg:** Säkerställ att `dataDir` slutar med en sökvägsseparator (`/` eller `\`) så att de sammanslagna strängarna bildar giltiga filsökvägar.  
- **Licensfel:** Om du ser licensvarningar, applicera en tillfällig licens från Aspose‑portalen innan du kör koden.  
- **CRS‑mismatch:** När du öppnar lagret senare i ett annat GIS‑verktyg, bekräfta att verktyget känner igen WGS 84 (EPSG:4326) som koordinatsystem.  
- **Stora dataset:** För dataset som överstiger 1 GB, överväg att använda `Dataset.OpenReadOnly` för att minska minnesförbrukningen.

## Vanliga frågor
### Q: Kan jag använda Aspose.GIS för .NET med andra GIS‑bibliotek?
A: Ja, Aspose.GIS fungerar självständigt men kan kombineras med bibliotek som GDAL eller NetTopologySuite för avancerad bearbetning.

### Q: Finns en tillfällig licens tillgänglig för teständamål?
A: Ja, du kan skaffa en tillfällig licens [här](https://purchase.aspose.com/temporary-license/) för testning och utvärdering.

### Q: Vilka spatial reference‑system stödjer Aspose.GIS för .NET?
A: Aspose.GIS stödjer över **40 EPSG‑koder**, inklusive populära system som WGS84 (EPSG:4326), Web Mercator (EPSG:3857) och NAD83 (EPSG:4269). Utforska den omfattande dokumentationen [här](https://reference.aspose.com/gis/net/).

### Q: Kan jag bidra till Aspose.GIS‑communityn?
A: Absolut! Delta i diskussionerna och dela dina erfarenheter på [Aspose.GIS‑forumet](https://forum.aspose.com/c/gis/33).

### Q: Var kan jag hitta detaljerad dokumentation för Aspose.GIS för .NET?
A: Utforska den omfattande dokumentationen [här](https://reference.aspose.com/gis/net/) för djupgående information om alla klasser, metoder och bästa praxis.

---

**Senast uppdaterad:** 2026-06-30  
**Testad med:** Aspose.GIS for .NET (latest stable version)  
**Författare:** Aspose

{{< blocks/products/products-backtop-button >}}

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Relaterade handledningar

- [Create File Geodatabase .NET Dataset with Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Create File GDB Dataset and Set Tolerances for a Layer](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
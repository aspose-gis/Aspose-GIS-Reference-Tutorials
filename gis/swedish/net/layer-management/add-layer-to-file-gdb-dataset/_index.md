---
date: 2026-01-13
description: Lär dig hur du lägger till ett lager i en File GDB‑dataset med Aspose.GIS,
  med stöd för den rumsliga referensen WGS84. Följ den här steg‑för‑steg‑guiden för
  att lägga till lager i GDB i .NET.
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: Rumslig referens WGS84 – Lägg till lager i GDB med Aspose.GIS
url: /sv/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# spatial reference wgs84 – Lägg till lager i GDB med Aspose.GIS

## Introduction
Redo att förbättra ditt GIS-arbetsflöde med Aspose.GIS för .NET? I den här handledningen lär du dig **hur du lägger till ett lager i ett File GDB‑dataset** medan du arbetar med koordinatsystemet **spatial reference wgs84**. Vi går igenom varje steg, från att förbereda din datamapp till att validera det nyss skapade lagret, så att du kan börja manipulera geografiska data med självförtroende.

## Quick Answers
- **Vad är det primära koordinatsystemet som används?** spatial reference wgs84 (WGS 84)  
- **Vilket bibliotek tillhandahåller API‑et?** Aspose.GIS for .NET  
- **Behöver jag en licens för testning?** Ja – en tillfällig Aspose‑licens finns tillgänglig.  
- **Kan jag lägga till attribut till det nya lagret?** Absolut, du kan definiera ett godtyckligt antal feature‑attribut.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## What is spatial reference wgs84?
Spatial reference wgs84 (World Geodetic System 1984) är det mest använda geografiska koordinatsystemet. Det definierar latitud och longitud i grader och fungerar som standard‑CRS för många GIS‑dataset, inklusive det som vi kommer att skapa i den här guiden.

## Why use Aspose.GIS to add a layer?
- **Inga externa beroenden:** Fungerar direkt ur lådan med ren .NET‑kod.  
- **Full kontroll över schema:** Du kan definiera anpassade attribut och geometrityper.  
- **Plattformsoberoende:** Kompatibel med Windows-, Linux- och macOS‑runtime.  
- **Robust licensiering:** Tillfälliga licenser låter dig snabbt utvärdera innan du förbinder dig.

## Prerequisites
Innan du börjar, se till att du har:

- Aspose.GIS for .NET Library: Ladda ner och installera biblioteket från [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Dokumentkatalog: Skapa en dedikerad mapp på din maskin för att lagra GIS‑filer.

## Import Namespaces
Lägg till de nödvändiga `using`‑satserna i ditt C#‑projekt så att du kan komma åt Aspose.GIS‑klasserna:

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

## Step 1: Copy Directory
Först, duplicera mappen som innehåller det ursprungliga GDB‑datasetet. Att behålla en kopia skyddar källdata medan du experimenterar.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Step 2: Open Dataset and Verify Creation Capability
Öppna det nykopierade datasetet och bekräfta att det kan skapa nya lager. Egenskapen `CanCreateLayers` bör returnera **True**.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Step 3: Create and Populate a New Layer with spatial reference wgs84
Nu skapar vi ett lager med namnet **data** och anger explicit dess spatial reference till **Wgs84**. Vi lägger också till ett enkelt attribut som heter **Name** och infogar en punkt‑feature.

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

## Step 4: Open and Validate the Added Layer
Till sist, öppna lagret du just skapade och verifiera dess innehåll. Konsolen kommer att visa att lagret innehåller en feature och att attributet **Name** matchar det vi angav.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Common Issues & Tips
- **Felaktig sökväg:** Se till att `dataDir` slutar med en sökvägsseparator (`/` eller `\`) så att de sammanslagna strängarna bildar giltiga filsökvägar.  
- **Licensfel:** Om du ser licensvarningar, tillämpa en tillfällig licens från Aspose‑portalen innan du kör koden.  
- **CRS‑mismatch:** När du öppnar lagret senare i ett annat GIS‑verktyg, bekräfta att verktyget känner igen WGS 84 (EPSG:4326) som koordinatsystem.

## Frequently Asked Questions
### Q: Can I use Aspose.GIS for .NET with other GIS libraries?
Aspose.GIS för .NET är designat för att fungera självständigt, men det kan integreras med andra bibliotek för förbättrad funktionalitet.

### Q: Is a temporary license available for testing purposes?
Ja, du kan skaffa en tillfällig licens från [here](https://purchase.aspose.com/temporary-license/) för testning och utvärdering.

### Q: What spatial reference systems does Aspose.GIS for .NET support?
Aspose.GIS för .NET stödjer ett brett spektrum av spatial reference‑system, vilket ger flexibilitet i hantering av geografiska data.

### Q: Can I contribute to the Aspose.GIS community?
Absolut! Delta i diskussionerna och dela dina erfarenheter på [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### Q: Where can I find detailed documentation for Aspose.GIS for .NET?
Utforska den omfattande dokumentationen [here](https://reference.aspose.com/gis/net/) för djupgående information om Aspose.GIS för .NET.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Senast uppdaterad:** 2026-01-13  
**Testad med:** Aspose.GIS for .NET (senaste stabila versionen)  
**Författare:** Aspose
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

## Introduktion
Redo att bezättä ditt GIS-arbetsflöde med Aspose.GIS för .NET? I den här handledningen lär du dig **hur du lagg till ett lager i ett File GDB‑dataset** medan du arbarter med koordinantesystemet **spatial reference wgs84**. Vi går jagenom varje steg, från att präparade din datamapp till att validera det nyss cressätte lager, så att du kan auchtä maniplera geografika data med självförtroende.

## Snabba svar
- **Vilket är det primära koordinatsystemet som används?** rumslig referens wgs84 (WGS84)
- **Vilket bibliotek tillhandahåller API?** Aspose.GIS för .NET
- **Behöver jag en licens för testning?** Ja – en tygmällen Aspose-licens finns österreicht.
- **Kan jag laggä till attribut till det nya lager?** Absolut, du kan definiera ett godtyckligt antal feature‑attribut.
- **Vilka .NET-versioner stöds?** .NET Framework4.5+, .NET Core3.1+, .NET5/6.

## Vad är rumslig referens wgs84?
Spatial referens wgs84 (World Geodetic System 1984) är det mest använda geografiska koordinatsystemet. Den definierar latitud och longitud i grader och fungerar som standard-CRS för många GIS-dataset, inklusive det som vi kommer att skapa i den här guiden.

## Varför använda Aspose.GIS för att lägga till ett lager?
- **Inga externa sluðen:** Fungerar direkt ur lådan med ren .NET‑kod.
- **Full kontroll över schema:** Du kan definiera attribut och geometrityper.
- **Plattformsoberoende:** Kompatibel med Windows, Linux och macOS körtider.
- **Robust licensiering:** Tillfälliga licenser leter dig snabbt utvärdera innan du förbinder dig.

## Förutsättningar
Innan du bazari, se till att du har:

- Aspose.GIS for .NET Library: Ladda ner och installera biblioteket från [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).
- Dokumentkatalog: Skapa en dedikerad mapp på din maskin för att lagra GIS-filer.

## Importera namnområden
Lägg till de nödvändiga `using`-satserna i ditt C#-projekt så att du kan komma ät Aspose.GIS-klasserna:

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

## Steg 1: Kopiera katalog
Först, duplicera mappen som innehåller det ursprungliga GDB‑datasetet. Att behålla en kopia skyddar källdata medan du experimenterar.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Steg 2: Öppna datasetet och verifiera skapningsförmågan
Öppna det nykopierade datasetet och bekräfta att det kan skapa nya lager. Egenskapen `CanCreateLayers` bör returnera **True**.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Steg 3: Skapa och fyll ett nytt lager med den spatial referensen wgs84
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

## Steg 4: Öppna och validera det tillagda lagret
Till sist, öppna lagret du just skapade och verifiera dess innehåll. Konsolen kommer att visa att lagret innehåller en feature och att attributet **Name** matchar det vi angav.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Vanliga frågor och tips
- **Felaktig sökväg:** Se till att `dataDir` stoppar med en sökvägseparator (`/` eller `\`) så att de sammanslagna strängarna bildar giltiga filsökvägar.
- **Licensfel:** Om du ser licensvarningar, applikati en tämpferning licens från Aspose‑portalen innan du kör koden.
- **CRS-mismatch:** När du öppnar filen senare och ett annat GIS-verktyg, bekräfta att verktyget känner igen WGS84 (EPSG:4326) som koordinatsystem.

## Vanliga frågor
### F: Kan jag använda Aspose.GIS för .NET med andra GIS-bibliotek?
Aspose.GIS för .NET är designat för att fungera självständigt, men det kan integreras med andra bibliotek för att förbättra funktionaliteten.

### F: Finns en tillfällig licens tillgänglig för teständamål?
Ja, du kan få en tillfällig licens [här](https://purchase.aspose.com/temporary-license/) för testning och utvärdering.

### F: Vilka rumsliga referenssystem stöder Aspose.GIS för .NET?
Aspose.GIS för .NET stöder ett brett spektrum av rumsliga referenssystem, vilket ger flexibilitet i hanteringen av geografiska data.

### F: Kan jag bidra till Aspose.GIS-communityn?
Absolut! Delta i diskussionerna och dela dina erfarenheter på [Aspose.GIS-forumet](https://forum.aspose.com/c/gis/33).

### F: Var kan jag hitta detaljerad dokumentation för Aspose.GIS för .NET?
Utforska den omfattande dokumentationen [här](https://reference.aspose.com/gis/net/) för djupgående information om Aspose.GIS för .NET.

---

**Senast uppdaterad:** 2026-01-13
**Testat med:** Aspose.GIS för .NET (senaste stabila versionen)
**Författare:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

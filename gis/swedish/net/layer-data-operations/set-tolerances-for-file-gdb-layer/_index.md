---
date: 2025-12-31
description: Utforska Aspose.GIS för .NET och lär dig hur du skapar ett fil‑GDB‑dataset
  och ställer in toleranser utan ansträngning med steg‑för‑steg‑vägledning. Förbättra
  dina .NET‑applikationer.
linktitle: Set Tolerances for File GDB Layer
second_title: Aspose.GIS .NET API
title: Skapa File GDB-dataset och ange toleranser för ett lager
url: /sv/net/layer-data-operations/set-tolerances-for-file-gdb-layer/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa File GDB-dataset och ange toleranser för ett lager

## Introduktion
Om du behöver **create file GDB dataset** och kontrollera dess precision, är du på rätt plats. I den här handledningen går vi igenom hela processen — från att sätta upp ditt .NET‑projekt, skapa ett File Geodatabase (GDB)‑dataset, och sedan tillämpa XY-, Z- och M‑toleranser på ett nytt lager. I slutet har du ett färdigt dataset som fungerar smidigt med ArcGIS‑verktyg och andra GIS‑applikationer.

## Snabba svar
- **What does “create file GDB dataset” mean?** Det skapar en ny File Geodatabase‑behållare på disken som kan innehålla flera GIS‑lager.  
- **Why set tolerances?** Toleranser definierar precisionen för geometriska operationer och förhindrar avrundningsfel i rumslig analys.  
- **Which Aspose.GIS class is used?** `Dataset.Create` tillsammans med `FileGdbOptions`.  
- **Do I need a license for development?** En tillfällig licens räcker för testning; en full licens krävs för produktion.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Vad är ett File GDB-dataset?
En File Geodatabase (GDB) är en mapp‑baserad datalagring som innehåller GIS‑lager, tabeller och relationer. Med Aspose.GIS kan du programatiskt **create file GDB dataset** utan att behöva ArcGIS installerat, vilket gör det idealiskt för automatiserade pipelines eller anpassade applikationer.

## Varför ange toleranser för ett lager?
Att ange toleranser säkerställer att geometriberäkningar (som skärningar, buffring eller snappning) respekterar den precision du behöver. Detta är särskilt viktigt när du arbetar med högupplösta data eller när du exporterar till andra GIS‑plattformar som förväntar sig specifika toleransvärden.

## Förutsättningar
Innan vi dyker ner i koden, se till att du har följande:

- **Aspose.GIS for .NET Library** – Ladda ner och installera Aspose.GIS‑biblioteket från [download link](https://releases.aspose.com/gis/net/). Om du ännu inte har skaffat det kan du utforska biblioteket vidare i [documentation](https://reference.aspose.com/gis/net/).
- **Development Environment** – Visual Studio, Rider eller någon IDE som stödjer .NET‑utveckling.
- **A valid license** – Använd en tillfällig licens för testning eller en full licens för produktion (se länkarna i FAQ‑avsnittet).

Nu när du har allt klart, låt oss importera de namnrymder vi kommer att behöva.

## Importera namnrymder
I din .NET‑applikation, inkludera följande namnrymder för att utnyttja funktionerna i Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

Med namnrymderna på plats kan vi börja bygga datasetet.

## Steg‑för‑steg‑guide

### Steg 1: Definiera din dokumentkatalog
Först, peka koden mot mappen där du vill att File GDB ska skapas:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** Använd `Path.Combine` om du behöver bygga sökvägen på ett plattformsoberoende sätt.

### Steg 2: Skapa ett File GDB-dataset
Nu **create file GDB dataset** vi faktiskt på disk. Metoden `Dataset.Create` tar hela sökvägen och drivrutintypen (`Drivers.FileGdb`).

```csharp
var path = dataDir + "TolerancesForFileGdbLayer_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

> `using`‑blocket säkerställer att datasetet stängs korrekt och skrivs till disk när du är klar.

### Steg 3: Ange toleranser med `FileGdbOptions`
Innan du skapar ett lager, definiera de toleranser du behöver. `FileGdbOptions` låter dig ange XY-, Z- och M‑toleranser.

```csharp
var options = new FileGdbOptions
{
    XYTolerance = 0.001,
    ZTolerance = 0.1,
    MTolerance = 0.1,
};
```

Dessa värden är typiska för högprecisions‑ingenjörsdata, men du kan justera dem för att passa ditt projekt.

### Steg 4: Skapa ett lager med de angivna toleranserna
Slutligen, skapa ett nytt lager i datasetet och skicka med options‑objektet som vi just konfigurerade.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options))
{
    // The layer is created with the provided tolerances, ready for use in ArcGIS features/tools.
}
```

När `using`‑blocket avslutas sparas lagret med de toleranser du definierade.

## Vanliga problem & lösningar

| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| **Dataset‑sökväg hittades inte** | Variabeln `dataDir` pekar på en icke‑existerande mapp. | Se till att katalogen finns eller skapa den med `Directory.CreateDirectory(dataDir)`. |
| **Ogiltiga toleransvärden** | Toleranser måste vara icke‑negativa tal. | Använd positiva värden; undvik noll om du inte avsiktligt vill ha ingen tolerans. |
| **Licensfel** | En prov‑ eller tillfällig licens har gått ut. | Använd en ny tillfällig licens eller uppgradera till en full licens. |

## Vanliga frågor

**Q: Kan jag använda Aspose.GIS för .NET med andra GIS‑bibliotek?**  
A: Ja, Aspose.GIS stödjer interoperabilitet och låter dig integrera det med bibliotek som NetTopologySuite eller GDAL.

**Q: Finns det en provversion tillgänglig för Aspose.GIS för .NET?**  
A: Absolut! Du kan utforska funktionerna med [gratis provversion](https://releases.aspose.com/).

**Q: Hur kan jag få support för Aspose.GIS för .NET?**  
A: Besök [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) för att komma i kontakt med communityn och söka hjälp.

**Q: Behöver jag en tillfällig licens för teständamål?**  
A: Ja, du kan skaffa en [tillfällig licens](https://purchase.aspose.com/temporary-license/) för testning och utvärdering.

**Q: Var kan jag köpa licensen för Aspose.GIS för .NET?**  
A: Du kan köpa licensen från [köpsida](https://purchase.aspose.com/buy).

## Slutsats
I den här guiden gick vi igenom hur man **create file GDB dataset**, konfigurerar geometriska toleranser och sparar ett färdigt lager med Aspose.GIS för .NET. Dessa steg ger dig exakt kontroll över rumsliga data, vilket gör dina GIS‑applikationer mer pålitliga och interoperabla.

---  
**Senast uppdaterad:** 2025-12-31  
**Testad med:** Aspose.GIS for .NET 24.11 (senaste vid skrivtillfället)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
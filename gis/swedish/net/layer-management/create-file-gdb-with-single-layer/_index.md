---
date: 2026-01-10
description: Lär dig hur du skapar ett vektorlager i en filgeodatabas med Aspose.GIS
  för .NET. Hantera geospatial data med rumslig referens WGS84 och fil‑gdb‑alternativ.
linktitle: Create File GDB with Single Layer
second_title: Aspose.GIS .NET API
title: Skapa vektorlager i File GDB – Aspose.GIS .NET-handledning
url: /sv/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa vektorlager i File GDB

## Introduktion
Om du behöver **skapa vektorlager** i en File Geodatabase (GDB) och hantera geospatiala data effektivt, ger Aspose.GIS för .NET dig ett rent, kod‑först‑tillvägagångssätt. I den här steg‑för‑steg‑guiden visar vi hur du skriver ett linjefeature, konfigurerar File GDB‑alternativ och arbetar med den rumsliga referensen WGS84 – allt i några få rader C#. När du är klar kan du räkna features i ett lager och integrera den resulterande GDB:n i vilken .NET‑kartläggnings‑ eller analysarbetsflöde som helst.

## Snabba svar
- **Vad betyder “skapa vektorlager”?** Det betyder att lägga till en ny vektordataset (punkter, linjer eller polygoner) i en geodatabasfil.  
- **Vilket bibliotek ska jag använda?** Aspose.GIS för .NET erbjuder fullständigt stöd för skapande och redigering av File GDB.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en kommersiell licens krävs för produktion.  
- **Kan jag ange den rumsliga referensen?** Ja – använd `SpatialReferenceSystem.Wgs84` för den vanliga WGS84‑datumet.  
- **Hur många kodrader?** Mindre än 30 rader för att skapa GDB:n, lägga till ett linjefeature och läsa tillbaka feature‑antalet.

## Vad är en “skapa vektorlager”-operation?
Att skapa ett vektorlager innebär att definiera en ny tabell i en geodatabase som lagrar geometriska objekt (punkter, linjer, polygoner) tillsammans med deras attribut. Denna operation är grunden för alla GIS‑baserade applikationer som behöver **hantera geospatiala data**.

## Varför använda Aspose.GIS för att skapa ett vektorlager?
- **Inga externa beroenden** – API‑et fungerar direkt på .NET Framework, .NET Core och .NET 5/6.  
- **Fullt stöd för File GDB** – du kan konfigurera `FileGdbOptions` för att styra komprimering, rumslig indexering och mer.  
- **Inbyggd hantering av rumsliga referenser** – skicka bara `SpatialReferenceSystem.Wgs84` för att arbeta i det globala koordinatsystemet.  
- **Enkel API** – skriv linjefeature, lägg till det i ett lager och hämta feature‑antalet med bara några metodanrop.

## Förutsättningar
Innan du börjar, se till att du har:

1. **Aspose.GIS för .NET** – ladda ner det från [Aspose.GIS för .NET nedladdningssida](https://releases.aspose.com/gis/net/).  
2. **En .NET‑utvecklingsmiljö** – Visual Studio, Rider eller `dotnet`‑CLI.  
3. **En mapp** där File GDB‑filen ska skapas (vi kallar den *Your Document Directory*).

## Importera namnrymder
Lägg till de nödvändiga `using`‑satserna högst upp i din C#‑fil:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```

## Steg 1: Ställ in din dokumentkatalog
```csharp
string dataDir = "Your Document Directory";
```
Byt ut `"Your Document Directory"` mot den absoluta sökvägen där du vill att File GDB‑filen ska ligga.

## Steg 2: Skapa en File Geodatabase med ett enda lager
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Detta kodsnutt **skapar ett vektorlager** med `FileGdbOptions`, skriver ett enkelt linjefeature och lagrar det i en File GDB som använder **den rumsliga referensen WGS84**.

## Steg 3: Öppna File Geodatabase och hämta lagerinformation
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```
Här **räknar vi features i lagret** genom att öppna datasetet och skriva ut antalet features – i detta fall `1`.

## Vanliga problem och lösningar
| Problem | Orsak | Lösning |
|-------|--------|-----|
| **`File not found`** | Felaktig `path`‑variabel | Verifiera att `dataDir` pekar på en befintlig mapp och att `path` kombineras med ett filnamn, t.ex. `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | En geometrityp som inte stöds i File GDB används | Håll dig till `Point`, `LineString` eller `Polygon` för grundläggande lager. |
| **`License not set`** | Kör utan en giltig licens i produktion | Registrera din licens med `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Vanliga frågor
### Kan jag använda Aspose.GIS för .NET i mina befintliga .NET‑projekt?
Ja, Aspose.GIS för .NET kan sömlöst integreras i dina befintliga .NET‑projekt.

### Finns det en provversion av Aspose.GIS för .NET?
Ja, du kan utforska funktionerna i Aspose.GIS för .NET genom att ladda ner [gratis provversion](https://releases.aspose.com/).

### Var kan jag hitta detaljerad dokumentation för Aspose.GIS för .NET?
Se [dokumentationen](https://reference.aspose.com/gis/net/) för omfattande information om Aspose.GIS för .NET.

### Hur får jag support för Aspose.GIS för .NET?
Besök [Aspose.GIS‑forumet](https://forum.aspose.com/c/gis/33) för community‑support och hjälp.

### Finns det tillfälliga licenser för Aspose.GIS för .NET?
Ja, du kan skaffa en [tillfällig licens](https://purchase.aspose.com/temporary-license/) för Aspose.GIS för .NET.

---

**Senast uppdaterad:** 2026-01-10  
**Testad med:** Aspose.GIS 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
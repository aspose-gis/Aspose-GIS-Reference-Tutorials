---
date: 2026-06-30
description: Lär dig hur du skapar Vector Layer i en File Geodatabase med Aspose.GIS
  för .NET. Hantera geospatial data med spatial reference WGS84 och file gdb options.
keywords:
- create vector layer
- add line feature
- manage geospatial data
- feature count example
- file gdb compression
linktitle: Skapa File GDB med Single Layer
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  headline: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  type: TechArticle
- description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  name: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  steps:
  - name: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
    text: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
  - name: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
    text: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
  type: HowTo
- questions:
  - answer: It means adding a new vector dataset (points, lines, or polygons) to a
      geodatabase file.
    question: What does “create vector layer” mean?
  - answer: Aspose.GIS for .NET provides full support for File GDB creation and editing.
    question: Which library should I use?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `SpatialReferenceSystem.Wgs84` for the common WGS84 datum.
    question: Can I set the spatial reference?
  - answer: Less than 30 lines to create the GDB, add a line feature, and read back
      the feature count.
    question: How many lines of code?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Skapa Vector Layer i File GDB – Aspose.GIS .NET Tutorial
url: /sv/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa vektorlager i File GDB

## Introduktion
Om du behöver **create vector layer** i en File Geodatabase (GDB) och hantera geospatiala data effektivt, ger Aspose.GIS för .NET dig ett rent, kod‑först tillvägagångssätt. I den här steg‑för‑steg‑guiden visar vi hur du skriver ett linjefeature, konfigurerar fil‑GDB‑alternativ och arbetar med den rumsliga referensen WGS84 — allt i några rader C#. I slutet kommer du kunna räkna funktioner i ett lager och integrera den resulterande GDB:n i vilket .NET‑kartläggnings‑ eller analysflöde som helst.

## Snabba svar
- **Vad betyder “create vector layer”?** Det betyder att lägga till ett nytt vektordataset (punkter, linjer eller polygoner) till en geodatabasfil.  
- **Vilket bibliotek ska jag använda?** Aspose.GIS för .NET erbjuder fullt stöd för skapande och redigering av File GDB.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en kommersiell licens krävs för produktion.  
- **Kan jag ange den rumsliga referensen?** Ja – använd `SpatialReferenceSystem.Wgs84` för det vanliga WGS84‑datumet.  
- **Hur många kodrader?** Mindre än 30 rader för att skapa GDB:n, lägga till ett linjefeature och läsa tillbaka antalet funktioner.

## Vad är en “create vector layer”-operation?
Att skapa ett vektorlager definierar en ny tabell i en geodatabas som lagrar geometriska objekt (punkter, linjer, polygoner) och deras attribut. Varje rad representerar ett feature, och geometrikolumnen innehåller dess form. I Aspose.GIS skapar du det genom att instansiera en `FeatureClass` inom en `FileGdbDataSource` och ange geometritypen.

## Varför använda Aspose.GIS för att skapa ett vektorlager?
Aspose.GIS eliminerar externa beroenden och stödjer **50+** GIS‑format, vilket gör det till en allt‑i‑ett‑lösning för .NET‑utvecklare.  
Den erbjuder inbyggd fil‑GDB‑komprimering (upp till 70 % minskning för typisk vektordata), rumslig indexering och full WGS84‑hantering direkt ur lådan. Biblioteket fungerar på .NET Framework 4.6+, .NET Core 2.0+, och .NET 5/6, så du kan rikta in dig på vilken modern Windows‑ eller plattformsoberoende miljö som helst utan ytterligare inhemska bibliotek.

## Förutsättningar
1. **Aspose.GIS for .NET** – ladda ner det från [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).  
2. **En .NET‑utvecklingsmiljö** – Visual Studio, Rider eller `dotnet`‑CLI.  
3. **En mapp** där File GDB kommer att skapas (vi kallar den *Your Document Directory*).

## Importera namnrymder
`using`‑satserna importerar de nödvändiga typerna till scopet.  

`Document`‑namnrymden tillhandahåller de centrala GIS‑objekten, medan `System.IO` hanterar filsökvägar.

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
Byt ut `"Your Document Directory"` mot den absoluta sökvägen där du vill att File GDB ska ligga.  
Att skapa katalogen i förväg undviker felet “File not found” som ofta drabbar nya användare.

```csharp
string dataDir = "Your Document Directory";
```

## Steg 2: Skapa en File Geodatabase med ett enda lager
FileGdbOptions är en klass som låter dig konfigurera komprimering, rumslig indexering och andra inställningar för en File Geodatabase.  
Detta kodexempel **creates a vector layer** med `FileGdbOptions`, skriver ett enkelt linjefeature och lagrar det i en File GDB som använder **spatial reference WGS84**.

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

## Steg 3: Öppna File Geodatabase och hämta lagerinformation
`FileGdbDataSource` är ingångspunkten för att skapa och öppna File Geodatabases.  
`FeatureClass` representerar ett vektorlager i en geodatabas och ger åtkomst till dess features.  
Här **count features in the layer** genom att öppna datasetet och skriva ut antalet features – i detta fall `1`.

```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```

## Hur verifierar du att lagret skapades korrekt?
Öppna geodatabasen med `FileGdbDataSource.Open` och fråga `FeatureClass`. `Count`‑egenskapen returnerar det totala antalet features, vilket bekräftar att linjen har sparats. Detta snabba verifieringssteg hjälper dig att upptäcka problem tidigt, särskilt vid automatisering av massimport.

## Vanliga problem och lösningar
| Problem | Orsak | Lösning |
|-------|--------|-----|
| **`File not found`** | Felaktig `path`‑variabel | Verifiera att `dataDir` pekar på en befintlig mapp och att `path` kombineras med ett filnamn, t.ex. `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | Använder en geometrityp som inte tillåts i File GDB | Håll dig till `Point`, `LineString` eller `Polygon` för grundläggande lager. |
| **`License not set`** | Kör utan en giltig licens i produktion | Registrera din licens med `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Vanliga frågor
### Kan jag använda Aspose.GIS för .NET i mina befintliga .NET‑projekt?
Ja, Aspose.GIS för .NET kan sömlöst integreras i dina befintliga .NET‑projekt.

### Finns det en provversion av Aspose.GIS för .NET?
Ja, du kan utforska funktionerna i Aspose.GIS för .NET genom att ladda ner [free trial version](https://releases.aspose.com/).

### Var kan jag hitta detaljerad dokumentation för Aspose.GIS för .NET?
Se [documentation](https://reference.aspose.com/gis/net/) för omfattande information om Aspose.GIS för .NET.

### Hur kan jag få support för Aspose.GIS för .NET?
Besök [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) för community‑support och hjälp.

### Finns tillfälliga licenser för Aspose.GIS för .NET?
Ja, du kan skaffa en [temporary license](https://purchase.aspose.com/temporary-license/) för Aspose.GIS för .NET.

---

**Last Updated:** 2026-06-30  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Relaterade handledningar

- [Skapa File Geodatabase .NET-dataset med Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Skapa vektorlager och ange lagerets rumsliga referenssystem](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Hur man tar bort lager från File GDB-dataset med Aspose.GIS](/gis/net/layer-data-operations/remove-layers-from-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}
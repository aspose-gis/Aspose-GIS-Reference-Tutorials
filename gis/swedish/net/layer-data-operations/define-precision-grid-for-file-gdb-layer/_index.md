---
date: 2026-04-24
description: Lär dig hur du skapar en filgeodatabas och ställer in ett precisionsrutnät
  för ett File GDB‑lager med Aspose.GIS för .NET, inklusive att lägga till objekt
  i lagret och validera koordinatområdet.
keywords:
- create file geodatabase
- handle out of range
- add features layer
- configure coordinate grid
- validate coordinate range
linktitle: Definiera precisionsrutnät för File GDB‑lager
second_title: Aspose.GIS .NET API
title: Skapa filgeodatabas & ange rutnät för GDB-lager (Aspose.GIS)
url: /sv/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ställer in rutnät för File GDB-lager i Aspose.GIS

## Introduktion
I den här handledningen kommer du att **create file geodatabase**-objekt och lära dig hur du **set grid** för ett File Geodatabase (GDB)-lager med Aspose.GIS för .NET. Att definiera ett precision‑rutnät låter dig **validate coordinate range**, förhindrar fel utanför intervallet och garanterar att varje **add features layer**‑operation lagrar data exakt. Vi går igenom varje steg, förklarar varför varje inställning är viktig och visar hur du **handle out of range**‑scenarier på ett smidigt sätt.

## Snabba svar
- **What does “set grid” mean?** Det definierar koordinatprecisionen och det giltiga intervallet för ett GIS‑lager.  
- **Why use a precision grid?** Det skyddar dina data från ogiltiga koordinater och förbättrar lagringseffektiviteten.  
- **Which library provides this feature?** Aspose.GIS for .NET.  
- **Do I need a license?** En provversion finns tillgänglig; en kommersiell licens krävs för produktion.  
- **Can I use this with .NET Core?** Ja, Aspose.GIS stöder .NET Framework och .NET Core.

## Vad är ett precision‑rutnät och varför ställa in det?
Ett precision‑rutnät är en uppsättning parametrar (origin, scale, osv.) som talar om för GIS‑motorn hur koordinatvärden ska avrundas och lagras. Genom att konfigurera ett rutnät **validate coordinate range** automatiskt, och varje försök att infoga en punkt utanför rutnätet kommer att kasta ett undantag—vilket hjälper dig att **handle out of range**‑scenarier tidigt i utvecklingen.

## Varför skapa en File Geodatabase med ett precision‑rutnät?
Att skapa en file geodatabase ger dig en portabel, högpresterande behållare för vektordata. Att lägga till ett precision‑rutnät vid skapandet säkerställer:

- **Consistent data quality** – varje feature respekterar samma numeriska precision.  
- **Faster indexing** – motorn kan lagra koordinater mer effektivt.  
- **Early error detection** – out‑of‑range‑koordinater fångas innan de korruptar datasetet.

## Förutsättningar
1. **Visual Studio** – någon recent version (Community, Professional eller Enterprise).  
2. **Aspose.GIS for .NET** – ladda ner den från [website](https://releases.aspose.com/gis/net/).  
3. **Basic C# knowledge** – du bör vara bekväm med att skapa .NET‑konsolprojekt.

## Vanliga användningsfall
- **Field data collection** där GPS‑enheter kan producera koordinater som ligger något utanför det avsedda området.  
- **Data migration** från äldre system som använde olika koordinatprecisioner.  
- **Automated ETL pipelines** som behöver upprätthålla spatial integritet innan data laddas in i en GIS‑databas.

## Importera namnrymder
Först importerar du de namnrymder som krävs för att arbeta med Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## Hur man konfigurerar koordinatrutnät i ett File GDB‑lager
Nedan följer en steg‑för‑steg‑guide som visar exakt hur du konfigurerar rutnätet, skapar ett lager och säkert **add features to layer**.

### Steg 1: Skapa ett dataset
Vi börjar med att skapa ett nytt File Geodatabase‑dataset. Detta är där lagret kommer att finnas.

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### Steg 2: Definiera alternativ för precision‑rutnät
Här specificerar vi rutnätsparametrarna. Justera origin och skalor så att de matchar ditt projekts koordinatsystem.

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

*Flaggan `EnsureValidCoordinatesRange = true` talar om för Aspose.GIS att **validate coordinate range** för varje feature du lägger till.*

### Steg 3: Skapa ett lager med rutnätet
Nu skapar vi ett nytt lager i datasetet och tillämpar de rutnätsalternativ vi just definierade. Vi kommer att använda det rumsliga referenssystemet WGS84.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### Steg 4: Lägg till features i lagret
Vi konstruerar två punkt‑features. Den första punkten ligger inom rutnätet, medan den andra medvetet ligger utanför för att demonstrera **how to handle out of range**‑fel.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### Steg 5: Hantera undantag när du lägger till out‑of‑Range‑features
Att försöka lägga till den andra feature:n kommer att utlösa ett undantag eftersom dess X‑koordinat (`-410`) ligger utanför det definierade rutnätet. Vi fångar undantaget och skriver ut ett tydligt meddelande.

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

### Steg 6: Rensa upp
`using`‑satserna stänger och frigör automatiskt datasetet och lagret, vilket säkerställer att alla resurser släpps.

## Vanliga problem och lösningar
| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| **Exception: “X value … is out of valid range.”** | Koordinater ligger utanför precision‑rutnätet. | Justera `XOrigin`, `YOrigin` eller `XYScale` så att de omfattar dina data, eller säkerställ att indata ligger inom det definierade intervallet. |
| **Features not appearing in GIS viewer** | Lager sparades inte eller fel rumslig referens. | Verifiera att `SpatialReferenceSystem.Wgs84` matchar visningsprogrammets CRS, och att `Dataset.Create` lyckades. |
| **M values ignored** | `MScale` satt till 0 eller för lågt. | Sätt en rimlig `MScale` (t.ex. `1e4`) för att lagra måttvärden. |

## Felsökningstips
- **Double‑check the grid extents** innan du laddar stora datamängder; ett litet stavfel i `XOrigin` kan leda till att många rader avvisas.  
- **Log the exception message** (som visas i try‑catch‑blocket) till en fil när du bearbetar automatiska importeringar; detta gör det enklare att upptäcka mönster i out‑of‑range‑data.  
- **Use `EnsureValidCoordinatesRange = false` only for trusted data sources** – att stänga av det hoppar över validering och kan leda till korrupta geometrier.

## Vanliga frågor

**Q: Kan jag använda Aspose.GIS för .NET med andra GIS‑filformat?**  
A: Ja, Aspose.GIS stöder Shapefile, GeoJSON, KML och många fler format.

**Q: Är Aspose.GIS för .NET kompatibel med .NET Core?**  
A: Absolut. Biblioteket fungerar med .NET Framework, .NET Core och .NET 5/6+.

**Q: Kan jag utföra rumsliga operationer som buffring eller skärning?**  
A: Ja, API‑et innehåller metoder för buffring, skärning och beräkning av avstånd.

**Q: Tillhandahåller Aspose.GIS koordinattransformeringsmöjligheter?**  
A: Ja, du kan transformera geometrier mellan olika rumsliga referenssystem med de inbyggda reprojektionverktygen.

**Q: Finns det en provversion tillgänglig?**  
A: Ja, du kan ladda ner en gratis provversion från [website](https://releases.aspose.com/gis/net/).

---

**Senast uppdaterad:** 2026-04-24  
**Testad med:** Aspose.GIS 24.11 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2025-12-28
description: Learn how to set grid for a File GDB layer using Aspose.GIS for .NET,
  including add features to layer and validate coordinate range.
linktitle: Define Precision Grid for File GDB Layer
second_title: Aspose.GIS .NET API
title: How to Set Grid for File GDB Layer in Aspose.GIS
url: /sv/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ställer in rutnät för File GDB-lager i Aspose.GIS

## Introduktion
I den här handledningen lär du dig **hur man ställer in rutnät** för ett File Geodatabase (GDB)-lager med Aspose.GIS för .NET. Att sätta ett precisionsrutnät hjälper dig **validera koordinatområde**, förhindrar fel utanför intervallet och säkerställer att de data du **lägger till funktioner i lager** förblir korrekta och pålitliga. Vi går igenom varje steg, förklarar varför inställningarna är viktiga och visar hur du hanterar vanliga fallgropar.

## Snabba svar
- **Vad betyder “set grid”?** Det definierar koordinatprecisionen och det giltiga intervallet för ett GIS-lager.  
- **Varför använda ett precisionsrutnät?** Det skyddar dina data från ogiltiga koordinater och förbättrar lagringseffektiviteten.  
- **Vilket bibliotek tillhandahåller denna funktion?** Aspose.GIS för .NET.  
- **Behöver jag en licens?** En provversion finns tillgänglig; en kommersiell licens krävs för produktion.  
- **Kan jag använda detta med .NET Core?** Ja, Aspose.GIS stödjer .NET Framework och .NET Core.

## Vad är ett precisionsrutnät och varför ställa in det?
Ett precisionsrutnät är en uppsättning parametrar (origin, skala osv.) som talar om för GIS-motorn hur koordinatvärden ska avrundas och lagras. Genom att definiera ett rutnät **validerar du koordinatområdet** automatiskt, och varje försök att infoga en punkt utanför rutnätet kommer att kasta ett undantag—vilket hjälper dig **hantera utanför intervall**-scenarier tidigt i utvecklingen.

## Förutsättningar
Innan vi börjar, se till att du har följande installerat:

1. **Visual Studio** – någon recent version (Community, Professional eller Enterprise).  
2. **Aspose.GIS för .NET** – ladda ner det från [webbplatsen](https://releases.aspose.com/gis/net/).  
3. **Grundläggande C#-kunskaper** – du bör vara bekväm med att skapa .NET-konsolprojekt.

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

## Hur man ställer in rutnät i ett File GDB-lager
Nedan följer en steg‑för‑steg‑guide som visar exakt hur du konfigurerar rutnätet, skapar ett lager och säkert **lägger till funktioner i lager**.

### Steg 1: Skapa en dataset
Vi börjar med att skapa ett nytt File Geodatabase‑dataset. Detta är där lagret kommer att ligga.

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### Steg 2: Definiera alternativ för precisionsrutnät
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

*Flaggan `EnsureValidCoordinatesRange = true` talar om för Aspose.GIS att **validera koordinatområdet** för varje funktion du lägger till.*

### Steg 3: Skapa ett lager med rutnätet
Nu skapar vi ett nytt lager i datasetet och tillämpar de rutnätsalternativ vi just definierat. Vi använder det geografiska referenssystemet WGS84.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### Steg 4: Lägg till funktioner i lagret
Vi konstruerar två punktfunktioner. Den första punkten ligger inom rutnätet, medan den andra medvetet hamnar utanför för att demonstrera **hur man hanterar utanför intervall**‑fel.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### Steg 5: Hantera undantag när du lägger till funktioner utanför intervallet
Att försöka lägga till den andra funktionen kommer att utlösa ett undantag eftersom dess X‑koordinat (`-410`) ligger utanför det definierade rutnätet. Vi fångar undantaget och skriver ut ett tydligt meddelande.

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
`using`‑satserna stänger och disponerar automatiskt datasetet och lagret, vilket säkerställer att alla resurser frigörs.

## Vanliga problem och lösningar
| Problem | Varför det händer | Åtgärd |
|-------|----------------|-----|
| **Undantag: “X‑värde … är utanför giltigt intervall.”** | Koordinater faller utanför precisionsrutnätet. | Justera `XOrigin`, `YOrigin` eller `XYScale` så att de omfattar dina data, eller säkerställ att indata ligger inom det definierade intervallet. |
| **Funktioner visas inte i GIS‑visare** | Lager sparas inte eller fel spatial referens. | Verifiera att `SpatialReferenceSystem.Wgs84` matchar visarens CRS, och att `Dataset.Create` lyckades. |
| **M‑värden ignoreras** | `MScale` är satt till 0 eller för lågt. | Sätt en rimlig `MScale` (t.ex. `1e4`) för att lagra måttvärden. |

## Vanliga frågor

**Q: Kan jag använda Aspose.GIS för .NET med andra GIS-filformat?**  
A: Ja, Aspose.GIS stödjer Shapefile, GeoJSON, KML och många fler format.

**Q: Är Aspose.GIS för .NET kompatibel med .NET Core?**  
A: Absolut. Biblioteket fungerar med .NET Framework, .NET Core och .NET 5/6+.

**Q: Kan jag utföra rumsliga operationer såsom buffring eller korsning?**  
A: Ja, API‑et innehåller metoder för buffring, korsning och beräkning av avstånd.

**Q: Tillhandahåller Aspose.GIS koordinattransformationsmöjligheter?**  
A: Ja, du kan transformera geometrier mellan olika spatiala referenssystem med de inbyggda reprojekteringsverktygen.

**Q: Finns det en provversion tillgänglig?**  
A: Ja, du kan ladda ner en gratis provversion från [webbplatsen](https://releases.aspose.com/gis/net/).

---

**Senast uppdaterad:** 2025-12-28  
**Testad med:** Aspose.GIS 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
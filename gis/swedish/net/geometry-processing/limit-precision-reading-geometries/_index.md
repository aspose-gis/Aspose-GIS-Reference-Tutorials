---
date: 2025-12-20
description: Lär dig hur du skapar ett vektorlager och begränsar precisionen när du
  läser geometrier med Aspose.GIS för .NET. Steg‑för‑steg‑guide för optimal hantering
  av geospatiala data.
linktitle: Limit Precision Reading Geometries
second_title: Aspose.GIS .NET API
title: Skapa vektorlager, begränsa precision med Aspose.GIS för .NET
url: /sv/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa vektorlager, begränsa precision med Aspose.GIS för .NET

## Introduktion
När du arbetar med geospatial data behöver du ofta **create vector layer**-objekt och kontrollera hur mycket numerisk detalj som behålls vid läsning. Aspose.GIS för .NET gör det enkelt att begränsa precision, vilket kan förbättra prestanda och minska lagringsstorleken när ultra‑hög noggrannhet inte krävs. I den här handledningen kommer du att se exakt hur du skapar ett vektorlager, skriver en enkel punktgeometri och sedan läser tillbaka den med både exakt och trunkerad precision.

## Snabba svar
- **What does “limit precision” mean?** Det rundar koordinatvärden till ett definierat antal decimaler.  
- **Why create a vector layer first?** Ett vektorlager är behållaren som lagrar geometrier såsom punkter, linjer och polygoner.  
- **Which precision models are available?** `PrecisionModel.Exact` (ingen avrundning) och `PrecisionModel.Rounding(n)` (avrunda till *n* decimaler).  
- **Do I need a license to try this?** En gratis provversion finns tillgänglig på releases‑sidan.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core och .NET 5/6+.

## Förutsättningar
Innan vi ger oss av, se till att du har följande förutsättningar på plats:
1. **Installation** – Aspose.GIS for .NET‑biblioteket bör vara installerat i din utvecklingsmiljö. Om inte, kan du ladda ner det från [releases page](https://releases.aspose.com/gis/net/).
2. **Familiarity with .NET** – Grundläggande kunskap om C# och .NET‑ramverket är nödvändig för att förstå och implementera de medföljande kodexemplen.
3. **Development Environment** – En fungerande .NET‑utvecklingsmiljö, såsom Visual Studio, krävs.
4. **Document Directory** – Ha en katalog konfigurerad där du kan lagra och komma åt shapefilen som genereras under processen.

## Importera namnrymder
Innan vi börjar implementera funktionaliteten för att begränsa precision när vi läser geometrier, låt oss säkerställa att vi importerar de nödvändiga namnrymderna:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Hur man skapar vektorlager
Det första steget är att **create vector layer** som kommer att hålla vår geometri. Detta lager sparas som en Shapefile så att vi senare kan öppna det igen med olika precisionsinställningar.
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Ställa in precisionalternativ
Nästa steg är att definiera alternativ för att läsa geometrier, med angiven precisionsmodell. Vi kan börja med exakt precision:
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Läsa geometrier med exakt precision
Nu öppnar vi vektorlageret med de specificerade alternativen för att läsa geometrier med exakt precision:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Trunkera precision
Om vi vill trunkera precisionen till ett specifikt antal decimaler kan vi justera precisionsmodellen därefter:
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Vanliga problem och lösningar
- **Unexpected coordinate values** – Se till att du sätter `options.XYPrecisionModel` *innan* lagret öppnas. Att ändra det efter öppning har ingen effekt.
- **File not found** – Verifiera att variabeln `path` pekar på en giltig katalog och att Shapefilen skapades framgångsrikt i föregående steg.
- **Incorrect geometry type** – Exemplet använder en `Point`. För andra geometri‑typer (t.ex. `LineString`) bör castingen matcha den faktiska typen.

## Slutsats
Sammanfattningsvis är hantering av precision vid läsning av geometrier en avgörande aspekt av geospatial datamanipulation. Aspose.GIS för .NET erbjuder robusta funktioner för att uppnå detta effektivt. Genom att följa stegen som beskrivs i den här handledningen kan du sömlöst **create vector layer**‑objekt och begränsa precision enligt dina krav, vilket säkerställer optimal datahantering i dina applikationer.

## Vanliga frågor
### Kan jag använda Aspose.GIS för .NET med andra .NET‑ramverk som .NET Core eller .NET Standard?
Ja, Aspose.GIS för .NET är kompatibel med olika .NET‑ramverk, inklusive .NET Core och .NET Standard.  
### Finns det en provversion tillgänglig för Aspose.GIS för .NET?
Ja, du kan få en gratis provversion från [releases page](https://releases.aspose.com/).  
### Var kan jag hitta omfattande dokumentation för Aspose.GIS för .NET?
Du kan hänvisa till [documentation](https://reference.aspose.com/gis/net/) för detaljerad information och exempel.  
### Hur kan jag skaffa tillfälliga licenser för Aspose.GIS för .NET?
Tillfälliga licenser kan erhållas från [purchase page](https://purchase.aspose.com/temporary-license/) för Aspose.GIS.  
### Var kan jag få hjälp eller support för Aspose.GIS för .NET?
Du kan besöka Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) för frågor, diskussioner eller support.

## Vanliga frågor
**Q: Påverkar begränsning av precision den ursprungliga shapefilen?**  
A: Nej. Precision appliceras endast vid läsning av geometrin; källfilen förblir oförändrad.  

**Q: Kan jag använda en annan precisionsmodell för X‑ och Y‑koordinater?**  
A: Aspose.GIS tillämpar för närvarande samma `XYPrecisionModel` på båda axlarna.  

**Q: Är det möjligt att ange en anpassad avrundningsfunktion?**  
A: API:et stöder endast den inbyggda `PrecisionModel.Rounding(int)`‑metoden. För anpassad logik måste du efterbehandla koordinaterna efter läsning.

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
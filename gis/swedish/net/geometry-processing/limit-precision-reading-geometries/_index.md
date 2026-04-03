---
date: 2026-04-03
description: Lär dig hur du skapar ett vektorlager och begränsar precisionen när du
  läser geometrier med Aspose.GIS för .NET. Steg‑för‑steg‑guide för optimal hantering
  av geospatiala data.
keywords:
- create vector layer
- reduce shapefile size
- set precision model
linktitle: Begränsa precision för läsning av geometrier
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
När du arbetar med geospatiala data behöver du ofta **skapa vektorlager**‑objekt och bestämma hur många decimaler av koordinatdetaljer du faktiskt behöver. Att begränsa precisionen snabbar inte bara upp bearbetningen utan kan också **reducera shapefilens storlek**, vilket gör lagring och överföring mer effektiv. I den här handledningen går vi igenom hur du skapar ett vektorlager, skriver en enkel punktgeometri och sedan läser tillbaka den med både exakt och avrundad precisionsmodell. I slutet förstår du hur du **ställer in precisionsmodell**‑alternativ som passar din applikations noggrannhetskrav.

## Snabba svar
- **Vad betyder “begränsa precision”?** Det avrundar koordinatvärden till ett definierat antal decimaler.  
- **Varför skapa ett vektorlager först?** Ett vektorlager är behållaren som lagrar geometrier såsom punkter, linjer och polygoner.  
- **Vilka precisionsmodeller finns tillgängliga?** `PrecisionModel.Exact` (ingen avrundning) och `PrecisionModel.Rounding(n)` (avrunda till *n* decimaler).  
- **Behöver jag en licens för att prova detta?** En gratis provversion finns tillgänglig på releases‑sidan.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core och .NET 5/6+.

## Varför begränsa precision och hur hjälper det?
- **Prestandaförbättring** – Färre siffror betyder mindre data att parsas och serialiseras.  
- **Mindre filer** – Avrundning av koordinater kan märkbart krympa en shapefil, särskilt för stora dataset.  
- **Tillräcklig noggrannhet** – Många GIS‑analyser kräver inte sub‑millimetern precision, så avrundning till 2‑3 decimaler räcker ofta.

## Förutsättningar
Innan vi ger oss av på denna resa, se till att du har följande förutsättningar på plats:
1. **Installation** – Aspose.GIS för .NET‑biblioteket bör vara installerat i din utvecklingsmiljö. Om inte, kan du ladda ner det från [releases page](https://releases.aspose.com/gis/net/).
2. **Bekantskap med .NET** – Grundläggande kunskap om C# och .NET‑ramverket är nödvändig för att förstå och implementera de medföljande kodexemplen.
3. **Utvecklingsmiljö** – En fungerande .NET‑utvecklingsmiljö, såsom Visual Studio, krävs.
4. **Dokumentkatalog** – Ha en katalog skapad där du kan lagra och komma åt shapefilen som genereras under processen.

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

## Så skapar du vektorlager
Det första steget är att **skapa vektorlager** som kommer att hålla vår geometri. Detta lager kommer att sparas som en Shapefile så att vi senare kan öppna det igen med olika precisionsinställningar.
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
Nästa steg är att definiera alternativ för att läsa geometrier, där vi specificerar den önskade precisionsmodellen. Vi kan börja med exakt precision:
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Läsa geometrier med exakt precision
Nu öppnar vi vektorlageret med de angivna alternativen för att läsa geometrier med exakt precision:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Avkortning av precision
Om vi vill avkorta precisionen till ett specifikt antal decimaler kan vi justera precisionsmodellen därefter:
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Hur man ställer in precisionsmodell för olika scenarier
Du kanske undrar när du ska använda `Exact` kontra `Rounding`. Här är två vanliga scenarier:

| Scenario | Rekommenderad modell | Orsak |
|----------|----------------------|-------|
| Högprecisions vetenskaplig analys | `PrecisionModel.Exact` | Ingen förlust av koordinatdetalj |
| Webbkartläggningstilex eller mobilappar | `PrecisionModel.Rounding(2)` | Minskar filstorlek och snabbar upp rendering |

Att välja rätt modell är en del av **set precision model**‑beslutsprocessen som balanserar noggrannhet mot prestanda.

## Vanliga problem och lösningar
- **Oväntade koordinatvärden** – Se till att du sätter `options.XYPrecisionModel` *innan* du öppnar lagret. Att ändra den efter öppning har ingen effekt.  
- **Filen hittas inte** – Kontrollera att variabeln `path` pekar på en giltig katalog och att Shapefile skapades framgångsrikt i föregående steg.  
- **Fel geometrityp** – Exemplet använder en `Point`. För andra geometrityper (t.ex. `LineString`) bör casten matcha den faktiska typen.  

## Tips för att minska shapefilens storlek
- Använd `PrecisionModel.Rounding` med det minsta antalet decimaler som fortfarande uppfyller dina noggrannhetskrav.  
- Ta bort onödiga attributfält innan du skriver lagret.  
- Komprimera de resulterande `.shp`, `.shx` och `.dbf`‑filerna med vanliga ZIP‑verktyg om du behöver överföra dem.

## Slutsats
Sammanfattningsvis är hantering av precision när man läser geometrier en avgörande aspekt av manipulation av geospatiala data. Aspose.GIS för .NET erbjuder robust funktionalitet för att uppnå detta på ett effektivt sätt. Genom att följa stegen ovan kan du sömlöst **skapa vektorlager**, **ställa in precisionsmodell** och till och med **reducera shapefilens storlek** när det är lämpligt, vilket säkerställer optimal datahantering i dina applikationer.

## Vanliga frågor
### Kan jag använda Aspose.GIS för .NET med andra .NET-ramverk som .NET Core eller .NET Standard?
Ja, Aspose.GIS för .NET är kompatibel med olika .NET‑ramverk, inklusive .NET Core och .NET Standard.  
### Finns det en provversion tillgänglig för Aspose.GIS för .NET?
Ja, du kan få en gratis provversion från [releases page](https://releases.aspose.com/).  
### Var kan jag hitta omfattande dokumentation för Aspose.GIS för .NET?
Du kan hänvisa till [documentation](https://reference.aspose.com/gis/net/) för detaljerad information och exempel.  
### Hur kan jag skaffa tillfälliga licenser för Aspose.GIS för .NET?
Tillfälliga licenser kan erhållas från [purchase page](https://purchase.aspose.com/temporary-license/) för Aspose.GIS.  
### Var kan jag söka hjälp eller support för Aspose.GIS för .NET?
Du kan besöka Aspose.GIS‑[forum](https://forum.aspose.com/c/gis/33) för frågor, diskussioner eller supportbehov.

## Vanligt förekommande frågor
**Q: Påverkar begränsning av precision den ursprungliga shapefilen?**  
A: Nej. Precisionen tillämpas endast när geometrin läses; källfilen förblir oförändrad.  

**Q: Kan jag använda en annan precisionsmodell för X‑ och Y‑koordinater?**  
A: Aspose.GIS tillämpar för närvarande samma `XYPrecisionModel` på båda axlarna.  

**Q: Är det möjligt att ange en egen avrundningsfunktion?**  
A: API‑et stödjer endast den inbyggda metoden `PrecisionModel.Rounding(int)`. För egen logik måste du efterbehandla koordinaterna efter läsning.

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
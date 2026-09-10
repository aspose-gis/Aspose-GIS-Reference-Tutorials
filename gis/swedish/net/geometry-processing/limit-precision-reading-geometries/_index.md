---
date: 2026-09-10
description: Lär dig hur du skapar vector layer med Aspose.GIS for .NET och begränsar
  precision för att minska shapefile‑storlek, öka performance och behålla coordinate
  accuracy.
keywords:
- how to create vector layer
- limit precision reading geometries
- reduce shapefile size
lastmod: 2026-09-10
linktitle: Begränsa Precision vid läsning av Geometries
og_description: Lär dig hur du skapar vector layer med Aspose.GIS for .NET och begränsar
  precision för att minska shapefile‑storlek, förbättra performance och hantera coordinate
  accuracy.
og_image_alt: Screenshot showing Aspose.GIS code for creating a vector layer and setting
  precision
og_title: Hur man skapar vector layer med Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  headline: How to create vector layer with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  name: How to create vector layer with Aspose.GIS for .NET
  steps:
  - name: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
    text: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
  - name: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
    text: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
  - name: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
    text: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
  - name: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
    text: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
  type: HowTo
- questions:
  - answer: No. Precision is applied only when reading the geometry; the source file
      remains unchanged.
    question: Does limiting precision affect the original shapefile?
  - answer: Aspose.GIS currently applies the same `XYPrecisionModel` to both axes.
    question: Can I use a different precision model for X and Y coordinates?
  - answer: The API supports only the built‑in `PrecisionModel.Rounding(int)` method.
      For custom logic, you would need to post‑process the coordinates after reading.
    question: Is it possible to set a custom rounding function?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- Aspose.GIS
- vector layer
- precision model
- .NET GIS
title: Hur man skapar vector layer med Aspose.GIS for .NET
url: /sv/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar vektorlager med Aspose.GIS för .NET

## Introduktion
När du arbetar med geospatiala data undrar du ofta **hur man skapar vektorlager** objekt som matchar den noggrannhet som din applikation verkligen behöver. Att avrunda koordinater till ett rimligt antal decimaler snabbar inte bara upp parsning utan kan också **reducera shapefilens storlek med upp till 30 %** för typiska punktdatamängder. I den här steg‑för‑steg‑guiden kommer du att se hur man skapar ett vektorlager, skriver en punktgeometri och sedan läser tillbaka den med både exakta och avrundade precisionsmodeller. I slutet kommer du att veta hur man **ställer in precision model**‑alternativ som balanserar prestanda med den erforderliga rumsliga noggrannheten.

## Snabba svar
- **Vad betyder “limit precision”?** Den avrundar koordinatvärden till ett definierat antal decimaler.  
- **Varför skapa ett vektorlager först?** Ett vektorlager är behållaren som lagrar geometrier såsom punkter, linjer och polygoner.  
- **Vilka precisionsmodeller finns tillgängliga?** `PrecisionModel.Exact` (ingen avrundning) och `PrecisionModel.Rounding(n)` (avrunda till *n* decimaler).  
- **Behöver jag en licens för att prova detta?** En gratis provversion finns tillgänglig på releases‑sidan.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core, och .NET 5/6+.

## Vad innebär att skapa ett vektorlager?
Handling av **att skapa ett vektorlager** innebär att instansiera Aspose.GIS:s `VectorLayer`‑klass, som representerar en enda shapefile på disk och innehåller alla geometrifunktioner du lägger till. Detta lager blir ingångspunkten för att läsa, skriva och manipulera rumsliga data. Det låter dig också definiera attributfält och ange den rumsliga referensen för datasetet.

## Varför begränsa precision och hur hjälper det?
- **Prestandaförbättring** – Att minska antalet decimaler minskar mängden binär data som måste parsas och serialiseras, vilket ofta ger en 15‑20 % hastighetsökning på stora filer.  
- **Mindre filer** – Att avrunda koordinater till två eller tre decimaler kan minska en 10 MB shapefile till ungefär 7 MB, vilket underlättar lagring och nätverkstransfer.  
- **Tillräcklig noggrannhet** – De flesta GIS‑analyser (t.ex. kartläggning på stadsnivå) kräver bara meter‑nivå precision, vilket gör 3‑decimalers avrundning mer än tillräcklig.

## Förutsättningar
Innan vi påbörjar denna resa, se till att du har följande förutsättningar på plats:
1. **Installation** – Aspose.GIS for .NET-biblioteket bör vara installerat i din utvecklingsmiljö. Om inte, kan du ladda ner det från [releases page](https://releases.aspose.com/gis/net/).  
2. **Familiarity with .NET** – Grundläggande kunskap om C# och .NET‑ramverket är nödvändig för att förstå och implementera de medföljande kodexemplen.  
3. **Development environment** – En fungerande .NET‑utvecklingsmiljö, såsom Visual Studio, krävs.  
4. **Document directory** – Ha en katalog konfigurerad där du kan lagra och komma åt shapefilen som genereras under processen.

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
Läs in ett nytt `VectorLayer` genom att ange output‑mappen och önskat shapefile‑namn. Detta skapar en tom behållare redo att ta emot geometriska objekt.

`VectorLayer`‑klassen är Aspose.GIS:s översta objekt som representerar en enda shapefile på disk. Efter att du skapat en instans kan du lägga till funktioner, definiera attributfält och slutligen anropa `Save()` för att skriva filerna till filsystemet.
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Ställa in precisionsalternativ
`PrecisionModel` definierar hur koordinatvärden avrundas eller behålls exakt när geometrier läses. Du ställer in modellen på ett `ReadOptions`‑objekt innan du öppnar ett lager.

`PrecisionModel`‑klassen är en kärnkomponent i Aspose.GIS som styr avrundningsbeteendet för både X‑ och Y‑axlar. Genom att välja rätt modell bestämmer du om biblioteket bevarar varje siffra eller trunkerar till ett specifikt antal decimaler.
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Läsa geometrier med exakt precision
`ReadOptions` specificerar parametrar för att läsa ett vektorlager, såsom den precisionsmodell som ska tillämpas.  
Öppna det tidigare sparade vektorlageret med en `ReadOptions`‑instans som refererar `PrecisionModel.Exact`. Detta säkerställer att varje koordinat läses utan någon avrundning.

När du använder `PrecisionModel.Exact` läser Aspose.GIS de råa dubbelprecisionsvärdena som lagras i shapefilen, vilket garanterar att ingen information går förlorad under läsoperationen.
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Trunkera precision
Om du vill trunkera precisionen till ett specifikt antal decimaler, ersätt `Exact` med `PrecisionModel.Rounding(n)`, där *n* är antalet decimaler du vill behålla.

Avrundning till två decimaler (`PrecisionModel.Rounding(2)`) minskar vanligtvis filstorleken med 20‑30 % samtidigt som koordinatnoggrannheten hålls inom några centimeter för de flesta kartskala.
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Hur man ställer in precision model för olika scenarier
Välj den modell som matchar ditt användningsfall:
- **Högprecisions vetenskaplig analys** – Använd `PrecisionModel.Exact` för att behålla varje siffra.  
- **Web‑kartläggningstileller mobila appar** – Använd `PrecisionModel.Rounding(2)` för att hålla filer lätta och rendering snabb.

Att välja rätt modell är en del av beslutsprocessen för **set precision model** som balanserar noggrannhet mot prestanda.

## Vanliga problem och lösningar
`XYPrecisionModel` är en egenskap hos `ReadOptions` som anger precisionsmodellen för både X‑ och Y‑koordinater.  

- **Oväntade koordinatvärden** – Se till att du sätter `options.XYPrecisionModel` *innan* du öppnar lagret. Att ändra det efter öppning har ingen effekt.  
- **Filen hittades inte** – Verifiera att `path`‑variabeln pekar på en giltig katalog och att shapefilen skapades framgångsrikt i föregående steg.  
- **Fel geometrityp** – Exemplet använder en `Point`. För andra geometrityper (t.ex. `LineString`) bör castingen matcha den faktiska typen.  

## Tips för att minska shapefile‑storlek
- Använd `PrecisionModel.Rounding` med det minsta antalet decimaler som fortfarande uppfyller dina noggrannhetskrav.  
- Ta bort onödiga attributfält innan du skriver lagret.  
- Komprimera de resulterande `.shp`, `.shx` och `.dbf`‑filerna med vanliga ZIP‑verktyg om du behöver överföra dem.

## Slutsats
Hantering av precision när geometrier läses är en avgörande aspekt av manipulation av geospatiala data. Aspose.GIS för .NET erbjuder robusta funktioner för att uppnå detta effektivt. Genom att följa stegen ovan kan du sömlöst **create vector layer**‑objekt, **set precision model**, och till och med **reduce shapefile size** när det är lämpligt, vilket säkerställer optimal datahantering i dina applikationer.

## Vanliga frågor
### Kan jag använda Aspose.GIS för .NET med andra .NET‑ramverk som .NET Core eller .NET Standard?
Ja, Aspose.GIS för .NET är kompatibel med olika .NET‑ramverk, inklusive .NET Core och .NET Standard.  
### Finns det en provversion tillgänglig för Aspose.GIS för .NET?
Ja, du kan få en gratis provversion från [releases page](https://releases.aspose.com/).  
### Var kan jag hitta omfattande dokumentation för Aspose.GIS för .NET?
Du kan hänvisa till [documentation](https://reference.aspose.com/gis/net/) för detaljerad information och exempel.  
### Hur kan jag skaffa tillfälliga licenser för Aspose.GIS för .NET?
Tillfälliga licenser kan erhållas från [purchase page](https://purchase.aspose.com/temporary-license/) för Aspose.GIS.  
### Var kan jag söka hjälp eller support för Aspose.GIS för .NET?
Du kan besöka Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) för eventuella frågor, diskussioner eller supportbehov.

## Vanligt förekommande frågor
**Q: Påverkar begränsning av precision den ursprungliga shapefilen?**  
A: Nej. Precisionen tillämpas endast när geometrin läses; källfilen förblir oförändrad.  

**Q: Kan jag använda en annan precisionsmodell för X‑ och Y‑koordinater?**  
A: Aspose.GIS använder för närvarande samma `XYPrecisionModel` för båda axlarna.  

**Q: Är det möjligt att ange en anpassad avrundningsfunktion?**  
A: API‑et stödjer endast den inbyggda `PrecisionModel.Rounding(int)`‑metoden. För anpassad logik måste du efterbehandla koordinaterna efter läsning.

---

**Senast uppdaterad:** 2026-09-10  
**Testad med:** Aspose.GIS 24.11 för .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man begränsar precision vid skrivning av geometrier med Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)
- [Hur man skapar vektorlager med SRS med Aspose.GIS för .NET](/gis/net/layer-management/create-vector-layer-with-srs/)
- [Skapa vektorlager i File GDB – Aspose.GIS .NET‑handledning](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
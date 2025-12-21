---
date: 2025-12-21
description: Lär dig hur du skapar ett vektorlager, ställer in linjäriseringstolerans
  och lägger till ett objekt i lagret med Aspose.GIS för .NET. Följ den här steg‑för‑steg‑guiden
  för att exportera GeoJSON‑filer.
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: Skapa vektorlager och ställ in linjäriseringstolerans med Aspose.GIS för .NET
url: /sv/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa Vector Layer och ställ in Linearization Tolerance med Aspose.GIS för .NET

## Introduktion
Om du behöver **create vector layer**‑filer, kontrollera kurvprecision och exportera resultatet som ett GeoJSON‑dokument, gör Aspose.GIS för .NET det enkelt. I den här handledningen lär du dig hur du konfigurerar GeoJSON‑alternativ, ställer in linjäriserings toleransen och **add feature to layer**‑objekt — allt medan koden hålls ren och produktionsklar.

## Snabba svar
- **Vad betyder “create vector layer”?** Det skapar ett nytt GIS‑vektordataset (t.ex. en GeoJSON‑fil) som kan lagra geometrier och attribut.  
- **Hur ställer man in tolerans?** Använd egenskapen `LinearizationTolerance` i `GeoJsonOptions`.  
- **Kan jag exportera en GeoJSON‑fil?** Ja — skapa helt enkelt ett `VectorLayer` med drivrutinen `Drivers.GeoJson`.  
- **Behöver jag en licens?** En giltig Aspose.GIS‑licens låser upp alla funktioner; en tillfällig licens fungerar för utvärdering.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Vad är “create vector layer”?
Att skapa ett vector layer innebär att initiera en ny GIS‑behållare (t.ex. en GeoJSON‑fil) som kan innehålla geometriska funktioner som punkter, linjer och polygoner. Detta lager blir målet för all geometri du konstruerar och alla attribut du bifogar.

## Varför konfigurera GeoJSON‑alternativ?
Att konfigurera GeoJSON‑alternativ — särskilt **linearization tolerance** — säkerställer att kurvade geometrier (t.ex. `CircularString`) approximeras med en precision som uppfyller ditt programs noggrannhetskrav. Detta steg är avgörande när du senare **export GeoJSON file** för användning i webbkartor eller rumsliga analyser.

## Förutsättningar
1. **Visual Studio** installerat (någon nyare version).  
2. **Aspose.GIS‑licens** (eller en tillfällig utvärderingsnyckel).  
3. **Aspose.GIS for .NET**‑biblioteket nedladdat och refererat i ditt projekt.  
4. Grundläggande kunskap om **C#**.

## Importera namnrymder
Först importerar du de nödvändiga namnrymderna så att kompilatorn vet var GIS‑klasserna finns:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Steg‑för‑steg‑guide

### Steg 1: Konfigurera GeoJSON‑alternativ (hur man ställer in tolerans)
Vi skapar ett `GeoJsonOptions`‑objekt och talar om för Aspose.GIS hur nära den linjäriserade geometrin måste vara den ursprungliga kurvan.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Steg 2: Definiera utdata‑sökvägen (hur man exporterar GeoJSON)
Ange var den resulterande filen ska sparas. Ersätt platshållaren med din faktiska mapp.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Steg 3: **Create Vector Layer** med de konfigurerade alternativen
Nu **create vector layer** faktiskt med `VectorLayer.Create`‑metoden. `using`‑blocket garanterar korrekt resurshantering.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Steg 4: Konstruera en geometri (t.ex. en circular string)
Här bygger vi en exempelgeometri — en `CircularString`. Du kan ersätta detta med valfri giltig WKT.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Steg 5: **Add Feature to Layer** och spara
Till sist skapar vi ett feature, tilldelar geometrin och lägger till det i lagret. Detta är kärnan i **add feature to layer**‑operationen.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

När `using`‑blocket avslutas skrivs lagret automatiskt till filen som definierats i `path`, vilket ger dig en färdig‑att‑använda GeoJSON‑fil.

## Vanliga problem och tips
- **Felaktig sökväg** – Se till att katalogen finns och att du har skrivrättigheter.  
- **Toleransen för låg** – Att sätta `LinearizationTolerance` till ett mycket litet värde kan öka filstorleken dramatiskt. Justera efter dina noggrannhetsbehov.  
- **Licensfel** – Om du ser licensvarningar, kontrollera att licensfilen har laddats korrekt innan några Aspose.GIS‑anrop.

## Vanliga frågor

**Q: Är Aspose.GIS för .NET kompatibel med andra .NET‑ramverk?**  
A: Ja, den fungerar med .NET Framework, .NET Core och .NET 5/6/7.

**Q: Kan jag använda Aspose.GIS i kommersiella projekt?**  
A: Absolut. En kommersiell licens tar bort alla utvärderingsrestriktioner.

**Q: Stöder Aspose.GIS andra GIS‑format förutom GeoJSON?**  
A: Ja, den stöder Shapefile, KML, GML och många fler.

**Q: Finns en provversion?**  
A: Du kan ladda ner en gratis provversion från Aspose‑webbplatsen.

**Q: Var kan jag få support?**  
A: Använd Aspose‑forumet eller supportlänken i resurser‑sektionen.

## Slutsats
Genom att följa dessa steg vet du nu hur du **create vector layer**, konfigurerar linjäriserings toleransen och **add feature to layer** för sömlös **export GeoJSON file**‑skapande. Utforska ytterligare geometrityper och attributhantering för att fullt utnyttja Aspose.GIS i dina .NET‑GIS‑projekt.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Senast uppdaterad:** 2025-12-21  
**Testat med:** Aspose.GIS 24.11 för .NET  
**Författare:** Aspose
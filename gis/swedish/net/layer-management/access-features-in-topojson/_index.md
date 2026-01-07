---
date: 2026-01-07
description: Lär dig hur du hämtar egenskaper för objekt från TopoJSON med Aspose.GIS
  för .NET och effektivt hämtar objekt‑ID.
linktitle: Access Features in TopoJSON
second_title: Aspose.GIS .NET API
title: Hämta funktionsegenskaper från TopoJSON med Aspose.GIS för .NET
url: /sv/net/layer-management/access-features-in-topojson/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hämta egenskaper för funktioner från TopoJSON med Aspose.GIS för .NET

## Introduktion
I den här handledningen får du lära dig hur du **hämtar egenskaper för funktioner** från en TopoJSON‑fil med Aspose.GIS för .NET. Oavsett om du behöver läsa attributvärden, extrahera geometri eller helt enkelt *hämta funktion‑id* för vidare bearbetning, så guidar stegen nedan dig genom en ren, end‑to‑end‑lösning. När du är klar kan du plocka vilken egenskap som helst från dina TopoJSON‑data och använda den i dina .NET‑applikationer.

## Snabba svar
- **Vad betyder “hämta egenskaper för funktioner”?** Det innebär att läsa av attributvärden (t.ex. id, name) som är kopplade till varje geografisk funktion.  
- **Vilket bibliotek stödjer detta?** Aspose.GIS för .NET erbjuder ett enkelt API för hantering av TopoJSON.  
- **Behöver jag en licens?** En gratis provversion fungerar för testning; en kommersiell licens krävs för produktion.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Hur snabbt är operationen?** Laddning och iteration över funktioner sker i minnet och är lämplig för de flesta medelstora dataset.

## Vad betyder “hämta egenskaper för funktioner”?
Att hämta egenskaper för funktioner betyder att komma åt attributdata som lagras med varje geografiskt objekt i en TopoJSON‑fil. Dessa egenskaper kan inkludera identifierare, namn, klassificeringar eller annan anpassad metadata som beskriver funktionen.

## Varför hämta funktion‑id?
Operationen **hämta funktion‑id** är ofta det första steget i data‑drivna arbetsflöden — såsom filtrering, sammanslagning med externa tabeller eller visualisering av specifika funktioner på en karta. Att känna till ID‑t låter dig exakt identifiera vilken funktion du arbetar med.

## Förutsättningar
Innan vi börjar, se till att du har följande:
- Grundläggande kunskaper i C# och .NET.  
- Aspose.GIS för .NET‑biblioteket installerat. Du kan ladda ner det [här](https://releases.aspose.com/gis/net/).  
- En exempel‑TopoJSON‑fil för testning. Du hittar en i [dokumentationen](https://reference.aspose.com/gis/net/).

## Importera namnrymder
Börja med att importera de nödvändiga namnrymderna i din C#‑kod:
```csharp
using Aspose.Gis;
using System;
using System.Text;
```

## Steg 1: Ställ in ditt projekt
Skapa ett nytt C#‑projekt (Console App, ASP.NET, etc.) och lägg till en referens till Aspose.GIS för .NET‑DLL‑filen. Säkerställ att projektet riktar sig mot en stödjande .NET‑version.

## Steg 2: Ladda TopoJSON‑data och hämta egenskaper för funktioner
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string sampleTopoJsonPath = dataDir + "sample.topojson";
StringBuilder builder = new StringBuilder();
// Open the TopoJSON file
using (VectorLayer layer = VectorLayer.Open(sampleTopoJsonPath, Drivers.TopoJson))
{
    // Iterate through each feature in the layer
    foreach (Feature feature in layer)
    {
        // get id property
        int id = feature.GetValue<int>("id");
        // get name of the object that contains this feature
        string objectName = feature.GetValue<string>("topojson_object_name");
        // get name attribute property, located inside 'properties' object
        string name = feature.GetValue<string>("name");
        // get geometry of the feature.
        string geometry = feature.Geometry.AsText();
        // Build the output string
        builder.AppendFormat("Feature with ID {0}:\n", id);
        builder.AppendFormat("Object Name = {0}\n", objectName);
        builder.AppendFormat("Name        = {0}\n", name);
        builder.AppendFormat("Geometry    = {0}\n", geometry);
    }
}
// Display the output
Console.WriteLine("Output:");
Console.WriteLine(builder.ToString());
```

I kodsnutten ovan **hämtar vi funktion‑id** (`id`) och andra attribut (`name`, `topojson_object_name`). Detta är kärnan i “att hämta egenskaper för funktioner” från en TopoJSON‑källa.

## Vanliga problem och lösningar
- **Fil ej funnen** – Kontrollera att `sample.topojson` finns i den angivna katalogen och att sökvägen är korrekt.  
- **Saknad egenskap** – Om ett egenskapsnamn är felstavat (t.ex. ett stavfel i `"name"`), kommer `GetValue<T>` att kasta ett undantag. Använd `feature.TryGetValue<T>` för att säkert hantera valfria egenskaper.  
- **Stora filer** – För mycket stora TopoJSON‑filer, överväg att bearbeta funktioner i batcher eller använda streaming‑API:er för att minska minnesförbrukningen.

## Vanliga frågor

**Q: Var kan jag hitta mer dokumentation?**  
A: Besök [Aspose.GIS för .NET‑dokumentationen](https://reference.aspose.com/gis/net/).

**Q: Hur kan jag ladda ner Aspose.GIS för .NET?**  
A: Ladda ner biblioteket [här](https://releases.aspose.com/gis/net/).

**Q: Var kan jag få support för Aspose.GIS?**  
A: Gå med i [Aspose.GIS‑forumet](https://forum.aspose.com/c/gis/33) för hjälp.

**Q: Finns det en gratis provversion?**  
A: Ja, du kan få tillgång till en gratis provversion [här](https://releases.aspose.com/).

**Q: Hur köper jag en licens?**  
A: Köp en licens [här](https://purchase.aspose.com/buy).

**Q: Kan jag använda den här koden med .NET Core?**  
A: Absolut — Aspose.GIS stödjer .NET Core 3.1 och senare.

**Q: Vad om jag behöver skriva de extraherade egenskaperna till en CSV‑fil?**  
A: Efter att du byggt `StringBuilder` kan du skriva dess innehåll till en fil med `File.WriteAllText("output.csv", builder.ToString());`.

## Slutsats
Grattis! Du har lärt dig hur du **hämtar egenskaper för funktioner** från en TopoJSON‑fil och **hämtar funktion‑id** med Aspose.GIS för .NET. Detta ger dig en solid grund för att bygga rikare geografiska applikationer, utföra dataanalys eller integrera GIS‑data i vilken .NET‑lösning som helst.

---

**Senast uppdaterad:** 2026-01-07  
**Testad med:** Aspose.GIS för .NET 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-01-10
description: Lär dig hur du skapar .NET‑dataset för filgeodatabas med Aspose.GIS för
  .NET. Steg‑för‑steg‑guide för enkel GIS‑databehandling.
linktitle: Create New File GDB Dataset
second_title: Aspose.GIS .NET API
title: Skapa filgeodatabas .NET-dataset med Aspose.GIS
url: /sv/net/layer-management/create-new-file-gdb-dataset/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa File Geodatabase .NET-dataset med Aspose.GIS

## Introduktion
I den här handledningen kommer du att **skapa file geodatabase .NET**-dataset från grunden med Aspose.GIS för .NET. Oavsett om du bygger ett skrivbords‑GIS‑verktyg, en webbtjänst som lagrar rumsliga data, eller helt enkelt behöver ett pålitligt sätt att programatiskt generera File Geodatabases, så guidar den här guiden dig genom varje steg med tydliga förklaringar och verklig kontext.

## Snabba svar
- **Vad täcker den här handledningen?** Skapa en ny File Geodatabase, lägga till två lager och verifiera datasetet med Aspose.GIS för .NET.  
- **Hur lång tid tar det?** Ungefär 10‑15 minuter för en utvecklare som är bekant med C#.  
- **Förutsättningar?** .NET‑utvecklingsmiljö, Aspose.GIS för .NET‑biblioteket och en skrivbar mappväg.  
- **Kan jag använda detta i .NET Core / .NET 6+?** Ja – API:et är fullt kompatibelt med moderna .NET‑runtime.  
- **Behöver jag en licens?** En tillfällig eller permanent Aspose.GIS‑licens krävs för produktionsbruk.

## Vad är en File Geodatabase?
En File Geodatabase (File GDB) är en mapp‑baserad datalagring som innehåller GIS‑feature‑klasser, raster‑dataset och relaterad metadata. Den erbjuder snabb läs‑/skrivprestanda, stödjer stora dataset och används i stor utsträckning i Esris ArcGIS‑ekosystem. Med Aspose.GIS kan du skapa och manipulera dessa databaser direkt från .NET‑kod utan någon extern GIS‑programvara.

## Varför skapa file geodatabase .NET med Aspose.GIS?
- **Inga externa beroenden** – biblioteket hanterar alla filformatdetaljer.  
- **Plattformsoberoende** – fungerar på Windows, Linux och macOS .NET‑runtime.  
- **Rik geometri‑stöd** – punkter, linjer, polygoner och mer.  
- **Full kontroll** – du bestämmer schema, attribut och rumslig referens.

## Förutsättningar
Innan du börjar, se till att du har följande:

- Aspose.GIS för .NET installerat. Du kan ladda ner det från [Aspose.GIS för .NET nedladdningssida](https://releases.aspose.com/gis/net).  
- En utvecklingsmiljö som Visual Studio 2022 (eller någon IDE som stödjer .NET).  
- En skrivbar mapp på din maskin där den nya GDB‑filen ska skapas – ersätt `"Your Document Directory"` i koden med den sökvägen.  
- Grundläggande kunskap om C# och .NET‑projektstruktur.

## Importera namnrymder
Först, importera namnrymderna som ger dig åtkomst till Aspose.GIS‑klasserna:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Steg‑för‑steg‑guide

### Steg 1: Skapa ett nytt File GDB‑dataset
Följande kodsnutt skapar en tom File Geodatabase. Detta är kärnan i **create file geodatabase .net**.

```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Output: 0
    // Continue with subsequent steps...
}
```

**Förklaring:** `Dataset.Create` initierar GDB på den angivna sökvägen med `FileGdb`‑drivrutinen. Vid detta tillfälle innehåller datasetet inga lager, så lagerräkningen är noll.

### Steg 2: Skapa och fyll `layer_1`
Nu lägger vi till ett första lager som lagrar heltalsattribut och punktgeometrier.

```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```

**Förklaring:**  
- `CreateLayer` skapar en ny feature‑klass med namnet **layer_1**.  
- Ett heltalsattribut som heter **value** definieras.  
- Loopen lägger till tio features, var och en med ett unikt heltal och en punkt på koordinaterna *(i, i)*.

### Steg 3: Skapa och fyll `layer_2`
Därefter lägger vi till ett andra lager som demonstrerar hantering av linjegeometri.

```csharp
using (var layer = dataset.CreateLayer("layer_2"))
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

**Förklaring:** Detta skapar **layer_2** och infogar en enda feature vars geometri är en `LineString` som förbinder två punkter.

### Steg 4: Verifiera det uppdaterade lagerräkningen
Slutligen, bekräfta att båda lagren har lagts till korrekt.

```csharp
Console.WriteLine(dataset.LayersCount); // Output: 2
```

**Förklaring:** Datasetet rapporterar nu två lager, vilket bekräftar att processen **create file geodatabase .net** slutfördes som förväntat.

## Vanliga problem och lösningar

| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| **`UnauthorizedAccessException`** när datasetet skapas | Mappens sökväg är skrivskyddad eller du saknar behörighet. | Välj en skrivbar katalog eller kör Visual Studio som administratör. |
| **`ArgumentException` för drivrutin** | Drivrutinsnamnet är felstavat eller biblioteksversionen stödjer den inte. | Använd `Drivers.FileGdb` exakt som visat; säkerställ att du har den senaste Aspose.GIS‑paketet. |
| **Features visas inte i ArcGIS** | Saknad rumslig referens eller inkompatibel geometri. | Ställ in en rumslig referens på lagret om det behövs, och säkerställ att geometrierna är giltiga. |

## Vanliga frågor

### Fråga: Kan jag använda Aspose.GIS för .NET med andra GIS‑bibliotek?
Aspose.GIS för .NET är ett fristående verktyg; du kan dock integrera det med andra .NET‑bibliotek för att utöka funktionaliteten.

### Fråga: Finns det ett community‑forum för support av Aspose.GIS?
Ja, du kan hitta support och diskussioner på [Aspose.GIS Forum](https://forum.aspose.com/c/gis/33).

### Fråga: Hur kan jag skaffa en tillfällig licens för Aspose.GIS?
Besök sidan [Temporary License](https://purchase.aspose.com/temporary-license/) för information om hur du får en tillfällig licens.

### Fråga: Finns det fler exempel och dokumentation tillgängliga?
Utforska [Aspose.GIS documentation](https://reference.aspose.com/gis/net/) för fler exempel och detaljerad information.

### Fråga: Var kan jag köpa Aspose.GIS för .NET?
Du kan köpa Aspose.GIS för .NET på [purchase page](https://purchase.aspose.com/buy).

## Slutsats
Du har nu framgångsrikt **skapat file geodatabase .NET**‑dataset, lagt till två olika lager och verifierat resultatet med Aspose.GIS. Denna grund låter dig bygga rikare GIS‑applikationer — lägg till fler lager, definiera komplexa scheman eller integrera med webbtjänster. Utforska Aspose.GIS‑API:t vidare för att arbeta med rasterdata, rumsliga frågor och avancerade geometriska operationer.

**Senast uppdaterad:** 2026-01-10  
**Testad med:** Aspose.GIS för .NET 24.11 (eller senaste)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
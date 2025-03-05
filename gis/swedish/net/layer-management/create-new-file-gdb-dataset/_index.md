---
title: Skapa ny fil GDB Dataset
linktitle: Skapa ny fil GDB Dataset
second_title: Aspose.GIS .NET API
description: Utforska Aspose.GIS för .NET för att enkelt skapa och hantera GIS-datauppsättningar. Ladda ner nu för sömlös geospatial utveckling. #Aspose #GIS
type: docs
weight: 10
url: /sv/net/layer-management/create-new-file-gdb-dataset/
---
## Introduktion
Inom området för geospatial utveckling framstår Aspose.GIS för .NET som en kraftfull verktygslåda för att hantera och manipulera Geographic Information System (GIS) data. Oavsett om du är en erfaren utvecklare eller precis har börjat din resa till GIS, kommer den här handledningen att leda dig genom processen att skapa en ny File Geodatabase (GDB) dataset med Aspose.GIS för .NET.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
-  Aspose.GIS för .NET: Se till att du har Aspose.GIS för .NET-biblioteket installerat. Du kan ladda ner den från[Aspose.GIS för .NET nedladdningssida](https://releases.aspose.com/gis/net/).
- Utvecklingsmiljö: Konfigurera din utvecklingsmiljö med en kompatibel IDE, som Visual Studio, och ha en grundläggande förståelse för .NET-programmering.
- Dokumentkatalog: Ersätt "Din dokumentkatalog" i kodavsnittet med rätt sökväg där du vill lagra din GDB-datauppsättning.
- Bekantskap med C#: Denna handledning förutsätter att du är bekant med programmeringsspråket C#.
## Importera namnområden
de första stegen, importera de nödvändiga namnområdena för att utnyttja Aspose.GIS-funktionaliteten i din .NET-applikation:
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
## Steg 1: Skapa en ny fil GDB-datauppsättning
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Utgång: 0
    // Fortsätt med efterföljande steg...
}
```
 Förklaring: I det här steget skapar vi en ny GDB-datauppsättning med hjälp av`Dataset.Create` metod. Vi anger sökvägen och drivrutinen (FileGdb) för att skapa en filgeodatabas. Konsolutmatningen visar det initiala lagerantalet, vilket är noll vid denna tidpunkt.
## Steg 2: Skapa och fyll i lager_1
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
Förklaring: Det här steget innebär att man skapar ett lager med namnet "lager_1" i datamängden. Den definierar ett attribut som heter "värde" av heltalstyp och fyller lagret med tio funktioner, som var och en har en punktgeometri.
## Steg 3: Skapa och fyll i lager_2
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
Förklaring: Här skapar vi ett andra lager med namnet "layer_2" och lägger till en enda funktion med en linjesträngsgeometri.
## Steg 4: Kontrollera antalet uppdaterade lager
```csharp
Console.WriteLine(dataset.LayersCount); // Utgång: 2
```
Förklaring: Slutligen kontrollerar vi antalet uppdaterade lager efter att ha lagt till de två lagren. I det här fallet bör utgången vara 2.
## Slutsats
Grattis! Du har framgångsrikt skapat en ny File GDB-datauppsättning och fyllt den med lager med Aspose.GIS för .NET. Denna handledning ger en grundläggande förståelse för att arbeta med geospatial data i en .NET-miljö.
## Vanliga frågor
### F: Kan jag använda Aspose.GIS för .NET med andra GIS-bibliotek?
Aspose.GIS för .NET är en fristående verktygslåda; Du kan dock integrera den med andra .NET-bibliotek för att förbättra funktionaliteten.
### F: Finns det ett communityforum för Aspose.GIS-stöd?
 Ja, du kan hitta stöd och diskussioner på[Aspose.GIS Forum](https://forum.aspose.com/c/gis/33).
### F: Hur kan jag få en tillfällig licens för Aspose.GIS?
 Besök[Tillfällig licens](https://purchase.aspose.com/temporary-license/) sida för information om att få en tillfällig licens.
### F: Finns det ytterligare exempel och dokumentation tillgänglig?
 Utforska[Aspose.GIS-dokumentation](https://reference.aspose.com/gis/net/) för fler exempel och detaljerad information.
### F: Var kan jag köpa Aspose.GIS för .NET?
 Du kan köpa Aspose.GIS för .NET på[köpsidan](https://purchase.aspose.com/buy).
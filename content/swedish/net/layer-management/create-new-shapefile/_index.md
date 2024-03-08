---
title: Skapa ny Shapefil
linktitle: Skapa ny Shapefil
second_title: Aspose.GIS .NET API
description: Lär dig hur du skapar en ny shapefil med Aspose.GIS för .NET. Följ vår steg-för-steg-guide och lås upp kraften i manipulering av rumslig data.
type: docs
weight: 12
url: /sv/net/layer-management/create-new-shapefile/
---
## Introduktion
Om du fördjupar dig i utveckling av geografiska informationssystem (GIS) med .NET, är Aspose.GIS din bästa lösning. Detta kraftfulla bibliotek ger utvecklare möjlighet att arbeta sömlöst med rumslig data, och i denna handledning guidar vi dig genom processen att skapa en ny shapefil med Aspose.GIS för .NET.
## Förutsättningar
Innan vi går in i handledningen, se till att du har följande förutsättningar på plats:
- Grundläggande förståelse för programmeringsspråket C#.
- Visual Studio installerat på din dator.
-  Aspose.GIS för .NET-bibliotek. Du kan ladda ner den[här](https://releases.aspose.com/gis/net/).
## Importera namnområden
Börja med att importera de nödvändiga namnrymden för att dra nytta av funktionaliteten i Aspose.GIS:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Steg 1: Konfigurera ditt projekt
Börja med att skapa ett nytt C#-projekt i Visual Studio och inkludera Aspose.GIS-biblioteket.
## Steg 2: Definiera dokumentkatalogen
```csharp
string dataDir = "Your Document Directory";
```
Ersätt "Din dokumentkatalog" med den faktiska sökvägen där du vill spara din nya shapefil.
## Steg 3: Skapa ett VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //lägg till attribut innan du lägger till funktioner
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Detta kodsegment ställer in vektorlagret och definierar attribut för dina funktioner.
## Steg 4: Lägg till funktioner
### Fall 1: Anger värden individuellt
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
### Fall 2: Anger nya värden för alla attribut
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## Slutsats
 Grattis! Du har framgångsrikt skapat en ny shapefil med Aspose.GIS för .NET. Denna handledning täckte grunderna för att ställa in ditt projekt, definiera attribut och lägga till funktioner. När du utforskar vidare, se[dokumentation](https://reference.aspose.com/gis/net/) för avancerade funktioner och funktioner.
## Vanliga frågor
### F: Kan jag använda Aspose.GIS med andra programmeringsspråk?
Aspose.GIS stöder i första hand .NET, men det finns versioner tillgängliga för Java också.
### F: Finns det en gratis provperiod?
 Ja, du kan komma åt den kostnadsfria provperioden[här](https://releases.aspose.com/).
### F: Var kan jag hitta support för Aspose.GIS?
 Besök[Aspose.GIS forum](https://forum.aspose.com/c/gis/33) för samhällsstöd och diskussioner.
### F: Hur kan jag få en tillfällig licens?
 Skaffa din tillfälliga licens[här](https://purchase.aspose.com/temporary-license/).
### F: Var kan jag köpa Aspose.GIS för .NET?
 Du kan köpa biblioteket[här](https://purchase.aspose.com/buy).
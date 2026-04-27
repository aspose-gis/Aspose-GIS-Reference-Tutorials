---
date: 2026-01-13
description: Lär dig hur du skapar en ny shapefil med Aspose.GIS för .NET. Denna steg‑för‑steg‑guide
  visar hur du definierar ett vektorlager, lägger till ett datumattribut och hanterar
  rumsliga data.
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
title: Skapa ny shapefil
url: /sv/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa ny shapefile

## Introduktion
Om du ger dig in i geografiska informationssystem (GIS)‑utveckling med .NET är Aspose.GIS din självklara lösning. Detta kraftfulla bibliotek gör det möjligt för utvecklare att arbeta sömlöst med rumsliga data, och i den här handledningen guidar vi dig genom hur du **skapar en ny shapefile** med Aspose.GIS för .NET. Du får se varför det är viktigt att definiera ett vektorlager och lägga till ett datumattribut för robusta GIS‑projekt.

## Snabba svar
- **Vad lär den här handledningen ut?** Hur du skapar en ny shapefile, definierar ett vektorlager och lägger till attribut (inklusive ett datumfält).  
- **Vilket bibliotek krävs?** Aspose.GIS för .NET.  
- **Behöver jag en licens?** En gratis provversion räcker för inlärning; en kommersiell licens krävs för produktion.  
- **Vilken IDE bör jag använda?** Visual Studio (valfri nyare version).  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för det grundläggande exemplet.

## Förutsättningar
Innan vi hoppar in i handledningen, se till att du har följande förutsättningar på plats:
- Grundläggande förståelse för programmeringsspråket C#.  
- Visual Studio installerat på din maskin.  
- Aspose.GIS för .NET‑biblioteket. Du kan ladda ner det [här](https://releases.aspose.com/gis/net/).

## Importera namnrymder
Börja med att importera de nödvändiga namnrymderna för att utnyttja funktionaliteten i Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Steg 1: Ställ in ditt projekt
Börja med att skapa ett nytt C#‑projekt i Visual Studio och inkludera Aspose.GIS‑biblioteket.

## Steg 2: Definiera dokumentkatalogen
```csharp
string dataDir = "Your Document Directory";
```
Ersätt *Your Document Directory* med den faktiska sökvägen där du vill spara din nya shapefile.

## Steg 3: Skapa ett VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Detta kodsegment **definierar ett vektorlager** och deklarerar tre attribut: ett textfält (`name`), ett heltalsfält (`age`) och ett datum‑tid‑fält (`dob`). Att lägga till datumattributet är avgörande för temporala GIS‑analyser.

## Steg 4: Lägg till funktioner
### Fall 1: Sätt värden individuellt
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
Här skapar vi två punkter, sätter varje attribut separat och lägger till funktionerna i lagret.

### Fall 2: Sätt nya värden för alla attribut
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
I detta tillvägagångssätt fyller vi i alla attributvärden i ett anrop med en objektarray – praktiskt när du har många attribut.

## Varför detta är viktigt
Att programatiskt skapa en shapefile låter dig automatisera datapipelines, generera testdatamängder eller integrera GIS‑utdata direkt i webbtjänster. Genom att behärska **hur man skapar shapefile** med Aspose.GIS får du full kontroll över geometrin, attributschemat och filformatets efterlevnad.

## Vanliga fallgropar & tips
- **Sökvägsavgränsare:** Använd `Path.Combine` för plattformsoberoende kompatibilitet istället för strängkonkatenering.  
- **Attributordning:** Ordningen på värdena i `SetValues` måste matcha den ordning du lade till attributen.  
- **Datumhantering:** Använd alltid `DateTimeKind.Utc` om dina GIS‑data ska delas över tidszoner.

## Slutsats
Grattis! Du har framgångsrikt skapat en ny shapefile med Aspose.GIS för .NET. Denna handledning täckte grunderna för att sätta upp ditt projekt, definiera ett vektorlager och lägga till funktioner – inklusive ett datumattribut. När du utforskar vidare, hänvisa till [dokumentationen](https://reference.aspose.com/gis/net/) för avancerade funktioner och möjligheter.

## Vanliga frågor
### Q: Kan jag använda Aspose.GIS med andra programmeringsspråk?
Aspose.GIS stödjer främst .NET, men det finns även versioner för Java.  

### Q: Finns det en gratis provversion?
Ja, du kan komma åt den gratis provversionen [här](https://releases.aspose.com/).  

### Q: Var kan jag hitta support för Aspose.GIS?
Besök [Aspose.GIS‑forumet](https://forum.aspose.com/c/gis/33) för community‑support och diskussioner.  

### Q: Hur får jag en tillfällig licens?
Skaffa din tillfälliga licens [här](https://purchase.aspose.com/temporary-license/).  

### Q: Var kan jag köpa Aspose.GIS för .NET?
Du kan köpa biblioteket [här](https://purchase.aspose.com/buy).

---

**Senast uppdaterad:** 2026-01-13  
**Testat med:** Aspose.GIS 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
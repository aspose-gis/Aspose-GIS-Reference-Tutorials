---
date: 2026-06-30
description: Lär dig hur du skapar shapefile med Aspose.GIS för .NET. Denna steg‑för‑steg‑guide
  visar hur du definierar ett vector layer, lägger till ett date attribute och hanterar
  spatial data effektivt.
keywords:
- how to create shapefile
- temporal gis shapefile
- Aspose.GIS vector layer
- GIS data automation
linktitle: Skapa ny Shapefile
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create shapefile using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to define a vector layer, add a date attribute, and manage
    spatial data efficiently.
  headline: How to Create Shapefile with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS primarily supports .NET, but there are versions available for
      Java as well.
    question: Can I use Aspose.GIS with other programming languages?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I find support for Aspose.GIS?
  - answer: Get your temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license?
  - answer: You can buy the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hur du skapar Shapefile med Aspose.GIS för .NET
url: /sv/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa ny shapefile

## Introduktion
Om du fördjupar dig i geografiska informationssystem (GIS)‑utveckling med .NET är Aspose.GIS din självklara lösning för **hur man skapar shapefile** programatiskt. Detta bibliotek ger dig full kontroll över vektorlager, attributscheman och filformatskompatibilitet, så att du kan automatisera datapipelines eller generera testdatamängder på några minuter.

## Snabba svar
- **Vad lär den här handledningen ut?** Hur man skapar en ny shapefile, definierar ett vektorlager och lägger till attribut (inklusive ett datumfält).  
- **Vilket bibliotek krävs?** Aspose.GIS för .NET.  
- **Behöver jag en licens?** En gratis provversion fungerar för lärande; en kommersiell licens krävs för produktion.  
- **Vilken IDE bör jag använda?** Visual Studio (någon nyare version).  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för grundexemplet.

## Hur man skapar shapefile med Aspose.GIS för .NET?
Läs in Aspose.GIS‑biblioteket, ange utdatamappen, skapa ett `VectorLayer`, definiera attribut och lägg till funktioner — detta hela arbetsflöde kan skrivas på under 30 rader C#. Biblioteket hanterar geometrisk skapelse, attributtyper och filskrivning automatiskt, så du behöver inte själv hantera låg‑nivå‑specifikationer för Shapefile.

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
Byt ut *Your Document Directory* mot den faktiska sökvägen där du vill spara din nya shapefile.

## Steg 3: Skapa ett VectorLayer
Klassen `VectorLayer` representerar ett enskilt shapefile‑lager som lagrar geometri och attributdata.  
I detta steg definierar vi ett vektorlager och deklarerar tre attribut: ett textfält (`name`), ett heltalsfält (`age`) och ett datum‑tid‑fält (`dob`). Att lägga till datumattributet är avgörande för **temporal GIS shapefile**‑analyser.

```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```

## Steg 4: Lägg till features
### Fall 1: Sätter värden individuellt
Metoden `SetValues` tilldelar attributvärden till ett feature i den ordning de definierades.  
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
Här skapar vi två punkter, sätter varje attribut separat och lägger till features i lagret.

### Fall 2: Sätter nya värden för alla attribut
Alternativt kan du ange alla attributvärden på en gång med `SetValues` och en objektarray.  
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
I detta tillvägagångssätt fyller vi i alla attributvärden i ett anrop med en objektarray — praktiskt när du har många attribut.

## Varför är detta viktigt?
Att programatiskt skapa en shapefile låter dig automatisera datapipelines, generera testdatamängder eller bädda in GIS‑utdata direkt i webbtjänster. Aspose.GIS stödjer **30+ vektor‑ och rasterformat** och kan skriva shapefiles med hundratals sidor utan att ladda hela filen i minnet, vilket ger både hastighet och skalbarhet.

## Vanliga fallgropar & tips
- **Sökvägsavgränsare:** Använd `Path.Combine` för plattformsoberoende kompatibilitet istället för strängkonkatenering.  
- **Attributordning:** Ordningen på värden i `SetValues` måste matcha den ordning du lade till attribut.  
- **Datumhantering:** Använd alltid `DateTimeKind.Utc` om dina GIS‑data ska delas över tidszoner.

## Slutsats
Grattis! Du har framgångsrikt skapat en ny shapefile med Aspose.GIS för .NET. Denna handledning täckte grunderna för att sätta upp ditt projekt, definiera ett vektorlager och lägga till features — inklusive ett datumattribut. När du utforskar vidare, se [dokumentationen](https://reference.aspose.com/gis/net/) för avancerade funktioner och möjligheter.

## Vanliga frågor
**Q: Kan jag använda Aspose.GIS med andra programmeringsspråk?**  
A: Aspose.GIS stödjer främst .NET, men det finns också versioner för Java.

**Q: Finns det en gratis provversion tillgänglig?**  
A: Ja, du kan komma åt den gratis provversionen [här](https://releases.aspose.com/).

**Q: Var kan jag hitta support för Aspose.GIS?**  
A: Besök [Aspose.GIS‑forum](https://forum.aspose.com/c/gis/33) för community‑support och diskussioner.

**Q: Hur kan jag få en tillfällig licens?**  
A: Skaffa din tillfälliga licens [här](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag köpa Aspose.GIS för .NET?**  
A: Du kan köpa biblioteket [här](https://purchase.aspose.com/buy).

---

**Last Updated:** 2026-06-30  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Relaterade handledningar

- [Hämta lagerattribut – Hämta lagerattributinformation med Aspose.GIS för .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Skapa vektorlager och ange lagerets rumsliga referenssystem](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Skapa vektorlager i File GDB – Aspose.GIS .NET‑handledning](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
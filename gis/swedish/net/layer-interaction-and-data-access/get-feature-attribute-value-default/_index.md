---
date: 2026-01-05
description: Lär dig hur du hämtar attributvärden och anger standardvärden i Aspose.GIS
  för .NET. Denna steg‑för‑steg‑guide visar hur du skapar GeoJSON‑lager och konstruerar
  GIS‑funktioner.
linktitle: How to Get Attribute Value (Default)
second_title: Aspose.GIS .NET API
title: Hur man hämtar attributvärde (standard) med Aspose.GIS för .NET
url: /sv/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man hämtar attributvärde (standard) med Aspose.GIS för .NET

## Introduction
I den här omfattande handledningen kommer du att upptäcka **hur man hämtar attribut**värden från ett GIS‑objekt med Aspose.GIS för .NET, och hur du arbetar med standardvärden när ett attribut saknas. Oavsett om du bygger en rumslig analysmotor eller en enkel kartvisare, är behärskning av attributhämtning och standardhantering avgörande för pålitliga GIS‑applikationer.

## Quick Answers
- **Vad är den primära metoden?** `Feature.GetValueOrDefault<T>()`  
- **Kan jag ange ett eget standardvärde?** Ja, via överlagringen som accepterar ett standardvärde eller genom att definiera `DefaultValue` på attributet.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en kommersiell licens krävs för produktion.  
- **Stödda geometriformat?** GeoJSON, Shapefile, GML och många andra via Aspose.GIS‑drivrutiner.  
- **Fungerar med .NET Core/.NET 6+?** Absolut – biblioteket är plattformsoberoende.

## Prerequisites
Innan vi dyker ner, se till att du har:

- Grundläggande kunskap om C# och .NET‑ekosystemet.  
- Aspose.GIS för .NET installerat. Om du ännu inte har gjort det, ladda ner det från [här](https://releases.aspose.com/gis/net/).  
- En kodredigerare som Visual Studio eller Visual Studio Code.

## Import Namespaces
Lägg till de nödvändiga `using`‑satserna i din C#‑fil så att API‑typerna är tillgängliga:

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Låt oss nu gå igenom varje exempel steg för steg.

## How to Get Attribute Value (Default)
### Step 1: Set up the Environment
Definiera sökvägen till mappen som innehåller dina testdokument:

```csharp
string dataDir = "Your Document Directory";
```

### Step 2: Create a GeoJSON Layer
Vi kommer **skapa geojson‑lager** — den första platsen där vi definierar ett attribut som kan vara null eller odefinierat:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```

### Step 3: Construct a GIS Feature
Nu **konstruerar vi GIS‑objekt** — detta ger oss en ny objektinstans som följer det attributschema vi just definierade:

```csharp
    Feature feature = layer.ConstructFeature();
```

### Step 4: Retrieve Values
Slutligen **hämtar vi attributvärden** för objektet med flera scenarier, vilket demonstrerar hur standardvärden fungerar:

```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // value == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // value == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // value == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```

## How to Set Default Values
### Step 1: Create Another GeoJSON Layer
Denna gång **sätter vi attributstandard** direkt på schemat:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```

### Step 2: Construct a GIS Feature (Again)
```csharp
    Feature feature = layer.ConstructFeature();
```

### Step 3: Retrieve and Set Values
Vi hämtar standardvärdet, och ändrar sedan det för att se effekten av **hur man sätter standard** vid körning:

```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // value == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // value == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // value == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```

## Common Pitfalls & Tips
- **Glöm aldrig att stänga `using`‑blocket.** Lagret tas automatiskt bort, vilket frigör filhandtag.  
- **När `CanBeNull` är falskt, kommer `GetValueOrDefault` alltid att returnera ett värde** (antingen det lagrade eller det definierade standardvärdet).  
- **Använd den generiska överlagringen** (`GetValueOrDefault<T>`) för att undvika boxing/unboxing för värdetyper.  
- **Proffstips:** Om du behöver kontrollera om ett attribut faktiskt är satt, använd `feature.IsAttributeSet("attribute")` innan du anropar `GetValueOrDefault`.

## Frequently Asked Questions
### Is Aspose.GIS compatible with .NET Core?
Ja, Aspose.GIS är fullt kompatibel med .NET Core och erbjuder plattformsoberoende stöd.

### Can I use Aspose.GIS for commercial projects?
Absolut! Aspose.GIS levereras med en kommersiell licens som låter dig använda den i dina kommersiella applikationer utan några begränsningar.

### Where can I find additional support and resources?
Besök [Aspose.GIS forumet](https://forum.aspose.com/c/gis/33) för community‑support och utforska [dokumentationen](https://reference.aspose.com/gis/net/) för djupgående information.

### Is there a free trial available?
Ja, du kan utforska Aspose.GIS med en gratis provversion. Ladda ner den [här](https://releases.aspose.com/).

### How do I obtain a temporary license for testing purposes?
För tillfälliga licenser, besök [här](https://purchase.aspose.com/temporary-license/).

## Additional FAQ
**Q: Vad händer om jag anropar `GetValueOrDefault` på ett attribut som inte finns?**  
A: Metoden kastar ett `ArgumentException`. Verifiera alltid attributnamnet eller använd `feature.HasAttribute("name")` först.

**Q: Kan jag ändra standardvärdet efter att lagret har skapats?**  
A: Ja, du kan ändra `attribute.DefaultValue` och sedan anropa `layer.UpdateAttribute(attribute)` för att spara ändringen.

**Q: Stöder Aspose.GIS massuppdateringar av attributvärden?**  
A: Du kan iterera över en funktionssamling och anropa `SetValue` på varje funktion; för stora dataset, överväg att använda `FeatureCursor`‑API:t för bättre prestanda.

## Conclusion
I den här guiden har vi gått igenom **hur man hämtar attribut**värden, hur man definierar och åsidosätter standardvärden, samt hur man **skapar GeoJSON‑lager**‑scheman som passar dina applikationsbehov. Med dessa tekniker kan du bygga robusta GIS‑lösningar som elegant hanterar saknade eller valfria data.

---

**Last Updated:** 2026-01-05  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
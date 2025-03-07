---
title: Få funktionsattributvärde (standard)
linktitle: Få funktionsattributvärde (standard)
second_title: Aspose.GIS .NET API
description: Lås upp kraften i Aspose.GIS för .NET! Hämta och manipulera funktionsattributvärden utan ansträngning med denna steg-för-steg-guide. Ladda ner din testversion nu!
weight: 14
url: /sv/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Få funktionsattributvärde (standard)

## Introduktion
Välkommen till Aspose.GIS-världen för .NET! I den här omfattande guiden kommer vi att dyka ner i krångligheterna med att hämta funktionsattributvärden med de kraftfulla funktionerna i Aspose.GIS. Oavsett om du är en erfaren utvecklare eller precis har börjat, kommer den här handledningen att ge dig en steg-för-steg-genomgång, vilket säkerställer att du utnyttjar den fulla potentialen i detta enastående verktyg.
## Förutsättningar
Innan vi ger oss ut på detta kodningsäventyr, se till att du har följande förutsättningar på plats:
- En praktisk kunskap om C# och .NET framework.
-  Aspose.GIS för .NET installerat. Om inte, ladda ner den från[här](https://releases.aspose.com/gis/net/).
- En kodredigerare, som Visual Studio, för att följa med sömlöst.
## Importera namnområden
Se till att inkludera de nödvändiga namnrymden i ditt C#-projekt:
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
Låt oss nu dela upp varje exempel i en serie lätta att följa steg.
## Få funktionsattributvärde (standard)
### Steg 1: Ställ in miljön
Börja med att definiera sökvägen till din dokumentkatalog:
```csharp
string dataDir = "Your Document Directory";
```
### Steg 2: Skapa ett GeoJson-lager
Skapa ett GeoJson-lager och definiera ett attribut med standardvärden:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### Steg 3: Konstruera en funktion
Konstruera en funktion med det definierade attributet:
```csharp
    Feature feature = layer.ConstructFeature();
```
### Steg 4: Hämta värden
Hämta attributvärden med olika scenarier:
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // värde == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // värde == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // värde == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## Ställa in standardvärden
### Steg 1: Skapa ytterligare ett GeoJson-lager
Upprepa processen med ett annat GeoJson-lager och ett dubbelt attribut:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### Steg 2: Konstruera en funktion (igen)
```csharp
    Feature feature = layer.ConstructFeature();
```
### Steg 3: Hämta och ställ in värden
Hämta och ställ in attributvärden, visa standardvärden:
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // värde == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // värde == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // värde == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
Grattis! Du har framgångsrikt utnyttjat kraften i Aspose.GIS för .NET för att hämta och manipulera funktionsattributvärden.
## Slutsats
I den här handledningen har vi utforskat nyanserna av att hämta funktionsattributvärden med Aspose.GIS för .NET. Med sitt intuitiva API och robusta möjligheter öppnar Aspose.GIS upp en värld av möjligheter för GIS-utveckling i .NET-miljöer.
## Vanliga frågor
### Är Aspose.GIS kompatibel med .NET Core?
Ja, Aspose.GIS är helt kompatibelt med .NET Core, vilket ger plattformsoberoende stöd.
### Kan jag använda Aspose.GIS för kommersiella projekt?
Absolut! Aspose.GIS kommer med en kommersiell licens som tillåter dig att använda den i dina kommersiella applikationer utan några begränsningar.
### Var kan jag hitta ytterligare support och resurser?
 Besök[Aspose.GIS forum](https://forum.aspose.com/c/gis/33) för samhällsstöd och utforska[dokumentation](https://reference.aspose.com/gis/net/) för fördjupad information.
### Finns det en gratis provperiod?
 Ja, du kan utforska Aspose.GIS med en gratis provperiod. Ladda ner det[här](https://releases.aspose.com/).
### Hur får jag en tillfällig licens för teständamål?
 För tillfälliga licenser, besök[här](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

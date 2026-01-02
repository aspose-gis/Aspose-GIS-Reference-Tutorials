---
date: 2026-01-02
description: Lär dig hur du lägger till en punktfunktion samtidigt som du anger fältnamn
  och läser objekt‑ID med Aspose.GIS för .NET. Steg‑för‑steg‑guide för utvecklare.
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
title: Lägg till punktfunktion och specificera objekt‑ID och geometrifältnamn
url: /sv/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till punktfunktion och specificera objekt‑ID och geometri‑fältnamn

## Introduktion
Att ge dig in på området Geographic Information Systems (GIS) med Aspose.GIS för .NET öppnar en värld av möjligheter för utvecklare och entusiaster. I den här handledningen **kommer du att lära dig hur du lägger till en punktfunktion** samtidigt som du **anger fältnamn** och **läser objekt‑ID‑värden**, vilket ger dig full kontroll över dina rumsliga data.

## Snabba svar
- **Vad är huvudsyftet med den här guiden?** Att visa hur man lägger till en punktfunktion och konfigurerar objekt‑ID‑ och geometri‑fältnamn.  
- **Vilket bibliotek används?** Aspose.GIS för .NET.  
- **Behöver jag en licens?** En gratis provversion finns tillgänglig; en licens krävs för produktion.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Kan jag läsa objekt‑ID efter insättning?** Ja – handledningen demonstrerar hur man läser objekt‑ID från lagret.

## Förutsättningar
Innan du dyker ner i handledningen, se till att du har följande förutsättningar på plats:
- Aspose.GIS för .NET: Ladda ner och installera biblioteket från [here](https://releases.aspose.com/gis/net/).
- Dokumentkatalog: Skapa en katalog för dina dokument där du lagrar geodatabaserna.
- .NET‑miljö: Se till att du har en fungerande .NET‑miljö.

## Importera namnrymder
För att komma igång behöver du importera de nödvändiga namnrymderna till ditt projekt. Dessa namnrymder tillhandahåller de grundläggande klasserna och metoderna för att interagera med Aspose.GIS för .NET.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Steg 1: Lägg till punktfunktion och specificera objekt‑ID och geometri‑fältnamn
I detta steg lär du dig hur du ställer in objekt‑ID‑ och geometri‑fältnamnen för dina GIS‑data. Detta är avgörande för effektiv datahantering och för att kunna **läsa objekt‑ID** senare.

### Steg 1.1: Ange dokumentkatalog
Börja med att definiera sökvägen till din dokumentkatalog:

```csharp
string dataDir = "Your Document Directory";
```

### Steg 1.2: Skapa en GeoDatabase och definera alternativ
Skapa en GeoDatabase med de önskade **fältnamnen** för objekt‑ID och geometri:

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

### Steg 1.3: Skapa och lägg till ett lager
Skapa ett lager i GeoDatabase och lägg till en funktion som representerar en punktgeometri:

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

### Steg 1.4: Öppna och hämta data från lagret
Öppna lagret och hämta den funktion du just lagt till. Detta demonstrerar hur du **läser objekt‑ID** från datasetet:

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Varför ange anpassade fältnamn?
Att anpassa objekt‑ID‑ och geometri‑fältnamnen ger dig flexibilitet när du integrerar med befintliga databaser eller följer namngivningskonventioner som krävs av efterföljande applikationer. Det gör också data mer själv‑beskrivande, vilket förenklar underhåll och samarbete.

## Vanliga fallgropar och felsökning
- **Saknad katalog** – Se till att `dataDir` pekar på en befintlig mapp; annars kastar `Dataset.Create` ett undantag.
- **Fältnamnskonflikter** – Om ett fält med samma namn redan finns i geodatabasen misslyckas skapandet. Välj unika namn.
- **Spatial referens‑mismatch** – Matcha alltid det rumsliga referenssystemet (t.ex. WGS84) med de data du avser att lagra.

## Slutsats
Grattis! Du har nu lärt dig hur du **lägger till punktfunktion**, **anger fältnamn** och **läser objekt‑ID** med Aspose.GIS för .NET. Denna grund ger dig möjlighet att bygga robusta GIS‑applikationer och hantera rumsliga data med självförtroende.

## Vanliga frågor
### Fråga: Kan jag använda Aspose.GIS för .NET i mina webbapplikationer?
**Svar:** Ja, Aspose.GIS för .NET är lämpligt för både skrivbords‑ och webbapplikationer och erbjuder mångsidiga geospatiala funktioner.

### Fråga: Finns det en provversion tillgänglig innan jag köper?
**Svar:** Ja, du kan utforska funktionerna i Aspose.GIS för .NET med en gratis provversion som finns [here](https://releases.aspose.com/).

### Fråga: Hur kan jag skaffa en temporär licens för Aspose.GIS för .NET?
**Svar:** Du kan få en temporär licens [here](https://purchase.aspose.com/temporary-license/) för utvärderingsändamål.

### Fråga: Vilka rumsliga referenssystem stödjer Aspose.GIS för .NET?
**Svar:** Aspose.GIS för .NET stödjer olika rumsliga referenssystem, vilket ger flexibilitet för olika geografiska dataset.

### Fråga: Var kan jag söka hjälp eller diskutera frågor relaterade till Aspose.GIS?
**Svar:** Besök Aspose.GIS‑forumet [here](https://forum.aspose.com/c/gis/33) för support och diskussioner.

## Ytterligare vanliga frågor

**Fråga: Kan jag ändra objekt‑ID‑fältet efter att lagret har skapats?**  
**Svar:** Nej. Fältnamnet definieras när lagret skapas; du måste återskapa lagret med ett nytt `FileGdbOptions`‑objekt för att ändra det.

**Fråga: Hur hämtar jag andra attributvärden förutom objekt‑ID?**  
**Svar:** Använd `feature.GetValue<T>("FieldName")` där `FieldName` är namnet på det attribut du vill läsa.

**Fråga: Är det möjligt att lägga till flera punktfunktioner i ett batch?**  
**Svar:** Ja. Loopa igenom dina data, skapa en funktion för varje punkt, sätt dess geometri och anropa `layer.Add(feature)` inom samma `using`‑block.

**Fråga: Stöder Aspose.GIS andra geometri‑typer?**  
**Svar:** Absolut. Du kan arbeta med `LineString`, `Polygon`, `MultiPoint` och fler genom att skapa motsvarande geometriobjekt.

**Fråga: Vad händer om jag försöker läsa ett objekt‑ID som inte finns?**  
**Svar:** Att komma åt ett index utanför intervallet (t.ex. `layer[10]` när bara en funktion finns) kastar ett `IndexOutOfRangeException`. Kontrollera alltid `layer.Count` först.

---

**Last Updated:** 2026-01-02  
**Tested With:** Aspose.GIS for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
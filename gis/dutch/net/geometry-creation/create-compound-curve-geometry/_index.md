---
date: 2026-02-15
description: Leer hoe je krommen kunt toevoegen en samengestelde kromme geometrieën
  kunt maken in .NET met Aspose.GIS voor naadloze verwerking van geospatiale gegevens.
linktitle: How to Add Curves – Compound Curve Geometry
second_title: Aspose.GIS .NET API
title: Hoe krommen toe te voegen - Samengestelde kromme geometrie met Aspose.GIS
url: /nl/net/geometry-creation/create-compound-curve-geometry/
weight: 19
---

.

Also keep shortcodes at top and bottom.

Let's craft final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe krommen toe te voegen: samengestelde kromme geometrie met Aspose.GIS

## Inleiding
In de wereld van .NET‑ontwikkeling is het leren **hoe krommen toe te voegen** met Aspose.GIS essentieel voor het bouwen van geavanceerde geospatiale toepassingen. Of je nu interactieve kaarten maakt, ruimtelijke analyses uitvoert of complexe GIS‑datasets genereert, Aspose.GIS biedt de tools die je nodig hebt om snel en betrouwbaar met geavanceerde geometrieën te werken. Deze gids leidt je stap voor stap door het volledige proces van **hoe krommen toe te voegen** en ze samen te voegen tot één herbruikbare samengestelde kromme geometrie.

## Snelle antwoorden
- **Wat is het primaire doel?** Krommen toevoegen en een samengestelde kromme geometrie bouwen in een Shapefile.  
- **Welke bibliotheek wordt gebruikt?** Aspose.GIS voor .NET.  
- **Voorvereisten?** Visual Studio, Aspose.GIS geïnstalleerd, en een basis C#‑project.  
- **Typische implementatietijd?** Ongeveer 10‑15 minuten voor een werkend voorbeeld.  
- **Ondersteund uitvoerformaat?** Shapefile (maar dezelfde aanpak werkt voor GeoJSON, KML, enz.).

## Wat is een samengestelde kromme?
Een **samengestelde kromme** is een enkele geometrie die bestaat uit meerdere verbonden kromme‑componenten—rechte lijnreeksen en cirkelbogen—samengevoegd tot een complexere vorm. Deze structuur is nuttig wanneer een enkele eenvoudige lijn het gewenste pad niet nauwkeurig kan weergeven, zoals wegen met bochten of riviermeanders.

## Waarom Aspose.GIS gebruiken voor het toevoegen van krommen?
- **Rijke geometrie‑API:** Ondersteunt line strings, circular strings en samengestelde krommen out‑of‑the‑box.  
- **Cross‑platform:** Werkt met .NET Framework, .NET Core en .NET 5/6+.  
- **Geen externe afhankelijkheden:** Geen native GIS‑bibliotheken of COM‑interop nodig.  
- **Gemakkelijk te exporteren:** Direct schrijven naar Shapefile, GeoJSON, KML en vele andere formaten.

## Waarom dit belangrijk is
Krommen toevoegen stelt je in staat om real‑world kenmerken nauwkeuriger te modelleren, wat de visuele kwaliteit van kaartrenderingen verbetert en de precisie van ruimtelijke analyses zoals nabijheidszoekopdrachten of netwerk‑routing verhoogt. Door **hoe krommen toe te voegen** te beheersen, kun je de getrouwheid van elke GIS‑gedreven .NET‑oplossing verhogen.

## Veelvoorkomende gebruikssituaties
- **Transportnetwerken:** Modelleer snelwegen, spoorwegen of fietspaden met vloeiende bochten.  
- **Hydrologie:** Geef rivierlopen weer die natuurlijke bogen volgen.  
- **Stedelijke planning:** Teken perceelgrenzen met gebogen secties.  
- **Aangepaste symbolen:** Maak decoratieve of schematische vormen voor kaartlegenda’s.

## Voorvereisten
- **Visual Studio** geïnstalleerd op je werkstation.  
- **Aspose.GIS voor .NET** gedownload van de [download page](https://releases.aspose.com/gis/net/).  
- Een C#‑project dat target .NET 6 (of een andere ondersteunde versie).

## Namespaces importeren
Om met Aspose.GIS te werken, importeer je de benodigde namespaces bovenaan je C#‑bestand:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Stapsgewijze handleiding om een samengestelde kromme geometrie te maken

### Stap 1: Definieer het uitvoerpad
Vertel eerst de bibliotheek waar het resultaat moet worden weggeschreven. Vervang de placeholder door een echte map op je computer.

```csharp
string path = "Your Document Directory" + "CreateCompoundCurve_out.shp";
```

### Stap 2: Maak een VectorLayer aan
Een `VectorLayer` fungeert als container voor ruimtelijke features. Alle geometriewerk gebeurt binnen dit `using`‑blok, dat bovendien garandeert dat bronnen correct worden vrijgegeven.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block for creating the compound curve geometry will be inserted here.
}
```

### Stap 3: Construeer de Compound Curve‑feature
Binnen de laag maken we een nieuwe feature en een leeg `CompoundCurve`‑object dat de individuele kromme‑onderdelen zal bevatten.

```csharp
var feature = layer.ConstructFeature();
var compoundCurve = new CompoundCurve();
```

### Stap 4: Definieer componentkrommen
Hier bereiden we vijf afzonderlijke stukken voor—twee rechte `LineString`s, twee `CircularString`‑bogen en een laatste `LineString`. Deze stukken worden aan elkaar gekoppeld om de volledige samengestelde kromme te vormen.

```csharp
var bottom = (ILineString)Geometry.FromText("LineString (0 0, 3 0)");
var firstArc = (ICircularString)Geometry.FromText("CircularString (3 0, 4 1, 3 2)");
var middle = (ILineString)Geometry.FromText("LineString (3 2, 1 2)");
var secondArc = (ICircularString)Geometry.FromText("CircularString (1 2, 0 3, 1 4)");
var top = (ILineString)Geometry.FromText("LineString (1 4, 4 4)");
```

### Stap 5: Voeg componentkrommen toe aan de samengestelde kromme
Elke component wordt in volgorde toegevoegd, zodat de geometrie continu en correct georiënteerd blijft.

```csharp
compoundCurve.AddCurve(bottom);
compoundCurve.AddCurve(firstArc);
compoundCurve.AddCurve(middle);
compoundCurve.AddCurve(secondArc);
compoundCurve.AddCurve(top);
```

### Stap 6: Wijs geometrie toe aan de feature
Nu wordt de samengestelde `CompoundCurve` de geometrie van de feature die we gaan opslaan.

```csharp
feature.Geometry = compoundCurve;
```

### Stap 7: Voeg de feature toe aan de laag
Tot slot schrijven we de feature naar de Shapefile. Wanneer het `using`‑blok eindigt, wordt het bestand gesloten en is het klaar voor gebruik in elke GIS‑applicatie.

```csharp
layer.Add(feature);
```

## Veelvoorkomende problemen & tips
- **Coördinaatvolgorde:** Aspose.GIS verwacht coördinaten in `X Y`‑volgorde (longitude, latitude). Het verwisselen van de volgorde kan omgekeerde geometrieën opleveren.  
- **CircularString‑syntaxis:** Zorg ervoor dat het middelste punt van een `CircularString` op de beoogde boog ligt; anders kan de kromme afgevlakt worden.  
- **Bestand overschrijven:** Als de doel‑Shapefile al bestaat, zal `VectorLayer.Create` deze zonder waarschuwing overschrijven—gebruik een unieke bestandsnaam tijdens ontwikkeling.  
- **Prestaties:** Voor grote datasets kun je beter features in batches toevoegen in plaats van één voor één binnen het `using`‑blok.  
- **Pro tip:** Hergebruik hetzelfde `CompoundCurve`‑object bij het maken van meerdere gelijkaardige features; roep `compoundCurve.Clear()` aan voordat je het opnieuw vult.

## Veelgestelde vragen

**Q: Kan ik Aspose.GIS voor .NET gebruiken met andere .NET‑frameworks?**  
**A:** Ja, Aspose.GIS voor .NET werkt met .NET Framework, .NET Core en .NET Standard.

**Q: Ondersteunt Aspose.GIS het lezen en schrijven van verschillende geospatiale bestandsformaten?**  
**A:** Absoluut! Het ondersteunt Shapefile, GeoJSON, KML, GML en nog veel meer formaten.

**Q: Is Aspose.GIS geschikt voor zowel desktop‑ als webapplicaties?**  
**A:** Ja, de bibliotheek kan worden gebruikt in desktop‑, web‑ en cloudservices.

**Q: Kan ik ruimtelijke analyses uitvoeren met Aspose.GIS voor .NET?**  
**A:** Ja, je kunt afstanden berekenen, geometrische bewerkingen uitvoeren en ruimtelijke queries uitvoeren.

**Q: Waar kan ik community‑ondersteuning vinden voor Aspose.GIS?**  
**A:** Bezoek het [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) om vragen te stellen en ideeën te delen.

---

**Laatst bijgewerkt:** 2026-02-15  
**Getest met:** Aspose.GIS voor .NET (latest stable release)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
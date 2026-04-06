---
date: 2026-04-06
description: Leer hoe u krommen naar lijnen kunt omzetten en geometrie kunt lineariseren
  met Aspose.GIS voor .NET, waardoor snelle geospatiale verwerking en analyse in uw
  .NET‑toepassingen mogelijk wordt.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS linearize geometry
linktitle: Lineariseer een geometrie
second_title: Aspose.GIS .NET API
title: Krommen converteren naar lijnen met Aspose.GIS voor .NET
url: /nl/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converteer Curves naar Lijnen met Aspose.GIS voor .NET

## Introductie
Als u **curves naar lijnen moet converteren** voor cartografie, ruimtelijke analyse of gegevens‑uitwisselingstaken, biedt Aspose.GIS voor .NET een nette, programmeerbare manier om dit te doen. In deze tutorial lopen we een volledig, real‑world voorbeeld door dat laat zien hoe u een complexe geometrie—met curves en samengestelde vormen—omzet in een eenvoudige lineaire weergave die met elk GIS‑systeem werkt.

## Snelle Antwoorden
- **Wat betekent het lineariseren van een geometrie?** Curves en complexe vormen omzetten in rechte‑lijnsegmenten.  
- **Waarom Aspose.GIS gebruiken?** Het ondersteunt tientallen GIS‑formaten en verwerkt geometrieconversie zonder externe tools.  
- **Vereisten?** .NET Framework of .NET Core, Visual Studio en de Aspose.GIS‑bibliotheek.  
- **Hoe lang duurt het voorbeeld?** Minder dan vijf minuten om uit te voeren zodra de bibliotheek is geïnstalleerd.  
- **Kan ik opslaan in andere formaten?** Ja—vervang de KML‑driver door Shapefile, GeoJSON, enz.

## Wat is het lineariseren van geometrie?
Het lineariseren van geometrie betekent het opdelen van elke gebogen of samengestelde vorm in een reeks rechte‑lijnsegmenten (een “lineaire geometrie”). Dit vereenvoudigt weergave, analyse en interoperabiliteit met tools die alleen lijnen en punten begrijpen.

## Waarom curves naar lijnen converteren?
- **Prestaties:** Lineaire geometrieën renderen en queryen sneller.  
- **Compatibiliteit:** Veel GIS‑platformen (bijv. oudere kaartservices) accepteren alleen lineaire objecten.  
- **Vereenvoudiging:** Handig voor het maken van miniaturen, snelle previews, of het voeden van gegevens aan algoritmen die lineaire invoer vereisen.

## Vereisten
Before diving into the code, make sure you have:

1. **Aspose.GIS for .NET** – download het van de [Aspose.GIS website](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (of .NET Core) geïnstalleerd op uw ontwikkelmachine.  
3. **Visual Studio** (of een andere C#‑compatibele IDE) om het voorbeeld te schrijven en uit te voeren.

## Namespaces importeren
Om Aspose.GIS-functionaliteit te gebruiken, importeert u de vereiste namespaces.

### Stap 1: Importeer de Aspose.GIS Core Namespaces
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Stap 2: Importeer de driver voor uw doelformaat
Voor dit voorbeeld schrijven we het resultaat naar een KML‑bestand:
```csharp
using Aspose.GIS.Kml;
```

## Hoe curves naar lijnen te converteren – Stapsgewijze gids
Hieronder vindt u een gedetailleerde walkthrough van elke code‑regel, met uitleg over **hoe curves naar lijnen te converteren** en waarom elke stap belangrijk is.

### Stap 1: Definieer het uitvoerpad
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Vervang `"Your Document Directory"` door de map waarin u het KML‑bestand wilt opslaan.

### Stap 2: Maak een laag voor het uitvoerbestand
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
Een *laag* is een container voor geografische objecten. Hier maken we een nieuwe KML‑laag die onze gelinieerde geometrie zal bevatten.

### Stap 3: Maak een nieuw object aan
```csharp
var feature = layer.ConstructFeature();
```
Een *object* vertegenwoordigt een enkel geografisch object (punt, lijn, polygoon, enz.). We zullen onze lineaire geometrie aan dit object koppelen.

### Stap 4: Definieer de oorspronkelijke complexe geometrie
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
We maken een geometrie aan vanuit een Well‑Known Text (WKT)‑string. Dit voorbeeld bevat een `LineString`, een `CompoundCurve` en een `CircularString`—perfect om de conversie van curves naar lijnen te demonstreren.

### Stap 5: Lineariseer de geometrie
```csharp
var linear = geometry.ToLinearGeometry();
```
De `ToLinearGeometry()`‑methode zet alle curves om in rechte‑lijnsegmenten, waardoor een *lineaire* versie van de oorspronkelijke geometrie ontstaat.

### Stap 6: Wijs de lineaire geometrie toe aan het object
```csharp
feature.Geometry = linear;
```
Nu bevat het object de vereenvoudigde, lineaire geometrie.

### Stap 7: Voeg het object toe aan de laag
```csharp
layer.Add(feature);
```
Ten slotte voegen we het object toe aan de KML‑laag, die de lineaire geometrie naar het uitvoerbestand schrijft wanneer het `using`‑blok eindigt.

## Veelvoorkomende valkuilen & tips
- **Pad‑scheidingstekens:** Gebruik `Path.Combine` voor platform‑onafhankelijke padopbouw.  
- **Grote geometrieën:** Het lineariseren van zeer complexe vormen kan veel vertices opleveren; overweeg `Simplify()` te gebruiken na het lineariseren als u minder punten nodig heeft.  
- **Driver‑selectie:** Als u een ander uitvoerformaat nodig heeft, vervang `Drivers.Kml` door `Drivers.Shapefile`, `Drivers.GeoJson`, enz., en pas de bestandsextensie dienovereenkomstig aan.

## Veelgestelde vragen (Verbeterd)

**V: Is Aspose.GIS for .NET compatibel met .NET Core?**  
A: Ja, Aspose.GIS for .NET werkt met .NET Core, waardoor u cross‑platform applicaties kunt bouwen.

**V: Kan ik met verschillende GIS‑bestandsformaten werken met Aspose.GIS for .NET?**  
A: Absoluut! Aspose.GIS ondersteunt KML, Shapefile, GeoJSON en vele andere formaten.

**V: Biedt Aspose.GIS ondersteuning voor ruimtelijke bewerkingen en analyses?**  
A: Ja, het biedt een breed scala aan ruimtelijke bewerkingen en analysemogelijkheden om complexe georuimtelijke taken te verwerken.

**V: Is er een gratis proefversie beschikbaar voor Aspose.GIS for .NET?**  
A: Ja, u kunt een gratis proefversie downloaden van de [Aspose website](https://releases.aspose.com/).

**V: Waar kan ik hulp en ondersteuning vinden voor Aspose.GIS?**  
A: Bezoek het [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) voor hulp van de community en het Aspose‑ondersteuningsteam.

### Aanvullende V&A

**V: Kan ik geometrieën lineariseren die 3D (Z) coördinaten bevatten?**  
A: Ja, `ToLinearGeometry()` werkt met zowel 2D‑ als 3D‑geometrieën; de Z‑waarden worden behouden in de resulterende lijnsegmenten.

**V: Hoe beïnvloedt linearisatie de grootte van het uitvoerbestand?**  
A: Het omzetten van curves naar veel korte lijnsegmenten kan de bestandsgrootte vergroten. Gebruik `Simplify()` na linearisatie als bestandsgrootte een zorg is.

**V: Is het mogelijk de segmentlengte te regelen bij linearisatie?**  
A: De standaardmethode gebruikt een interne tolerantie. Voor aangepaste segmentatie kunt u curves handmatig tesselleren voordat u `ToLinearGeometry()` aanroept.

## Conclusie
In deze tutorial hebben we **hoe curves naar lijnen te converteren** met Aspose.GIS voor .NET behandeld, van het opzetten van de omgeving tot het schrijven van het gelinieerde resultaat naar een KML‑bestand. U kunt deze workflow nu integreren in kaartapplicaties, gegevensverwerkings‑pipelines, of elk GIS‑gerelateerd project dat vereenvoudigde geometrieën vereist.

---

**Last Updated:** 2026-04-06  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
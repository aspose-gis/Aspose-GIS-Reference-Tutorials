---
date: 2026-01-02
description: Leer hoe u GeoJSON naar een stream schrijft in C# met Aspose.GIS voor
  .NET. Bekijk GeoJSON C#-voorbeelden en verbeter uw geospatiale apps.
linktitle: Write GeoJSON to Stream
second_title: Aspose.GIS .NET API
title: Hoe GeoJSON naar stream schrijven met Aspose.GIS voor .NET
url: /nl/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe GeoJSON naar Stream Schrijven

## Introductie
Als je **how to write geojson** direct in een geheugen‑ of bestandsstream in een .NET‑applicatie moet schrijven, ben je op de juiste plek. In deze tutorial lopen we stap voor stap door hoe je GeoJSON naar een stream schrijft met de Aspose.GIS for .NET‑bibliotheek, en laten we ook zien hoe je **display GeoJSON C#** output in de console kunt weergeven. Aan het einde heb je een herbruikbaar patroon dat je in elk geospatiaal project kunt gebruiken.

## Snelle Antwoorden
- **Wat betekent “write GeoJSON to stream”?** Het betekent het serialiseren van een vectorlaag naar het GeoJSON‑formaat en het verzenden van de bytes naar een `Stream`‑object (bijv. `MemoryStream`).  
- **Welke bibliotheek behandelt dit?** Aspose.GIS for .NET biedt een ingebouwde GeoJSON‑driver.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Kan ik dit op Linux uitvoeren?** Ja – Aspose.GIS is cross‑platform en werkt op Windows, Linux en macOS.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Wat is “how to write geojson” in .NET?
Aspose.GIS stelt je in staat een `VectorLayer` te maken, features toe te voegen en vervolgens de laag te serialiseren met de `Drivers.GeoJson`‑driver. De driver schrijft de GeoJSON‑tekst direct naar elke `Stream`, waardoor je volledige controle hebt over waar de gegevens naartoe gaan (geheugen, bestand, netwerk, enz.).

## Waarom Aspose.GIS voor deze taak gebruiken?
- **Zero‑dependency serialisatie** – geen externe JSON‑bibliotheken nodig.  
- **Volledige GeoJSON‑specificatie‑naleving** – ondersteunt FeatureCollections, properties en coördinatenprecisie.  
- **Cross‑platform** – werkt hetzelfde op Windows, Linux en macOS.  
- **Prestaties‑geoptimaliseerd** – schrijft direct naar de stream zonder tussenliggende strings.

## Voorvereisten
1. **Aspose.GIS for .NET** – download het [hier](https://releases.aspose.com/gis/net/).  
2. **Documentdirectory** – bepaal waar je tijdelijke bestanden of output‑streams wilt bewaren.

Laten we nu in de code duiken.

## Namespaces Importeren
Eerst, importeer de namespaces die je toegang geven tot Aspose.GIS‑klassen en standaard .NET I/O‑hulpmiddelen:

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Stap 1: Documentdirectory Instellen
Definieer de map die eventuele tijdelijke bestanden zal bevatten die je nodig hebt.

```csharp
string dataDir = "Your Document Directory";
```

Vervang `"Your Document Directory"` door het daadwerkelijke pad op jouw machine.

## Stap 2: Een Memory Stream Maken
Een `MemoryStream` stelt je in staat de GeoJSON in het geheugen te houden, wat perfect is voor API's of wanneer je de gegevens direct aan een client wilt retourneren.

```csharp
using (var memoryStream = new MemoryStream())
{
    // Subsequent steps will be placed inside this block
}
```

## Stap 3: Een Vector Layer Maken met GeoJSON Driver
Binnen het memory‑stream‑blok, maak een `VectorLayer` die de GeoJSON‑driver gebruikt. Dit vertelt Aspose.GIS de laag als GeoJSON te serialiseren.

```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Feature creation goes here
}
```

## Stap 4: Feature‑attributen Definiëren
Voeg attribuutdefinities toe die als properties in de uiteindelijke GeoJSON‑output zullen verschijnen.

```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Stap 5: Features Maken en Toevoegen
Maak twee voorbeeldpunten, ken attribuutwaarden toe, en voeg ze toe aan de laag.

```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);

// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## Stap 6: GeoJSON C# Output Weergeven
Nadat de laag is gevuld, converteer je de bytes van de stream naar een UTF‑8‑string en schrijf je deze naar de console. Dit toont hoe je **display GeoJSON C#** resultaten kunt weergeven.

```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Je zou een geldige GeoJSON FeatureCollection in de terminal moeten zien afgedrukt.

## Veelvoorkomende Problemen en Oplossingen
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| Lege output | Stream‑positie staat aan het einde bij het lezen | Roep `memoryStream.Position = 0;` aan voordat je converteert naar een string. |
| Ongeldige geometrie | Coördinaten liggen buiten geldige bereiken | Controleer of latitude tussen -90 en 90 ligt, longitude tussen -180 en 180. |
| Licentie‑exception | Uitvoeren zonder een geldige licentie in productie | Pas een tijdelijke of volledige licentie toe met `License license = new License(); license.SetLicense("Aspose.GIS.lic");` |

## Veelgestelde Vragen
### Kan ik Aspose.GIS voor .NET gebruiken in zowel Windows‑ als Linux‑omgevingen?
Ja, Aspose.GIS for .NET is compatibel met zowel Windows als Linux systemen.  

### Is er een gratis proefversie beschikbaar?
Absoluut! Je kunt een gratis proefversie verkennen [hier](https://releases.aspose.com/).  

### Waar kan ik gedetailleerde documentatie vinden?
Bekijk de documentatie [hier](https://reference.aspose.com/gis/net/).  

### Hoe kan ik een tijdelijke licentie krijgen?
Tijdelijke licenties zijn beschikbaar [hier](https://purchase.aspose.com/temporary-license/).  

### Hulp nodig of meer vragen?
Bezoek ons ondersteuningsforum [hier](https://forum.aspose.com/c/gis/33).

## FAQ
**V: Kan ik GeoJSON direct naar een bestand schrijven in plaats van een memory stream?**  
A: Ja—vervang `MemoryStream` door `FileStream` en geef een bestandspad op. Dezelfde driver werkt.

**V: Hoe kan ik de inspringing of opmaak van de gegenereerde GeoJSON controleren?**  
A: Aspose.GIS schrijft standaard compacte JSON. Voor mooi opgemaakte output, verwerk de string nadien met `JsonSerializerOptions { WriteIndented = true }`.

**V: Is het mogelijk om complexere geometrieën (bijv. polygonen) aan de laag toe te voegen?**  
A: Absoluut. Maak een `Polygon`‑ of `LineString`‑object, wijs het toe aan `Feature.Geometry`, en voeg de feature toe zoals hierboven getoond.

**V: Past een grote dataset in een `MemoryStream`?**  
A: Voor zeer grote collecties, overweeg direct naar een bestand te streamen of een `BufferedStream` te gebruiken om hoog geheugenverbruik te vermijden.

**V: Ondersteunt de GeoJSON‑driver CRS‑definities (Coordinate Reference System)?**  
A: Ja—stel de `SpatialReferenceSystem`‑eigenschap van de laag in vóór het toevoegen van features als je een niet‑WGS84 CRS nodig hebt.

## Conclusie
Je hebt nu een compleet, productie‑klaar patroon voor **how to write geojson** naar elke .NET‑stream met behulp van Aspose.GIS. Of je nu GeoJSON wilt retourneren vanuit een web‑API, opslaan in een bestand, of eenvoudigweg weergeven in de console, de bovenstaande stappen dekken de volledige workflow. Verken de bibliotheek verder om met andere formaten zoals Shapefile, KML of GML te werken, en blijf rijkere geospatiale applicaties bouwen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2026-01-02  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose  

---
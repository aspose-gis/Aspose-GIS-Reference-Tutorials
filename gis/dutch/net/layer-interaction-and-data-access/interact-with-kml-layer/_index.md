---
date: 2026-01-07
description: Leer hoe u een KML‑bestand schrijft met Aspose.GIS voor .NET, hoe u KML
  maakt, een booleaanse attribuut toevoegt en een lijnstring maakt in uw toepassingen.
linktitle: Interact with KML Layer
second_title: Aspose.GIS .NET API
title: Hoe een KML‑bestand te schrijven met Aspose.GIS voor .NET
url: /nl/net/layer-interaction-and-data-access/interact-with-kml-layer/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een KML-bestand te schrijven met Aspose.GIS voor .NET

## Introductie
In de data‑gedreven wereld van vandaag geeft de mogelijkheid om **KML-bestand schrijven** programmatisch je de kracht om geografische informatie te delen over verschillende platforms, routes op kaarten te visualiseren en locatiegegevens te integreren in web‑ of mobiele apps. Aspose.GIS voor .NET maakt dit proces eenvoudig, zodat je je kunt concentreren op de logica in plaats van op de complexiteit van het bestandsformaat. In deze tutorial lopen we stap voor stap door het maken van een KML‑laag, het toevoegen van attributen (inclusief een boolean‑attribuut) en het bouwen van een line‑string‑geometrie — allemaal met duidelijke, stap‑voor‑stap code.

## Snelle antwoorden
- **Wat betekent “KML‑bestand schrijven”?** Het genereren van een KML (Keyhole Markup Language) document dat geografische kenmerken beschrijft, zoals punten, lijnen en polygonen.  
- **Welke bibliotheek is het beste voor .NET?** Aspose.GIS voor .NET biedt een vloeiende API voor het maken en bewerken van KML‑bestanden.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie is geschikt voor evaluatie; een licentie is vereist voor productiegebruik.  
- **Kan ik aangepaste attributen toevoegen?** Ja – je kunt string-, integer-, boolean- en double‑attributen toevoegen aan elk object.  
- **Wordt geometriecreatie ondersteund?** Zeker – je kunt punten, lijnstrings, polygonen en meer maken.

## Voorvereisten
Voordat we aan deze reis beginnen, zorg ervoor dat je de volgende voorwaarden hebt:
- Aspose.GIS voor .NET: Download en installeer de bibliotheek vanaf de [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).
- Ontwikkelomgeving: Stel een geschikte ontwikkelomgeving in, zoals Visual Studio, om Aspose.GIS naadloos te integreren in je .NET‑projecten.

## Namespaces importeren
Voordat we beginnen met het werken met KML‑lagen, zorg ervoor dat je de benodigde namespaces in je project opneemt. Deze stap zorgt ervoor dat je toegang hebt tot de klassen en methoden die nodig zijn voor het manipuleren van georuimtelijke gegevens.

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Drawing;
using System.Threading;
using Aspose.Gis.Formats.Kml;
using Aspose.Gis.Formats.Kml.Styles;
using Aspose.Gis.Geometries;
using Point = Aspose.Gis.Geometries.Point;
```

## Stap 1: Stel de documentdirectory in
Definieer het pad naar je documentdirectory waar de KML‑bestanden worden opgeslagen.

```csharp
string dataDir = "Your Document Directory";
```

## Stap 2: Maak een KML‑laag
Initialiseer een KML‑laag met Aspose.GIS, waarbij je het pad voor het KML‑bestand opgeeft.

```csharp
using (var layer = Drivers.Kml.CreateLayer(dataDir + "Kml_File_out.kml"))
{
```

## Stap 3: Definieer attributen (voeg boolean‑attribuut toe)
Voeg attributen toe aan de KML‑laag om verschillende gegevenstypen te vertegenwoordigen, zoals string, integer, **boolean** en double. Dit is waar je “boolean‑attribuut” toevoegt aan elk object.

```csharp
layer.Attributes.Add(new FeatureAttribute("string_data", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("int_data", AttributeDataType.Integer));
layer.Attributes.Add(new FeatureAttribute("bool_data", AttributeDataType.Boolean));
layer.Attributes.Add(new FeatureAttribute("float_data", AttributeDataType.Double));
```

## Stap 4: Construeer en vul objecten (lijnstring maken)
Construeer objecten die georuimtelijke entiteiten vertegenwoordigen en stel waarden in voor de gedefinieerde attributen. Hier **maken we een line string** geometrie om een eenvoudig pad te illustreren.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("string_data", "string value");
feature.SetValue("int_data", 10);
feature.SetValue("bool_data", true);
feature.SetValue("float_data", 3.14);
feature.Geometry = new LineString(new[] { new Point(0, 0), new Point(1, 1) });
layer.Add(feature);
```

## Stap 5: Voeg een ander object toe
Herhaal het proces om een tweede object toe te voegen met andere attribuutwaarden en een null‑geometrie.

```csharp
Feature feature2 = layer.ConstructFeature();
feature2.SetValue("string_data", "string value2");
feature2.SetValue("int_data", 100);
feature2.SetValue("bool_data", false);
feature2.SetValue("float_data", 3.1415);
feature2.Geometry = Geometry.Null;
layer.Add(feature2);
```

## Hoe een KML‑bestand te schrijven – Alles samenvoegen
Door de bovenstaande stappen te volgen, heb je nu een volledig functioneel KML‑bestand dat aangepaste attributen (inclusief een boolean‑vlag) en een line‑string‑geometrie bevat. Je kunt het resulterende `Kml_File_out.kml` openen in Google Earth, ArcGIS of elke GIS‑viewer die KML ondersteunt.

## Veelvoorkomende problemen & probleemoplossing
- **Bestandspad‑fouten** – Zorg ervoor dat `dataDir` eindigt met een pad‑scheidingsteken (`\` of `/`) dat geschikt is voor je besturingssysteem.  
- **Ontbrekende licentie** – De proefversie werkt voor evaluatie, maar een gelicentieerde versie is vereist voor onbeperkt schrijven van KML‑bestanden.  
- **Null‑geometrie** – Het instellen van `Geometry.Null` is opzettelijk voor objecten zonder ruimtelijke gegevens; laat dit weg als je altijd geometrie nodig hebt.

## Veelgestelde vragen
### Is Aspose.GIS compatibel met andere GIS‑formaten?
Ja, Aspose.GIS ondersteunt verschillende GIS‑formaten, waaronder shapefile, GeoJSON en KML.

### Kan ik de met Aspose.GIS gemaakte georuimtelijke gegevens visualiseren?
Absoluut! Aspose.GIS integreert naadloos met kaartbibliotheken, waardoor je je georuimtelijke gegevens kunt visualiseren.

### Is er een proefversie beschikbaar voor Aspose.GIS?
Ja, je kunt de functies van Aspose.GIS verkennen door de [gratis proefversie te downloaden](https://releases.aspose.com/).

### Hoe kan ik ondersteuning krijgen voor Aspose.GIS?
Bezoek het [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) voor community‑ondersteuning of bekijk premium‑ondersteuningsopties [hier](https://purchase.aspose.com/buy).

### Zijn tijdelijke licenties beschikbaar voor Aspose.GIS?
Ja, je kunt een tijdelijke licentie verkrijgen [hier](https://purchase.aspose.com/temporary-license/).

## Aanvullende veelgestelde vragen

**Q: Hoe maak ik **KML**‑bestanden met aangepaste styling?**  
A: Gebruik de `Aspose.Gis.Formats.Kml.Styles` namespace om iconen, lijnkleuren en labelstijlen te definiëren voordat je objecten toevoegt.

**Q: Kan ik grote KML‑bestanden efficiënt schrijven?**  
A: Schrijf objecten in batches en flush de laag periodiek om het geheugenverbruik laag te houden.

**Q: Ondersteunt Aspose.GIS .NET Core en .NET 6+?**  
A: Ja, de bibliotheek is volledig compatibel met .NET Core, .NET 5 en .NET 6.

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.GIS 24.10 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
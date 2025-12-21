---
date: 2025-12-21
description: Leer hoe u een vectorlaag maakt, de linearisatietolerantie instelt en
  een object aan de laag toevoegt met Aspose.GIS voor .NET. Volg deze stapsgewijze
  handleiding om GeoJSON‑bestanden te exporteren.
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: Vectorlaag maken en linearisatietolerantie instellen met Aspose.GIS voor .NET
url: /nl/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vectorlaag maken en linearisatietolerantie instellen met Aspose.GIS voor .NET

## Introductie
Als je **create vector layer** bestanden moet maken, de precisie van krommen moet beheersen, en het resultaat als een GeoJSON‑document wilt exporteren, maakt Aspose.GIS voor .NET dit eenvoudig. In deze tutorial leer je hoe je GeoJSON‑opties configureert, de linearisatietolerantie instelt en **add feature to layer** objecten toevoegt — allemaal terwijl de code schoon en productie‑klaar blijft.

## Snelle antwoorden
- **Wat betekent “create vector layer”?** Het maakt een nieuwe GIS‑vector dataset (bijv. een GeoJSON‑bestand) die geometrieën en attributen kan opslaan.  
- **Hoe stel je de tolerantie in?** Gebruik de `LinearizationTolerance`‑eigenschap van `GeoJsonOptions`.  
- **Kan ik een GeoJSON‑bestand exporteren?** Ja — maak eenvoudig een `VectorLayer` met de `Drivers.GeoJson` driver.  
- **Heb ik een licentie nodig?** Een geldige Aspose.GIS‑licentie ontgrendelt alle functies; een tijdelijke licentie werkt voor evaluatie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Wat is “create vector layer”?
Een vectorlaag maken betekent het initialiseren van een nieuwe GIS‑container (zoals een GeoJSON‑bestand) die geometrische objecten zoals punten, lijnen en polygonen kan bevatten. Deze laag wordt het doelwit voor elke geometrie die je maakt en alle attributen die je toevoegt.

## Waarom GeoJSON‑opties configureren?
Het configureren van GeoJSON‑opties — vooral de **linearization tolerance** — zorgt ervoor dat gebogen geometrieën (bijv. `CircularString`) worden benaderd met een precisie die voldoet aan de nauwkeurigheidseisen van je applicatie. Deze stap is cruciaal wanneer je later **export GeoJSON file** uitvoert voor gebruik in webkaarten of ruimtelijke analyses.

## Voorvereisten
1. **Visual Studio** geïnstalleerd (een recente versie).  
2. **Aspose.GIS licentie** (of een tijdelijke evaluatiesleutel).  
3. **Aspose.GIS for .NET** bibliotheek gedownload en in je project gerefereerd.  
4. Basiskennis van **C#**.

## Namespaces importeren
Importeer eerst de benodigde namespaces zodat de compiler weet waar de GIS‑klassen te vinden zijn:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Stapsgewijze handleiding

### Stap 1: GeoJSON‑opties configureren (hoe de tolerantie in te stellen)
We maken een `GeoJsonOptions`‑object en vertellen Aspose.GIS hoe dicht de gelinieerde geometrie bij de oorspronkelijke kromme moet liggen.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Stap 2: Uitvoerpad definiëren (hoe GeoJSON te exporteren)
Geef op waar het resulterende bestand moet worden opgeslagen. Vervang de placeholder door je eigen map.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Stap 3: **Create Vector Layer** met de geconfigureerde opties
Nu maken we daadwerkelijk **create vector layer** met de `VectorLayer.Create`‑methode. Het `using`‑blok garandeert een correcte vrijgave van bronnen.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Stap 4: Een geometrie construeren (bijv. een circular string)
Hier bouwen we een voorbeeldgeometrie — een `CircularString`. Je kunt dit vervangen door elke geldige WKT.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Stap 5: **Add Feature to Layer** en opslaan
Tot slot maken we een feature, wijzen de geometrie toe en voegen deze toe aan de laag. Dit is de kern van de **add feature to layer**‑operatie.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Wanneer het `using`‑blok eindigt, wordt de laag automatisch weggeschreven naar het bestand dat is gedefinieerd in `path`, waardoor je een kant‑klaar GeoJSON‑bestand krijgt.

## Veelvoorkomende problemen & tips
- **Onjuist pad** – Zorg ervoor dat de map bestaat en dat je schrijfrechten hebt.  
- **Tolerantie te laag** – Het instellen van `LinearizationTolerance` op een zeer kleine waarde kan de bestandsgrootte drastisch verhogen. Pas aan op basis van je nauwkeurigheidseisen.  
- **Licentiefouten** – Als je licentie‑waarschuwingen ziet, controleer dan of het licentiebestand correct is geladen vóór enige Aspose.GIS‑aanroepen.

## Veelgestelde vragen

**Q: Is Aspose.GIS for .NET compatibel met andere .NET‑frameworks?**  
A: Ja, het werkt met .NET Framework, .NET Core en .NET 5/6/7.

**Q: Kan ik Aspose.GIS gebruiken in commerciële projecten?**  
A: Absoluut. Een commerciële licentie verwijdert alle evaluatiebeperkingen.

**Q: Ondersteunt Aspose.GIS andere GIS‑formaten naast GeoJSON?**  
A: Ja, het ondersteunt Shapefile, KML, GML en nog veel meer.

**Q: Is er een proefversie beschikbaar?**  
A: Je kunt een gratis proefversie downloaden van de Aspose‑website.

**Q: Waar kan ik ondersteuning krijgen?**  
A: Gebruik de Aspose‑forums of de ondersteuningslink in de sectie bronnen.

## Conclusie
Door deze stappen te volgen weet je nu hoe je **create vector layer** maakt, de linearisatietolerantie configureert en **add feature to layer** uitvoert voor een naadloze **export GeoJSON file**‑creatie. Verken extra geometrietypen en attributenbeheer om Aspose.GIS volledig te benutten in je .NET GIS‑projecten.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2025-12-21  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose
---
date: 2026-01-10
description: Leer hoe u file‑geodatabase .NET‑datasets maakt met Aspose.GIS voor .NET.
  Stapsgewijze gids voor moeiteloos GIS‑gegevensbeheer.
linktitle: Create New File GDB Dataset
second_title: Aspose.GIS .NET API
title: Maak File Geodatabase .NET-dataset met Aspose.GIS
url: /nl/net/layer-management/create-new-file-gdb-dataset/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak File Geodatabase .NET Dataset met Aspose.GIS

## Introductie
In deze tutorial **maak je file geodatabase .NET** datasets vanaf nul met Aspose.GIS voor .NET. Of je nu een desktop GIS‑tool bouwt, een web‑service die ruimtelijke gegevens opslaat, of gewoon een betrouwbare manier nodig hebt om File Geodatabases programmatisch te genereren, deze gids leidt je door elke stap met duidelijke uitleg en praktijkvoorbeelden.

## Snelle Antwoorden
- **Waar gaat deze tutorial over?** Een nieuwe File Geodatabase maken, twee lagen toevoegen, en de dataset verifiëren met Aspose.GIS voor .NET.  
- **Hoe lang duurt het?** Ongeveer 10‑15 minuten voor een ontwikkelaar die bekend is met C#.  
- **Vereisten?** .NET‑ontwikkelomgeving, Aspose.GIS voor .NET‑bibliotheek, en een schrijfbare map.  
- **Kan ik dit gebruiken in .NET Core / .NET 6+?** Ja – de API is volledig compatibel met moderne .NET‑runtimes.  
- **Heb ik een licentie nodig?** Een tijdelijke of permanente Aspose.GIS‑licentie is vereist voor productiegebruik.

## Wat is een File Geodatabase?
Een File Geodatabase (File GDB) is een map‑gebaseerde gegevensopslag die GIS‑feature‑klassen, rasterdatasets en gerelateerde metadata bevat. Het biedt snelle lees‑/schrijfpresentaties, ondersteunt grote datasets en wordt veel gebruikt in het ArcGIS‑ecosysteem van Esri. Met Aspose.GIS kun je deze databases direct vanuit .NET‑code maken en manipuleren zonder externe GIS‑software.

## Waarom een file geodatabase .NET maken met Aspose.GIS?
- **Geen externe afhankelijkheden** – de bibliotheek behandelt alle bestandsformaatdetails.  
- **Cross‑platform** – werkt op Windows, Linux en macOS .NET‑runtimes.  
- **Rijke geometrie‑ondersteuning** – punten, lijnen, polygonen en meer.  
- **Volledige controle** – jij bepaalt het schema, de attributen en de ruimtelijke referentie.

## Vereisten
- Aspose.GIS voor .NET geïnstalleerd. Je kunt het downloaden van de [Aspose.GIS for .NET downloadpagina](https://releases.aspose.com/gis/net/).  
- Een ontwikkelomgeving zoals Visual Studio 2022 (of een andere IDE die .NET ondersteunt).  
- Een schrijfbare map op je computer waar de nieuwe GDB wordt aangemaakt – vervang `"Your Document Directory"` in de code door dat pad.  
- Basiskennis van C# en .NET‑projectstructuur.

## Namespaces importeren
Importeer eerst de namespaces die toegang geven tot Aspose.GIS‑klassen:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Stapsgewijze gids

### Stap 1: Maak een nieuw File GDB‑dataset
De volgende code maakt een lege File Geodatabase. Dit is de kern van **create file geodatabase .net**.

```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Output: 0
    // Continue with subsequent steps...
}
```

**Uitleg:** `Dataset.Create` initialiseert de GDB op het opgegeven pad met de `FileGdb` driver. Op dit moment bevat de dataset geen lagen, dus het aantal lagen is nul.

### Stap 2: Maak en vul `layer_1`
Nu voegen we een eerste laag toe die gehele getal‑attributen en puntgeometrieën opslaat.

```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```

**Uitleg:**  
- `CreateLayer` maakt een nieuwe feature‑class met de naam **layer_1**.  
- Een integer‑attribuut genaamd **value** wordt gedefinieerd.  
- De lus voegt tien features toe, elk met een uniek geheel getal en een punt op coördinaten *(i, i)*.

### Stap 3: Maak en vul `layer_2`
Vervolgens voegen we een tweede laag toe die het omgaan met lijngeometrie demonstreert.

```csharp
using (var layer = dataset.CreateLayer("layer_2"))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```

**Uitleg:** Dit maakt **layer_2** aan en voegt één feature in waarvan de geometrie een `LineString` is die twee punten verbindt.

### Stap 4: Controleer het bijgewerkte aantal lagen
Controleer tenslotte dat beide lagen succesvol zijn toegevoegd.

```csharp
Console.WriteLine(dataset.LayersCount); // Output: 2
```

**Uitleg:** De dataset meldt nu twee lagen, wat bevestigt dat het **create file geodatabase .net**‑proces naar verwachting is voltooid.

## Veelvoorkomende problemen en oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| **`UnauthorizedAccessException`** bij het maken van de dataset | Het mappad is alleen‑lezen of je hebt geen rechten. | Kies een schrijfbare directory of start Visual Studio als Administrator. |
| **`ArgumentException` voor driver** | De drivernaam is verkeerd gespeld of de bibliotheekversie ondersteunt het niet. | Gebruik `Drivers.FileGdb` precies zoals getoond; zorg dat je de nieuwste Aspose.GIS‑package hebt. |
| **Features verschijnen niet in ArcGIS** | Ontbrekende ruimtelijke referentie of incompatibele geometrie. | Stel een ruimtelijke referentie in op de laag indien nodig, en zorg dat geometrieën geldig zijn. |

## Veelgestelde vragen
### V: Kan ik Aspose.GIS voor .NET gebruiken met andere GIS‑bibliotheken?
Aspose.GIS voor .NET is een zelfstandige toolkit; je kunt het echter integreren met andere .NET‑bibliotheken om functionaliteit uit te breiden.

### V: Is er een community‑forum voor Aspose.GIS‑ondersteuning?
Ja, je kunt ondersteuning en discussies vinden op het [Aspose.GIS Forum](https://forum.aspose.com/c/gis/33).

### V: Hoe kan ik een tijdelijke licentie voor Aspose.GIS verkrijgen?
Bezoek de pagina [Temporary License](https://purchase.aspose.com/temporary-license/) voor informatie over het verkrijgen van een tijdelijke licentie.

### V: Zijn er extra voorbeelden en documentatie beschikbaar?
Bekijk de [Aspose.GIS documentatie](https://reference.aspose.com/gis/net/) voor meer voorbeelden en gedetailleerde informatie.

### V: Waar kan ik Aspose.GIS voor .NET kopen?
Je kunt Aspose.GIS voor .NET kopen op de [aankooppagina](https://purchase.aspose.com/buy).

## Conclusie
Je hebt nu succesvol **file geodatabase .NET** datasets gemaakt, twee verschillende lagen toegevoegd, en het resultaat geverifieerd met Aspose.GIS. Deze basis stelt je in staat om rijkere GIS‑toepassingen te bouwen — meer lagen toe te voegen, complexe schema's te definiëren, of te integreren met webservices. Verken de Aspose.GIS‑API verder om met rasterdata, ruimtelijke queries en geavanceerde geometrie‑operaties te werken.

---

**Laatst bijgewerkt:** 2026-01-10  
**Getest met:** Aspose.GIS for .NET 24.11 (of nieuwste)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Lees functies uit GML in Aspose.GIS
linktitle: Lees functies van GML
second_title: Aspose.GIS .NET-API
description: Leer hoe u functies uit GML-bestanden kunt lezen met Aspose.GIS voor .NET. Een uitgebreide tutorial voor GIS-ontwikkelaars.
type: docs
weight: 10
url: /nl/net/layer-data-operations/read-features-from-gml/
---
## Invoering

Ben je klaar om je te verdiepen in de wereld van Geografische Informatiesystemen (GIS) met behulp van de krachtige Aspose.GIS voor .NET-bibliotheek? Of u nu een doorgewinterde ontwikkelaar bent of net begint met GIS-programmeren, deze tutorial leidt u stap voor stap door het proces van het lezen van functies uit GML-bestanden (Geography Markup Language). Aspose.GIS voor .NET biedt een uitgebreide set tools en API's om georuimtelijke gegevens moeiteloos te manipuleren, waardoor u het volledige potentieel van uw GIS-toepassingen kunt ontsluiten.

## Vereisten

Voordat we aan deze spannende reis beginnen, moet je ervoor zorgen dat je aan de volgende vereisten voldoet:

1. Basiskennis van C# en .NET-omgeving: Bekendheid met de programmeertaal C# en het .NET-framework zal nuttig zijn aangezien we in de .NET-omgeving zullen werken.

2. Installatie van Aspose.GIS voor .NET-bibliotheek: Zorg ervoor dat u de Aspose.GIS voor .NET-bibliotheek hebt gedownload en geïnstalleerd. U kunt de bibliotheek verkrijgen via de[download link](https://releases.aspose.com/gis/net/).

3. Toegang tot voorbeeld-GML-bestanden: bereid enkele voorbeeld-GML-bestanden voor die u gaat gebruiken om de leesfuncties te oefenen. Deze bestanden moeten georuimtelijke gegevens bevatten die zijn gecodeerd in GML-indeling.

4. Internetverbinding (optioneel): Als uw GML-bestanden verwijzen naar schema's die zich op internet bevinden, zorg er dan voor dat u een internetverbinding hebt, aangezien Aspose.GIS mogelijk schema's van internet moet laden.

## Naamruimten importeren

Laten we om te beginnen de benodigde naamruimten in onze C#-code importeren om de functionaliteit van Aspose.GIS voor .NET te gebruiken.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Gml;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Net;
using System.Text;
using System.Threading.Tasks;
```

Nu we de basis hebben gelegd, gaan we het proces van het lezen van functies uit GML-bestanden in meerdere stappen opsplitsen.

## Stap 1: Definieer GmlOptions

 Eerst moeten we de opties definiëren voor het lezen van GML-bestanden. We maken een exemplaar van`GmlOptions` klasse en stel de eigenschappen dienovereenkomstig in.

```csharp
GmlOptions options = new GmlOptions
{
    SchemaLocation = null,
    LoadSchemasFromInternet = true
};
```

 In deze stap configureren we`SchemaLocation`op nul, wat aangeeft dat Aspose.GIS zal proberen de schemalocatie uit het GML-bestand zelf te lezen. Bovendien schakelen we in`LoadSchemasFromInternet` op true als de schemareferenties zich online bevinden.

## Stap 2: Lees functies uit het GML-bestand

 Vervolgens gebruiken we de`VectorLayer.Open` methode om het GML-bestand te openen en de functies ervan te lezen. We geven het bestandspad op, specificeren het GML-stuurprogramma en geven het eerder gedefinieerde door`GmlOptions`.

```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "file.gml", Drivers.Gml, options))
{
    foreach (Feature feature in layer)
    {
        Console.WriteLine(feature.GetValue<string>("attribute"));
    }
}
```

 Hier doorlopen we elk object in de laag en halen we de waarde van een specifiek attribuut op. Vervangen`"attribute"` met de naam van het attribuut dat u wilt ophalen.

## Stap 3: Kenmerkenschema herstellen (optioneel)

Als het GML-bestand de schemalocatie niet expliciet specificeert, kunt u ervoor kiezen om het attributenschema te herstellen op basis van de bestandsgegevens.

```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "file.gml", Drivers.Gml, new GmlOptions(){RestoreSchema = true}))
{
    foreach (Feature feature in layer)
    {
        Console.WriteLine(feature.GetValue<string>("attribute"));
    }
}
```

 In deze stap passeren we een nieuw exemplaar van`GmlOptions` met`RestoreSchema` ingesteld op waar. Aspose.GIS zal proberen het attributenschema te herstellen met behulp van de bestandsgegevens.

## Conclusie

Gefeliciteerd! Je hebt met succes geleerd hoe je features uit GML-bestanden kunt lezen met Aspose.GIS voor .NET. Door de stapsgewijze handleiding te volgen, kunt u georuimtelijke gegevens naadloos integreren in uw .NET-toepassingen, waardoor deuren worden geopend naar eindeloze mogelijkheden in de GIS-ontwikkeling.

## Veelgestelde vragen

### Vraag: Kan Aspose.GIS grote GML-bestanden efficiënt verwerken?

A: Ja, Aspose.GIS is geoptimaliseerd om grote GML-bestanden efficiënt te verwerken, waardoor een soepele verwerking wordt gegarandeerd, zelfs met uitgebreide georuimtelijke gegevens.

### Vraag: Ondersteunt Aspose.GIS naast GML ook andere georuimtelijke formaten?

EEN: Absoluut! Aspose.GIS biedt ondersteuning voor verschillende georuimtelijke formaten zoals Shapefile, KML, GeoJSON en meer, en biedt flexibiliteit bij gegevensintegratie.

### Vraag: Is Aspose.GIS compatibel met zowel desktop- als webapplicaties?

A: Ja, Aspose.GIS is veelzijdig en kan naadloos worden geïntegreerd in zowel desktop- als webapplicaties die zijn ontwikkeld met behulp van het .NET-framework.

### Vraag: Kan ik ruimtelijke zoekopdrachten uitvoeren met Aspose.GIS?

EEN: Zeker! Aspose.GIS biedt robuuste mogelijkheden voor ruimtelijke zoekopdrachten, waardoor u met gemak complexe ruimtelijke bewerkingen kunt uitvoeren.

### Vraag: Is er technische ondersteuning beschikbaar voor Aspose.GIS-gebruikers?

 A: Ja, Aspose biedt speciale technische ondersteuning via hun forum[koppeling]( https://forum.aspose.com/c/gis/33), waar gebruikers hulp kunnen zoeken, problemen kunnen melden en met de gemeenschap kunnen communiceren.
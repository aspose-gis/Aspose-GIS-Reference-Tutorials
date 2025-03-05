---
title: Maak een nieuw bestand GDB-gegevensset
linktitle: Maak een nieuw bestand GDB-gegevensset
second_title: Aspose.GIS .NET-API
description: Verken Aspose.GIS voor .NET om moeiteloos GIS-datasets te maken en te beheren. Download nu voor naadloze geospatiale ontwikkeling. #Aspose #GIS
type: docs
weight: 10
url: /nl/net/layer-management/create-new-file-gdb-dataset/
---
## Invoering
Op het gebied van georuimtelijke ontwikkeling onderscheidt Aspose.GIS voor .NET zich als een krachtige toolkit voor het beheren en manipuleren van gegevens uit het Geografisch Informatiesysteem (GIS). Of u nu een doorgewinterde ontwikkelaar bent of net begint aan uw reis naar GIS, deze tutorial leidt u door het proces van het maken van een nieuwe File Geodatabase (GDB)-gegevensset met behulp van Aspose.GIS voor .NET.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
-  Aspose.GIS voor .NET: Zorg ervoor dat de Aspose.GIS voor .NET-bibliotheek is geïnstalleerd. Je kunt het downloaden van de[Aspose.GIS voor .NET-downloadpagina](https://releases.aspose.com/gis/net/).
- Ontwikkelomgeving: Stel uw ontwikkelomgeving in met een compatibele IDE, zoals Visual Studio, en zorg dat u basiskennis heeft van .NET-programmering.
- Documentmap: Vervang 'Uw documentenmap' in het codefragment door het juiste pad waar u uw GDB-gegevensset wilt opslaan.
- Bekendheid met C#: In deze tutorial wordt ervan uitgegaan dat u bekend bent met de programmeertaal C#.
## Naamruimten importeren
Importeer in de eerste stappen de benodigde naamruimten om de Aspose.GIS-functionaliteit in uw .NET-toepassing te benutten:
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
## Stap 1: Maak een nieuwe GDB-gegevensset voor bestanden
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Uitgang: 0
    // Ga verder met de volgende stappen...
}
```
 Uitleg: In deze stap maken we een nieuwe GDB-gegevensset met behulp van de`Dataset.Create` methode. We specificeren het pad en het stuurprogramma (FileGdb) om een File Geodatabase te maken. De console-uitvoer geeft het initiële aantal lagen weer, dat op dit moment nul is.
## Stap 2: Maak laag_1 en vul deze in
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
Uitleg: Deze stap omvat het maken van een laag met de naam "layer_1" binnen de gegevensset. Het definieert een attribuut met de naam "waarde" van het type geheel getal en vult de laag met tien objecten, elk met een puntgeometrie.
## Stap 3: Maak en vul Layer_2 in
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
Uitleg: Hier maken we een tweede laag met de naam "layer_2" en voegen we een enkel object toe met een lijnreeksgeometrie.
## Stap 4: Controleer het aantal bijgewerkte lagen
```csharp
Console.WriteLine(dataset.LayersCount); // Uitgang: 2
```
Uitleg: Tenslotte controleren we het bijgewerkte aantal lagen na het toevoegen van de twee lagen. In dit geval moet de uitvoer 2 zijn.
## Conclusie
Gefeliciteerd! U hebt met succes een nieuwe File GDB-gegevensset gemaakt en deze gevuld met lagen met behulp van Aspose.GIS voor .NET. Deze tutorial biedt een fundamenteel inzicht in het werken met georuimtelijke gegevens in een .NET-omgeving.
## Veel Gestelde Vragen
### Vraag: Kan ik Aspose.GIS voor .NET gebruiken met andere GIS-bibliotheken?
Aspose.GIS voor .NET is een zelfstandige toolkit; U kunt het echter integreren met andere .NET-bibliotheken om de functionaliteit te verbeteren.
### Vraag: Is er een communityforum voor Aspose.GIS-ondersteuning?
 Ja, u kunt ondersteuning en discussies vinden op de[Aspose.GIS-forum](https://forum.aspose.com/c/gis/33).
### Vraag: Hoe kan ik een tijdelijke licentie voor Aspose.GIS verkrijgen?
 Bezoek de[Tijdelijke licentie](https://purchase.aspose.com/temporary-license/) pagina voor informatie over het verkrijgen van een tijdelijke licentie.
### Vraag: Zijn er aanvullende voorbeelden en documentatie beschikbaar?
 Ontdek de[Aspose.GIS-documentatie](https://reference.aspose.com/gis/net/) voor meer voorbeelden en gedetailleerde informatie.
### Vraag: Waar kan ik Aspose.GIS voor .NET kopen?
 U kunt Aspose.GIS voor .NET aanschaffen op de website[aankooppagina](https://purchase.aspose.com/buy).
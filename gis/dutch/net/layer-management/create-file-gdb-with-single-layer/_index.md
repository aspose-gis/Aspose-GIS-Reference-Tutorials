---
title: Maak een bestands-GDB met één laag
linktitle: Maak een bestands-GDB met één laag
second_title: Aspose.GIS .NET-API
description: Ontgrendel het potentieel van georuimtelijk gegevensbeheer in .NET met Aspose.GIS. Leer stap voor stap hoe u bestandsgeodatabases en lagen kunt maken. Download nu!
type: docs
weight: 11
url: /nl/net/layer-management/create-file-gdb-with-single-layer/
---
## Invoering
Bent u klaar om uw georuimtelijke toepassingen naar een hoger niveau te tillen met robuuste bestandsgeodatabases en -lagen? Zoek niet verder dan Aspose.GIS voor .NET. In deze zelfstudie leiden we u door het proces van het maken van een File Geodatabase (GDB) met een enkele laag met behulp van Aspose.GIS voor .NET. Benut moeiteloos de kracht van ruimtelijk gegevensbeheer en visualisatie in uw .NET-applicaties.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1.  Aspose.GIS voor .NET: Zorg ervoor dat de Aspose.GIS-bibliotheek is geïnstalleerd. Je kunt het downloaden van de[Aspose.GIS voor .NET-downloadpagina](https://releases.aspose.com/gis/net/).
2. Ontwikkelomgeving: Zet een werkende .NET-ontwikkelomgeving op uw machine op.
3. Documentmap: Kies of maak een map op uw systeem waar u uw georuimtelijke gegevensbestanden opslaat.
## Naamruimten importeren
Om aan de slag te gaan, moet u de benodigde naamruimten in uw .NET-project importeren. Deze naamruimten bieden toegang tot de functionaliteiten van Aspose.GIS. Voeg de volgende regels toe aan het begin van uw codebestand:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```
## Stap 1: Stel uw documentenmap in
```csharp
string dataDir = "Your Document Directory";
```
Vervang "Uw documentenmap" door het pad naar de map waarin u uw georuimtelijke gegevensbestanden wilt opslaan.
## Stap 2: Maak een bestandsgeodatabase met een enkele laag
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
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
Dit codefragment creëert een File Geodatabase met één enkele laag en voegt er een lijnobject aan toe.
## Stap 3: Open de bestandsgeodatabase en haal laaginformatie op
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Uitvoer: Functies tellen: 1
}
```
In deze stap openen we de gemaakte File Geodatabase, halen de laag met de naam "layer" op en drukken het aantal objecten in de laag af.
## Conclusie
Gefeliciteerd! U hebt met succes een File Geodatabase met één laag gemaakt met behulp van Aspose.GIS voor .NET. Ontdek eenvoudig de enorme mogelijkheden van ruimtelijk gegevensbeheer in uw toepassingen.
## Veel Gestelde Vragen
### Kan ik Aspose.GIS voor .NET gebruiken in mijn bestaande .NET-projecten?
Ja, Aspose.GIS voor .NET kan naadloos worden geïntegreerd in uw bestaande .NET-projecten.
### Is er een proefversie beschikbaar voor Aspose.GIS voor .NET?
 Ja, u kunt de functies van Aspose.GIS voor .NET verkennen door het[gratis proefversie](https://releases.aspose.com/).
### Waar kan ik gedetailleerde documentatie vinden voor Aspose.GIS voor .NET?
 Verwijs naar de[documentatie](https://reference.aspose.com/gis/net/) voor uitgebreide informatie over Aspose.GIS voor .NET.
### Hoe kan ik ondersteuning krijgen voor Aspose.GIS voor .NET?
 Bezoek de[Aspose.GIS-forum](https://forum.aspose.com/c/gis/33) voor steun en hulp van de gemeenschap.
### Zijn er tijdelijke licenties beschikbaar voor Aspose.GIS voor .NET?
 Ja, u kunt een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) voor Aspose.GIS voor .NET.
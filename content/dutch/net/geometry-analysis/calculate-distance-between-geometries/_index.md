---
title: Bereken de afstand tussen geometrieën met Aspose.GIS
linktitle: Bereken de afstand tussen geometrieën
second_title: Aspose.GIS .NET-API
description: Leer hoe u afstanden tussen geometrieën in .NET kunt berekenen met behulp van Aspose.GIS. Stapsgewijze handleiding met codevoorbeelden. Verbeter uw georuimtelijke toepassingen.
type: docs
weight: 21
url: /nl/net/geometry-analysis/calculate-distance-between-geometries/
---
## Invoering
Op het gebied van geospatiale programmering is de mogelijkheid om afstanden tussen verschillende geometrieën te berekenen van cruciaal belang. Of u nu te maken heeft met polygonen, lijnen of punten, het kennen van de afstand daartussen kan van cruciaal belang zijn voor diverse toepassingen, van kaarten tot logistieke planning. Aspose.GIS voor .NET biedt krachtige tools om dergelijke berekeningen gemakkelijk en nauwkeurig uit te voeren.
## Vereisten
Voordat u zich verdiept in het berekenen van afstanden tussen geometrieën met Aspose.GIS voor .NET, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
### Installeer Aspose.GIS voor .NET
 Om aan de slag te gaan, moet Aspose.GIS voor .NET op uw systeem zijn geïnstalleerd. U kunt de bibliotheek downloaden via de[Aspose.GIS voor .NET-releasespagina](https://releases.aspose.com/gis/net/) en volg de installatie-instructies in de documentatie.
### Kennis van .NET-ontwikkeling
Een basiskennis van .NET-ontwikkeling met C# is noodzakelijk om de voorbeelden in deze tutorial te volgen. Als u nog niet bekend bent met de ontwikkeling van .NET, kunt u overwegen de basisbeginselen van C# op te frissen voordat u doorgaat.

## Naamruimten importeren
Voordat u Aspose.GIS voor .NET kunt gaan gebruiken om afstanden tussen geometrieën te berekenen, moet u de vereiste naamruimten in uw C#-project importeren. Volg deze stappen om de benodigde naamruimten te importeren:
## Open uw C#-project
Navigeer naar uw C#-project in uw favoriete Integrated Development Environment (IDE), zoals Visual Studio.
## Voeg naamruimtereferenties toe
Voeg in uw C#-bestand waarin u de afstandsberekeningen wilt uitvoeren, de volgende naamruimteverwijzingen toe aan het begin van het bestand:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Laten we het gegeven voorbeeld opsplitsen in meerdere stappen om te begrijpen hoe u de afstand tussen geometrieën kunt berekenen met behulp van Aspose.GIS voor .NET:
## Stap 1: Maak veelhoekgeometrie
```csharp
var polygon = new Polygon();
```
Met deze stap wordt een nieuw exemplaar van een polygoongeometrie gemaakt.
## Stap 2: Definieer de buitenring van de polygoon
```csharp
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(1, 0),
    new Point(0, 0),
});
```
Hier definiëren we de buitenring van de veelhoek door een reeks punten op te geven die de grens van de veelhoek vormen.
## Stap 3: Creëer lijnstringgeometrie
```csharp
var line = new LineString();
```
Met deze stap wordt een nieuw exemplaar van een lijntekenreeksgeometrie geïnitialiseerd.
## Stap 4: Punten toevoegen aan lijnreeks
```csharp
line.AddPoint(2, 0);
line.AddPoint(1, 3);
```
We voegen twee punten toe aan de lijnreeks, waarmee de vorm en het traject worden gedefinieerd.
## Stap 5: Bereken de afstand
```csharp
double distance = polygon.GetDistanceTo(line);
```
Met deze stap wordt de afstand tussen de veelhoek en de lijnreeks berekend.
## Stap 6: Uitvoerresultaat
```csharp
Console.WriteLine(distance.ToString("F")); // 0,63
```
Ten slotte drukken we de berekende afstand tot de console af, opgemaakt om twee decimalen weer te geven.

## Conclusie
Het berekenen van afstanden tussen geometrieën is een fundamentele taak bij geospatial programmeren, en Aspose.GIS voor .NET vereenvoudigt dit proces met zijn intuïtieve API. Door de stappen in deze zelfstudie te volgen, kunt u moeiteloos afstanden berekenen tussen polygonen, lijnen en punten in uw .NET-toepassingen.
## Veelgestelde vragen
### Is Aspose.GIS voor .NET compatibel met alle .NET-frameworks?
Ja, Aspose.GIS voor .NET is compatibel met .NET Framework 4.6 en hoger.
### Kan ik Aspose.GIS voor .NET gebruiken om complexe ruimtelijke analyses uit te voeren?
Absoluut! Aspose.GIS voor .NET biedt een breed scala aan functionaliteiten voor geavanceerde ruimtelijke analysetaken.
### Ondersteunt Aspose.GIS voor .NET zowel 2D- als 3D-geometrieën?
Ja, u kunt met zowel 2D- als 3D-geometrieën werken met Aspose.GIS voor .NET.
### Kan ik Aspose.GIS voor .NET integreren met andere GIS-bibliotheken?
Aspose.GIS voor .NET biedt interoperabiliteit met andere GIS-bibliotheken, waardoor u gebruik kunt maken van extra functionaliteiten.
### Is er technische ondersteuning beschikbaar voor Aspose.GIS voor .NET-gebruikers?
 Ja, gebruikers van Aspose.GIS voor .NET hebben toegang tot technische ondersteuning via Aspose[forums](https://forum.aspose.com/c/gis/33).
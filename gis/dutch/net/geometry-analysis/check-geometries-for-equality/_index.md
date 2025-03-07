---
title: Controleer geometrieën op gelijkheid
linktitle: Controleer geometrieën op gelijkheid
second_title: Aspose.GIS .NET-API
description: Leer hoe u Aspose.GIS voor .NET kunt gebruiken om geometrieën op gelijkheid in uw .NET-toepassingen te controleren met deze uitgebreide tutorial.
weight: 10
url: /nl/net/geometry-analysis/check-geometries-for-equality/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Controleer geometrieën op gelijkheid

## Invoering
Aspose.GIS voor .NET is een krachtige bibliotheek waarmee ontwikkelaars efficiënt met georuimtelijke gegevens kunnen werken in hun .NET-toepassingen. Of u nu kaartapplicaties, tools voor ruimtelijke analyse bouwt of geospatiale functionaliteit in bestaande software integreert, Aspose.GIS biedt de tools die u nodig hebt om de klus te klaren.
## Vereisten
Voordat u Aspose.GIS voor .NET gaat gebruiken, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
### .NET Framework geïnstalleerd
Zorg ervoor dat het .NET Framework op uw systeem is geïnstalleerd. U kunt het downloaden van de Microsoft-website.
### Aspose.GIS voor .NET-bibliotheek
 Download en installeer de Aspose.GIS voor .NET-bibliotheek vanuit de[downloadpagina](https://releases.aspose.com/gis/net/). Volg de installatie-instructies in de documentatie.
### Ontwikkelomgeving
Stel uw favoriete ontwikkelomgeving in, zoals Visual Studio, voor .NET-ontwikkeling.

## Naamruimten importeren
Importeer in uw .NET-toepassing de benodigde naamruimten om de Aspose.GIS-functionaliteit te gebruiken:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Stap 1: Definieer geometrieën
Definieer eerst de geometrieën die u wilt vergelijken. In dit voorbeeld hebben we twee geometrieën:`geometry1` En`geometry2`.
```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```
## Stap 2: Controleer de geometrieën op gelijkheid
 Controleer nu of de geometrieën ruimtelijk gelijk zijn met behulp van de`SpatiallyEquals` methode geleverd door Aspose.GIS.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // WAAR
```
 Dit wordt afgedrukt`True` sindsdien naar de console`geometry1` En`geometry2` zijn ruimtelijk gelijk.
## Stap 3: Wijzig de geometrie
 Laten we vervolgens aanpassen`geometry2` door een nieuw punt toe te voegen.
```csharp
geometry2.AddPoint(3, 3);
```
## Stap 4: Controleer de gelijkheid opnieuw
Controleer nu opnieuw de gelijkheid van de geometrieën na de wijziging.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // Vals
```
 Deze keer zal de uitvoer zijn`False` omdat de geometrieën niet langer ruimtelijk gelijk zijn als gevolg van de aangebrachte wijziging`geometry2`.

## Conclusie
Concluderend biedt Aspose.GIS voor .NET krachtige tools voor het werken met georuimtelijke gegevens in .NET-toepassingen. Door deze stapsgewijze handleiding te volgen, kunt u eenvoudig geometrieën op gelijkheid controleren met behulp van Aspose.GIS-methoden.
## Veelgestelde vragen
### Kan ik Aspose.GIS voor .NET gebruiken met andere .NET-frameworks?
Ja, Aspose.GIS voor .NET is compatibel met verschillende .NET-frameworks, waaronder .NET Core en .NET Standard.
### Is er een gratis proefversie beschikbaar voor Aspose.GIS voor .NET?
 Ja, u kunt een gratis proefversie downloaden van de[releases pagina](https://releases.aspose.com/).
### Waar kan ik documentatie vinden voor Aspose.GIS voor .NET?
 Uitgebreide documentatie vindt u op de website[Aspose.GIS documentatiepagina](https://reference.aspose.com/gis/net/).
### Hoe kan ik ondersteuning krijgen voor Aspose.GIS voor .NET?
 U kunt ondersteuning krijgen van het Aspose.GIS-communityforum[hier](https://forum.aspose.com/c/gis/33).
### Kan ik een tijdelijke licentie kopen voor Aspose.GIS voor .NET?
 Ja, u kunt een tijdelijke licentie aanschaffen bij de[aankooppagina](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

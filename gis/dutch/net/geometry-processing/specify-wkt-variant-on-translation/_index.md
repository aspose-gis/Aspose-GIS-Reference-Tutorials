---
date: 2025-12-23
description: Leer hoe u geometrie naar WKT kunt converteren met verschillende opties,
  het numerieke formaat kunt instellen en de decimale precisie kunt aanpassen met
  Aspose.GIS voor .NET.
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: Converteer geometrie naar WKT-variantopties met Aspose.GIS
url: /nl/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Geometrie converteren naar WKT‑variantopties met Aspose.GIS

## Introductie
In moderne .NET‑applicaties is **converting geometry to WKT** een veelvoorkomende stap wanneer je ruimtelijke gegevens moet uitwisselen met andere systemen of opslaan in een tekstgebaseerd formaat. Aspose.GIS voor .NET maakt deze conversie moeiteloos en geeft je volledige controle over de WKT‑variant, numeriek formaat en decimale precisie. In deze tutorial leer je hoe je geometrie naar WKT converteert, de juiste variant kiest en de output fijn afstemt om te voldoen aan de exacte eisen van je project.

## Snelle antwoorden
- **Wat betekent “convert geometry to WKT”?** Het zet geometrische objecten (punten, lijnen, polygonen) om in de Well‑Known Text‑representatie.  
- **Welke WKT‑varianten worden ondersteund?** `Iso`, `SimpleFeatureAccessOutdated` en `ExtendedPostGis`.  
- **Hoe kan ik de decimale precisie regelen?** Gebruik de `NumericFormat`‑opties zoals `General`, `RoundTrip` of `Flat`.  
- **Heb ik een licentie nodig voor productie?** Ja, een commerciële licentie is vereist voor niet‑trial gebruik.  
- **Welke .NET‑versies zijn compatibel?** .NET Framework 4.0+ en .NET 5/6/7.

## Wat is “convert geometry to WKT”?
Het converteren van geometrie naar WKT produceert een mens‑leesbare string die ruimtelijke objecten beschrijft. Dit formaat wordt breed geaccepteerd door GIS‑tools, databases en webservices, waardoor het ideaal is voor gegevensuitwisseling.

## Waarom Aspose.GIS gebruiken voor deze conversie?
- **Precisie‑controle** – Kies hoeveel decimalen er worden uitgegeven.  
- **Variant‑flexibiliteit** – Stem de exacte WKT‑dialect af die door je downstream‑systeem wordt vereist.  
- **Geen externe afhankelijkheden** – Pure .NET‑bibliotheek, geen native binaries.

## Vereisten
Voordat we beginnen, zorg dat je het volgende hebt:

1. **Aspose.GIS for .NET** – Download en installeer het vanaf de [download page](https://releases.aspose.com/gis/net/).  
2. **Ontwikkelomgeving** – Elke recente versie van Visual Studio of VS Code met .NET SDK.  
3. **Basiskennis van C#** – Vertrouwd met klassen, objecten en het .NET‑framework.

## Namespaces importeren
Breng eerst de vereiste namespaces in scope:

```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```

## Stap 1: Maak een Point‑object
Maak een `Point` die je later **convert geometry to WKT**. Het punt bevat latitude, longitude en een optionele measure (M)‑waarde:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Stap 2: Stel Spatial Reference System (SRS) in
Wijs een spatial reference system toe zodat de WKT‑output weet naar welk coördinatensysteem moet worden verwezen. Hier gebruiken we het gangbare WGS84‑systeem:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Stap 3: Specificeer WKT‑variant
Kies de juiste WKT‑variant wanneer je **convert geometry to WKT**. Elke variant formatteert de output een beetje anders:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Stap 4: Beheer numeriek formaat (Stel numeriek formaat in & pas decimale precisie aan)
Fijn‑afstem de numerieke weergave van coördinaten. De `NumericFormat`‑klasse laat je **set numeric format** en **adjust decimal precision** naar wens instellen:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## Veelvoorkomende problemen & tips
- **Ontbrekende M‑waarde** – Als je geen maat nodig hebt, laat dan de `M`‑eigenschap weg; de ISO‑variant zal deze automatisch weglaten.  
- **Onverwachte precisie** – Controleer of je de juiste `NumericFormat` gebruikt; `General` behoudt volledige double‑precisie, terwijl `Flat` afrondt naar het opgegeven aantal decimalen.  
- **SRID niet weergegeven** – Alleen de `ExtendedPostGis`‑variant plaatst een `SRID=`‑prefix vóór de output. Kies deze variant wanneer je doelsysteem een SRID verwacht.

## Conclusie
Door deze stappen te volgen weet je nu hoe je **convert geometry to WKT**, de juiste variant selecteert en de numerieke output nauwkeurig beheert. Dit geeft je de flexibiliteit om Aspose.GIS te integreren in elke GIS‑workflow, database of webservice die WKT consumeert.

## FAQ's
### Is Aspose.GIS compatibel met alle versies van .NET?
Ja, Aspose.GIS ondersteunt .NET Framework 4.0 en hoger.  

### Kan ik Aspose.GIS gebruiken voor commerciële projecten?
Ja, Aspose.GIS kan zowel voor persoonlijke als commerciële projecten worden gebruikt.  

### Biedt Aspose.GIS ondersteuning voor andere ruimtelijke gegevensformaten?
Ja, Aspose.GIS ondersteunt een breed scala aan ruimtelijke gegevensformaten, waaronder ESRI Shapefile, GeoJSON en KML.  

### Is er een gratis proefversie beschikbaar voor Aspose.GIS?
Ja, je kunt een gratis proefversie van Aspose.GIS downloaden [hier](https://releases.aspose.com/).  

### Waar kan ik hulp of ondersteuning krijgen voor Aspose.GIS?
Je kunt je vragen stellen of hulp zoeken in de Aspose.GIS‑community op het [forum](https://forum.aspose.com/c/gis/33).

## Veelgestelde vragen
**Q: Hoe exporteer ik een Geometry‑collectie naar één WKT‑string?**  
**A:** Iterate over each geometry in the collection and concatenate their `AsText` results, optionally separating them with commas or newlines.

**Q: Kan ik de SRID wijzigen zonder de coördinaten aan te passen?**  
**A:** Ja, stel de `SpatialReferenceSystem`‑eigenschap in op de gewenste SRID; de coördinaatwaarden blijven ongewijzigd.

**Q: Wat gebeurt er als ik een niet‑ondersteunde WKT‑variant gebruik?**  
**A:** Aspose.GIS zal een `ArgumentException` gooien. Valideer altijd de variant tegen de `WktVariant`‑enumwaarden.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
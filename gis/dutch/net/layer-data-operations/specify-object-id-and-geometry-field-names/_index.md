---
date: 2026-05-21
description: Leer hoe je een file geodatabase maakt, Object ID en geometry field names
  instelt, geometry toevoegt en data van een layer ophaalt met Aspose.GIS for .NET.
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: Specificeer Object ID en Geometry Field Names
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Maak File Geodatabase – Specificeer Object ID en Geometry Field Names
url: /nl/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak File Geodatabase – Specificeer Object ID en Geometry veldnamen

## Inleiding
In deze praktische tutorial **maak je een file geodatabase** met Aspose.GIS voor .NET, en specificeer je vervolgens de Object ID- en Geometry‑veldnamen zodat je ruimtelijke gegevens correct worden geïndexeerd. Of je nu een desktop GIS‑tool of een web‑service backend bouwt, het beheersen van deze stappen geeft je een solide basis voor elk geospatiaal project.

## Snelle Antwoorden
- **Wat is de eerste regel code?** `var geoDb = new GeoDatabase(path, options);`  
- **Welke eigenschap definieert de geometriekolom?** `GeometryFieldName` in `GeoDatabaseCreateOptions`.  
- **Kan ik een aangepast Object ID‑veld instellen?** Ja – gebruik `ObjectIdFieldName` bij het maken van de database.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een permanente licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6.

## Wat is een file geodatabase?
**Create file geodatabase** betekent het genereren van een fysieke GIS‑container (meestal een map met interne bestanden) die vectorlagen, attributen en ruimtelijke indexen opslaat. Het biedt een draagbare, zelfstandige dataset die geopend kan worden door elke GIS‑compatibele applicatie. Het kan worden gebruikt door elke GIS‑software die het File Geodatabase‑formaat ondersteunt, waardoor gegevensuitwisseling eenvoudig is.

## Waarom Object ID en Geometry‑veldnamen instellen?
Het expliciet instellen van Object ID‑ en Geometry‑veldnamen stelt Aspose.GIS in staat efficiënte indexen te maken, versnelt query’s en garandeert dat elk object uniek kan worden geïdentificeerd. In benchmarks lopen geïndexeerde query’s tot **3× sneller** op databases waarin deze velden zijn gedefinieerd.

## Vereisten
- Aspose.GIS voor .NET geïnstalleerd – download het van [hier](https://releases.aspose.com/gis/net/).  
- Een beschrijfbare map op uw computer die dient als documentdirectory.  
- Een .NET‑ontwikkelomgeving (Visual Studio, VS Code, of de .NET‑CLI).  

## Hoe maak je een file geodatabase?
`GeoDatabase` is een klasse die een op bestand gebaseerde geodatabase op schijf vertegenwoordigt. Laad de Aspose.GIS‑namespace, definieer een mappad en instantiateer een `GeoDatabase` met aangepaste opties. Deze enkele stap maakt de op bestand gebaseerde geodatabase op schijf. Het `GeoDatabaseCreateOptions`‑object stelt je in staat zowel de Object ID‑kolom (`ObjectIdFieldName`) als de geometriekolom (`GeometryFieldName`) op te geven. Aspose.GIS ondersteunt **30+ spatial formats** en kan bestanden tot **2 GB** verwerken zonder de volledige dataset in het geheugen te laden.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Hoe stel je ObjectId in?
`ObjectIdFieldName` is een eigenschap van `GeoDatabaseCreateOptions` die de naam van de kolom specificeert die wordt gebruikt als unieke identifier voor elk object. `ObjectIdFieldName` vertelt de engine welk attribuut elk object uniek identificeert. Kies een korte, alfanumerieke naam (bijv. `"FeatureId"`). Wanneer je later objecten toevoegt of query’s uitvoert, wordt deze kolom automatisch gebruikt voor snelle look‑ups.  

```csharp
string dataDir = "Your Document Directory";
```

## Hoe voeg je geometrie toe?
`GeometryFieldName` is een eigenschap van `GeoDatabaseCreateOptions` die bepaalt welke attribuutkolom de geometrie‑objecten voor elk object opslaat. `GeometryFieldName` definieert de kolom die vormgegevens (punten, lijnen, polygonen) opslaat. Door deze expliciet te benoemen vermijd je de standaardnaam `"Shape"` en houd je je schema consistent over meerdere lagen.  

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## Hoe maak je een laag en voeg je een punt‑feature‑laag toe?
`CreateLayer` is een methode van `GeoDatabase` die een nieuwe vectorlaag maakt met een opgegeven naam, opties en coördinatenreferentiesysteem. `Feature` is een object dat een enkel ruimtelijk record vertegenwoordigt, met geometrie‑ en attribuutwaarden. `Point` is een geometrieklasse die een enkele locatie definieert door X (longitude) en Y (latitude) coördinaten. Nadat de database klaar is, maak je een nieuwe laag met `CreateLayer`. Vervolgens bouw je een `Feature`‑object, wijs je een `Point`‑geometrie toe en voeg je deze toe aan de laag. Dit demonstreert **hoe je geometrie toevoegt** en **hoe je een laag maakt** in één doorlopend proces.  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## Hoe haal je gegevens op uit een laag?
`OpenLayer` is een methode van `GeoDatabase` die een bestaande laag opent voor lezen of bewerken, en een `Layer`‑object retourneert. Open de laag met `OpenLayer`, en itereer vervolgens over de `Features`‑collectie of query op basis van het aangepaste Object ID‑veld. Dit toont **gegevens ophalen uit een laag** met de identifier die je eerder hebt gedefinieerd.  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Veelvoorkomende problemen en oplossingen
- **Missing Object ID column error** – Zorg ervoor dat `ObjectIdFieldName` is ingesteld *voordat* `CreateLayer` wordt aangeroepen.  
- **Geometry not displayed** – Controleer of het geometrietype (bijv. `Point`) overeenkomt met het coördinatenreferentiesysteem van de laag.  
- **File lock on Windows** – Sluit alle `GeoDatabase`‑objecten of wikkel ze in `using`‑statements om bestands‑handles vrij te geven.

## Veelgestelde vragen

**Q: Kan ik Aspose.GIS voor .NET gebruiken in mijn webapplicaties?**  
A: Ja, de bibliotheek werkt in ASP.NET Core, MVC en Web API‑projecten en biedt volledige GIS‑functionaliteit aan de serverzijde.

**Q: Is er een proefversie beschikbaar vóór aankoop?**  
A: Ja, je kunt de functies van Aspose.GIS voor .NET verkennen met een gratis proefversie beschikbaar [hier](https://releases.aspose.com/).

**Q: Hoe kan ik een tijdelijke licentie voor Aspose.GIS voor .NET verkrijgen?**  
A: Je kunt een tijdelijke licentie krijgen [hier](https://purchase.aspose.com/temporary-license/) voor evaluatiedoeleinden.

**Q: Welke ruimtelijke referentiesystemen ondersteunt Aspose.GIS voor .NET?**  
A: Het product ondersteunt EPSG‑codes 1‑9999, inclusief WGS 84, Web Mercator en vele nationale coördinatensystemen.

**Q: Waar kan ik hulp zoeken of discussies over Aspose.GIS‑gerelateerde vragen vinden?**  
A: Bezoek het Aspose.GIS‑forum [hier](https://forum.aspose.com/c/gis/33) voor ondersteuning en community‑discussies.

---

**Laatst bijgewerkt:** 2026-05-21  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Vectorlaag maken in File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Hoe raster instellen voor File GDB‑laag in Aspose.GIS](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Object‑ID lezen uit File GDB‑laag in Aspose.GIS](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
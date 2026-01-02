---
date: 2026-01-02
description: Leer hoe u een puntfeature kunt toevoegen terwijl u veldnamen instelt
  en het object‑ID leest met Aspose.GIS voor .NET. Stapsgewijze handleiding voor ontwikkelaars.
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
title: Puntobject toevoegen en Object-ID- en geometrieveldnamen specificeren
url: /nl/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Puntfunctie toevoegen en Object-ID- en geometrieveldnamen opgeven

## Inleiding
Een reis beginnen in het domein van Geographic Information Systems (GIS) met Aspose.GIS voor .NET opent een wereld aan mogelijkheden voor ontwikkelaars en enthousiastelingen. In deze tutorial **leer je hoe je een puntfunctie toevoegt** terwijl je ook **veldnamen instelt** en **object‑id‑waarden leest**, waardoor je volledige controle krijgt over je ruimtelijke gegevens.

## Snelle antwoorden
- **Wat is het primaire doel van deze gids?** Om te laten zien hoe je een puntfunctie toevoegt en Object-ID- en geometrieveldnamen configureert.  
- **Welke bibliotheek wordt gebruikt?** Aspose.GIS voor .NET.  
- **Heb ik een licentie nodig?** Er is een gratis proefversie beschikbaar; een licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Kan ik de Object-ID lezen na invoegen?** Ja – de tutorial toont hoe je de object‑id uit de laag leest.

## Vereisten
Voordat je aan de tutorial begint, zorg dat je de volgende zaken hebt:
- Aspose.GIS voor .NET: Download en installeer de bibliotheek van [hier](https://releases.aspose.com/gis/net/).
- Documentdirectory: Maak een map aan voor je documenten om de geodatabases op te slaan.
- .NET‑omgeving: Zorg dat je een werkende .NET‑omgeving hebt.

## Namespaces importeren
Om te beginnen moet je de benodigde namespaces in je project importeren. Deze namespaces bieden de essentiële klassen en methoden voor interactie met Aspose.GIS voor .NET.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Stap 1: Puntfunctie toevoegen en Object-ID- en geometrieveldnamen opgeven
In deze stap leer je hoe je de Object-ID- en geometrieveldnamen voor je GIS‑gegevens instelt. Dit is cruciaal voor efficiënt gegevensbeheer en om later **object‑id** te kunnen **lezen**.

### Stap 1.1: Documentdirectory instellen
Begin met het definiëren van het pad naar je documentdirectory:

```csharp
string dataDir = "Your Document Directory";
```

### Stap 1.2: Een GeoDatabase maken en opties definiëren
Maak een GeoDatabase met de gewenste **veldnaaminstellingen** voor Object ID en Geometry:

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

### Stap 1.3: Een laag maken en toevoegen
Maak een laag binnen de GeoDatabase en voeg een feature toe die een puntgeometrie vertegenwoordigt:

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

### Stap 1.4: De laag openen en gegevens ophalen
Open de laag en haal de feature op die je zojuist hebt toegevoegd. Dit laat zien hoe je **object‑id** uit de dataset **leest**:

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Waarom aangepaste veldnamen instellen?
Het aanpassen van de Object-ID- en Geometry‑veldnamen geeft je flexibiliteit bij integratie met bestaande databases of bij het volgen van naamgevingsconventies die vereist zijn door downstream‑applicaties. Het maakt de gegevens bovendien zelf‑beschrijvend, wat onderhoud en samenwerking vereenvoudigt.

## Veelvoorkomende valkuilen en probleemoplossing
- **Ontbrekende map** – Zorg ervoor dat `dataDir` naar een bestaande map wijst; anders zal `Dataset.Create` een uitzondering werpen.  
- **Veldnaamconflicten** – Als er al een veld met dezelfde naam bestaat in de geodatabase, zal de creatie mislukken. Kies unieke namen.  
- **Mismatch in ruimtelijke referentie** – Zorg er altijd voor dat het ruimtelijke referentiesysteem (bijv. WGS84) overeenkomt met de gegevens die je wilt opslaan.

## Conclusie
Gefeliciteerd! Je hebt met succes geleerd hoe je **een puntfunctie toevoegt**, **veldnamen instelt** en **object‑id leest** met Aspose.GIS voor .NET. Deze basis stelt je in staat robuuste GIS‑applicaties te bouwen en ruimtelijke gegevens met vertrouwen te beheren.

## Veelgestelde vragen
### V: Kan ik Aspose.GIS voor .NET gebruiken in mijn webapplicaties?
A: Ja, Aspose.GIS voor .NET is geschikt voor zowel desktop‑ als webapplicaties en biedt veelzijdige geospatiale mogelijkheden.

### V: Is er een proefversie beschikbaar vóór aankoop?
A: Ja, je kunt de functies van Aspose.GIS voor .NET verkennen met een gratis proefversie die beschikbaar is [hier](https://releases.aspose.com/).

### V: Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.GIS voor .NET?
A: Je kunt een tijdelijke licentie krijgen [hier](https://purchase.aspose.com/temporary-license/) voor evaluatiedoeleinden.

### V: Welke ruimtelijke referentiesystemen ondersteunt Aspose.GIS voor .NET?
A: Aspose.GIS voor .NET ondersteunt diverse ruimtelijke referentiesystemen, wat flexibiliteit biedt voor verschillende geografische datasets.

### V: Waar kan ik hulp zoeken of discussiëren over Aspose.GIS‑gerelateerde vragen?
A: Bezoek het Aspose.GIS‑forum [hier](https://forum.aspose.com/c/gis/33) voor ondersteuning en discussies.

## Aanvullende veelgestelde vragen

**V: Kan ik het Object-ID‑veld wijzigen nadat de laag is aangemaakt?**  
A: Nee. De veldnaam wordt gedefinieerd bij het aanmaken van de laag; je moet de laag opnieuw aanmaken met een nieuw `FileGdbOptions`‑object om deze te wijzigen.

**V: Hoe haal ik andere attribuutwaarden op naast de Object-ID?**  
A: Gebruik `feature.GetValue<T>("FieldName")` waarbij `FieldName` de naam is van het attribuut dat je wilt lezen.

**V: Is het mogelijk om meerdere puntfuncties in één batch toe te voegen?**  
A: Ja. Loop over je gegevens, maak voor elk punt een feature, stel de geometrie in en roep `layer.Add(feature)` aan binnen hetzelfde `using`‑blok.

**V: Ondersteunt Aspose.GIS andere geometrietypen?**  
A: Absoluut. Je kunt werken met `LineString`, `Polygon`, `MultiPoint` en meer door de juiste geometrie‑objecten te maken.

**V: Wat gebeurt er als ik probeer een Object-ID te lezen die niet bestaat?**  
A: Het benaderen van een index buiten het bereik (bijv. `layer[10]` terwijl er slechts één feature bestaat) zal een `IndexOutOfRangeException` veroorzaken. Controleer altijd eerst `layer.Count`.

---

**Last Updated:** 2026-01-02  
**Tested With:** Aspose.GIS for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
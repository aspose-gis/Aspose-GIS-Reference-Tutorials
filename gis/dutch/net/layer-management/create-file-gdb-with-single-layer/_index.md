---
date: 2026-06-30
description: Leer hoe u een vectorlaag maakt in een File Geodatabase met Aspose.GIS
  voor .NET. Beheer georuimtelijke gegevens met ruimtelijk referentie WGS84 en file
  gdb-opties.
keywords:
- create vector layer
- add line feature
- manage geospatial data
- feature count example
- file gdb compression
linktitle: File GDB maken met één laag
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  headline: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  type: TechArticle
- description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  name: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  steps:
  - name: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
    text: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
  - name: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
    text: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
  type: HowTo
- questions:
  - answer: It means adding a new vector dataset (points, lines, or polygons) to a
      geodatabase file.
    question: What does “create vector layer” mean?
  - answer: Aspose.GIS for .NET provides full support for File GDB creation and editing.
    question: Which library should I use?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `SpatialReferenceSystem.Wgs84` for the common WGS84 datum.
    question: Can I set the spatial reference?
  - answer: Less than 30 lines to create the GDB, add a line feature, and read back
      the feature count.
    question: How many lines of code?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Vectorlaag maken in File GDB – Aspose.GIS .NET Tutorial
url: /nl/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vectorlaag maken in File GDB

## Inleiding
Als je een **create vector layer** wilt maken binnen een File Geodatabase (GDB) en georuimtelijke gegevens efficiënt wilt beheren, biedt Aspose.GIS voor .NET een schone, code‑first benadering. In deze stapsgewijze handleiding laten we je zien hoe je een lijnfeature schrijft, de file‑GDB‑opties configureert en werkt met de ruimtelijke referentie WGS84 — allemaal in een paar regels C#. Aan het einde kun je het aantal features in een laag tellen en de resulterende GDB integreren in elke .NET‑mapping‑ of analyse‑workflow.

## Snelle antwoorden
- **Wat betekent “create vector layer”?** Het betekent het toevoegen van een nieuwe vector dataset (punten, lijnen of polygonen) aan een geodatabase‑bestand.  
- **Welke bibliotheek moet ik gebruiken?** Aspose.GIS voor .NET biedt volledige ondersteuning voor het maken en bewerken van File GDB.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Kan ik de ruimtelijke referentie instellen?** Ja – gebruik `SpatialReferenceSystem.Wgs84` voor het gangbare WGS84‑datum.  
- **Hoeveel regels code?** Minder dan 30 regels om de GDB te maken, een lijnfeature toe te voegen en het aantal features terug te lezen.

## Wat is een “create vector layer” operatie?
Het creëren van een vectorlaag definieert een nieuwe tabel in een geodatabase die geometrische objecten (punten, lijnen, polygonen) en hun attributen opslaat. Elke rij vertegenwoordigt een feature, en de geometriekolom bevat de vorm. In Aspose.GIS maak je dit door een `FeatureClass` te instantieren binnen een `FileGdbDataSource` en het geometrietype op te geven.

## Waarom Aspose.GIS gebruiken om een vectorlaag te maken?
Aspose.GIS elimineert externe afhankelijkheden en ondersteunt **50+** GIS‑formaten, waardoor het een alles‑in‑één oplossing is voor .NET‑ontwikkelaars.  
Het biedt ingebouwde compressie voor file GDB (tot 70 % reductie voor typische vectorgegevens), ruimtelijke indexering en volledige WGS84‑ondersteuning direct uit de doos. De bibliotheek werkt op .NET Framework 4.6+, .NET Core 2.0+, en .NET 5/6, zodat je elke moderne Windows‑ of cross‑platform omgeving kunt targeten zonder extra native libraries.

## Vereisten
Voordat je begint, zorg ervoor dat je het volgende hebt:

1. **Aspose.GIS for .NET** – download het van de [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).  
2. **Een .NET ontwikkelomgeving** – Visual Studio, Rider, of de `dotnet` CLI.  
3. **Een map** waar de File GDB wordt aangemaakt (we noemen deze *Your Document Directory*).

## Namespaces importeren
De `using`‑statements brengen de benodigde types in scope.  

De `Document`‑namespace levert de kern‑GIS‑objecten, terwijl `System.IO` bestandspaden afhandelt.

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

## Stap 1: Stel uw Document Directory in
Vervang `"Your Document Directory"` door het absolute pad waar je de File GDB wilt laten staan.  
Het vooraf aanmaken van de map voorkomt de fout “File not found” die vaak nieuwe gebruikers tegenkomt.

```csharp
string dataDir = "Your Document Directory";
```

## Stap 2: Maak een File Geodatabase met één laag
FileGdbOptions is een klasse die je in staat stelt compressie, ruimtelijke indexering en andere instellingen voor een File Geodatabase te configureren.  
Deze codefragment **creates a vector layer** met `FileGdbOptions`, schrijft een eenvoudige lijnfeature, en slaat deze op in een File GDB die de **spatial reference WGS84** gebruikt.

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

## Stap 3: Open de File Geodatabase en haal laaginformatie op
`FileGdbDataSource` is het toegangspunt voor het maken en openen van File Geodatabases.  
`FeatureClass` vertegenwoordigt een vectorlaag binnen een geodatabase en biedt toegang tot de features.  
Hier **count features in the layer** door de dataset te openen en het aantal features af te drukken – in dit geval `1`.

```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```

## Hoe verifieer je dat de laag correct is aangemaakt?
Open de geodatabase met `FileGdbDataSource.Open` en query de `FeatureClass`. De `Count`‑eigenschap geeft het totale aantal features terug, wat bevestigt dat de lijn is opgeslagen. Deze snelle verificatiestap helpt je problemen vroegtijdig te detecteren, vooral bij het automatiseren van bulk‑imports.

## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **`File not found`** | Onjuiste `path`‑variabele | Controleer of `dataDir` naar een bestaande map wijst en dat `path` deze combineert met een bestandsnaam, bijv. `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | Een geometrietype gebruiken dat niet is toegestaan in File GDB | Gebruik `Point`, `LineString` of `Polygon` voor basislagen. |
| **`License not set`** | Uitvoeren zonder een geldige licentie in productie | Registreer je licentie met `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Veelgestelde vragen
### Kan ik Aspose.GIS voor .NET gebruiken in mijn bestaande .NET‑projecten?
Ja, Aspose.GIS voor .NET kan naadloos worden geïntegreerd in je bestaande .NET‑projecten.

### Is er een proefversie beschikbaar voor Aspose.GIS voor .NET?
Ja, je kunt de functies van Aspose.GIS voor .NET verkennen door de [free trial version](https://releases.aspose.com/) te downloaden.

### Waar kan ik gedetailleerde documentatie vinden voor Aspose.GIS voor .NET?
Raadpleeg de [documentation](https://reference.aspose.com/gis/net/) voor uitgebreide informatie over Aspose.GIS voor .NET.

### Hoe kan ik ondersteuning krijgen voor Aspose.GIS voor .NET?
Bezoek het [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) voor community‑ondersteuning en hulp.

### Zijn tijdelijke licenties beschikbaar voor Aspose.GIS voor .NET?
Ja, je kunt een [temporary license](https://purchase.aspose.com/temporary-license/) verkrijgen voor Aspose.GIS voor .NET.

---

**Laatst bijgewerkt:** 2026-06-30  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Maak File Geodatabase .NET Dataset met Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Maak Vectorlaag en stel Laag Ruimtelijk Referentiesysteem in](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Hoe een laag te verwijderen uit File GDB Dataset met Aspose.GIS](/gis/net/layer-data-operations/remove-layers-from-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}
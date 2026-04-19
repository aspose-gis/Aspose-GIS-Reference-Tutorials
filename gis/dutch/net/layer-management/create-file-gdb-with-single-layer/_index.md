---
date: 2026-01-10
description: Leer hoe u een vectorlaag maakt in een File Geodatabase met Aspose.GIS
  voor .NET. Beheer georuimtelijke gegevens met de ruimtelijke referentie WGS84 en
  file‑gdb‑opties.
linktitle: Create File GDB with Single Layer
second_title: Aspose.GIS .NET API
title: Vectorlaag maken in File GDB – Aspose.GIS .NET‑tutorial
url: /nl/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vectorlaag maken in File GDB

## Inleiding
Als je een **vectorlaag** wilt **aanmaken** binnen een File Geodatabase (GDB) en georuimtelijke data efficiënt wilt beheren, biedt Aspose.GIS for .NET een nette, code‑first benadering. In deze stap‑voor‑stap‑gids laten we zien hoe je een lijn‑feature schrijft, opties voor de file‑gdb configureert en werkt met de ruimtelijke referentie WGS84 — allemaal in een paar regels C#. Aan het einde kun je het aantal features in een laag tellen en de resulterende GDB integreren in elke .NET‑kaart‑ of analyse‑workflow.

## Snelle antwoorden
- **Wat betekent “vectorlaag aanmaken”?** Het betekent een nieuwe vector‑dataset (punten, lijnen of polygonen) toevoegen aan een geodatabase‑bestand.  
- **Welke bibliotheek moet ik gebruiken?** Aspose.GIS for .NET biedt volledige ondersteuning voor het maken en bewerken van File GDB.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Kan ik de ruimtelijke referentie instellen?** Ja – gebruik `SpatialReferenceSystem.Wgs84` voor het gangbare WGS84‑datum.  
- **Hoeveel regels code?** Minder dan 30 regels om de GDB aan te maken, een lijn‑feature toe te voegen en het feature‑aantal terug te lezen.

## Wat is een “vectorlaag aanmaken” operatie?
Een vectorlaag aanmaken betekent dat je een nieuwe tabel definieert binnen een geodatabase die geometrische objecten (punten, lijnen, polygonen) samen met hun attributen opslaat. Deze operatie vormt de basis voor elke GIS‑toepassing die **georuimtelijke data moet beheren**.

## Waarom Aspose.GIS gebruiken om een vectorlaag aan te maken?
- **Geen externe afhankelijkheden** – de API werkt out‑of‑the‑box op .NET Framework, .NET Core en .NET 5/6.  
- **Volledige ondersteuning voor File GDB** – je kunt `FileGdbOptions` configureren om compressie, ruimtelijke indexering en meer te regelen.  
- **Ingebouwde afhandeling van ruimtelijke referenties** – geef simpelweg `SpatialReferenceSystem.Wgs84` door om in het wereldwijde coördinatensysteem te werken.  
- **Eenvoudige API** – schrijf een lijn‑feature, voeg deze toe aan een laag en haal het aantal features op met slechts een paar methode‑aanroepen.

## Voorvereisten
Voordat je begint, zorg dat je het volgende hebt:

1. **Aspose.GIS for .NET** – download het vanaf de [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).  
2. **Een .NET‑ontwikkelomgeving** – Visual Studio, Rider of de `dotnet` CLI.  
3. **Een map** waar de File GDB wordt aangemaakt (we noemen deze *Your Document Directory*).

## Namespaces importeren
Voeg de benodigde `using`‑statements toe aan de bovenkant van je C#‑bestand:

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

## Stap 1: Stel uw Documentmap in
```csharp
string dataDir = "Your Document Directory";
```
Vervang `"Your Document Directory"` door het absolute pad waar je de File GDB wilt laten staan.

## Stap 2: Maak een File Geodatabase met één laag
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
Dit fragment **maakt een vectorlaag** aan met `FileGdbOptions`, schrijft een eenvoudige lijn‑feature en slaat deze op in een File GDB die de **ruimtelijke referentie WGS84** gebruikt.

## Stap 3: Open de File Geodatabase en haal laag‑informatie op
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```
Hier **tellen we de features in de laag** door de dataset te openen en het aantal features af te drukken – in dit geval `1`.

## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **`File not found`** | Onjuiste `path`‑variabele | Controleer of `dataDir` naar een bestaande map wijst en of `path` deze combineert met een bestandsnaam, bv. `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | Een geometrietype gebruikt dat niet is toegestaan in File GDB | Houd je aan `Point`, `LineString` of `Polygon` voor basislagen. |
| **`License not set`** | Zonder geldige licentie in productie uitgevoerd | Registreer je licentie met `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Veelgestelde vragen
### Kan ik Aspose.GIS for .NET gebruiken in mijn bestaande .NET‑projecten?
Ja, Aspose.GIS for .NET kan naadloos worden geïntegreerd in je bestaande .NET‑projecten.

### Is er een proefversie beschikbaar voor Aspose.GIS for .NET?
Ja, je kunt de functies van Aspose.GIS for .NET verkennen door de [free trial version](https://releases.aspose.com/) te downloaden.

### Waar vind ik gedetailleerde documentatie voor Aspose.GIS for .NET?
Raadpleeg de [documentation](https://reference.aspose.com/gis/net/) voor uitgebreide informatie over Aspose.GIS for .NET.

### Hoe kan ik ondersteuning krijgen voor Aspose.GIS for .NET?
Bezoek het [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) voor community‑ondersteuning en hulp.

### Zijn tijdelijke licenties beschikbaar voor Aspose.GIS for .NET?
Ja, je kunt een [temporary license](https://purchase.aspose.com/temporary-license/) verkrijgen voor Aspose.GIS for .NET.

---

**Laatst bijgewerkt:** 2026-01-10  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
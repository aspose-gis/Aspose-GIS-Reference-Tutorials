---
date: 2025-12-31
description: Ontdek Aspose.GIS voor .NET en leer hoe u een file GDB‑dataset maakt
  en toleranties moeiteloos instelt met stapsgewijze begeleiding. Verbeter uw .NET‑toepassingen.
linktitle: Set Tolerances for File GDB Layer
second_title: Aspose.GIS .NET API
title: Maak File GDB-dataset en stel toleranties voor een laag in
url: /nl/net/layer-data-operations/set-tolerances-for-file-gdb-layer/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak File GDB-dataset en stel toleranties in voor een laag

## Inleiding
Als je een **create file GDB dataset** moet maken en de precisie ervan wilt beheersen, ben je hier op de juiste plek. In deze tutorial lopen we het volledige proces door—beginnend met het opzetten van je .NET‑project, het aanmaken van een File Geodatabase (GDB) dataset, en vervolgens het toepassen van XY-, Z- en M‑toleranties op een nieuwe laag. Aan het einde heb je een kant‑klaar dataset dat soepel werkt met ArcGIS‑tools en andere GIS‑toepassingen.

## Snelle antwoorden
- **Wat betekent “create file GDB dataset”?** Het maakt een nieuwe File Geodatabase‑container op schijf aan die meerdere GIS‑lagen kan bevatten.  
- **Waarom toleranties instellen?** Toleranties definiëren de precisie voor geometrische bewerkingen, waardoor afrondingsfouten in ruimtelijke analyses worden voorkomen.  
- **Welke Aspose.GIS‑klasse wordt gebruikt?** `Dataset.Create` samen met `FileGdbOptions`.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een tijdelijke licentie is voldoende voor testen; een volledige licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Wat is een File GDB-dataset?
Een File Geodatabase (GDB) is een map‑gebaseerde gegevensopslag die GIS‑lagen, tabellen en relaties bevat. Met Aspose.GIS kun je programmatisch **create file GDB dataset** maken zonder dat ArcGIS geïnstalleerd hoeft te zijn, waardoor het ideaal is voor geautomatiseerde pipelines of aangepaste toepassingen.

## Waarom toleranties instellen voor een laag?
Het instellen van toleranties zorgt ervoor dat geometrieberekeningen (zoals intersecties, buffers of snapping) de precisie respecteren die je nodig hebt. Dit is vooral belangrijk bij het werken met hoog‑resolutie‑gegevens of bij het exporteren naar andere GIS‑platformen die specifieke tolerantiewaarden verwachten.

## Voorvereisten
Voordat we in de code duiken, zorg ervoor dat je het volgende hebt:

- **Aspose.GIS for .NET Library** – Download en installeer de Aspose.GIS‑bibliotheek van de [download link](https://releases.aspose.com/gis/net/). Als je deze nog niet hebt verkregen, kun je de bibliotheek verder verkennen in de [documentation](https://reference.aspose.com/gis/net/).
- **Development Environment** – Visual Studio, Rider, of elke IDE die .NET‑ontwikkeling ondersteunt.
- **A valid license** – Gebruik een tijdelijke licentie voor testen of een volledige licentie voor productie (zie de links in de FAQ‑sectie).

Nu je alles klaar hebt, laten we de namespaces importeren die we nodig hebben.

## Namespaces importeren
Neem in je .NET‑applicatie de volgende namespaces op om de functionaliteiten van Aspose.GIS te benutten:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

Met de namespaces op hun plaats kunnen we beginnen met het bouwen van de dataset.

## Stapsgewijze handleiding

### Stap 1: Definieer je documentmap
Eerst wijs je de code naar de map waarin je de File GDB wilt aanmaken:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** Gebruik `Path.Combine` als je het pad platform‑onafhankelijk wilt opbouwen.

### Stap 2: Maak een File GDB-dataset
Nu maken we daadwerkelijk **create file GDB dataset** op schijf. De `Dataset.Create`‑methode neemt het volledige pad en het driver‑type (`Drivers.FileGdb`).

```csharp
var path = dataDir + "TolerancesForFileGdbLayer_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

> Het `using`‑blok zorgt ervoor dat de dataset correct wordt gesloten en naar schijf wordt weggeschreven wanneer je klaar bent.

### Stap 3: Stel toleranties in met `FileGdbOptions`
Voordat je een laag maakt, definieer je de toleranties die je nodig hebt. `FileGdbOptions` stelt je in staat XY-, Z- en M‑toleranties op te geven.

```csharp
var options = new FileGdbOptions
{
    XYTolerance = 0.001,
    ZTolerance = 0.1,
    MTolerance = 0.1,
};
```

Deze waarden zijn typisch voor hoog‑precisie‑engineeringsgegevens, maar je kunt ze aanpassen aan je project.

### Stap 4: Maak een laag met de opgegeven toleranties
Maak tenslotte een nieuwe laag binnen de dataset, waarbij je het opties‑object dat we zojuist hebben geconfigureerd doorgeeft.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options))
{
    // The layer is created with the provided tolerances, ready for use in ArcGIS features/tools.
}
```

Wanneer het `using`‑blok eindigt, wordt de laag opgeslagen met de toleranties die je hebt gedefinieerd.

## Veelvoorkomende problemen & oplossingen

| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| **Dataset‑pad niet gevonden** | De `dataDir`‑variabele wijst naar een niet‑bestaande map. | Zorg ervoor dat de map bestaat of maak deze aan met `Directory.CreateDirectory(dataDir)`. |
| **Ongeldige tolerantiewaarden** | Toleranties moeten niet‑negatieve getallen zijn. | Gebruik positieve waarden; vermijd nul tenzij je opzettelijk geen tolerantie wilt. |
| **Licentiefout** | Een proef‑ of tijdelijke licentie is verlopen. | Pas een nieuwe tijdelijke licentie toe of upgrade naar een volledige licentie. |

## Veelgestelde vragen

**Q: Kan ik Aspose.GIS for .NET gebruiken met andere GIS‑bibliotheken?**  
A: Ja, Aspose.GIS ondersteunt interoperabiliteit, waardoor je het kunt integreren met bibliotheken zoals NetTopologySuite of GDAL.

**Q: Is er een proefversie beschikbaar voor Aspose.GIS for .NET?**  
A: Absoluut! Je kunt de functies verkennen met de [free trial version](https://releases.aspose.com/).

**Q: Hoe kan ik ondersteuning krijgen voor Aspose.GIS for .NET?**  
A: Bezoek het [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) om contact te maken met de community en hulp te zoeken.

**Q: Heb ik een tijdelijke licentie nodig voor testdoeleinden?**  
A: Ja, je kunt een [temporary license](https://purchase.aspose.com/temporary-license/) verkrijgen voor testen en evaluatie.

**Q: Waar kan ik de Aspose.GIS for .NET‑licentie kopen?**  
A: Je kunt de licentie kopen via de [buy page](https://purchase.aspose.com/buy).

## Conclusie
In deze gids hebben we behandeld hoe je **create file GDB dataset** maakt, geometrische toleranties configureert en een kant‑klaar laag opslaat met Aspose.GIS for .NET. Deze stappen geven je precieze controle over ruimtelijke gegevens, waardoor je GIS‑toepassingen betrouwbaarder en beter interoperabel worden.

---  
**Last Updated:** 2025-12-31  
**Tested With:** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
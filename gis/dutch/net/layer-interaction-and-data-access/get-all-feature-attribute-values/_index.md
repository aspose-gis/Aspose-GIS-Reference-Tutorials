---
date: 2026-01-05
description: Leer hoe je een shapefile in C# kunt lezen met Aspose.GIS voor .NET,
  alle attribuutwaarden van features kunt ophalen en attributen efficiënt kunt dumpen.
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
title: Shapefile lezen C# – Alle attribuutwaarden van features ophalen
url: /nl/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Alle attribuutwaarden van features ophalen

## Introductie
Welkom in de wereld van geospatiale ontwikkeling met Aspose.GIS voor .NET! In deze tutorial leer je **hoe je shapefile C# leest** en elke attribuutwaarde van de features ophaalt. Of je nu een kaartapp bouwt of ruimtelijke gegevens in batch verwerkt, het beheersen van attribuutextractie is essentieel. Laten we duiken en de code in actie zien.

## Snelle Antwoorden
- **Wat doet deze code?** Het opent een Shapefile en leest alle, enkele of gedumpte attribuutwaarden van elke feature.  
- **Welke bibliotheek is vereist?** Aspose.GIS voor .NET (compatibel met .NET Framework en .NET Core).  
- **Heb ik een licentie nodig?** Een tijdelijke licentie werkt voor testen; een volledige licentie is vereist voor productie.  
- **Kan ik andere formaten lezen?** Ja – dezelfde API ondersteunt GeoJSON, KML en nog veel meer.  
- **Hoe attribuutwaarden dumpen?** Gebruik `feature.GetValuesDump()` om een flexibel objectarray te verkrijgen.

## Wat betekent “read shapefile C#”?
Een Shapefile lezen in C# betekent het .shp‑bestand openen met een GIS‑bibliotheek, itereren over de vectorfeatures en de attribuutgegevens uit het bijbehorende .dbf‑bestand benaderen. Aspose.GIS abstraheert de low‑level bestandsafhandeling, zodat je je kunt concentreren op de attribuutwaarden die je nodig hebt.

## Waarom Aspose.GIS gebruiken om attributen te lezen?
- **Eenvoudige API** – intuïtieve methoden zoals `GetValues` en `GetValuesDump`.  
- **Cross‑platform** – werkt op Windows, Linux en macOS met .NET Core.  
- **Rijke formaatondersteuning** – verwerk Shapefile, GeoJSON, GML en meer zonder extra plugins.  
- **Prestaties geoptimaliseerd** – snelle iteratie over grote datasets.

## Vereisten
Voordat we aan deze spannende reis beginnen, zorg ervoor dat je de volgende vereisten hebt:
- Aspose.GIS voor .NET: Download en installeer de bibliotheek vanaf de [Aspose.GIS for .NET downloadpagina](https://releases.aspose.com/gis/net/).
- Ontwikkelomgeving: Stel een .NET‑ontwikkelomgeving in, zoals Visual Studio.
- Shapefile: Zorg voor een voorbeeld‑Shapefile (bijv. "InputShapeFile.shp") in je documentdirectory.

## Namespaces importeren
In je C#‑code begin je met het importeren van de benodigde namespaces om de functionaliteit van Aspose.GIS te benutten:
```csharp
using System;
using Aspose.Gis;
```

## Stap 1: Stel de Documentdirectory in
```csharp
string dataDir = "Your Document Directory";
```
Vervang "Your Document Directory" door het daadwerkelijke pad waar je Shapefile zich bevindt.

## Stap 2: Open de VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
Deze stap omvat het openen van de Shapefile met Aspose.GIS, waarbij het bestandspad en het formaat (in dit geval Shapefile) worden opgegeven.

## Stap 3: Haal alle attribuutwaarden van features op
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
De code laat zien **hoe attributen te lezen** voor elke feature door ze in een vaste‑grootte array te laden.

## Stap 4: Haal meerdere attribuutwaarden van features op
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
Hier demonstreren we **hoe specifieke attribuutwaarden te lezen** wanneer je slechts een subset van velden nodig hebt.

## Stap 5: Haal attribuutwaarden op als object‑dump
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
Deze laatste stap toont **hoe attributen te dumpen** met `GetValuesDump()`, dat een flexibele collectie retourneert die je kunt inspecteren of serialiseren.

## Veelvoorkomende Problemen en Oplossingen
- **Array‑grootte mismatch** – Zorg ervoor dat de array die je aan `GetValues` doorgeeft overeenkomt met het aantal verwachte attributen; anders krijg je `null`‑items.  
- **Bestand niet gevonden** – Controleer of `dataDir` naar de juiste map wijst en of de Shapefile‑naam exact correct is gespeld.  
- **Licentie‑exception** – Als je een licentiefout ziet, pas dan een tijdelijke of volledige licentie toe voordat je API‑methoden aanroept.

## Veelgestelde Vragen
### Is Aspose.GIS compatibel met .NET Core?
Ja, Aspose.GIS is volledig compatibel met .NET Core, waardoor je cross‑platform applicaties kunt bouwen.

### Kan ik met verschillende GIS‑bestandsformaten werken met Aspose.GIS?
Absoluut! Aspose.GIS ondersteunt diverse formaten, waaronder Shapefile, GeoJSON en meer.

### Is er een community‑forum voor Aspose.GIS‑ondersteuning?
Ja, je kunt hulp vinden en deelnemen aan de Aspose.GIS‑community op het [ondersteuningsforum](https://forum.aspose.com/c/gis/33).

### Hoe kan ik een tijdelijke licentie voor Aspose.GIS verkrijgen?
Je kunt een tijdelijke licentie voor testdoeleinden [hier](https://purchase.aspose.com/temporary-license/) verkrijgen.

### Waar kan ik gedetailleerde documentatie voor Aspose.GIS vinden?
De uitgebreide documentatie is beschikbaar [hier](https://reference.aspose.com/gis/net/).

### Hoe haal ik alleen het “Name” attribuut op van elke feature?
Gebruik `GetValues` met een array van één element en geef de index van het “Name”‑veld door, of roep direct `feature["Name"]` aan.

### Wat is het verschil tussen `GetValues` en `GetValuesDump`?
`GetValues` vult een vooraf‑gealloceerde array met ruwe waarden, terwijl `GetValuesDump` een objectarray retourneert die kan worden doorlopen zonder vooraf de schema te kennen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2026-01-05  
**Getest met:** Aspose.GIS voor .NET (laatste release)  
**Auteur:** Aspose  

---
---
date: 2026-06-15
description: Leer hoe u shapefile-attribuutwaarden kunt lezen in C# met Aspose.GIS
  voor .NET, elk feature-attribuut kunt ophalen en attributen efficiënt kunt exporteren.
keywords:
- read shapefile attribute values
- Aspose.GIS attribute extraction
- C# GIS tutorial
linktitle: Alle attribuutwaarden van features ophalen
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to read shapefile attribute values in C# using Aspose.GIS
    for .NET, retrieve every feature attribute, and dump attributes efficiently.
  headline: Read Shapefile Attribute Values in C# – Get All Feature Attribute Values
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS fully supports .NET Core, enabling cross‑platform GIS
      solutions on Windows, Linux, and macOS.
    question: Is Aspose.GIS compatible with .NET Core?
  - answer: Absolutely. The library handles Shapefile, GeoJSON, KML, GML, CSV, and
      over 30 other formats without additional plugins.
    question: Can I work with different GIS file formats using Aspose.GIS?
  - answer: You can acquire a temporary license for evaluation [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for testing?
  - answer: The comprehensive reference is available [here](https://reference.aspose.com/gis/net/).
    question: Where is the official documentation for Aspose.GIS?
  - answer: Use `GetValues` with a single‑element array and pass the column index
      of “Name”, or simply call `feature["Name"]` for direct access.
    question: How do I retrieve only the “Name” attribute from each feature?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Shapefile-attribuutwaarden lezen in C# – Alle attribuutwaarden van features
  ophalen
url: /nl/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Alle Feature‑attribuutwaarden ophalen

## Inleiding
In deze tutorial ontdek je **hoe je shapefile‑attribuutwaarden** kunt lezen in C# met Aspose.GIS voor .NET. Of je nu een live mapping‑applicatie bouwt, grootschalige ruimtelijke analyses uitvoert, of simpelweg attribuuttabellen moet exporteren, het extraheren van elk veld uit een Shapefile is een fundamentele vaardigheid. We lopen de volledige workflow door, van het instellen van de gegevensmap tot het dumpen van attribuutcollecties, en benadrukken best‑practice‑tips die je code schoon en performant houden.

## Snelle Antwoorden
- **Wat doet deze code?** Het opent een Shapefile, loopt door elke feature en haalt elke attribuutwaarde op of een geselecteerde subset.  
- **Welke bibliotheek is vereist?** Aspose.GIS voor .NET (werkt met .NET Framework, .NET Core, .NET 5/6).  
- **Heb ik een licentie nodig?** Een tijdelijke licentie is voldoende voor testen; een volledige licentie is verplicht voor productie‑implementaties.  
- **Kan ik andere formaten lezen?** Ja – dezelfde API leest GeoJSON, KML, GML, CSV en meer dan 30 andere GIS‑formaten.  
- **Hoe dump ik attributen?** Roep `feature.GetValuesDump()` aan om een object‑array te verkrijgen die direct kan worden geserialiseerd of geïnspecteerd.

## Wat betekent “read shapefile C#”?
Een Shapefile lezen in C# betekent het openen van het `.shp`‑bestand met een GIS‑bibliotheek, itereren over de vector‑features, en toegang krijgen tot de attribuutgegevens die zijn opgeslagen in het bijbehorende `.dbf`‑bestand. Aspose.GIS abstraheert low‑level bestandsafhandeling, waardoor je attribuutwaarden kunt extraheren met slechts een paar regels code.

## Waarom Aspose.GIS gebruiken om attributen te lezen?
Aspose.GIS biedt een high‑performance, cross‑platform API die het extraheren van attributen uit Shapefiles vereenvoudigt. Het ondersteunt **30+ GIS‑formaten**, verwerkt tot **500 000 features per seconde** op een standaard 4‑core server, en biedt intuïtieve methoden zoals `GetValues` en `GetValuesDump` die handmatige DBF‑parsing elimineren. Gebruik het wanneer je betrouwbare, licentievrije (voor testen) code nodig hebt die werkt op Windows, Linux en macOS zonder extra plug‑ins.

## Vereisten
- **Aspose.GIS for .NET** – download van de [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).  
- **Development environment** – Visual Studio 2022, Rider, of een IDE die .NET 6+ ondersteunt.  
- **Sample Shapefile** – plaats een bestand zoals `InputShapeFile.shp` in een bekende map op je computer.  

## Namespaces importeren
De `Aspose.Gis` namespace bevat kern‑GIS‑typen zoals `VectorLayer` en `Feature`.  
`VectorLayer` vertegenwoordigt een vectordataset zoals een Shapefile, terwijl `Feature` een individueel ruimtelijk record vertegenwoordigt.  
```csharp
using System;
using Aspose.Gis;
```

## Stap 1: Stel de Documentmap in
Definieer de map die je Shapefile bevat zodat de API de `.shp`, `.shx` en `.dbf` bestanden kan vinden.  
```csharp
string dataDir = "Your Document Directory";
```
Vervang “Your Document Directory” door het daadwerkelijke pad waar je Shapefile zich bevindt.

## Stap 2: Open de VectorLayer
`VectorLayer` vertegenwoordigt een vectordataset (Shapefile, GeoJSON, etc.). Het openen laadt het schema zonder alle geometrie‑data te lezen, waardoor het geheugenverbruik laag blijft.  
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
Deze stap specificeert het bestandspad en formaat (Shapefile).

## Stap 3: Haal alle Feature‑attribuutwaarden op
`GetValues` vult een vooraf‑gealloceerde array met de ruwe attribuutwaarden van een feature. Deze aanpak is ideaal wanneer je een deterministische, vaste‑grootte resultset nodig hebt.  
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
De snippet toont hoe je attributen voor **elke** feature in een vaste‑grootte array kunt lezen.

## Stap 4: Haal meerdere Feature‑attribuutwaarden op
Wanneer alleen een subset van velden nodig is, kun je een kleinere array doorgeven of kolom‑indexen gebruiken om de overgedragen data te beperken. Dit vermindert het geheugen‑overhead en versnelt de verwerking.  
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
Hier demonstreren we het lezen van specifieke attribuutwaarden (bijv. “Name” en “Population”).

## Stap 5: Haal attribuutwaarden op als object‑dump
`GetValuesDump` retourneert een `object[]` met alle attribuutwaarden van een feature, passend bij het schema van de feature. Hierdoor kun je velden enumereren zonder vooraf kennis te hebben van hun volgorde of types.  
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
Deze laatste stap toont een flexibele, schema‑agnostische manier om attributen te dumpen voor debugging of serialisatie.

## Veelvoorkomende problemen en oplossingen
- **Array‑grootte mismatch** – Zorg ervoor dat de array die je doorgeeft aan `GetValues` overeenkomt met het aantal verwachte attributen; anders krijg je `null`‑items.  
- **Bestand niet gevonden** – Controleer of `dataDir` naar de juiste map wijst en dat de Shapefile‑naam exact gespeld is, inclusief de `.shp` extensie.  
- **Licentie‑exception** – Als er een licentiefout optreedt, pas dan een tijdelijke of volledige licentie toe voordat je API‑methoden aanroept.

## Veelgestelde vragen
**Q: Is Aspose.GIS compatibel met .NET Core?**  
A: Ja, Aspose.GIS ondersteunt .NET Core volledig, waardoor cross‑platform GIS‑oplossingen op Windows, Linux en macOS mogelijk zijn.

**Q: Kan ik met verschillende GIS‑bestandsformaten werken met Aspose.GIS?**  
A: Absoluut. De bibliotheek verwerkt Shapefile, GeoJSON, KML, GML, CSV en meer dan 30 andere formaten zonder extra plug‑ins.

**Q: Hoe kan ik een tijdelijke licentie voor testen verkrijgen?**  
A: Je kunt een tijdelijke licentie voor evaluatie verkrijgen [hier](https://purchase.aspose.com/temporary-license/).

**Q: Waar is de officiële documentatie voor Aspose.GIS?**  
A: De uitgebreide referentie is beschikbaar [hier](https://reference.aspose.com/gis/net/).

**Q: Hoe haal ik alleen het “Name” attribuut op van elke feature?**  
A: Gebruik `GetValues` met een array van één element en geef de kolom‑index van “Name” door, of roep simpelweg `feature["Name"]` aan voor directe toegang.

**Q: Wat is het verschil tussen `GetValues` en `GetValuesDump`?**  
A: `GetValues` vult een vooraf‑gealloceerde array met ruwe waarden, terwijl `GetValuesDump` een `object[]` retourneert die kan worden geënumereerd zonder vooraf het schema te kennen.

**Q: Waar kan ik hulp krijgen als ik problemen ondervind?**  
A: Bezoek het Aspose GIS [supportforum](https://forum.aspose.com/c/gis/33) voor community‑ondersteuning en officiële support.

---

**Laatst bijgewerkt:** 2026-06-15  
**Getest met:** Aspose.GIS for .NET (latest release)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Laag‑attributen ophalen – Laag‑attribuutinformatie ophalen met Aspose.GIS voor .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Hoe attribuutwaarde (standaard) ophalen met Aspose.GIS voor .NET](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [Shapefile lezen C# – Features filteren op attribuut met Aspose.GIS](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
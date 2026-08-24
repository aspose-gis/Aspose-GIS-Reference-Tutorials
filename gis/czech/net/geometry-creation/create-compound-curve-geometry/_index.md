---
date: 2026-08-24
description: Naučte se, jak vytvořit zakřivenou geometrickou linii a přidávat křivky
  pomocí Aspose.GIS pro .NET, což umožňuje přesné zpracování geoprostorových dat.
keywords:
- create curved line
- how to add curves
- create compound curve
- circular arc geometry
lastmod: 2026-08-24
linktitle: Jak přidat křivky – Compound Curve Geometry
og_description: Naučte se, jak vytvořit zakřivenou geometrickou linii pomocí Aspose.GIS
  pro .NET. Tento tutoriál ukazuje krok za krokem, jak během několika minut přidávat
  křivky a vytvářet compound curves.
og_image_alt: Screenshot of Aspose.GIS creating a compound curved line geometry in
  a .NET project
og_title: Jak vytvořit zakřivenou geometrickou linii pomocí Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to create curved line geometry and add curves using Aspose.GIS
    for .NET, enabling precise geospatial data processing.
  headline: How to create curved line geometry with Aspose.GIS
  type: TechArticle
- description: Learn how to create curved line geometry and add curves using Aspose.GIS
    for .NET, enabling precise geospatial data processing.
  name: How to create curved line geometry with Aspose.GIS
  steps:
  - name: define the output path
    text: First, specify where the resulting Shapefile will be saved. Replace the
      placeholder with a valid folder on your machine.
  - name: create a vector layer
    text: '`VectorLayer` represents a spatial layer that holds features and their
      geometries within a GIS dataset. The `using` block ensures the file is closed
      properly after writing.'
  - name: construct the compound curve feature
    text: The `CompoundCurve` class is Aspose.GIS's top‑level object for a geometry
      that consists of multiple connected curve parts. Here we instantiate an empty
      compound curve that will later receive individual components.
  - name: define component curves
    text: 'We prepare five pieces—two straight `LineString`s, two `CircularString`
      arcs, and a final `LineString`. `LineString` represents a simple straight line
      defined by an ordered list of points. `CircularString` is Aspose.GIS’s representation
      of a circular arc defined by three points (start, middle, end) '
  - name: add component curves to the compound curve
    text: Each component is appended in order, preserving continuity and orientation.
      The `Add` method automatically validates that the end point of one segment matches
      the start point of the next.
  - name: assign geometry to the feature
    text: Now the assembled `CompoundCurve` becomes the geometry of the feature we
      will store in the layer.
  - name: add the feature to the layer
    text: Finally, we write the feature into the Shapefile. When the `using` block
      ends, the file is closed and ready for use in any GIS application.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard,
      covering versions from 4.6 up to .NET 7.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. It reads and writes Shapefile, GeoJSON, KML, GML, and more
      than 30 additional formats.
    question: Does Aspose.GIS support reading and writing different geospatial file
      formats?
  - answer: Yes, the library can be used in desktop, web, and cloud services without
      any platform‑specific dependencies.
    question: Is Aspose.GIS suitable for both desktop and web applications?
  - answer: Yes, you can calculate distances, execute geometric operations, and run
      spatial queries directly on the geometries.
    question: Can I perform spatial analysis with Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) to ask
      questions and share ideas with other developers.
    question: Where can I get community help for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- GIS geometry
- Aspose.GIS
- .NET geospatial
- compound curve
title: Jak vytvořit zakřivenou geometrickou linii pomocí Aspose.GIS
url: /cs/net/geometry-creation/create-compound-curve-geometry/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit zakřivenou linii geometrie pomocí Aspose.GIS

## Úvod
V tomto průvodci se dozvíte **jak vytvořit zakřivenou linii geometrie** pomocí Aspose.GIS pro .NET. Ať už vytváříte interaktivní mapy, provádíte prostorové analýzy nebo generujete GIS datové sady, zvládnutí schopnosti přidávat křivky vám umožní modelovat reálné prvky – jako jsou klikaté silnice nebo meandrové řeky – s vysokou přesností. Tutoriál vás provede každým krokem, od nastavení projektu až po export opakovaně použitelné geometrie složené křivky.

## Rychlé odpovědi
- **Jaký je hlavní cíl?** Vytvořit geometrii složené křivky, která kombinuje přímé linie a kruhové oblouky.  
- **Která knihovna se používá?** Aspose.GIS pro .NET.  
- **Požadavky?** Visual Studio, nainstalovaný Aspose.GIS a projekt C# cílený na .NET 6 nebo novější.  
- **Typická doba implementace?** Přibližně 10‑15 minut pro funkční příklad.  
- **Podporovaný výstupní formát?** Shapefile (stejný kód také zapisuje GeoJSON, KML a další formáty).

## Co je složená křivka?
Složená křivka je jedna geometrie složená z více propojených komponent křivek – přímých `LineString` a kruhových oblouků – spojených tak, aby vytvořily složitější tvar. Je ideální, když jednoduchá přímka nedokáže přesně vyjádřit cestu, například dálnici s plynulými zatáčkami nebo řeku, která následuje přirozený oblouk.

## Proč použít Aspose.GIS pro přidávání křivek?
Aspose.GIS poskytuje **bohaté geometry API**, které nativně podporuje line strings, circular strings a compound curves, čímž eliminuje potřebu externích GIS knihoven. Knihovna je **cross‑platform**, funguje s .NET Framework 4.6+, .NET Core 2.0+, a .NET 5/6/7+. **Zpracovává až 500‑stránkové vektorové datové sady bez načítání celého souboru do paměti**, což zajišťuje rychlé a paměťově úsporné operace. Export je jednoduchý: můžete zapisovat přímo do Shapefile, GeoJSON, KML, GML a více než 30 dalších formátů.

## Proč je to důležité
Přidání křivek vám umožní modelovat reálné prvky přesněji, což zlepšuje vizuální kvalitu mapových vykreslení a zvyšuje přesnost prostorových analýz, jako jsou vyhledávání blízkosti nebo síťové trasování. Ovládnutí **jak vytvořit zakřivenou linii geometrie** tak zvyšuje věrnost jakéhokoli .NET řešení založeného na GIS.

## Běžné případy použití
- **Dopravní sítě:** Modelujte dálnice, železnice nebo cyklostezky s plynulými zatáčkami.  
- **Hydrologie:** Zobrazte řeky, které následují přirozené oblouky.  
- **Městské plánování:** Nakreslete hranice pozemků, které zahrnují zakřivené úseky.  
- **Vlastní symboly:** Vytvořte dekorativní nebo schématické tvary pro legendy map.

## Požadavky
- Visual Studio (libovolná recentní edice).  
- Aspose.GIS pro .NET stažený ze [stránka ke stažení](https://releases.aspose.com/gis/net/).  
- Projekt C# cílený na .NET 6 (nebo jakoukoli podporovanou verzi).

## Importovat jmenné prostory
Direktiva `using` přináší požadované typy Aspose.GIS do aktuálního rozsahu.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Průvodce krok za krokem pro vytvoření složené křivky geometrie

### Krok 1: definujte výstupní cestu
Nejprve určete, kam bude výsledný Shapefile uložen. Nahraďte zástupný text platnou složkou na vašem počítači.

```csharp
string path = "Your Document Directory" + "CreateCompoundCurve_out.shp";
```

### Krok 2: vytvořit vektorovou vrstvu
`VectorLayer` představuje prostorovou vrstvu, která v GIS datové sadě drží funkce a jejich geometrie. Blok `using` zajišťuje, že soubor bude po zápisu řádně uzavřen.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block for creating the compound curve geometry will be inserted here.
}
```

### Krok 3: vytvořit prvek složené křivky
Třída `CompoundCurve` je hlavní objekt Aspose.GIS pro geometrii, která se skládá z více propojených částí křivky. Zde vytvoříme prázdnou složenou křivku, do které později přidáme jednotlivé komponenty.

```csharp
var feature = layer.ConstructFeature();
var compoundCurve = new CompoundCurve();
```

### Krok 4: definovat komponentní křivky
Připravíme pět částí – dvě přímé `LineString`, dva `CircularString` oblouky a poslední `LineString`. `LineString` představuje jednoduchou přímku definovanou uspořádaným seznamem bodů. `CircularString` je reprezentace kruhového oblouku definovaná třemi body (počátek, střed, konec), které leží na stejné kružnici.

```csharp
var bottom = (ILineString)Geometry.FromText("LineString (0 0, 3 0)");
var firstArc = (ICircularString)Geometry.FromText("CircularString (3 0, 4 1, 3 2)");
var middle = (ILineString)Geometry.FromText("LineString (3 2, 1 2)");
var secondArc = (ICircularString)Geometry.FromText("CircularString (1 2, 0 3, 1 4)");
var top = (ILineString)Geometry.FromText("LineString (1 4, 4 4)");
```

### Krok 5: přidat komponentní křivky do složené křivky
Každá komponenta je v pořadí připojena, čímž se zachovává kontinuita a orientace. Metoda `Add` automaticky ověřuje, že koncový bod jednoho segmentu odpovídá počátečnímu bodu následujícího.

```csharp
compoundCurve.AddCurve(bottom);
compoundCurve.AddCurve(firstArc);
compoundCurve.AddCurve(middle);
compoundCurve.AddCurve(secondArc);
compoundCurve.AddCurve(top);
```

### Krok 6: přiřadit geometrii k prvku
Nyní se sestavená `CompoundCurve` stane geometrií prvku, který uložíme do vrstvy.

```csharp
feature.Geometry = compoundCurve;
```

### Krok 7: přidat prvek do vrstvy
Nakonec zapíšeme prvek do Shapefile. Po ukončení bloku `using` je soubor uzavřen a připraven k použití v jakékoli GIS aplikaci.

```csharp
layer.Add(feature);
```

## Běžné problémy a tipy
- **Pořadí souřadnic:** Aspose.GIS očekává souřadnice v pořadí `X Y` (zeměpisná délka, šířka). Prohození pořadí převrátí geometrii.  
- **Syntaxe CircularString:** Střední bod musí ležet na zamýšleném oblouku; jinak se křivka zhroutí do přímé linie.  
- **Přepsání souboru:** `VectorLayer.Create` přepíše existující Shapefile bez varování – během vývoje použijte jedinečný název souboru.  
- **Výkon:** Pro velké datové sady přidávejte funkce dávkově místo vkládání po jedné uvnitř bloku `using`.  
- **Tip pro profesionály:** Znovu použijte stejnou instanci `CompoundCurve` při vytváření mnoha podobných prvků; před opětovným naplněním zavolejte `compoundCurve.Clear()`, aby se snížily alokace.

## Často kladené otázky

**Q: Mohu použít Aspose.GIS pro .NET s jinými .NET frameworky?**  
A: Ano, Aspose.GIS funguje s .NET Framework, .NET Core a .NET Standard, pokrývající verze od 4.6 až po .NET 7.

**Q: Podporuje Aspose.GIS čtení a zápis různých geoprostorových formátů souborů?**  
A: Rozhodně. Čte a zapisuje Shapefile, GeoJSON, KML, GML a více než 30 dalších formátů.

**Q: Je Aspose.GIS vhodný jak pro desktopové, tak pro webové aplikace?**  
A: Ano, knihovnu lze použít v desktopových, webových i cloudových službách bez jakýchkoli specifických závislostí na platformě.

**Q: Mohu provádět prostorové analýzy s Aspose.GIS pro .NET?**  
A: Ano, můžete počítat vzdálenosti, provádět geometrické operace a spouštět prostorové dotazy přímo na geometriích.

**Q: Kde mohu získat komunitní podporu pro Aspose.GIS?**  
A: Navštivte [forum Aspose.GIS](https://forum.aspose.com/c/gis/33), kde můžete klást otázky a sdílet nápady s ostatními vývojáři.

---

**Poslední aktualizace:** 2026-08-24  
**Testováno s:** Aspose.GIS pro .NET (nejnovější stabilní verze)  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit vektorovou vrstvu a kruhový řetězec v Aspose.GIS pro .NET](/gis/net/geometry-creation/create-circular-string-geometry/)
- [Vytvořit vektorovou vrstvu a křivkový polygon s Aspose.GIS](/gis/net/geometry-creation/create-curve-polygon-geometry/)
- [Převést WKT na geometrii: MultiCurve s Aspose.GIS .NET](/gis/net/geometry-creation/create-multicurve-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
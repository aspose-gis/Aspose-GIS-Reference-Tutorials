---
date: 2026-06-10
description: Naučte se, jak přidávat body a přidávat souřadnice do tvaru při iteraci
  přes geometrii pomocí Aspose.GIS for .NET, výkonného GIS nástroje pro vývojáře .NET.
keywords:
- how to add points
- add coordinates to shape
- Aspose.GIS geometry
linktitle: Jak přidat body a iterovat přes geometrii v .NET
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  headline: How to Add Points and Iterate Over Geometry in .NET
  type: TechArticle
- description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  name: How to Add Points and Iterate Over Geometry in .NET
  steps:
  - name: Create a `LineString` object
    text: '`LineString` is Aspose.GIS''s geometry type that represents an ordered
      collection of points forming a polyline.'
  - name: Add points to the `LineString`
    text: The `AddPoint` method inserts a new vertex (longitude, latitude) at the
      end of the line. Call it repeatedly to **add coordinates to shape** objects.
  - name: Iterate over the points
    text: '`LineString` implements `IEnumerable<IPoint>`, allowing you to loop through
      each point with a `foreach` statement. This makes extracting X (longitude) and
      Y (latitude) values trivial. The loop prints each point’s X (longitude) and
      Y (latitude) values to the console, allowing you to verify that the p'
  type: HowTo
- questions:
  - answer: '`LineString`'
    question: What is the primary class for point collections?
  - answer: Use `AddPoint(longitude, latitude)`
    question: How do you add a point?
  - answer: Yes, `LineString` implements `IEnumerable<IPoint>`
    question: Can you iterate with a foreach loop?
  - answer: .NET 6+ (or .NET Core 3.1/Framework 4.6+) and Aspose.GIS for .NET library
    question: Prerequisites?
  - answer: Building routes, visualizing tracks, or preprocessing data for spatial
      analysis
    question: Typical use case?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Jak přidat body a iterovat přes geometrii v .NET
url: /cs/net/geometry-processing/iterate-over-points-in-geometry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat body a iterovat přes geometrii v .NET

## Úvod

Pokud pracujete s GIS daty v prostředí .NET, jednou z prvních věcí, kterou potřebujete vědět, je **jak přidat body** do geometrie a následně s těmito body pracovat. Aspose.GIS pro .NET poskytuje čisté, objektově orientované API, které tento proces usnadňuje. V tomto tutoriálu projdeme vytvoření `LineString`, přidání bodů do něj a iteraci přes tyto body, abyste mohli získat souřadnice nebo provést další analýzu. Také uvidíte, jak **efektivně přidávat souřadnice do shape** objektů.

## Rychlé odpovědi
- **Jaká je hlavní třída pro kolekce bodů?** `LineString`
- **Jak přidáte bod?** Použijte `AddPoint(longitude, latitude)`
- **Můžete iterovat pomocí smyčky foreach?** Ano, `LineString` implementuje `IEnumerable<IPoint>`
- **Požadavky?** .NET 6+ (nebo .NET Core 3.1/Framework 4.6+) a knihovna Aspose.GIS pro .NET
- **Typický případ použití?** Vytváření tras, vizualizace stop nebo předzpracování dat pro prostorovou analýzu
- **IPoint** představuje geometrii jednoho bodu se souřadnicemi X (longitude) a Y (latitude).

## Co znamená „přidávání bodů“ v GIS?

Přidávání bodů znamená vložení jednotlivých dvojic souřadnic (longitude, latitude) do geometrického kontejneru, jako je `LineString`, `Polygon` nebo `MultiPoint`. Každý bod se stane vrcholem, který definuje tvar nebo cestu, kterou modelujete, což umožňuje prostorové operace a vizualizace. Tyto vrcholy lze později přistupovat pro analýzu, exportovat do různých GIS formátů nebo použít ve prostorových výpočtech, jako je měření vzdálenosti či testování průniku.

## Proč přidávat body pomocí Aspose.GIS?

Přidáváte body pomocí Aspose.GIS, protože knihovna zaručuje **typově bezpečnou manipulaci s geometrií**, podporuje **více než 30 vektorových a rastrových formátů** a může zpracovat **datové sady o stovkách stránek** bez načítání celého souboru do paměti. API také nabízí vestavěnou iteraci, prostorové operace a konverzi formátů (Shapefile, GeoJSON, KML atd.) na každé podporované platformě.

## Požadavky

- Visual Studio 2022 (nebo jakékoli C# IDE)  
- Nainstalovaný NuGet balíček Aspose.GIS pro .NET  
- Základní znalost syntaxe C#

## Importovat jmenné prostory

Začněte importováním potřebných jmenných prostorů, aby bylo možné v aplikaci .NET přistupovat k funkcím Aspose.GIS:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Jak přidat body do geometrie?

Body přidáte vytvořením instance `LineString`, voláním její metody `AddPoint` pro každou dvojici souřadnic a následnou iterací přes kolekci podle potřeby. Tento tříkrokový vzor zahrnuje vytvoření, naplnění a procházení v stručném a čitelném způsobu. **LineString je typ geometrie představující uspořádanou kolekci bodů tvořících polyline.** Tento přístup zajišťuje, že geometrie zůstane platná a připravená pro další prostorové operace, jako je výpočet délky nebo export.

### Krok 1: Vytvořit objekt `LineString`  

`LineString` je typ geometrie Aspose.GIS, který představuje uspořádanou kolekci bodů tvořících polyline.

```csharp
LineString line = new LineString();
```

### Krok 2: Přidat body do `LineString`  

Metoda `AddPoint` vloží nový vrchol (longitude, latitude) na konec čáry. Volajte ji opakovaně, abyste **přidali souřadnice do shape** objektů.

```csharp
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```

### Krok 3: Iterovat přes body  

`LineString` implementuje `IEnumerable<IPoint>`, což vám umožní procházet každý bod pomocí smyčky `foreach`. To usnadňuje extrakci hodnot X (longitude) a Y (latitude).

```csharp
foreach (IPoint point in line)
{
    Console.WriteLine(point.X + "," + point.Y);
}
```

Smyčka vypíše hodnoty X (longitude) a Y (latitude) každého bodu do konzole, což vám umožní ověřit, že body byly přidány správně.

## Běžné případy použití

- **Plánování trasy** – Vytvořte cestu z GPS záznamů a poté analyzujte vzdálenosti mezi waypointy.  
- **Validace dat** – Iterujte přes body, abyste zajistili, že spadají do očekávaných hranic (např. v rámci hranic země).  
- **Vizualizace** – Exportujte `LineString` do GeoJSON nebo Shapefile pro použití v mapovacích nástrojích.

## Často kladené otázky

**Q1: Dokáže Aspose.GIS pro .NET zpracovávat jiné geometrické tvary kromě `LineString`?**  
A: Ano, Aspose.GIS podporuje `Point`, `Polygon`, `MultiLineString`, `MultiPolygon` a mnoho dalších typů geometrie.

**Q2: Je Aspose.GIS vhodný jak pro komerční, tak i osobní projekty?**  
A: Rozhodně. Licenční možnosti pokrývají komerční, osobní i vzdělávací případy použití.

**Q3: Nabízí Aspose.GIS pro .NET komplexní dokumentaci pro začátečníky?**  
A: Ano, produkt obsahuje rozsáhlou dokumentaci, reference API a desítky příkladů kódu, které vám pomohou rychle začít.

**Q4: Mohu rozšířit funkčnost Aspose.GIS pro .NET pomocí vlastního vývoje?**  
A: Můžete vytvářet rozšiřující metody nebo obalovat třídy Aspose.GIS tak, aby vyhovovaly konkrétním pracovním postupům, což vám poskytne plnou kontrolu nad vlastními geoprostorovými řešeními.

**Q5: Je k dispozici technická podpora pro uživatele Aspose.GIS?**  
A: Vyhrazená technická podpora je poskytována prostřednictvím fór Aspose a ticketovacího systému, což zajišťuje rychlou pomoc.

**Poslední aktualizace:** 2026-06-10  
**Testováno s:** Aspose.GIS pro .NET 24.5 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak spočítat body v geometrii pomocí Aspose.GIS pro .NET](/gis/net/geometry-creation/count-points-in-geometry/)
- [Jak přidat bod do LineString a převést geometrii do editovatelného formátu pomocí Aspose.GIS](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [Vytvořit MultiPoint geometrii pomocí Aspose.GIS pro .NET](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
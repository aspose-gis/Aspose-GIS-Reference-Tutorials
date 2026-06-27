---
date: 2026-06-05
description: Naučte se, jak porovnat geometries v .NET pomocí Aspose.GIS, detekovat
  duplicate geometries a zkontrolovat geometry equality ve vašich aplikacích.
keywords:
- how to compare geometries
- detect duplicate geometries
- Aspose.GIS geometry equality
linktitle: Jak porovnat geometries na rovnost
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to compare geometries in .NET using Aspose.GIS, detect duplicate
    geometries, and check geometry equality in your applications.
  headline: How to Compare Geometries for Equality using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard
      projects.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. Download a trial from the [Aspose.GIS releases page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Detailed docs are on the [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).
    question: Where can I find the full API documentation?
  - answer: Post your question on the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How do I get help if I run into an issue?
  - answer: Yes, temporary licenses are available on the [purchase page](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Jak porovnat geometries na rovnost pomocí Aspose.GIS pro .NET
url: /cs/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak porovnat geometrie pro rovnost pomocí Aspose.GIS pro .NET

## Úvod
V tomto tutoriálu se naučíte **jak porovnat geometrie** s Aspose.GIS pro .NET, úkol, který je zásadní, když potřebujete detekovat duplicitní geometrie, ověřovat prostorová data nebo vynucovat topologická pravidla. Ať už vytváříte mapovou službu, provádíte dávkovou prostorovou analýzu, nebo jen ověřujete, že dva tvary zabírají stejné místo, tento průvodce vás provede tvorbou, úpravou a testováním rovnosti geometrie pomocí čistého, produkčně připraveného C# kódu.

## Rychlé odpovědi
- **Co znamená „compare geometries“?** Kontroluje, zda dva geometrické objekty zabírají stejný prostor, bez ohledu na to, jak jsou vytvořeny.  
- **Která metoda se používá?** `SpatiallyEquals` z Aspose.GIS API.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Podporované verze .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Typický čas implementace?** Zhruba 5‑10 minut pro základní kontrolu rovnosti.

## Co je rovnost geometrie?
Rovnost geometrie, také nazývaná prostorová rovnost, znamená, že dvě geometrie představují přesně stejnou sadu bodů na povrchu Země. I když je jedna geometrie vytvořena jako `MultiLineString` a druhá jako jediný `LineString`, jsou považovány za rovné, pokud se každá souřadnice shoduje v rámci definované tolerance. Tato definice umožňuje vývojářům spolehlivě detekovat duplicitní geometrie napříč heterogenními zdroji dat.

## Proč použít Aspose.GIS k porovnání geometrie?
Aspose.GIS nabízí vysoce výkonný, offline geometrický engine, který eliminuje potřebu externích služeb. **Podporuje více než 30 vektorových a rastrových formátů** (včetně WKT, GeoJSON, Shapefile, KML, GML) a dokáže zpracovat soubory s **stovkami tisíců vrcholů** při zachování využití paměti pod 50 MB. Metoda `SpatiallyEquals` knihovny je citlivá na přesnost a poskytuje deterministické výsledky i při souřadnicích s plovoucí desetinnou čárkou.

### Proč je to důležité pro vývojáře
Když potřebujete **detekovat duplicitní geometrie** v dávkových procesech, real‑time validačních pipelinech nebo migracích GIS dat, osvědčená knihovna odstraňuje hádání a zaručuje konzistentní výsledky napříč různými poskytovateli dat.

## Požadavky
Před zahájením se ujistěte, že máte následující:

- **.NET Framework nebo .NET Core nainstalován** – jakákoli verze podporovaná Aspose.GIS.  
- **Knihovna Aspose.GIS pro .NET** – stáhněte z [Aspose.GIS download page](https://releases.aspose.com/gis/net/).  
- **Vývojové IDE** – Visual Studio, Rider nebo VS Code s rozšířeními pro C#.

## Importovat jmenné prostory
Ve svém .NET projektu přidejte požadované `using` příkazy, aby kompilátor věděl, kde najít GIS třídy:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Definovat geometrie
`MultiLineString` představuje kolekci liniových komponent, zatímco `LineString` definuje jednu souvislou linii. Obě třídy dědí z základního typu `Geometry`.

Nejprve vytvoříme dvě geometrie, které budeme porovnávat. V tomto příkladu je `geometry1` `MultiLineString` složený ze dvou úseků, zatímco `geometry2` je jediný `LineString`, který pokrývá stejné počáteční a koncové body.

```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```

## Krok 2: Zkontrolovat rovnost geometrie
`SpatiallyEquals` vyhodnocuje, zda dvě geometrie zabírají stejnou sadu bodů, volitelně přijímá hodnotu tolerance pro nepřesnost plovoucí desetinné čárky.

Nyní použijeme metodu `SpatiallyEquals`, abychom zjistili, zda jsou oba tvary považovány za rovné GIS enginem.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

Konzole vypíše `True`, protože navzdory odlišné konstrukci obě geometrie pokrývají stejnou linii od (0,0) do (2,2).

## Krok 3: Upravit jednu geometrii
Abychom ilustrovali, jak změna ovlivní rovnost, přidáme do `geometry2` další bod.

```csharp
geometry2.AddPoint(3, 3);
```

## Krok 4: Znovu zkontrolovat rovnost po úpravě
Po úpravě již geometrie nejsou stejné, takže `SpatiallyEquals` vrátí `False`.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

Výstup `False` potvrzuje, že přidaný bod narušil prostorovou rovnost.

## Jak detekovat duplicitní geometrie?
Načtěte každou geometrii, zavolejte `SpatiallyEquals` s vhodnou tolerancí a odfiltrujte ty, které vrátí `True`. Tento vzor se dobře škáluje s LINQ, což vám umožní identifikovat duplicitní tvary ve velkých kolekcích pomocí několika řádků kódu. Můžete jej také kombinovat s `GroupBy` pro agregaci identických geometrií a snížení nákladů na úložiště.

## Časté problémy a tipy
- **Problémy s přesností** – Pokud pracujete s velmi vysoce přesnými souřadnicemi, zvažte zaokrouhlování nebo použití přetížení s tolerancí metody `SpatiallyEquals`.  
- **Různé SRID** – Ujistěte se, že obě geometrie sdílejí stejný Spatial Reference System Identifier (SRID) před porovnáním.  
- **Výkon** – Pro velké kolekce mohou dávkové porovnání pomocí LINQ nebo paralelních smyček dramaticky snížit režii.

## Často kladené otázky
**Q: Mohu použít Aspose.GIS pro .NET s jinými .NET frameworky?**  
**A:** Ano, Aspose.GIS funguje s projekty .NET Framework, .NET Core i .NET Standard.

**Q: Je k dispozici bezplatná zkušební verze?**  
**A:** Rozhodně. Stáhněte si zkušební verzi z [Aspose.GIS releases page](https://releases.aspose.com/).

**Q: Kde najdu úplnou dokumentaci API?**  
**A:** Podrobné dokumenty jsou na [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).

**Q: Jak získám pomoc, pokud narazím na problém?**  
**A:** Položte svůj dotaz na komunitní fórum Aspose.GIS [zde](https://forum.aspose.com/c/gis/33).

**Q: Mohu zakoupit dočasnou licenci pro vyhodnocení?**  
**A:** Ano, dočasné licence jsou k dispozici na [purchase page](https://purchase.aspose.com/temporary-license/).

## Závěr
Nyní už víte **jak porovnat geometrie** pomocí Aspose.GIS pro .NET, od vytvoření objektů po kontrolu prostorové rovnosti a zpracování úprav. Tato schopnost je stavebním kamenem pro pokročilejší prostorové analýzy, jako je validace topologie, detekce duplicit a filtrování založené na geometrii.

---

**Poslední aktualizace:** 2026-06-05  
**Testováno s:** Aspose.GIS for .NET 24.11  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Vytvořit polygonovou geometrii C# a zkontrolovat průnik s Aspose.GIS pro .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Jak provést analýzu prostorového překrytí geometrie s Aspose.GIS pro .NET](/gis/net/geometry-analysis/check-geometries-overlap/)
- [Kontrola síťového směrování: dotýkající se geometrie s Aspose.GIS](/gis/net/geometry-analysis/check-geometries-touching/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
date: 2026-08-03
description: Naučte se, jak vytvořit linestring c# pomocí Aspose.GIS pro .NET, přidávat
  body do linestringu a provádět kontrolu bodu na linii pomocí metody covers.
keywords:
- create linestring c#
- point on line check
- add points to linestring
- use covers method
lastmod: 2026-08-03
linktitle: Vytvořit linestring c# – Zkontrolovat, zda geometrie pokrývá jinou
og_description: Vytvořte linestring c# a ověřte bod na linii pomocí metody covers
  v Aspose.GIS. Naučte se přesné kontroly geometrie pro aplikace .NET. (150‑160 znaků)
og_image_alt: Developer guide showing linestring creation and covers check in C# with
  Aspose.GIS
og_title: Vytvořit linestring c# – Zkontrolovat, zda geometrie pokrývá jinou (50‑60
  znaků)
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  headline: Create linestring c# – Check geometry covers another
  type: TechArticle
- description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  name: Create linestring c# – Check geometry covers another
  steps:
  - name: create a linestring object
    text: The `LineString` class represents a sequence of points connected by straight
      line segments in a two‑dimensional plane. Here, we instantiate a new `LineString`
      object, which represents a sequence of connected line segments in a two‑dimensional
      space.
  - name: add points to linestring
    text: '`AddPoint` appends a coordinate pair to the end of the `LineString` collection,
      preserving the order of insertion. We **add points to linestring** using the
      `AddPoint` method. In this example, we add two points: (0, 0) and (1, 1), forming
      a simple diagonal line segment.'
  - name: create a point object
    text: The `Point` class models a single location in a two‑dimensional coordinate
      system. Instantiate a `Point` object representing a single point in a two‑dimensional
      space. Here, we create a point at coordinates (0, 0).
  - name: perform a point on line check – does the line cover the point?
    text: '`Covers` determines whether the first geometry completely contains the
      second geometry, returning true only when every point of the second geometry
      lies inside the first. Use the `Covers` method to check if the line covers the
      point. In this case, it returns `True` because the point (0, 0) lies exac'
  - name: verify the reverse relationship – is the point covered by the line?
    text: '`CoveredBy` is the inverse of `Covers`; it returns true when the invoking
      geometry is entirely inside the target geometry. Similarly, use the `CoveredBy`
      method to check if the point is covered by the line. Since the point (0, 0)
      lies on the line, it also returns `True`.'
  type: HowTo
- questions:
  - answer: Yes, you can use Aspose.GIS for .NET in both commercial and non‑commercial
      projects after obtaining the appropriate license.
    question: Can I use Aspose.GIS for .NET in my commercial projects?
  - answer: Yes, Aspose.GIS for .NET is compatible with both .NET Framework and .NET
      Core environments.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Yes, Aspose.GIS for .NET supports a wide range of GIS formats including
      Shapefile, GeoJSON, KML, and more.
    question: Does Aspose.GIS for .NET support various GIS formats?
  - answer: Aspose.GIS for .NET is a proprietary library developed by Aspose, so external
      contributions are not accepted. However, you can provide feedback and suggestions
      to improve the library.
    question: Can I contribute to the development of Aspose.GIS for .NET?
  - answer: Updates for Aspose.GIS for .NET are released regularly to introduce new
      features, enhancements, and bug fixes. Check the [website](https://releases.aspose.com/gis/net/)
      for the latest releases.
    question: How often are updates released for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create linestring
- Aspose.GIS
- C# geometry analysis
title: Vytvořit linestring c# – Zkontrolovat, zda geometrie pokrývá jinou
url: /cs/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zkontrolujte, zda geometrie pokrývá jinou

## Úvod
V tomto tutoriálu se naučíte **jak vytvořit LineString v C#** pomocí Aspose.GIS pro .NET, přidávat body do LineStringu a provádět spolehlivou **kontrolu bodu na linii** pomocí metod `Covers` a `CoveredBy`. Ať už budujete mapovací nástroj, provádíte prostorovou analytiku nebo jen potřebujete ověřit geometrické vztahy, zvládnutí těchto operací dodá vaší aplikaci potřebnou přesnost.

## Rychlé odpovědi
- **Co znamená „create linestring c#“?** Jedná se o vytvoření objektu geometrie `LineString` a naplnění jej souřadnicovými body.  
- **Která metoda kontroluje, zda bod leží na linii?** Použijte metodu `Covers` na objektu `LineString` nebo `CoveredBy` na objektu `Point`.  
- **Potřebuji licenci pro spuštění ukázky?** Dočasná licence stačí pro vyhodnocení; pro produkční nasazení je vyžadována plná licence.  
- **Lze to použít s .NET Core?** Ano, Aspose.GIS podporuje .NET Framework i .NET Core.  
- **Kolik bodů mohu přidat do LineStringu?** Neexistuje pevný limit; můžete přidat libovolný počet bodů potřebných pro vaši prostorovou analýzu.

## Co je „create linestring c#“?
`LineString` je geometrický tvar složený z uspořádaného seznamu bodů spojených přímými úseky. V C# jej vytvoříte instancí třídy `LineString` z jmenného prostoru `Aspose.Gis.Geometries` a následně **přidáte body do LineStringu** pomocí metody `AddPoint`. Tento objekt slouží jako základ pro jakoukoli lineární prostorovou analýzu, například mapování tras nebo sledování sítí.

## Proč použít Aspose.GIS pro kontrolu bodu na linii?
`Covers` je prostorový predikát, který vrací true, pokud první geometrie zcela obsahuje druhou.  
Aspose.GIS poskytuje deterministickou, vysoce přesnou implementaci prostorových predikátů. Podporuje více než 50 vstupních a výstupních GIS formátů, dokáže zpracovat stovky kilometrů lineárních sítí bez načítání celého datasetu do paměti a běží na .NET Framework, .NET Core i .NET 5/6+. Použití metody `Covers` zajišťuje, že jsou zohledněny chyby zaokrouhlování s plovoucí desetinnou čárkou, což poskytuje spolehlivé výsledky i v náročných podnicích.

## Předpoklady
Než se pustíte do používání Aspose.GIS pro .NET, ujistěte se, že máte nastavené následující předpoklady:

### 1. Instalace Visual Studio
Ujistěte se, že máte na svém systému nainstalováno Visual Studio. Aspose.GIS pro .NET se bez problémů integruje s Visual Studio a poskytuje plynulý vývojový zážitek.

### 2. Získání Aspose.GIS pro .NET
Stáhněte knihovnu Aspose.GIS pro .NET z [webových stránek](https://releases.aspose.com/gis/net/). Můžete knihovnu stáhnout přímo nebo použít správce balíčků jako NuGet k instalaci do vašeho projektu.

### 3. Základní znalost .NET Framework
Základní povědomí o .NET frameworku a programovacím jazyce C# je nezbytné pro efektivní využití Aspose.GIS pro .NET.

### 4. Přístup k dokumentaci a podpoře
Odkazujte se na [dokumentaci](https://reference.aspose.com/gis/net/) pro podrobné informace o API a funkcionalitách Aspose.GIS. V případě problémů nebo otázek využijte [Aspose.GIS fórum](https://forum.aspose.com/c/gis/33).

### 5. Volitelně: dočasná licence
Pokud Aspose.GIS pro .NET zkoušíte, můžete získat dočasnou licenci na [stránce dočasné licence](https://purchase.aspose.com/temporary-license/) pro vyhodnocení funkcí knihovny.

## Import jmenných prostorů
Před použitím Aspose.GIS pro .NET ve vašem projektu musíte importovat potřebné jmenné prostory:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Nyní rozdělíme ukázkový kód do několika kroků, abychom pochopili, **jak zkontrolovat, zda jedna geometrie pokrývá jinou** pomocí Aspose.GIS pro .NET.

## Jak vytvořit linestring c# – průvodce krok za krokem
Načtěte svůj projekt, importujte požadované jmenné prostory a poté postupujte podle následujících pěti stručných kroků. V několika řádcích kódu získáte objekt `LineString`, objekt `Point` a dva logické testy, které vám řeknou, zda linie pokrývá bod a zda je bod pokryt linií.

### Krok 1: vytvoření objektu linestring
Třída `LineString` představuje sekvenci bodů spojených přímými úseky v dvojrozměrném prostoru.  
```csharp
var line = new LineString();
```
Zde instancujeme nový objekt `LineString`, který představuje sekvenci spojených úseků v dvojrozměrném prostoru.

### Krok 2: přidání bodů do linestringu
`AddPoint` připojí souřadnicový pár na konec kolekce `LineString`, zachovávajíc pořadí vkládání.  
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
**Přidáváme body do linestringu** pomocí metody `AddPoint`. V tomto příkladu přidáváme dva body: (0, 0) a (1, 1), čímž vznikne jednoduchý úhlopříčný úsek.

### Krok 3: vytvoření objektu point
Třída `Point` modeluje jedinou polohu ve dvojrozměrném souřadnicovém systému.  
```csharp
var point = new Point(0, 0);
```
Instancujte objekt `Point` představující jediný bod ve dvojrozměrném prostoru. Zde vytvoříme bod se souřadnicemi (0, 0).

### Krok 4: provedení kontroly bodu na linii – pokrývá linie bod?
`Covers` určuje, zda první geometrie zcela obsahuje druhou geometrie, a vrací true pouze tehdy, když každý bod druhé geometrie leží uvnitř první.  
```csharp
Console.WriteLine(line.Covers(point));    // True
```
Použijte metodu `Covers` k ověření, zda linie pokrývá bod. V tomto případě vrátí `True`, protože bod (0, 0) leží přesně na linii.

### Krok 5: ověření opačného vztahu – je bod pokryt linií?
`CoveredBy` je inverzní metoda k `Covers`; vrací true, když je volající geometrie zcela uvnitř cílové geometrie.  
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
Podobně použijte metodu `CoveredBy` k ověření, zda je bod pokryt linií. Protože bod (0, 0) leží na linii, metoda také vrátí `True`.

## Časté problémy a řešení
| Problém | Proč k tomu dochází | Řešení |
|-------|----------------|-----|
| `line.Covers(point)` vrací `False`, i když bod vypadá, že leží na linii | Souřadnice bodu nejsou přesně stejné kvůli přesnosti plovoucí desetinné čárky. | Použijte `Math.Round` na souřadnice nebo provádějte kontrolu s tolerancí pomocí `line.Distance(point) < epsilon`. |
| Chybí `using Aspose.Gis.Geometries;` | Jmenný prostor není importován, což způsobuje chyby při kompilaci. | Ujistěte se, že importní příkaz je přítomen (viz sekce **Import jmenných prostorů**). |
| Výjimka licence za běhu | Není načtena platná licence pro produkční prostředí. | Načtěte dočasnou nebo plnou licenci pomocí `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Často kladené otázky

**Q: Mohu používat Aspose.GIS pro .NET ve svých komerčních projektech?**  
A: Ano, můžete používat Aspose.GIS pro .NET jak v komerčních, tak nekomerčních projektech po získání příslušné licence.

**Q: Je Aspose.GIS pro .NET kompatibilní s .NET Core?**  
A: Ano, Aspose.GIS pro .NET je kompatibilní jak s .NET Framework, tak s .NET Core.

**Q: Podporuje Aspose.GIS pro .NET různé GIS formáty?**  
A: Ano, Aspose.GIS pro .NET podporuje širokou škálu GIS formátů včetně Shapefile, GeoJSON, KML a dalších.

**Q: Mohu přispívat k vývoji Aspose.GIS pro .NET?**  
A: Aspose.GIS pro .NET je proprietární knihovna vyvíjená společností Aspose, takže externí příspěvky nejsou přijímány. Můžete však poskytovat zpětnou vazbu a návrhy na zlepšení knihovny.

**Q: Jak často jsou vydávány aktualizace pro Aspose.GIS pro .NET?**  
A: Aktualizace pro Aspose.GIS pro .NET jsou vydávány pravidelně, aby přinesly nové funkce, vylepšení a opravy chyb. Nejnovější verze najdete na [webových stránkách](https://releases.aspose.com/gis/net/).

## Závěr
Po absolvování výše uvedených kroků nyní umíte **vytvořit linestring v C#**, **přidat body do linestringu** a provést spolehlivou **kontrolu bodu na linii** pomocí metod `Covers` a `CoveredBy`. Tato schopnost rozšiřuje funkce prostorové analýzy vašeho softwaru a otevírá dveře k pokročilejším GIS operacím, jako je validace tras, kontrola topologie sítí a dotazy na blízkost.

---

**Poslední aktualizace:** 2026-08-03  
**Testováno s:** Aspose.GIS pro .NET (nejnovější verze)  
**Autor:** Aspose

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Naučte se vytvořit geometrie LineString s Aspose.GIS pro .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Jak přidat bod do LineString a převést geometrie do editovatelného formátu s Aspose.GIS](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [point inside polygon c# – Zkontrolujte, zda geometrie obsahuje jinou](/gis/net/geometry-analysis/check-geometry-contains-another/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
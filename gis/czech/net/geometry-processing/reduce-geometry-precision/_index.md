---
date: 2026-09-10
description: Zjistěte, jak snížit velikost souboru geometrie snížením přesnosti a
  zaokrouhlením hodnot Z pomocí Aspose.GIS for .NET, což zlepšuje výkon a snižuje
  využití paměti.
keywords:
- reduce geometry file size
- reduce geometry precision
- round Z values
- Aspose.GIS .NET
- geometry processing
lastmod: 2026-09-10
linktitle: Snížit přesnost geometrie
og_description: Zjistěte, jak snížit velikost souboru geometrie snížením přesnosti
  a zaokrouhlením hodnot Z pomocí Aspose.GIS for .NET, což zlepšuje výkon a snižuje
  využití paměti.
og_image_alt: Guide showing how to reduce geometry file size by rounding Z in .NET
  using Aspose.GIS
og_title: Jak snížit velikost souboru geometrie zaokrouhlením Z v .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to reduce geometry file size by lowering precision and rounding
    Z values with Aspose.GIS for .NET, improving performance and cutting memory usage.
  headline: How to reduce geometry file size by rounding Z in .NET
  type: TechArticle
- questions:
  - answer: Reducing geometry precision helps optimize memory usage and improve performance,
      especially when dealing with large datasets in GIS applications.
    question: Why is geometry precision reduction important in GIS?
  - answer: While minor accuracy is lost, the trade‑off often yields a good balance
      between precision and performance for most spatial analyses.
    question: Does reducing geometry precision affect accuracy?
  - answer: Yes, you can specify the desired number of decimal places for both XY
      and Z coordinates using the `RoundXY` and `RoundZ` methods.
    question: Can I customize the precision reduction level in Aspose.GIS for .NET?
  - answer: Absolutely—less data per vertex means faster spatial queries, reduced
      I/O, and lower memory consumption, often delivering **30 % faster processing**
      on typical datasets.
    question: Are there measurable performance benefits?
  - answer: You can get support by visiting the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      or accessing the documentation available in the [Aspose.GIS .NET API reference](https://reference.aspose.com/gis/net/).
    question: Where can I get support for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- reduce geometry file size
- Aspose.GIS
- .NET GIS
- geometry precision
- round Z
title: Jak snížit velikost souboru geometrie zaokrouhlením Z v .NET
url: /cs/net/geometry-processing/reduce-geometry-precision/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak snížit velikost souboru geometrie zaokrouhlením Z v .NET

## Úvod
Pokud pracujete s velkými prostorovými datovými sadami, pravděpodobně jste si všimli, že každé další desetinné místo ve vašich geometrických datech se sčítá – jak ve velikosti souboru, tak v čase zpracování. V tomto tutoriálu se naučíte **jak snížit velikost souboru geometrie** snížením přesnosti geometrie a **jak zaokrouhlit Z** hodnoty pomocí Aspose.GIS pro .NET. Na konci průvodce budete schopni zmenšit soubory geometrie, urychlit prostorové operace a udržet nízkou paměťovou stopu, vše pomocí několika jednoduchých volání metod.

## Rychlé odpovědi
- **Co znamená „round Z“?** Odstraňuje počet desetinných míst souřadnice Z v objektu geometrie.  
- **Proč snižovat velikost souboru geometrie?** Méně desetinných číslic na vrchol snižuje úložiště, urychluje dotazy a snižuje využití RAM.  
- **Která knihovna to řeší?** Aspose.GIS pro .NET poskytuje vestavěné metody `RoundZ` a `RoundXY`.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Mohu řídit počet desetinných míst?** Ano, požadovaný počet číslic zadáte v metodách `Round*`.

## Co je „zaokrouhlení Z“ v GIS?
Zaokrouhlení souřadnice Z odstraňuje zbytečnou desetinnou přesnost, převádí hodnotu například 3.345 na 3.3 (nebo na libovolnou zadanou přesnost). Toto snížení může výrazně zmenšit velikost souboru a urychlit zpracování, zejména když detail výšky jemnější než požadovaná tolerance analýzy není potřebný. Jedná se o běžnou techniku optimalizace 3‑D datových sad.

## Proč snižovat velikost souboru geometrie pomocí Aspose.GIS?
Aspose.GIS podporuje **více než 30 vektorových a rastrových formátů** a může zpracovávat soubory až do **2 GB** bez načítání celé datové sady do paměti. Snížení přesnosti snižuje množství dat na vrchol, což typicky přináší **20‑40 % rychlejší prostorové dotazy** a **15‑30 % nižší spotřebu paměti** u velkých datových sad.

## Požadavky
Před začátkem se ujistěte, že máte následující požadavky:
1. Knihovna Aspose.GIS pro .NET: Stáhněte a nainstalujte knihovnu z [webu Aspose.GIS](https://releases.aspose.com/gis/net/).  
2. Základní znalost programování v C#: Znalost jazyka C# bude užitečná.

## Importujte jmenné prostory
Nejprve importujte potřebné jmenné prostory pro použití tříd a metod Aspose.GIS.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Vytvořte bod
`Point` je základní třída geometrie, která představuje jedinou polohu ve 2‑D nebo 3‑D prostoru. Použijete ji k demonstraci snížení přesnosti.

```csharp
Point point = new Point(1.344, 2.345, 3.345, 4.345);
```

## Krok 2: Snižte přesnost XY
`RoundXY` snižuje počet desetinných míst pro souřadnice X a Y. Tato metoda přijímá požadovaný počet číslic a vrací novou geometrickou objekt s upravenou přesností.

```csharp
point.RoundXY(digits: 2);
```

## Krok 3: Zobrazte souřadnice
Po zaokrouhlení můžete zkontrolovat aktualizované hodnoty souřadnic.

```csharp
Console.WriteLine("{0}, {1}, {2}, {3}", point.X, point.Y, point.Z, point.M);
```

## Krok 4: Snižte přesnost Z – jak zaokrouhlit Z
`RoundZ` omezuje přesnost komponenty výšky (Z). Použití tohoto kroku často přináší největší snížení velikosti souboru u 3‑D datových sad, protože hodnoty výšky často obsahují mnoho desetinných míst.

```csharp
point.RoundZ(digits: 1);
```

## Krok 5: Zobrazte aktualizované souřadnice
Zobrazte souřadnice bodu po snížení přesnosti Z.

```csharp
Console.WriteLine("{0}, {1}, {2}, {3}", point.X, point.Y, point.Z, point.M);
```

## Krok 6: Vytvořte řetězec úseček
`LineString` je kolekce bodů, která tvoří linii. Je užitečný pro demonstraci hromadných změn přesnosti napříč více vrcholy.

```csharp
LineString line = new LineString();
line.AddPoint(1.2, 2.3);
line.AddPoint(2.4, 3.1);
```

## Krok 7: Snižte přesnost XY řetězce úseček
Použijte `RoundXY` na celý `LineString`, aby se ořízly hodnoty X/Y pro každý vrchol.

```csharp
line.RoundXY(digits: 0);
```

## Krok 8: Zobrazte aktualizované souřadnice řetězce úseček
Zkontrolujte souřadnice po snížení přesnosti XY.

```csharp
Console.WriteLine("{0}, {1}", line[0].X, line[0].Y);
Console.WriteLine("{0}, {1}", line[1].X, line[1].Y);
```

## Běžné případy použití a tipy
- **Velké raster‑vektorové konverze:** Zaokrouhlení Z může zmenšit mezilehlé soubory geometrie, což urychlí konverzní pipeline.  
- **Mobilní GIS aplikace:** Nižší přesnost snižuje šířku pásma při přenosu geometrie po síti.  
- **Profesionální tip:** Použijte `RoundXY` před `RoundZ`, aby byl pracovní postup konzistentní a vyhnuli jste se opakovanému zaokrouhlování již zaokrouhlených hodnot.

## Často kladené otázky

**Q: Proč je snížení přesnosti geometrie důležité v GIS?**  
A: Snížení přesnosti geometrie pomáhá optimalizovat využití paměti a zlepšit výkon, zejména při práci s velkými datovými sadami v GIS aplikacích.

**Q: Ovlivňuje snížení přesnosti geometrie přesnost?**  
A: Přestože se ztrácí malá část přesnosti, kompromis často poskytuje dobrý poměr mezi přesností a výkonem pro většinu prostorových analýz.

**Q: Mohu přizpůsobit úroveň snížení přesnosti v Aspose.GIS pro .NET?**  
A: Ano, můžete zadat požadovaný počet desetinných míst pro souřadnice XY i Z pomocí metod `RoundXY` a `RoundZ`.

**Q: Existují měřitelné výkonnostní výhody?**  
A: Rozhodně—méně dat na vrchol znamená rychlejší prostorové dotazy, snížený I/O a nižší spotřebu paměti, často poskytující **30 % rychlejší zpracování** na typických datových sadách.

**Q: Kde mohu získat podporu pro Aspose.GIS pro .NET?**  
A: Podporu můžete získat návštěvou [fóra Aspose.GIS](https://forum.aspose.com/c/gis/33) nebo přístupem k dokumentaci dostupné v [referenci Aspose.GIS .NET API](https://reference.aspose.com/gis/net/).

---

**Poslední aktualizace:** 2026-09-10  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose

## Související tutoriály

- [Jak omezit přesnost při zápisu geometrií pomocí Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)
- [Vytvořit vektorovou vrstvu, omezit přesnost pomocí Aspose.GIS pro .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Jak převést geometrii na WKT pomocí Aspose.GIS pro .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
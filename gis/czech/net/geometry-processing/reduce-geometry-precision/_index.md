---
date: 2026-04-09
description: Naučte se, jak snížit přesnost geometrie a zaokrouhlit hodnoty Z pomocí
  Aspose.GIS pro .NET, což zvyšuje výkon GIS a šetří paměť.
keywords:
- how to reduce geometry
- how to round z
- geometry precision .NET
linktitle: Snížit přesnost geometrie
second_title: Aspose.GIS .NET API
title: Jak snížit přesnost geometrie a zaokrouhlit Z v .NET
url: /cs/net/geometry-processing/reduce-geometry-precision/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak snížit přesnost geometrie a zaokrouhlit Z v .NET

## Úvod
Pokud pracujete s velkými prostorovými datovými sadami, pravděpodobně jste si všimli, že každé další desetinné místo ve vašich geometrických datech se sčítá – jak v velikosti souboru, tak v čase zpracování. V tomto tutoriálu se naučíte **jak snížit přesnost geometrie** a **jak zaokrouhlit Z** hodnoty pomocí Aspose.GIS pro .NET. Na konci průvodce budete schopni zmenšit soubory geometrie, urychlit prostorové operace a udržet nízkou paměťovou stopu, vše pomocí několika jednoduchých volání metod.

## Rychlé odpovědi
- **Co znamená „jak zaokrouhlit Z“?** Odstraňuje počet desetinných míst souřadnice Z v objektu geometrie.  
- **Proč snížit přesnost geometrie?** Snižuje množství dat uložených na každý vrchol, což urychluje prostorové dotazy a snižuje využití paměti.  
- **Která knihovna to řeší?** Aspose.GIS pro .NET poskytuje vestavěné metody `RoundZ` a `RoundXY`.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro testování; pro produkční nasazení je vyžadována komerční licence.  
- **Mohu řídit počet desetinných míst?** Ano, požadovaný počet číslic zadáte v metodách `Round*`.

## Jak snížit přesnost geometrie v .NET
Snížení přesnosti geometrie je tak jednoduché jako zavolat `RoundXY` na libovolném objektu geometrie. Metoda přijímá počet desetinných míst, které chcete zachovat pro souřadnice X a Y. Tento úkon je zvláště užitečný, když pro vaši analýzu není vyžadována přesnost pod metr.

## Jak zaokrouhlit hodnoty Z v .NET
Když vaše data obsahují komponentu Z (nadmořská výška), můžete zavolat `RoundZ` pro omezení její přesnosti. Toto je krok **jak zaokrouhlit Z**, který často přináší největší snížení velikosti souboru u 3‑D datových sad, protože hodnoty nadmořské výšky mají tendenci mít mnoho desetinných míst.

## Co je „jak zaokrouhlit Z“ v GIS?
Zaokrouhlení souřadnice Z odstraňuje nadbytečnou desetinnou přesnost, například převádí hodnotu 3.345 na 3.3 (nebo na libovolnou zvolenou přesnost). Tento jednoduchý úkon může dramaticky zmenšit velikost souborů a urychlit výpočty, zejména když třetí rozměr není pro vaši analýzu kritický.

## Proč snížit přesnost geometrie pomocí Aspose.GIS?
- **Zvýšení výkonu:** Méně dat ke zpracování znamená rychlejší prostorové dotazy a transformace.  
- **Úspora paměti:** Menší reprezentace vrcholů uvolní RAM, což umožní udržet ve paměti větší datové sady.  
- **Flexibilita:** Vy rozhodujete o úrovni přesnosti, která vyvažuje přesnost a rychlost.

## Požadavky
Před začátkem se ujistěte, že máte následující požadavky:
1. Knihovna Aspose.GIS pro .NET: Stáhněte a nainstalujte knihovnu z [webu Aspose.GIS](https://releases.aspose.com/gis/net/).  
2. Základní znalost programování v C#: Znalost programovacího jazyka C# bude užitečná.

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
Začneme vytvořením bodu s konkrétními souřadnicemi.

```csharp
Point point = new Point(1.344, 2.345, 3.345, 4.345);
```

## Krok 2: Snižte přesnost XY
Nyní snížíme přesnost souřadnic X a Y bodu na dvě desetinná místa.

```csharp
point.RoundXY(digits: 2);
```

## Krok 3: Zobrazte souřadnice
Zobrazte aktualizované souřadnice bodu.

```csharp
Console.WriteLine("{0}, {1}, {2}, {3}", point.X, point.Y, point.Z, point.M);
```

## Krok 4: Snižte přesnost Z – **jak zaokrouhlit z**
Dále snížíme přesnost souřadnice Z bodu na jedno desetinné místo. Toto je jádro **jak zaokrouhlit z**.

```csharp
point.RoundZ(digits: 1);
```

## Krok 5: Zobrazte aktualizované souřadnice
Zobrazte aktualizované souřadnice bodu po snížení přesnosti Z.

```csharp
Console.WriteLine("{0}, {1}, {2}, {3}", point.X, point.Y, point.Z, point.M);
```

## Krok 6: Vytvořte LineString
Nyní vytvoříme `LineString` a přidáme do něj body.

```csharp
LineString line = new LineString();
line.AddPoint(1.2, 2.3);
line.AddPoint(2.4, 3.1);
```

## Krok 7: Snižte přesnost XY u LineString
Snižte přesnost souřadnic X a Y `LineString` na nula desetinných míst.

```csharp
line.RoundXY(digits: 0);
```

## Krok 8: Zobrazte aktualizované souřadnice LineString
Zobrazte aktualizované souřadnice `LineString` po snížení přesnosti XY.

```csharp
Console.WriteLine("{0}, {1}", line[0].X, line[0].Y);
Console.WriteLine("{0}, {1}", line[1].X, line[1].Y);
```

## Běžné případy použití a tipy
- **Velké převody raster‑vektor:** Zaokrouhlení Z může zmenšit mezilehlé soubory geometrie.  
- **Mobilní GIS aplikace:** Nižší přesnost snižuje šířku pásma při přenosu geometrie po síti.  
- **Profesionální tip:** Použijte `RoundXY` před `RoundZ`, aby byl pracovní postup konzistentní.

## Často kladené otázky

**Q: Proč je snížení přesnosti geometrie důležité v GIS?**  
A: Snížení přesnosti geometrie pomáhá optimalizovat využití paměti a zlepšit výkon, zejména při práci s velkými datovými sadami v GIS aplikacích.

**Q: Ovlivňuje snížení přesnosti geometrie přesnost?**  
A: Přestože se ztrácí určitá drobná přesnost, kompromis často poskytuje dobrý poměr mezi přesností a výkonem pro většinu prostorových analýz.

**Q: Mohu přizpůsobit úroveň snížení přesnosti v Aspose.GIS pro .NET?**  
A: Ano, můžete zadat požadovaný počet desetinných míst pro souřadnice XY i Z pomocí metod `RoundXY` a `RoundZ`.

**Q: Existují měřitelné výkonnostní výhody?**  
A: Rozhodně – méně dat na vrchol znamená rychlejší prostorové dotazy, snížený I/O a nižší spotřebu paměti.

**Q: Kde mohu získat podporu pro Aspose.GIS pro .NET?**  
A: Podporu získáte návštěvou [fóra Aspose.GIS](https://forum.aspose.com/c/gis/33) nebo přístupem k dokumentaci dostupné [zde](https://reference.aspose.com/gis/net/).

---

**Poslední aktualizace:** 2026-04-09  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
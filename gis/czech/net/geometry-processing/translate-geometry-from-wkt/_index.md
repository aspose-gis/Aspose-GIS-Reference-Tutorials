---
date: 2025-12-23
description: Naučte se, jak převést WKT na geometrii a jak počítat body pomocí Aspose.GIS
  pro .NET. Podrobný návod krok za krokem pro vývojáře.
linktitle: Translate Geometry from WKT
second_title: Aspose.GIS .NET API
title: Jak převést WKT na geometrii pomocí Aspose.GIS v .NET
url: /cs/net/geometry-processing/translate-geometry-from-wkt/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod WKT na geometrii pomocí Aspose.GIS v .NET

## Úvod
V tomto tutoriálu objevíte **jak převést WKT na geometrii** pomocí Aspose.GIS pro .NET a uvidíte praktický příklad **jak spočítat body** v výsledném tvaru. Ať už vytváříte mapovou službu, zpracováváte GIS data, nebo jednoduše potřebujete číst Well‑Known Text v .NET aplikaci, tyto kroky vás rychle uvedou do provozu.

## Rychlé odpovědi
- **Může Aspose.GIS číst WKT?** Ano – metoda `Geometry.FromText` přímo parsuje řetězce WKT.  
- **Kolik řádků kódu je potřeba?** Přibližně 5‑6 řádků pro základní převod a spočítání bodů.  
- **Potřebuji licenci pro produkci?** Ano, pro ne‑zkušební použití je vyžadována komerční licence.  
- **Podporované verze .NET?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6+.  
- **Je počítání bodů vestavěné?** Naprosto – objekty geometrie mají vlastnost `Count`.

## Co je „převod WKT na geometrii“?
Well‑Known Text (WKT) je prostý textový zápis pro reprezentaci geometrických objektů. Převod WKT na geometrii znamená převést tento text na objektový model (např. `ILineString`, `IPolygon`), který můžete programově manipulovat.

## Proč použít Aspose.GIS pro tento převod?
- **Parsing bez závislostí** – není potřeba žádná externí knihovna.  
- **Kompletní sada GIS funkcí** – podporuje 2D/3D souřadnice, správu SRID a mnoho formátů souborů.  
- **Vysoký výkon** – optimalizováno pro velké datové sady a vícevláknové scénáře.  

## Požadavky
Než začneme, ujistěte se, že máte:

1. Aspose.GIS pro .NET API – stáhněte jej z [zde](https://releases.aspose.com/gis/net/).  
2. Základní znalost C# a vývojového prostředí .NET (Visual Studio, VS Code, atd.).

## Importování jmenných prostorů
Nejprve přidejte požadované jmenné prostory do vašeho C# souboru:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Vytvoření LineString z WKT
Nyní **převedeme WKT na geometrii** vytvořením objektu `LineString` z WKT řetězce, který obsahuje Z‑souřadnice:

```csharp
ILineString line = (ILineString)Geometry.FromText("LINESTRING Z (0.1 0.2 0.3, 1 2 1, 12 23 2)");
```

> *Tip:* Metoda `FromText` automaticky detekuje typ geometrie, takže ji můžete přetypovat na odpovídající rozhraní (`ILineString`, `IPolygon`, atd.).

## Jak spočítat body v LineString?
Pro odpověď na sekundární klíčové slovo **how to count points** (jak spočítat body) jednoduše přečtěte vlastnost `Count` instance `ILineString`:

```csharp
Console.WriteLine(line.Count); // Output: 3
```

Výstup ukazuje, že čára obsahuje tři vrcholy, což potvrzuje, že převod byl úspěšný a počet bodů je přesný.

## Závěr
Nyní víte **jak převést WKT na geometrii** pomocí Aspose.GIS pro .NET a jak získat počet bodů jedním voláním vlastnosti. Tyto základy vám umožní integrovat zpracování GIS dat do jakékoli .NET aplikace, od desktopových nástrojů po cloudové služby.

## Často kladené otázky
### Mohu používat Aspose.GIS pro .NET ve svých komerčních projektech?
Ano, můžete. Aspose.GIS pro .NET je licencováno na vývojáře, což vám umožňuje jej používat v komerčních projektech bez jakýchkoli omezení.

### Podporuje Aspose.GIS pro .NET jiné geometrické formáty kromě WKT?
Ano, Aspose.GIS pro .NET podporuje různé geometrické formáty, včetně WKB, GeoJSON a Shapefile.

### Je k dispozici bezplatná zkušební verze Aspose.GIS pro .NET?
Ano, můžete získat bezplatnou zkušební verzi z [zde](https://releases.aspose.com/).

### Kde najdu dokumentaci k Aspose.GIS pro .NET?
Dokumentaci najdete [zde](https://reference.aspose.com/gis/net/).

### Jak mohu získat podporu pro Aspose.GIS pro .NET?
Podporu můžete získat na fóru Aspose.GIS [zde](https://forum.aspose.com/c/gis/33).

## Často kladené otázky (další)

**Q: Co když můj WKT řetězec obsahuje neplatnou syntaxi?**  
A: `Geometry.FromText` vyhodí `FormatException`. Zabalte volání do bloku try‑catch, abyste neplatný WKT ošetřili elegantně.

**Q: Můžu převést kolekci WKT řetězců najednou?**  
A: Ano – projděte seznam řetězců, zavolejte `Geometry.FromText` pro každý prvek a uložte výsledky do `List<IGeometry>`.

**Q: Zachovává Aspose.GIS Z‑hodnoty při převodu?**  
A: Naprosto. Když WKT obsahuje Z souřadnici (jak je ukázáno v příkladu), výsledná geometrie si tyto hodnoty zachová.

**Q: Je možné exportovat geometrii zpět do WKT po úpravě?**  
A: Použijte metodu `ToText()` na libovolné instanci `IGeometry`, abyste získali WKT reprezentaci.

---

**Poslední aktualizace:** 2025-12-23  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
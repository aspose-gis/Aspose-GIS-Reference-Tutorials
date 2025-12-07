---
date: 2025-12-07
description: Naučte se provádět operace překrytí v tomto tutoriálu o prostorovém překrytí
  pomocí Aspose.GIS pro .NET. Ovládněte průnik, sjednocení, rozdíl a symetrický rozdíl.
language: cs
linktitle: Find Geometry Overlays
second_title: Aspose.GIS .NET API
title: Jak provádět překryvové operace pomocí Aspose.GIS pro .NET
url: /net/geometry-analysis/find-geometry-overlays/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak provádět operace překrytí pomocí Aspose.GIS pro .NET

## Úvod
Analýza překrytí je základní technikou v každém **spatial overlay tutorial** — umožňuje kombinovat, porovnávat a získávat poznatky z více geografických vrstev. V tomto průvodci se naučíte **jak provádět překrytí** operací jako Intersection, Union, Difference a Symmetric Difference pomocí výkonné knihovny Aspose.GIS pro .NET. Na konci tutoriálu budete schopni tyto metody použít na reálné GIS problémy, jako je plánování využití území, studie dopadu na životní prostředí a optimalizace tras.

## Rychlé odpovědi
- **Co je operace překrytí?** Prostorová metoda, která kombinuje dvě geometrie a vytváří novou geometrii (intersection, union atd.).  
- **Která knihovna zpracovává překrytí v .NET?** Aspose.GIS pro .NET.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní příklad.  
- **Potřebuji licenci?** Zkušební verze je zdarma; pro produkční nasazení je vyžadována komerční licence.  
- **Mohu to spustit na .NET Core / .NET 6+?** Ano — Aspose.GIS podporuje všechny moderní .NET runtime.

## Co je operace překrytí?
Operace překrytí vezme dva geometrické tvary a vypočítá nový tvar na základě jejich prostorového vztahu.  
- **Intersection** vrací oblast společnou pro oba tvary.  
- **Union** sloučí tvary do jedné geometrie.  
- **Difference** odečte jeden tvar od druhého.  
- **Symmetric Difference** vrací části, které patří buď jednomu, nebo druhému tvaru, ale ne oběma.

## Proč použít Aspose.GIS pro překrytí?
Aspose.GIS poskytuje čisté, plně spravované API, které abstrahuje nízkoúrovňovou matematiku a umožňuje soustředit se na obchodní logiku. Funguje napříč platformami, efektivně zpracovává velké datové sady a bezproblémově se integruje s dalšími .NET komponentami.

## Předpoklady
- Funkční vývojové prostředí .NET (Visual Studio, VS Code nebo .NET CLI).  
- Knihovna Aspose.GIS pro .NET – stáhněte nejnovější verzi z [oficiálního webu](https://releases.aspose.com/gis/net/).

### Importovat jmenné prostory
Před tím, než začnete používat Aspose.GIS pro .NET, musíte do svého projektu importovat potřebné jmenné prostory.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Jak provádět operace překrytí v .NET
Níže je podrobný návod krok za krokem, jak vytvořit dva polygony a použít každou metodu překrytí.

### Krok 1: Vytvořit objekty polygonu
Nejprve definujeme dva jednoduché čtvercové polygony, které se částečně překrývají. Ty budou sloužit jako testovací data.

```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```

### Krok 2: Provedení operace Intersection
**Intersection** nám poskytuje překrývající se oblast dvou polygonů.

```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Polygon
```

### Krok 3: Vytisknout body Intersection
Používáme pomocnou metodu (`PrintRing`) k zobrazení souřadnic výsledného polygonu.

```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```

### Krok 4: Provedení operace Union
**Union** sloučí oba polygony do jednoho tvaru, který pokrývá veškerou oblast pokrytou kterýmkoli z polygonů.

```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Polygon
```

### Krok 5: Vytisknout body Union
Vypište souřadnice spojené geometrie.

```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```

### Krok 6: Provedení operace Difference
**Difference** odečte `polygon2` od `polygon1`, zůstane pouze část `polygon1`, která se neprotíná s `polygon2`.

```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Polygon
```

### Krok 7: Vytisknout body Difference
Zobrazte zbývající vrcholy po odečtení.

```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```

### Krok 8: Provedení operace Symmetric Difference
**Symmetric Difference** vrací oblasti, které patří buď jednomu polygonu, ale ne oběma. Výsledkem je `MultiPolygon`.

```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // MultiPolygon
```

### Krok 9: Vytisknout polygony Symmetric Difference
Projděte každý polygon v `MultiPolygon` a vytiskněte jeho body.

```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```

## Časté problémy a řešení
| Problém | Proč k tomu dochází | Řešení |
|---------|---------------------|--------|
| `null` výsledek z `Intersection` | Polygony se ve skutečnosti nepřekrývají. | Ověřte souřadnice nebo použijte kontrolu `Intersects` před voláním `Intersection`. |
| Neočekávaný `MultiPolygon` z `SymDifference` | Symetrický rozdíl může vytvořit nespojené komponenty. | Přetypujte na `IMultiPolygon` a iterujte, jak je ukázáno. |
| Snížení výkonu u velkých datových sad | Každá operace přepočítává geometrii od začátku. | Znovu použijte mezivýsledky nebo zjednodušte geometrie pomocí `Simplify()` před překrytím. |

## Často kladené otázky

**Q: Mohu používat Aspose.GIS pro .NET ve svých komerčních projektech?**  
A: Ano, Aspose.GIS pro .NET může být používán jak v komerčních, tak nekomerčních projektech s platnou licencí.

**Q: Je k dispozici zkušební verze Aspose.GIS pro .NET?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

**Q: Jak mohu získat podporu pro Aspose.GIS pro .NET?**  
A: Podporu můžete získat na fóru komunity Aspose.GIS [zde](https://forum.aspose.com/c/gis/33).

**Q: Existují dočasné licence pro Aspose.GIS pro .NET?**  
A: Ano, dočasné licence jsou k dispozici pro testování a vyhodnocení. Můžete je získat [zde](https://purchase.aspose.com/temporary-license/).

**Q: Mohu si koupit Aspose.GIS pro .NET přímo?**  
A: Ano, můžete si zakoupit Aspose.GIS pro .NET na webu [zde](https://purchase.aspose.com/buy).

---

**Poslední aktualizace:** 2025-12-07  
**Testováno s:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
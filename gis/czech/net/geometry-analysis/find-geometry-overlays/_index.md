---
date: 2026-08-08
description: Naučte se analýzu symetrického rozdílu GIS překrytí pomocí Aspose.GIS
  pro .NET. Tento tutoriál ukazuje, jak provést překrytí, průnik polygonů, sjednocení,
  rozdíl a symetrický rozdíl v C#.
keywords:
- symmetric difference gis
- calculate polygon intersection
- how to perform overlay
lastmod: 2026-08-08
linktitle: Najít geometrické překrytí
og_description: Objevte, jak provést analýzu symetrického rozdílu GIS překrytí s Aspose.GIS
  pro .NET. Průvodce krok za krokem zahrnuje průnik, sjednocení, rozdíl a další.
og_image_alt: Screenshot of Aspose.GIS overlay operations in a .NET console app
og_title: Symetrický rozdíl GIS překrytí s Aspose.GIS pro .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn symmetric difference GIS overlay analysis using Aspose.GIS for
    .NET. This tutorial shows how to perform overlay, polygon intersection, union,
    difference, and symmetric difference in C#.
  headline: Symmetric difference GIS overlay with Aspose.GIS for .NET
  type: TechArticle
- description: Learn symmetric difference GIS overlay analysis using Aspose.GIS for
    .NET. This tutorial shows how to perform overlay, polygon intersection, union,
    difference, and symmetric difference in C#.
  name: Symmetric difference GIS overlay with Aspose.GIS for .NET
  steps:
  - name: create polygon objects
    text: A `Polygon` represents a closed shape defined by a series of coordinate
      points.
  - name: perform intersection operation
    text: '`Intersection` computes the common area shared by two polygons.'
  - name: print intersection points
    text: '`PrintRing` is a helper that prints each coordinate of a polygon’s exterior
      ring.'
  - name: perform union operation
    text: '`Union` merges two polygons into a single geometry covering all areas.'
  - name: print union points
    text: Output the coordinates of the united geometry.
  - name: perform difference operation
    text: '`Difference` subtracts the second polygon from the first, leaving the non‑overlapping
      portion.'
  - name: print difference points
    text: Show the remaining vertices after the subtraction.
  - name: perform symmetric difference operation
    text: '`SymmetricDifference` returns the parts belonging to either polygon but
      not both, producing a `MultiPolygon`.'
  - name: print symmetric difference polygons
    text: Iterate through each polygon in the `MultiPolygon` and print its points.
  type: HowTo
- questions:
  - answer: Yes, a valid commercial license permits unrestricted use in production
      applications.
    question: Can I use Aspose.GIS for .NET in my commercial projects?
  - answer: Yes, you can download a free trial from the [Aspose releases page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.GIS for .NET?
  - answer: Support is available through the Aspose GIS forum [Aspose GIS forum](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS for .NET?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses offered for testing?
  - answer: You can buy a license directly from the website [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase a full license for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- gis overlay
- Aspose.GIS
- .NET geometry analysis
title: Symetrický rozdíl GIS překrytí s Aspose.GIS pro .NET
url: /cs/net/geometry-analysis/find-geometry-overlays/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Symetrický rozdíl GIS: provádějte překryvné operace pomocí Aspose.GIS pro .NET

Celoanalýza překryvu je základní technikou v každém **návod na prostorový překryv**—umožňuje kombinovat, porovnávat a získávat poznatky z více geografických vrstev. V tomto průvodci se naučíte **jak provádět překryv** operace jako Intersection, Union, Difference a Symmetric Difference pomocí výkonné knihovny Aspose.GIS pro .NET. Na konci tutoriálu budete schopni tyto metody použít na reálné GIS problémy, jako je plánování využití půdy, studie dopadu na životní prostředí a optimalizace tras.

## Rychlé odpovědi
- **Co je operace překryvu?** Překryv kombinuje dvě geometrie a vytvoří nový tvar—intersection, union, difference nebo symmetric difference.  
- **Která .NET knihovna zpracovává překryvy?** Aspose.GIS pro .NET poskytuje plně spravované API pro všechny množinové geometrické operace.  
- **Jak dlouho trvá základní implementace?** Zhruba 10‑15 minut na napsání, zkompilování a spuštění ukázkového kódu.  
- **Potřebuji licenci pro produkci?** Ano—pro produkční nasazení je vyžadována komerční licence; pro vyhodnocení je k dispozici bezplatná zkušební verze.  
- **Mohu to spustit na .NET 6+?** Rozhodně—Aspose.GIS podporuje .NET Core, .NET 5, .NET 6 a novější.

## Co je operace překryvu?

Operace překryvu vypočítají novou geometrii na základě prostorového vztahu dvou vstupních tvarů. **Intersection** vrací společnou oblast, **Union** spojuje oblasti, **Difference** odečítá jeden tvar od druhého a **Symmetric Difference** poskytuje části, které patří buď k jednomu, nebo k druhému tvaru, ale ne k oběma. Tyto množinové funkce jsou matematickým základem GIS analýzy, umožňující odpovědět na otázky jako „kde se překrývají dva pozemky?“ nebo „jaká oblast zůstane po odebrání chráněné zóny.“

## Proč použít Aspose.GIS pro překryv?

Aspose.GIS podporuje **více než 50 vektorových a rastrových formátů**, dokáže zpracovat **datové sady o stovkách stránek bez načítání celého souboru do paměti** a běží na Windows, Linuxu i macOS. Jeho spravované API eliminuje potřebu nativních GIS knihoven, snižuje složitost nasazení a umožňuje mít veškerou logiku v jedné .NET řešení.

## Běžné případy použití
- **Plánování využití půdy:** Identifikujte překrývající se zóny mezi navrhovanými rozvojovými projekty a chráněnými oblastmi.  
- **Environmentální analýza:** Vypočítejte průnik biotopů s zdroji znečištění.  
- **Infrastrukturní trasování:** Určete, kde nové silnice protínají existující úseky inženýrských sítí.  
- **Městská analytika:** Sloučte více městských hranic pro vytvoření regionálního pohledu.

## Předpoklady
- Funkční vývojové prostředí .NET (Visual Studio, VS Code nebo .NET CLI).  
- Knihovna Aspose.GIS pro .NET – stáhněte nejnovější verzi z [oficiální stránky](https://releases.aspose.com/gis/net/).

### Importovat jmenné prostory
Než můžete začít používat Aspose.GIS pro .NET, musíte do svého projektu importovat potřebné jmenné prostory.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Jak provádět operace překryvu v .NET

`Polygon` představuje uzavřený rovinný tvar definovaný vnějším okrajem a volitelnými vnitřními okraji. Každá metoda překryvu (`Intersection`, `Union`, `Difference`, `SymmetricDifference`) vypočítá konkrétní množinovou operaci na dvou geometriích.

Načtěte dva objekty polygonu a poté zavolejte příslušnou metodu překryvu—Intersection, Union, Difference nebo SymmetricDifference. Celý pracovní postup se vejde do několika stručných řádků kódu a každá metoda vrací geometrii, kterou můžete dále dotazovat nebo exportovat.

**Přímá odpověď:** Pro provedení překryvu v Aspose.GIS vytvořte dvě instance `Polygon`, poté zavolejte požadovanou metodu (`Intersection`, `Union`, `Difference` nebo `SymmetricDifference`). Každé volání vrátí novou geometrii představující výsledek, kterou můžete serializovat do WKT, GeoJSON nebo jakéhokoli podporovaného formátu.

### Krok 1: vytvořit objekty polygonu
`Polygon` představuje uzavřený tvar definovaný sérií souřadnicových bodů.

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

### Krok 2: provést operaci průniku
`Intersection` vypočítá společnou oblast sdílenou dvěma polygony.

```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Polygon
```

### Krok 3: vypsat body průniku
`PrintRing` je pomocná funkce, která vypisuje každou souřadnici vnějšího okraje polygonu.

```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```

### Krok 4: provést operaci sjednocení
`Union` sloučí dva polygony do jedné geometrie pokrývající všechny oblasti.

```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Polygon
```

### Krok 5: vypsat body sjednocení
Vypište souřadnice sjednocené geometrie.

```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```

### Krok 6: provést operaci rozdílu
`Difference` odečte druhý polygon od prvního, zanechávajíc část, která se nepřekrývá.

```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Polygon
```

### Krok 7: vypsat body rozdílu
Zobrazte zbývající vrcholy po odečtení.

```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```

### Krok 8: provést operaci symetrického rozdílu
`SymmetricDifference` vrací části patřící buď k jednomu polygonu, nebo k druhému, ale ne k oběma, a vytváří `MultiPolygon`.

```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // MultiPolygon
```

### Krok 9: vypsat polygony symetrického rozdílu
Procházejte každý polygon v `MultiPolygon` a vypište jeho body.

```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```

## Běžné problémy a řešení
| Problém | Proč k tomu dochází | Řešení |
|-------|----------------|-----|
| `null` result from `Intersection` | Polygony se ve skutečnosti nepřekrývají. | Ověřte souřadnice nebo použijte kontrolu `Intersects` před voláním `Intersection`. |
| Unexpected `MultiPolygon` from `SymDifference` | Symetrický rozdíl může vytvořit nespojené komponenty. | Přetypujte na `IMultiPolygon` a iterujte podle ukázky. |
| Performance slowdown on large datasets | Každá operace přepočítává geometrii od začátku. | Znovu použijte mezivýsledky nebo zjednodušte geometrie pomocí `Simplify()` před překryvem. |

## Často kladené otázky

**Q: Mohu použít Aspose.GIS pro .NET ve svých komerčních projektech?**  
A: Ano, platná komerční licence umožňuje neomezené používání v produkčních aplikacích.

**Q: Je k dispozici zkušební verze pro Aspose.GIS pro .NET?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi ze [stránky vydání Aspose](https://releases.aspose.com/).

**Q: Jak mohu získat podporu pro Aspose.GIS pro .NET?**  
A: Podpora je k dispozici prostřednictvím fóra Aspose GIS [forum Aspose GIS](https://forum.aspose.com/c/gis/33).

**Q: Jsou k dispozici dočasné licence pro testování?**  
A: Ano, dočasné licence lze získat na [stránka dočasné licence](https://purchase.aspose.com/temporary-license/).

**Q: Kde mohu zakoupit plnou licenci pro Aspose.GIS pro .NET?**  
A: Licenci můžete zakoupit přímo na webu [stránka nákupu Aspose](https://purchase.aspose.com/buy).

---

**Poslední aktualizace:** 2026-08-08  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit polygonovou geometrii C# a zkontrolovat průnik pomocí Aspose.GIS pro .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Jak provést analýzu prostorového překryvu geometrií pomocí Aspose.GIS pro .NET](/gis/net/geometry-analysis/check-geometries-overlap/)
- [Vytvořit buffer geometrie pomocí Aspose.GIS pro .NET](/gis/net/geometry-analysis/create-geometry-buffer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
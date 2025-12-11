---
date: 2025-12-11
description: Naučte se, jak počítat geometrie a přidávat geometrie do kolekce pomocí
  Aspose.GIS pro .NET. Krok za krokem tutoriál s ukázkami kódu pro vývojáře.
linktitle: Count Geometries in Geometry
second_title: Aspose.GIS .NET API
title: Jak počítat geometrie v geometrii pomocí Aspose.GIS
url: /cs/net/geometry-creation/count-geometries-in-geometry/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak počítat geometrie v geometrii s Aspose.GIS

## Úvod
Pokud potřebujete **jak počítat geometrie** uvnitř složeného tvaru, Aspose.GIS pro .NET to usnadňuje. Ať už vytváříte mapovací aplikaci, službu založenou na poloze nebo analytický prostorový engine, schopnost spočítat jednotlivé geometrie v kolekci je základní úkol. V tomto tutoriálu vás provedeme vytvořením jednoduchých geometrií, jejich přidáním do kolekce a nakonec použitím API k získání počtu geometrií.

## Rychlé odpovědi
- **Jaká je hlavní metoda?** Použijte vlastnost `Count` třídy `GeometryCollection`.
- **Jaký namespace je vyžadován?** `Aspose.Gis.Geometries`.
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební vernocení; licence je vyžadována pro produkci.
- **Mohu přidávat různé typy geometrií?** Ano – body, čáry, polygonů atd. lze všechny přidat do stejné kolekce.
- **Je to kompatibilní s .NET Core?** Naprosto, Aspose.GIS podporuje .NET Framework i .NET Core.

## Co je „jak počítat geometrie“?
Počítání geometrií znamená určení, kolik jednotlivých geometrických objektů (body, čáry, polygonů atd.) je uloženo uvnitř složené struktury, jako je `GeometryCollection`. API tuto informaci zpřístupňuje prostřednictvím jednoduché celočíselné vlastnosti, čímž odstraňuje potřebu ruční iterace.

## Proč přidávat geometrie do kolekce?
Přidání geometrií do kolekce (`add geometries to collection`) vám umožní zacházet s více tvary jako s jednou logickou entitou. To je užitečné pro dávkové zpracování, prostorové dotazy a vykreslování více prvků najednou, aniž byste museli každou zvlášť zpracovávat.

## Předpoklady
1. **Visual Studio** – jakákoli recentní verze (2019, 2022 nebo novější).  
2. **Aspose.GIS for .NET** – stáhněte a nainstalujte jej ze [stránky ke stažení](https://releases.aspose.com/gis/net/).  
3. **Základní znalost C#** – měli byste být schopni vytvořit konzolovou aplikaci a přidat NuGet balíčky.

## Importujte jmenné prostory
Nejprve importujte jmenné prostory, které vám poskytují přístup ke třídám geometrie.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Vytvořte bodovou geometrii
`Point` představuje jeden pár souřadnic (zeměpisná šířka, zeměpisná délka). Zde vytvoříme jeden pro New York City.

```csharp
Point point = new Point(40.7128, -74.006);
```

## Krok 2: Vytvořte geometrii LineString
`LineString` je řada propojených bodů. Přidáme dva libovolné body pro ilustraci.

```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```

## Krok 3: Přidejte geometrie do kolekce
Nyní spojíme bod a čáru do jedné `GeometryCollection`. Zde **add geometries to collection**.

```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```

## Krok 4: Jak počítat geometrie
Vlastnost `Count` vrací celkový počet geometrií uložených v kolekci.

```csharp
int geometriesCount = geometryCollection.Count;
```

## Krok 5: Zobrazte počet
Nakonec vypište počet do konzole. V tomto příkladu je výsledek `2`.

```csharp
Console.WriteLine(geometriesCount); // 2
```

## Časté problémy a řešení
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **Count vždy vrací 0** | Kolekce nebyla nikdy naplněna. | Ujistěte se, že voláte `Add` pro každou geometrii před přístupem k `Count`. |
| **Neplatné pořadí souřadnic** | Konstruktor `Point` očekává nejprve zeměpisnou šířku, pak délku. | Ověřte pořadí parametrů při vytváření `Point` nebo `LineString`. |
| **Chyba chybějícího jmenného prostoru** | `Aspose.Gis.Geometries` nebyl importován. | Přidejte `using Aspose.Gis.Geometries;` na začátek souboru. |

## Často kladené otázky

**Q: Mohu míchat různé typy geometrií ve stejné kolekci?**  
A: Ano, můžete přidávat body, čáry, polygonů a dokonce i jiné kolekce do jedné `GeometryCollection`.

**Q: Podporuje Aspose.GIS export do GeoJSON pro kolekci?**  
A: Naprosto. Můžete použít `geometryCollection.ToGeoJson()` k serializaci kolekce.

**Q: Existuje způsob, jak iterovat přes každou geometrii po spočítání?**  
A: Ano, `foreach (var geom in geometryCollection)` vám umožní zpracovat každou geometrii jednotlivě.

**Q: Potřebuji licenci pro vývojové sestavení?**  
A: Bezplatná zkušební verze funguje pro hodnocení, ale pro produkční nasazení je vyžadována licencovaná verze.

### Je Aspose.GIS pro .NET vhodný jak pro desktopové, tak pro webové aplikace?
Ano, Aspose.GIS pro .NET lze použít jak v desktopových, tak ve webových aplikacích bez problémů.

### Mohu provádět prostorové dotazy pomocí Aspose.GIS pro .NET?
Ano, Aspose.GIS pro .NET poskytuje robustní podporu pro provádění prostorových dotazů na geometriích.

### Podporuje Aspose.GIS pro .NET různé GIS formáty souborů?
Ano, Aspose.GIS pro .NET podporuje širokou škálu GIS formátů včetně SHP, KML a GeoJSON.

### Je k dispozici bezplatná zkušební verze Aspose.GIS pro .NET?
Ano, můžete si stáhnout bezplatnou zkušební verzi ze [stránky](https://releases.aspose.com/).

### Kde mohu najít podporu pro Aspose.GIS pro .NET?
Podporu najdete na [fóru Aspose.GIS](https://forum.aspose.com/c/gis/33).

## Závěr
V tomto průvodci jsme pokryli **jak počítat geometrie** uvnitř `GeometryCollection` a ukázali praktické kroky k **add geometries to collection** pomocí Aspose.GIS pro .NET. S těmito základy nyní můžete vytvářet bohatší prostorové funkce, provádět dávkové operace a integrovat geoprostorovou inteligenci do jakékoli .NET aplikace.

**Poslední aktualizace:** 2025-12-11  
**Testováno s:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
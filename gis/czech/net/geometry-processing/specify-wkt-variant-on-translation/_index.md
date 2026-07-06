---
date: 2026-04-09
description: Naučte se, jak při vytváření bodu v C# s Aspose.GIS pro .NET přiřadit
  prostorový referenční systém a nastavit desetinnou přesnost ve vašich .NET aplikacích.
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: Určete variantu WKT při překladu
second_title: Aspose.GIS .NET API
title: Přiřazení prostorové reference a nastavení varianty WKT pomocí Aspose.GIS
url: /cs/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přiřazení prostorové reference a nastavení varianty WKT pomocí Aspose.GIS

## Úvod
V tomto tutoriálu se naučíte, jak **přiřadit prostorovou referenci** k geometrii a řídit přesný výstupní formát WKT pomocí Aspose.GIS pro .NET. Ať už potřebujete **vytvořit objekt point v C#** pro mapování, analytiku nebo výměnu dat, možnost vybrat správnou variantu WKT a číselnou přesnost umožňuje, aby vaše prostorová data byla interoperabilní a snadno čitelná. Projděme si proces krok za krokem.

## Rychlé odpovědi
- **Co znamená „přiřadit prostorovou referenci“?** Vazuje geometrii ke konkrétnímu souřadnicovému systému, jako je WGS‑84.  
- **Které varianty WKT jsou podporovány?** Iso, SimpleFeatureAccessOutdated a ExtendedPostGis.  
- **Jak mohu řídit desetinnou přesnost?** Použijte možnosti `NumericFormat` jako `General`, `RoundTrip` nebo `Flat`.  
- **Potřebuji licenci?** Je k dispozici bezplatná zkušební verze; pro produkční použití je vyžadována komerční licence.  
- **Jaké verze .NET jsou kompatibilní?** .NET Framework 4.0+ a .NET Core/5/6+.

## Co je „přiřadit prostorovou referenci“?
Přiřazení prostorové reference (nebo systému prostorových referencí, SRS) říká GIS softwaru, jak interpretovat souřadnicové hodnoty geometrie. Bez SRS nemají souřadnice zeměpisné šířky a délky bodu žádný reálný význam.

## Proč řídit variantu WKT a číselný formát?
Různé GIS nástroje očekávají mírně odlišné syntaxy WKT. Výběrem správné varianty zajistíte bezproblémovou výměnu dat, zatímco nastavení desetinné přesnosti zabraňuje zaokrouhlovacím chybám nebo příliš dlouhým číslům, která zaplňují logy a soubory.

## Předpoklady
1. Aspose.GIS pro .NET – stáhněte ze [stránky ke stažení](https://releases.aspose.com/gis/net/).  
2. Vývojové prostředí .NET (Visual Studio, VS Code nebo Rider).  
3. Základní znalost C# a .NET frameworku.

## Importovat jmenné prostory
Před použitím jakýchkoli tříd Aspose.GIS importujte požadované jmenné prostory:

```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```

## Krok 1: Vytvořit objekt Point (vytvořit point v C#)
Začneme konstrukcí `Point` s hodnotami zeměpisné šířky, délky a volitelnou měrnou (M) hodnotou:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Krok 2: Přiřadit systém prostorové reference (SRS)
Nyní **přiřadíme prostorovou referenci** k bodu. Zde používáme široce podporovaný systém WGS‑84 (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Krok 3: Zvolit požadovanou variantu WKT
Vyberte variantu WKT, která odpovídá vaší následné aplikaci:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Krok 4: Nastavit desetinnou přesnost pro výstup WKT
Řiďte, kolik číslic se objeví ve výsledném řetězci pomocí `NumericFormat`:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Běžné úskalí a tipy
- **Úskalí:** Zapomenutí nastavit SRS před voláním `AsText` může vést k chybějícím informacím o SRID.  
- **Tip:** Použijte `NumericFormat.RoundTrip`, když potřebujete bezztrátové zpětné převody souřadnic.  
- **Tip:** Varianta `Iso` je nejpřenosnější; `ExtendedPostGis` zvolte jen v případě, že potřebujete vložený SRID.

## Závěr
Nyní víte, jak **přiřadit prostorovou referenci**, vybrat vhodnou variantu WKT a **nastavit desetinnou přesnost** při **vytváření objektů point v C#** pomocí Aspose.GIS. Tyto možnosti vám poskytují flexibilitu splnit přesné požadavky jakéhokoli GIS pracovního postupu, od jednoduché vizualizace po vysoce přesnou prostorovou analýzu.

## Často kladené otázky

**Q:** Je Aspose.GIS kompatibilní se všemi verzemi .NET?  
**A:** Ano, Aspose.GIS podporuje .NET Framework 4.0 a vyšší, stejně jako .NET Core/5/6.

**Q:** Mohu použít Aspose.GIS pro komerční projekty?  
**A:** Rozhodně. Pro produkční použití je vyžadována komerční licence, ale je k dispozici bezplatná zkušební verze pro hodnocení.

**Q:** Podporuje Aspose.GIS i jiné formáty prostorových dat?  
**A:** Ano, funguje s ESRI Shapefile, GeoJSON, KML a mnoha dalšími formáty.

**Q:** Kde si mohu stáhnout bezplatnou zkušební verzi?  
**A:** Bezplatnou zkušební verzi Aspose.GIS můžete stáhnout [zde](https://releases.aspose.com/).

**Q:** Jak získám pomoc, pokud narazím na problémy?  
**A:** Položte své otázky na komunitním [fóru](https://forum.aspose.com/c/gis/33) Aspose.GIS, kde vám mohou pomoci jak zaměstnanci Aspose, tak členové komunity.

---

**Poslední aktualizace:** 2026-04-09  
**Testováno s:** Aspose.GIS pro .NET (nejnovější verze)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
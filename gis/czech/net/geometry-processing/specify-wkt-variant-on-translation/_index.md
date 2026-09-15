---
date: 2026-09-15
description: Zjistěte, jak přiřadit coordinate system, nastavit WKT variant a řídit
  decimal precision při vytváření point geometry v C# s Aspose.GIS pro .NET.
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: Specifikovat WKT Variant při překladu
og_description: Zjistěte, jak přiřadit coordinate system, nastavit WKT variant a řídit
  decimal precision při vytváření point geometry v C# s Aspose.GIS pro .NET.
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: Přiřazení coordinate system, nastavení WKT variant pomocí Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: Přiřazení coordinate system, nastavení WKT variant pomocí Aspose.GIS
url: /cs/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přiřazení souřadnicového systému, nastavení varianty WKT pomocí Aspose.GIS

## Úvod
V tomto tutoriálu se naučíte, jak **přiřadit souřadnicový systém**, vybrat správnou variantu WKT a řídit desetinnou přesnost při **vytváření bodové geometrie** v C# s Aspose.GIS pro .NET. Ať už vytváříte mapovou službu, provádíte prostorovou analytiku nebo vyměňujete data mezi GIS platformami, tato nastavení zajišťují, že váš výstup je interoperabilní a snadno čitelný. Projděme si proces krok za krokem.

## Rychlé odpovědi
- **Co znamená “assign coordinate system”?** Spojuje geometrii se specifickým referenčním souřadnicovým systémem, jako je WGS‑84.  
- **Které varianty WKT jsou podporovány?** Iso, SimpleFeatureAccessOutdated a ExtendedPostGis.  
- **Jak mohu řídit desetinnou přesnost?** Použijte výčtový typ `NumericFormat` (`General`, `RoundTrip`, `Flat`).  
- **Potřebuji licenci pro Aspose.GIS?** K dispozici je bezplatná zkušební verze; pro produkční použití je vyžadována komerční licence.  
- **Jaké verze .NET jsou kompatibilní?** .NET Framework 4.0+ a .NET Core/5/6+.

## Co je “assign coordinate system”?
Přiřazení prostorového referenčního systému (nebo prostorového referenčního systému, SRS) říká GIS softwaru, jak interpretovat souřadnicové hodnoty geometrie, propojující čísla s reálným souřadnicovým systémem, jako je WGS‑84. Bez SRS nemají souřadnice bodu (zeměpisná šířka‑délka) žádný reálný význam.

## Proč řídit variantu WKT a číselný formát?
Více než 30 GIS nástrojů očekává specifické syntaxy WKT, takže výběr správné varianty zabraňuje chybám při importu. Nastavení číselného formátu snižuje šum zaokrouhlování a udržuje výstup stručný, což je zvláště důležité, když jsou logy nebo soubory zpracovávány programově.

## Požadavky
1. Aspose.GIS pro .NET – stáhněte z [download page](https://releases.aspose.com/gis/net/).  
2. Vývojové prostředí .NET (Visual Studio, VS Code nebo Rider).  
3. Základní znalost C# a .NET frameworku.

## Importujte jmenné prostory
Než použijete jakékoli třídy Aspose.GIS, importujte požadované jmenné prostory:

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

## Jak přiřadit souřadnicový systém bodu?
Načtěte instanci `Point` a poté připojte systém prostorové reference (SRS) pomocí třídy `SpatialReference`. Tento dvoustupňový vzor zajišťuje, že geometrie nese metadata svého souřadnicového systému při exportu, což umožňuje následným nástrojům správně interpretovat souřadnice. Třída `Point` představuje jedinou polohu definovanou souřadnicemi X (zeměpisná délka) a Y (zeměpisná šířka).

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Krok 2: přiřadit systém prostorové reference (SRS)
Nyní **přiřadíme prostorovou referenci** bodu. `SpatialReference` představuje souřadnicový referenční systém identifikovaný pomocí SRID. Zde používáme široce podporovaný systém WGS‑84 (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Krok 3: specifikovat požadovanou variantu WKT
Vyberte variantu WKT, která odpovídá vaší následné aplikaci:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Jak nastavit desetinnou přesnost pro výstup WKT?
Řiďte, kolik číslic se objeví v konečném řetězci pomocí výčtového typu `NumericFormat`, který definuje pravidla formátování jako `General`, `RoundTrip` nebo `Flat`. Výběr `RoundTrip` zachovává plnou věrnost souřadnic pro scénáře zpětného převodu, zatímco `General` poskytuje stručnou reprezentaci vhodnou pro většinu vizualizačních úloh. Výčtový typ `NumericFormat` řídí, jak jsou číselné souřadnice formátovány ve výstupu WKT.

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Běžné úskalí a tipy
- **Úskalí:** Zapomenutí nastavit SRS před voláním `AsText` může vést k chybějícím informacím o SRID.  
- **Tip:** Použijte `NumericFormat.RoundTrip`, když potřebujete bezztrátový zpětný převod souřadnic.  
- **Tip:** Varianta `Iso` je nejpřenosnější; `ExtendedPostGis` zvolte jen tehdy, když potřebujete vložený SRID.

## Závěr
Nyní víte, jak **přiřadit souřadnicový systém**, vybrat vhodnou variantu WKT a **nastavit desetinnou přesnost** při **vytváření bodové geometrie** s Aspose.GIS. Tyto ovládací prvky vám poskytují flexibilitu splnit přesné požadavky jakéhokoli GIS pracovního postupu, od jednoduché vizualizace po vysoce přesnou prostorovou analýzu.

## Často kladené otázky

**Q:** Je Aspose.GIS kompatibilní se všemi verzemi .NET?  
**A:** Ano, Aspose.GIS podporuje .NET Framework 4.0 a vyšší, stejně jako .NET Core/5/6.

**Q:** Mohu použít Aspose.GIS pro komerční projekty?  
**A:** Rozhodně. Pro produkční použití je vyžadována komerční licence, ale pro vyhodnocení je k dispozici bezplatná zkušební verze.

**Q:** Podporuje Aspose.GIS jiné formáty prostorových dat?  
**A:** Ano, pracuje s více než 30 formáty, včetně ESRI Shapefile, GeoJSON, KML, CSV a mnoha dalších.

**Q:** Kde si mohu stáhnout bezplatnou zkušební verzi?  
**A:** Bezplatnou zkušební verzi Aspose.GIS můžete stáhnout ze [Aspose.GIS free trial download page](https://releases.aspose.com/).

**Q:** Jak získám pomoc, pokud narazím na problémy?  
**A:** Zveřejněte své otázky na komunitním [forum](https://forum.aspose.com/c/gis/33) Aspose.GIS, kde vám mohou pomoci jak zaměstnanci Aspose, tak členové komunity.

---

**Poslední aktualizace:** 2026-09-15  
**Testováno s:** Aspose.GIS for .NET (latest release)  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit vektorovou vrstvu a nastavit její systém prostorové reference](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Jak převést geometrii na WKT pomocí Aspose.GIS pro .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [Jak omezit přesnost při zápisu geometrií pomocí Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
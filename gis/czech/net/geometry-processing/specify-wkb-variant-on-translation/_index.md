---
date: 2026-06-10
description: Zjistěte, jak vytvořit geometrii Linestring v .NET a převést geometrii
  na WKB pomocí Aspose.GIS pro .NET s variantou ExtendedPostGis.
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: Určete variantu WKB při překladu
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  headline: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  name: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  steps:
  - name: Creating a Geometry Object
    text: The `Geometry` class is Aspose.GIS's base type that represents any spatial
      object in memory. Linestring represents a series of connected points forming
      a linear geometry. In this step we instantiate a `Linestring` with a collection
      of coordinate pairs that model a simple road segment.
  - name: Generating WKB Representation
    text: '`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to
      include SRID in the output binary. Here we call the `AsBinary` method, passing
      the EWKB variant, which returns a `byte[]` containing the full binary representation.'
  - name: Writing to File
    text: '`File.WriteAllBytes` writes the binary array to disk. The resulting file
      (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB`
      function.'
  type: HowTo
- questions:
  - answer: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which
      PostGIS reads directly via `ST_GeomFromEWKB`.
    question: Can I use the EWKB file with PostGIS?
  - answer: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry
      from its binary form.
    question: Is it possible to read a WKB file back into a geometry object?
  - answer: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons,
      and many more spatial types.
    question: Does the library support other geometry types like polygons?
  - answer: Set the `SRID` property on the geometry object before calling `AsBinary`,
      e.g., `linestring.SRID = 4326;`.
    question: How do I specify a different SRID when creating the geometry?
  - answer: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6
      without modification.
    question: Will this code work on .NET Core?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Vytvoření geometrie Linestring a varianty WKB v Aspose.GIS pro .NET
url: /cs/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření geometrie Linestring a varianty WKB v Aspose.GIS pro .NET

## Úvod
Pokud potřebujete **vytvořit linestring geometrie v .NET** a následně tuto geometrie převést do binární podoby, Aspose.GIS pro .NET vám poskytuje čisté, vysoce výkonné API, které funguje napříč .NET Framework, .NET Core a .NET 5/6+. V tomto tutoriálu projdeme každý krok – od importování jmenných prostorů po zápis souboru EWKB – abyste mohli zachovat informaci o SRID a integrovat GIS data do PostgreSQL/PostGIS nebo jakéhokoli binárního workflow bez komplikací.

## Rychlé odpovědi
- **Co znamená WKB?** Well‑Known Binary, kompaktní binární reprezentace geometrických objektů.  
- **Která varianta WKB ukládá SRID?** Varianta `ExtendedPostGis` (EWKB) vkládá SRID přímo do binárního souboru.  
- **Potřebuji licenci?** Pro produkční nasazení je vyžadována dočasná nebo plná licence Aspose.GIS.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, a .NET 5/6+.  
- **Jak dlouho trvá implementace?** Obvykle méně než 10 minut pro základní příklad.

## Co je geometrie Linestring?
Geometrie linestring je jednoduchý tvar složený z uspořádaného seznamu bodů spojených přímými úsečkami. Jedná se o základní reprezentaci lineárních prvků, jako jsou silnice, potrubí nebo řeky v prostorových databázích.

## Proč specifikovat variantu WKB?
Použití správné varianty WKB zajišťuje, že kritická metadata – zejména identifikátor prostorového referenčního systému (SRID) – cestují spolu s vaší geometrií. Varianta `ExtendedPostGis` (EWKB) ukládá SRID uvnitř binárního payloadu, což umožňuje bezproblémové round‑tripping s PostGIS, Oracle Spatial nebo jakýmkoli systémem očekávajícím binární soubory s informací o SRID.

## Požadavky
Před zahájením se ujistěte, že máte následující:

### Instalace Aspose.GIS pro .NET
1. Stáhněte Aspose.GIS: Navštivte [odkaz ke stažení](https://releases.aspose.com/gis/net/) a získejte nejnovější balíček.  
2. Přidejte NuGet balíček do svého projektu (např. `Install-Package Aspose.GIS`).  

### Základní znalost programování v C#
- Základní pochopení syntaxe C# a struktury projektu.  
- Schopnost spustit .NET konzolovou aplikaci nebo projekt knihovny tříd.

## Importování jmenných prostorů
Jmenný prostor `Aspose.GIS` vám poskytuje přístup ke všem třídám souvisejícím s geometrií.  

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Tyto jmenné prostory poskytují základní GIS funkčnost, včetně tvorby geometrie, transformací a binární serializace.

## Jak vytvořit geometrie linestring?
Pro vytvoření linestringu vytvořte objekt `Linestring` s uspořádaným seznamem souřadnicových párů, nastavte jeho SRID podle potřeby a poté jej serializujte do požadované varianty WKB. Proces zahrnuje tři kroky: vytvoření geometrie, výběr varianty `ExtendedPostGis` pro zachování SRID a zápis výsledného pole bajtů do souboru.

### Krok 1: Vytvoření objektu geometrie
Třída `Geometry` je základní typ Aspose.GIS, který představuje libovolný prostorový objekt v paměti.  
Linestring představuje sérii propojených bodů tvořících lineární geometrii.  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
V tomto kroku vytvoříme instanci `Linestring` s kolekcí souřadnicových párů, které modelují jednoduchý úsek silnice.

### Krok 2: Generování reprezentace WKB
`WkbVariant.ExtendedPostGis` je hodnota výčtu, která říká Aspose.GIS, aby zahrnula SRID do výstupního binárního souboru.  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Zde voláme metodu `AsBinary` s parametrem EWKB varianty, která vrací `byte[]` obsahující kompletní binární reprezentaci.

### Krok 3: Zápis do souboru
`File.WriteAllBytes` zapíše binární pole na disk.  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
Výsledný soubor (`EWkbFile.ewkb`) lze importovat přímo do tabulky PostGIS pomocí funkce `ST_GeomFromEWKB`.

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|-------|--------|----------|
| **Prázdný soubor** | `Path.Combine` ukazuje na neexistující adresář. | Zajistěte, aby cílový adresář existoval, nebo jej vytvořte pomocí `Directory.CreateDirectory`. |
| **Nesprávný SRID** | Použití výchozího `WkbVariant.Standard` odstraňuje SRID. | Vždy použijte `WkbVariant.ExtendedPostGis`, pokud je vyžadováno zachování SRID. |
| **Výjimka licence** | Spouštění bez platné licence v produkci. | Aplikujte dočasnou nebo plnou licenci před spuštěním kódu v produkčním prostředí. |

## Často kladené otázky
**Q: Mohu použít soubor EWKB s PostGIS?**  
A: Ano, varianta `ExtendedPostGis` vytváří EWKB, který obsahuje SRID, a PostGIS jej čte přímo pomocí funkce `ST_GeomFromEWKB`.  

**Q: Je možné načíst soubor WKB zpět do objektu geometrie?**  
A: Rozhodně. Použijte `Geometry.FromBinary(byteArray)` k obnovení geometrie z binární podoby.  

**Q: Podporuje knihovna i jiné typy geometrie, jako jsou polygony?**  
A: Ano, Aspose.GIS pracuje s body, linestringy, polygony, multipolygony a mnoha dalšími prostorovými typy.  

**Q: Jak mohu při vytváření geometrie zadat jiný SRID?**  
A: Nastavte vlastnost `SRID` na objektu geometrie před voláním `AsBinary`, např. `linestring.SRID = 4326;`.  

**Q: Bude tento kód fungovat na .NET Core?**  
A: Ano, stejné API funguje napříč .NET Framework, .NET Core a .NET 5/6 bez úprav.

---

**Poslední aktualizace:** 2026-06-10  
**Testováno s:** Aspose.GIS for .NET 23.9 (latest at time of writing)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Převod geometrie do formátu WKB pomocí Aspose.GIS pro .NET](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [Určení varianty WKT při převodu pomocí Aspose.GIS](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [Vytvoření geometrie MultiLineString pomocí Aspose.GIS pro .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
date: 2026-06-30
description: Naučte se, jak vytvořit vektorovou vrstvu v souborové geodatabázi pomocí
  Aspose.GIS pro .NET. Spravujte geoprostorová data se souřadnicovým referenčním systémem
  WGS84 a možnostmi souboru gdb.
keywords:
- create vector layer
- add line feature
- manage geospatial data
- feature count example
- file gdb compression
linktitle: Vytvořit soubor GDB s jednou vrstvou
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  headline: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  type: TechArticle
- description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  name: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  steps:
  - name: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
    text: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
  - name: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
    text: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
  type: HowTo
- questions:
  - answer: It means adding a new vector dataset (points, lines, or polygons) to a
      geodatabase file.
    question: What does “create vector layer” mean?
  - answer: Aspose.GIS for .NET provides full support for File GDB creation and editing.
    question: Which library should I use?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `SpatialReferenceSystem.Wgs84` for the common WGS84 datum.
    question: Can I set the spatial reference?
  - answer: Less than 30 lines to create the GDB, add a line feature, and read back
      the feature count.
    question: How many lines of code?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Vytvořit vektorovou vrstvu v souboru GDB – Aspose.GIS .NET tutoriál
url: /cs/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořit vektorovou vrstvu v souborové GDB

## Úvod
Pokud potřebujete **vytvořit vektorovou vrstvu** uvnitř souborové geodatabáze (GDB) a efektivně spravovat geoprostorová data, Aspose.GIS pro .NET vám poskytuje čistý přístup kódu‑první. V tomto krok‑za‑krokem průvodci vám ukážeme, jak zapsat lineární prvek, nakonfigurovat možnosti souborové GDB a pracovat s prostorovým referenčním systémem WGS84 — vše v několika řádcích C#. Na konci budete schopni spočítat prvky ve vrstvě a integrovat vzniklou GDB do jakéhokoli .NET mapovacího nebo analytického workflow.

## Rychlé odpovědi
- **Co znamená „vytvořit vektorovou vrstvu“?** Znamená to přidání nového vektorového datasetu (body, linie nebo polygony) do souboru geodatabáze.  
- **Kterou knihovnu mám použít?** Aspose.GIS pro .NET poskytuje plnou podporu pro vytváření a editaci File GDB.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Mohu nastavit prostorový referenční systém?** Ano – použijte `SpatialReferenceSystem.Wgs84` pro běžný datum WGS84.  
- **Kolik řádků kódu?** Méně než 30 řádků pro vytvoření GDB, přidání lineárního prvku a načtení počtu prvků.

## Co je operace „vytvořit vektorovou vrstvu“?
Vytvoření vektorové vrstvy definuje novou tabulku v geodatabázi, která ukládá geometrické objekty (body, linie, polygony) a jejich atributy. Každý řádek představuje prvek a sloupec geometrie obsahuje jeho tvar. V Aspose.GIS ji vytvoříte vytvořením instance `FeatureClass` v rámci `FileGdbDataSource` a specifikací typu geometrie.

## Proč použít Aspose.GIS k vytvoření vektorové vrstvy?
Aspose.GIS eliminuje externí závislosti a podporuje **50+** GIS formátů, což z něj činí jediné řešení pro .NET vývojáře.  
Poskytuje vestavěnou kompresi souborové GDB (až 70 % úspora pro typická vektorová data), prostorové indexování a plnou podporu WGS84 přímo z krabice. Knihovna funguje na .NET Framework 4.6+, .NET Core 2.0+, a .NET 5/6, takže můžete cílit na jakékoli moderní Windows nebo multiplatformní prostředí bez dalších nativních knihoven.

## Požadavky
Před zahájením se ujistěte, že máte:

1. **Aspose.GIS for .NET** – stáhněte jej z [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).  
2. **Vývojové prostředí .NET** – Visual Studio, Rider nebo `dotnet` CLI.  
3. **Složku**, kde bude vytvořena souborová GDB (nazveme ji *Your Document Directory*).

## Importovat jmenné prostory
Příkazy `using` přinášejí požadované typy do rozsahu.  

Jmenný prostor `Document` poskytuje základní GIS objekty, zatímco `System.IO` zpracovává souborové cesty.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```

## Krok 1: Nastavte svůj adresář dokumentů
Nahraďte `"Your Document Directory"` absolutní cestou, kde chcete, aby souborová GDB byla uložena.  
Vytvoření složky předem zabraňuje chybě „File not found“, která často zaskočí nové uživatele.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Vytvořte souborovou geodatabázi s jednou vrstvou
`FileGdbOptions` je třída, která umožňuje konfigurovat kompresi, prostorové indexování a další nastavení pro souborovou geodatabázi.  
Tento úryvek **vytváří vektorovou vrstvu** pomocí `FileGdbOptions`, zapisuje jednoduchý lineární prvek a ukládá jej do souborové GDB, která používá **prostorový referenční systém WGS84**.

```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```

## Krok 3: Otevřete souborovou geodatabázi a načtěte informace o vrstvě
`FileGdbDataSource` je vstupní bod pro vytváření a otevírání souborových geodatabází.  
`FeatureClass` představuje vektorovou vrstvu v rámci geodatabáze a poskytuje přístup k jejím prvkům.  
Zde **počítáme prvky ve vrstvě** otevřením datasetu a vytištěním počtu prvků — v tomto případě `1`.

```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```

## Jak ověříte, že byla vrstva vytvořena správně?
Otevřete geodatabázi pomocí `FileGdbDataSource.Open` a dotazujte `FeatureClass`. Vlastnost `Count` vrací celkový počet prvků, čímž potvrzuje, že linie byla uložena. Tento rychlý ověřovací krok vám pomůže zachytit problémy brzy, zejména při automatizaci hromadných importů.

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|-------|--------|-----|
| **`File not found`** | Nesprávná proměnná `path` | Ověřte, že `dataDir` ukazuje na existující složku a že `path` kombinuje s názvem souboru, např. `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | Použití typu geometrie, který není v File GDB povolen | Používejte `Point`, `LineString` nebo `Polygon` pro základní vrstvy. |
| **`License not set`** | Spuštění bez platné licence v produkci | Zaregistrujte svou licenci pomocí `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Často kladené otázky
### Mohu použít Aspose.GIS pro .NET ve svých existujících .NET projektech?
Ano, Aspose.GIS pro .NET může být bez problémů integrován do vašich existujících .NET projektů.

### Je k dispozici zkušební verze pro Aspose.GIS pro .NET?
Ano, můžete prozkoumat funkce Aspose.GIS pro .NET stažením [free trial version](https://releases.aspose.com/).

### Kde najdu podrobnou dokumentaci pro Aspose.GIS pro .NET?
Podívejte se na [documentation](https://reference.aspose.com/gis/net/) pro komplexní informace o Aspose.GIS pro .NET.

### Jak mohu získat podporu pro Aspose.GIS pro .NET?
Navštivte [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) pro komunitní podporu a pomoc.

### Jsou k dispozici dočasné licence pro Aspose.GIS pro .NET?
Ano, můžete získat [temporary license](https://purchase.aspose.com/temporary-license/) pro Aspose.GIS pro .NET.

---

**Poslední aktualizace:** 2026-06-30  
**Testováno s:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit .NET dataset souborové geodatabáze s Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Vytvořit vektorovou vrstvu a nastavit prostorový referenční systém vrstvy](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Jak odstranit vrstvu z datasetu File GDB pomocí Aspose.GIS](/gis/net/layer-data-operations/remove-layers-from-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}
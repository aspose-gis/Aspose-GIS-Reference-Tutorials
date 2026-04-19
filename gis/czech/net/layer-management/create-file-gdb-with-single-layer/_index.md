---
date: 2026-01-10
description: Naučte se, jak vytvořit vektorovou vrstvu v souborové geodatabázi pomocí
  Aspose.GIS pro .NET. Spravujte geoprostorová data s prostorovým referenčním systémem
  WGS84 a možnostmi souboru gdb.
linktitle: Create File GDB with Single Layer
second_title: Aspose.GIS .NET API
title: Vytvoření vektorové vrstvy v souboru GDB – Aspose.GIS .NET tutoriál
url: /cs/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření vektorové vrstvy v souborové GDB

## Úvod
Pokud potřebujete **create vector layer** uvnitř souborové geodatabáze (GDB) a efektivně spravovat geoprostorová data, Aspose.GIS pro .NET vám poskytuje čistý, code‑first přístup. V tomto krok‑za‑krokem průvodci vám ukážeme, jak zapsat line feature, nakonfigurovat file gdb options a pracovat s spatial reference WGS84 — vše během několika řádků C#. Na konci budete schopni spočítat features ve vrstvě a integrovat vzniklou GDB do jakéhokoli .NET mapovacího nebo analytického workflow.

## Rychlé odpovědi
- **What does “create vector layer” mean?** To znamená přidání nového vektorového datasetu (points, lines, or polygons) do souboru geodatabáze.  
- **Which library should I use?** Aspose.GIS pro .NET poskytuje plnou podporu pro File GDB creation a editing.  
- **Do I need a license for development?** Free trial funguje pro testování; komerční licence je vyžadována pro produkci.  
- **Can I set the spatial reference?** Ano – použijte `SpatialReferenceSystem.Wgs84` pro běžný datum WGS84.  
- **How many lines of code?** Méně než 30 řádků pro vytvoření GDB, přidání line feature a načtení počtu features.

## Co je operace “create vector layer”?
Vytvoření vektorové vrstvy znamená definování nové tabulky uvnitř geodatabáze, která ukládá geometrické objekty (points, lines, polygons) spolu s jejich atributy. Tato operace je základem pro jakoukoli GIS‑based aplikaci, která potřebuje **manage geospatial data**.

## Proč použít Aspose.GIS pro vytvoření vektorové vrstvy?
- **Zero external dependencies** – API funguje out‑of‑the‑box na .NET Framework, .NET Core a .NET 5/6.  
- **Full support for File GDB** – můžete konfigurovat `FileGdbOptions` pro řízení komprese, spatial indexing a další.  
- **Built‑in spatial reference handling** – jednoduše předáte `SpatialReferenceSystem.Wgs84` pro práci v globálním souřadnicovém systému.  
- **Straightforward API** – zapisujete line feature, přidáte ji do vrstvy a získáte počet features pomocí několika volání metod.

## Požadavky
Před začátkem se ujistěte, že máte:

1. **Aspose.GIS for .NET** – stáhněte jej ze [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).  
2. **A .NET development environment** – Visual Studio, Rider nebo `dotnet` CLI.  
3. **A folder** kde bude vytvořena File GDB (nazveme ji *Your Document Directory*).

## Importujte jmenné prostory
Přidejte požadované `using` příkazy na začátek vašeho C# souboru:

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

## Krok 1: Nastavte svůj Document Directory
Nahraďte `"Your Document Directory"` absolutní cestou, kde má File GDB být umístěna.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Vytvořte File Geodatabase s jednou vrstvou
Tento úryvek **creates a vector layer** pomocí `FileGdbOptions`, zapíše jednoduchý line feature a uloží jej do File GDB, která používá **spatial reference WGS84**.

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

## Krok 3: Otevřete File Geodatabase a načtěte informace o vrstvě
Zde **count features layer** otevřením datasetu a vytištěním počtu features – v tomto případě `1`.

```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```

## Časté problémy a řešení
| Issue | Reason | Fix |
|-------|--------|-----|
| **`File not found`** | Nesprávná proměnná `path` | Ověřte, že `dataDir` ukazuje na existující složku a že `path` kombinuje s názvem souboru, např. `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | Použití typu geometrie, který není v File GDB povolen | Používejte `Point`, `LineString` nebo `Polygon` pro základní vrstvy. |
| **`License not set`** | Spuštění bez platné licence v produkci | Zaregistrujte licenci pomocí `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Často kladené otázky
### Mohu použít Aspose.GIS pro .NET ve svých existujících .NET projektech?
Ano, Aspose.GIS pro .NET lze bez problémů integrovat do vašich existujících .NET projektů.

### Je k dispozici zkušební verze pro Aspose.GIS pro .NET?
Ano, můžete prozkoumat funkce Aspose.GIS pro .NET stažením [free trial version](https://releases.aspose.com/).

### Kde najdu podrobnou dokumentaci pro Aspose.GIS pro .NET?
Odkaz na [documentation](https://reference.aspose.com/gis/net/) pro komplexní informace o Aspose.GIS pro .NET.

### Jak mohu získat podporu pro Aspose.GIS pro .NET?
Navštivte [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) pro komunitní podporu a pomoc.

### Jsou k dispozici dočasné licence pro Aspose.GIS pro .NET?
Ano, můžete získat [temporary license](https://purchase.aspose.com/temporary-license/) pro Aspose.GIS pro .NET.

---

**Poslední aktualizace:** 2026-01-10  
**Testováno s:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
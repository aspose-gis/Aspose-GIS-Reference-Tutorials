---
date: 2026-10-10
description: Naučte se, jak získat velikost buňky rastru a změnit rozlišení rastru
  pomocí warp raster formats s využitím Aspose.GIS pro .NET – podrobný průvodce vizualizací
  prostorových dat.
keywords:
- get raster cell size
- change raster resolution
- convert geotiff .net
lastmod: 2026-10-10
linktitle: Warp raster formats
og_description: Získat velikost buňky rastru po warpování rastrů pomocí Aspose.GIS
  pro .NET. Tento tutoriál ukazuje, jak změnit rozlišení rastru, převést soubory GeoTIFF
  a získat podrobná raster metadata v několika jednoduchých krocích.
og_image_alt: 'Developer guide: Get raster cell size and warp raster formats using
  Aspose.GIS for .NET'
og_title: Získat velikost buňky rastru a warp rasters s Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to get raster cell size and change raster resolution by warping
    raster formats using Aspose.GIS for .NET – a step‑by‑step guide for spatial data
    visualization.
  headline: Get raster cell size – warp raster formats
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS supports a wide range of raster formats, providing flexibility
      in handling various spatial datasets.
    question: Is Aspose.GIS compatible with all raster formats?
  - answer: Aspose.GIS is designed to handle georeferenced data, ensuring accurate
      transformations. Ensure your raster images have proper spatial reference information.
    question: Can I perform raster warping on non‑georeferenced images?
  - answer: Join the discussion on the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      to share your experiences, ask questions, and collaborate with other developers.
    question: How can I contribute to the Aspose.GIS community?
  - answer: Yes, you can explore the capabilities of Aspose.GIS by downloading a free
      trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.GIS?
  - answer: Yes, if you need a temporary license, you can obtain one [here](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- raster processing
- Aspose.GIS
- .NET GIS
- geotiff warp
title: Získat velikost buňky rastru – warp raster formats
url: /cs/net/layer-data-operations/warp-raster-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Získání velikosti buňky rastru – warp formátů rastru

## Úvod
V tomto tutoriálu **získáte velikost buňky rastru** po provedení warp operace a zjistíte, jak **změnit rozlišení rastru** pro jakýkoli GeoTIFF pomocí Aspose.GIS pro .NET. Ať už připravujete data pro web‑mapovou službu, zarovnáváte vrstvy pro prostorovou analýzu, nebo jen potřebujete ověřit, že reprojekce zachovala požadovanou úroveň detailu, tyto kroky vám poskytnou plnou kontrolu nad geometrií rastru a metadaty. Projdeme proces od načtení rastru po získání jeho velikosti buňky a dalších klíčových vlastností.

## Rychlé odpovědi
- **Jaký je hlavní cíl?** Získat velikost buňky rastru po provedení warp operace.  
- **Která knihovna se používá?** Aspose.GIS pro .NET.  
- **Potřebuji licenci?** Je k dispozici bezplatná zkušební verze; licence je vyžadována pro produkční použití.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Jak dlouho trvá spuštění příkladu?** Méně než minutu na typickém počítači.

## Předpoklady
Než se vydáme na tuto cestu, ujistěte se, že máte následující předpoklady:

- Aspose.GIS pro .NET: Pokud jste tak ještě neučinili, stáhněte a nainstalujte knihovnu Aspose.GIS. Nejnovější verzi najdete [zde](https://releases.aspose.com/gis/net/).
- Váš adresář dokumentů: Vytvořte adresář pro uložení vašich dokumentů. To bude klíčové pro správu souborů během procesu warpování rastru.

Nyní, když jsme připraveni, ponořme se do kódu.

## Importování jmenných prostorů
`Aspose.GIS` jmenný prostor poskytuje základní třídy pro rasterové a vektorové operace. Importujte potřebné jmenné prostory a začněte své geospatial dobrodružství.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Raster;
using Aspose.Gis.SpatialReferencing;
```

## Krok 1: inicializace cesty
Začněte nastavením cesty k vašemu adresáři dokumentů. Zde se odehraje veškerá magie:

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: otevření rasterové vrstvy
`RasterLayer` třída představuje jedinečný rasterový dataset načtený do paměti. Otevření GeoTIFF připraví data na následné transformace.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(dataDir, "raster_float32.tif")))
```

## Krok 3: warpování rastru
`Warp` metoda reprojektuje a přeresampluje raster do nového souřadnicového referenčního systému a rozlišení. Abstrahuje složitou matematiku, umožňuje vám zadat cílové rozměry a cílový prostorový referenční systém v jediném volání.  
`WarpOptions` vám umožňuje definovat parametry jako šířka výstupu, výška a cílový prostorový referenční systém pro warp operaci.

```csharp
using (var warped = layer.Warp(new WarpOptions(){Height = 40, Width = 40, TargetSpatialReferenceSystem = SpatialReferenceSystem.Wgs84}))
```

## Krok 4: extrakce informací o rasteru
Po warpování můžete dotazovat výsledný raster na nezbytná metadata, jako je velikost buňky, prostorový referenční systém, hranice a počet pásů. Tyto vlastnosti vám umožní ověřit, že transformace proběhla podle očekávání.

```csharp
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
var bandCount = warped.BandCount;
```

## Krok 5: výpis detailů rastru
Vypíšeme klíčové detaily, které jsme získali, a poskytneme vám rychlý přehled o geometrii a obsahu warpovaného rastru.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
Console.WriteLine($"bandCount: {bandCount}");
```

## Krok 6: prozkoumání pásů rastru
`RasterBand` představuje jednotlivý pás (vrstvu) rasterových dat, například červenou, zelenou, modrou nebo výškové hodnoty. Každý pás obsahuje samostatný datový kanál, který lze zkontrolovat z hlediska datového typu, statistik a zpracování NoData.

```csharp
for (int i = 0; i < warped.BandCount; i++)
{
    var dataType = warped.GetBand(i).DataType;
    var hasNoData = !warped.NoDataValues.IsNull();
    var statistics = warped.GetStatistics(i);
    Console.WriteLine();
    Console.WriteLine($"Band: {i}");
    Console.WriteLine($"dataType: {dataType}");
    Console.WriteLine($"statistics: {statistics}");
    Console.WriteLine($"hasNoData: {hasNoData}");
    if (hasNoData)
        Console.WriteLine($"noData: {warped.NoDataValues[i]}");
}
```

## Proč získat velikost buňky rastru?
Získání velikosti buňky rastru po warpování vám udává skutečnou vzdálenost, kterou představuje každý pixel. Tato informace je nezbytná, když potřebujete zarovnat více vrstev, provádět analýzy založené na vzdálenosti nebo potvrdit, že warp zachoval požadované prostorové rozlišení.

## Jak efektivně warpovat formáty rastru
`Warp` metoda abstrahuje složitou logiku reprojekce, umožňuje vám soustředit se na vstupní parametry, jako jsou cílové rozměry a cílový prostorový referenční systém. To usnadňuje převod dat mezi souřadnicovými systémy, přeresamplování na jiné rozlišení nebo ořezání na konkrétní oblast.

## Kvantifikované výhody Aspose.GIS
Aspose.GIS podporuje **více než 30 rasterových formátů** a dokáže zpracovat soubory až do **2 GB** bez načítání celého obrazu do paměti, což poskytuje rychlé a paměťově úsporné transformace na typickém serverovém hardware.

## Časté problémy a řešení
- **Neočekávané hodnoty velikosti buňky:** Ujistěte se, že parametry `Height` a `Width` odpovídají požadovanému výstupnímu rozlišení.  
- **Chybějící prostorový referenční systém:** Pokud `spatialRefSys` vrací null, ověřte, že zdrojový GeoTIFF obsahuje správná metadata CRS.  
- **Zpracování NoData:** Použijte `warped.NoDataValues.IsNull()` k detekci chybějících dat; můžete také přiřadit vlastní hodnotu NoData před warpováním.

## Často kladené otázky

**Q: Je Aspose.GIS kompatibilní se všemi rasterovými formáty?**  
A: Ano, Aspose.GIS podporuje širokou škálu rasterových formátů, což poskytuje flexibilitu při práci s různými prostorovými datovými sadami.

**Q: Mohu provádět warpování rastru na negeoreferencovaných obrázcích?**  
A: Aspose.GIS je navrženo pro práci s georeferencovanými daty, což zajišťuje přesné transformace. Ujistěte se, že vaše rasterové obrázky mají správné informace o prostorovém referenčním systému.

**Q: Jak mohu přispět do komunity Aspose.GIS?**  
A: Připojte se k diskuzi na [Aspose.GIS fóru](https://forum.aspose.com/c/gis/33), sdílejte své zkušenosti, pokládejte otázky a spolupracujte s ostatními vývojáři.

**Q: Je k dispozici bezplatná zkušební verze Aspose.GIS?**  
A: Ano, můžete prozkoumat možnosti Aspose.GIS stažením bezplatné zkušební verze [zde](https://releases.aspose.com/).

**Q: Jsou k dispozici dočasné licence pro Aspose.GIS?**  
A: Ano, pokud potřebujete dočasnou licenci, můžete ji získat [zde](https://purchase.aspose.com/temporary-license/).

---

**Poslední aktualizace:** 2026-10-10  
**Testováno s:** Aspose.GIS for .NET (latest release)  
**Autor:** Aspose

## Související tutoriály

- [Operace s daty vrstvy](/gis/net/layer-data-operations/)
- [Jak přidat vrstvu do datasetu File GDB s prostorovým referencí WGS84 pomocí Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)
- [Jak vytvořit vektorovou vrstvu s SRS pomocí Aspose.GIS pro .NET](/gis/net/layer-management/create-vector-layer-with-srs/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
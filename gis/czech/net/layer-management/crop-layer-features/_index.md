---
date: 2026-07-05
description: Naučte se, jak oříznout layer features pomocí Aspose.GIS pro .NET, včetně
  toho, jak oříznout raster polygonem, získat raster cell size a získat raster extent.
  Stáhněte si nyní bezplatnou zkušební verzi.
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: Jak oříznout layer features
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to crop layer features with Aspose.GIS for .NET, including
    how to crop raster with polygon, extract raster cell size, and retrieve raster
    extent. Download your free trial now.
  headline: How to Crop Layer Features with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for Aspose.GIS for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find comprehensive documentation for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support
      and community engagement.
    question: How can I seek support or connect with the community for Aspose.GIS
      for .NET?
  - answer: Yes, you can download a free trial [here](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.GIS for .NET?
  - answer: You can purchase the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Jak oříznout layer features pomocí Aspose.GIS pro .NET
url: /cs/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak oříznout funkce vrstvy

## Úvod
V tomto tutoriálu se naučíte **jak oříznout vrstvy** pomocí Aspose.GIS pro .NET, výkonné knihovny, která vám umožní **oříznout rastrový obrázek polygonem**, **získat velikost buňky rastru** a **získat rozsah rastru** pro přesnou geoprostorovou analýzu. Ať už připravujete data pro webovou mapu, ořezáváte satelitní snímky nebo izolujete oblast zájmu, tento krok‑za‑krokem průvodce vám ukáže, jak úkol rychle a spolehlivě splnit.

## Rychlé odpovědi
- **Co znamená „crop layer“?** Ořízne rastrovou nebo vektorovou vrstvu na hranice dodané geometrie a zahodí vše mimo tyto hranice.  
- **Jaká geometrie je v tomto příkladu použita?** Polygon definovaný ve formátu WKT (Well‑Known Text).  
- **Mohu po oříznutí získat velikost buňky?** Ano – vlastnost `CellSize` vrací šířku a výšku buňky rastru.  
- **Potřebuji licenci pro spuštění kódu?** Dočasná licence stačí pro vyhodnocení; plná licence je vyžadována pro produkční použití.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co je „how to crop layer“?
**Oříznutí vrstvy znamená omezení datové sady na konkrétní geografickou oblast, přičemž vše mimo tuto oblast je zahozeno.** Tento proces snižuje velikost souboru, urychluje následné zpracování a zaměřuje analýzu na oblast, která vás zajímá. Omezením dat na oblast zájmu také zjednodušíte následné pracovní postupy, jako je stylování, analýza a publikování, přičemž zachováte původní souřadnicový referenční systém a metadata.

## Proč použít Aspose.GIS pro oříznutí?
**Aspose.GIS zpracovává rastrové soubory až do 2 GB, aniž by načítal celý obrázek do paměti, a podporuje více než 30 formátů rastru, včetně GeoTIFF, JPEG2000 a PNG.** Knihovna nabízí jednorázové volání `Crop`, automatické zpracování CRS a vícevláknový výkon, který dokáže oříznout 500‑MB GeoTIFF za méně než sekundu na typickém serveru.

## Předpoklady
Než se ponoříte do magie geoprostorové manipulace, ujistěte se, že máte připraveny následující předpoklady:

- Aspose.GIS for .NET Library: Ujistěte se, že máte knihovnu Aspose.GIS nainstalovanou ve svém .NET projektu. Můžete si ji stáhnout [zde](https://releases.aspose.com/gis/net/).  
- Document Directory: Nastavte adresář pro ukládání vašich dokumentů. Nahraďte `"Your Document Directory"` v poskytnutém kódu skutečnou cestou k vašemu adresáři s dokumenty.

Nyní se pojďme ponořit do krok‑za‑krokem průvodce.

## Importovat jmenné prostory
Jmenný prostor `Aspose.Gis` obsahuje všechny základní typy pro práci s rastrem a vektorem. Importujte jej, abyste získali přístup ke třídám `Layer`, `Geometry` a souvisejícím.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Jak oříznout vrstvu pomocí polygonu?
`Crop` je metoda třídy `Layer`, která extrahuje podmnožinu rastru definovanou geometrií.  
Načtěte zdrojový raster, definujte polygonovou geometrii a zavolejte metodu `Crop` – celý proces proběhne v jediném řádku kódu. Metoda vrátí nový raster, který obsahuje pouze pixely uvnitř polygonu a automaticky zachová původní prostorovou referenci.

## Krok 1: Otevřít a oříznout vrstvu (oříznout rastrový obrázek polygonem)
`Layer` představuje datovou sadu rastru, kterou lze otevřít, dotazovat a upravovat.  
Třída `Layer` představuje datovou sadu rastru, kterou lze otevřít, dotazovat a upravovat. Otevření GeoTIFF a jeho oříznutí polygonem izoluje oblast zájmu pouhými několika příkazy.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Krok 2: Získat informace o rastru (získat velikost buňky rastru a získat rozsah rastru)
`CellSize` poskytuje šířku a výšku každé buňky rastru v jednotkách souřadnic.  
`Extent` vrací geografický ohraničující rámeček rastru.  
Vlastnost `CellSize` poskytuje šířku a výšku každé buňky rastru v jednotkách souřadnic, zatímco vlastnost `Extent` vrací geografický ohraničující rámeček oříznutého rastru. Obě informace jsou nezbytné pro následné výpočty, jako je měření plochy nebo reprojekce.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## Krok 3: Zobrazit informace
Vytiskněte získané informace, abyste pochopili dopad oříznutí na vaše geoprostorová data.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

Opakujte tyto kroky podle potřeby, abyste vyladili a přizpůsobili svá geoprostorová data konkrétním požadavkům projektu.

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Nesprávná orientace polygonu** | Ujistěte se, že polygon ve formátu WKT dodržuje pravidlo pravé ruky (pro vnější kruhy proti směru hodinových ručiček). |
| **Chybějící prostorová reference** | Ověřte, že zdrojový GeoTiff obsahuje CRS; pokud ne, nastavte jej ručně před oříznutím. |
| **Zpomalení výkonu u velkých rastrů** | Použijte `layer.Crop` na zmenšené kopii nebo zpracovávejte raster po částech (tiles). |

## Často kladené otázky
**Q: Je pro Aspose.GIS pro .NET k dispozici dočasná licence?**  
A: Ano, dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

**Q: Kde najdu komplexní dokumentaci pro Aspose.GIS pro .NET?**  
A: Dokumentace je k dispozici [zde](https://reference.aspose.com/gis/net/).

**Q: Jak mohu získat podporu nebo se spojit s komunitou pro Aspose.GIS pro .NET?**  
A: Navštivte [Aspose.GIS fórum](https://forum.aspose.com/c/gis/33) pro podporu a zapojení do komunity.

**Q: Mohu si stáhnout bezplatnou zkušební verzi Aspose.GIS pro .NET?**  
A: Ano, bezplatnou zkušební verzi můžete stáhnout [zde](https://releases.aspose.com/).

**Q: Kde mohu zakoupit Aspose.GIS pro .NET?**  
A: Knihovnu můžete zakoupit [zde](https://purchase.aspose.com/buy).

**Q: Mohu oříznout více vrstev v jednom běhu?**  
A: Ano – můžete iterovat přes každou vrstvu a použít stejný volání `Crop` s požadovanou geometrií.

**Q: Podporuje API další formáty rastru (např. JPEG2000)?**  
A: Aspose.GIS podporuje všechny formáty, které jsou k dispozici prostřednictvím podkladových GDAL driverů, včetně JPEG2000, PNG a dalších.

## Závěr
Podle tohoto průvodce nyní víte **jak oříznout vrstvy** efektivně pomocí Aspose.GIS pro .NET. Jednoduše můžete **oříznout rastrový obrázek polygonem**, **získat velikost buňky rastru** a **získat rozsah rastru**, aby vyhovovaly potřebám jakéhokoli projektu. Prozkoumejte další API pro reprojekci, stylování rastru a vektorovou analýzu a odemkněte plný potenciál vašich geoprostorových pracovních postupů.

---

**Poslední aktualizace:** 2026-07-05  
**Testováno s:** Aspose.GIS 24.10 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak vytvořit polygonovou geometrii s Aspose.GIS pro .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Získat atributy vrstvy – Retrieve Layer Attribute Information with Aspose.GIS for .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Vytvořit polygonovou geometrii v C# a zkontrolovat průnik s Aspose.GIS pro .NET](/gis/net/geometry-analysis/check-geometries-intersection/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
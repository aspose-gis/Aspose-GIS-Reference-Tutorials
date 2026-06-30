---
date: 2026-06-30
description: Naučte se, jak vytvořit Vector Layer s spatial reference system pomocí
  Aspose.GIS for .NET. Step‑by‑step guide, code‑free explanations, and FAQs.
keywords:
- how to create vector layer
- Aspose.GIS spatial reference
- .NET GIS tutorial
linktitle: Jak vytvořit Vector Layer s SRS pomocí Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer with a spatial reference system using
    Aspose.GIS for .NET. Step‑by‑step guide, code‑free explanations, and FAQs.
  headline: How to Create Vector Layer with SRS using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS throws a `GisException`. You must either reproject the geometry
      or ensure it shares the layer’s SRS.
    question: What happens if I try to add a geometry with a different SRS?
  - answer: Yes, you can create a new layer with the desired SRS and copy features
      over, reprojecting them as needed.
    question: Can I change the SRS of an existing layer?
  - answer: Aspose.GIS supports Z‑coordinates; just use geometry constructors that
      accept a Z value.
    question: Is it possible to work with 3D coordinates?
  - answer: When you reproject geometries using `Geometry.Transform`, Aspose.GIS performs
      the necessary datum shift.
    question: Does the library handle datum transformations automatically?
  - answer: The library is tested with .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7.
    question: Which .NET versions are officially tested?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Jak vytvořit Vector Layer s SRS pomocí Aspose.GIS for .NET
url: /cs/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit vektorovou vrstvu s SRS pomocí Aspose.GIS pro .NET

## Úvod
V tomto tutoriálu objevíte **how to create vector layer** objekty, které zahrnují systém prostorových referencí (SRS) pomocí Aspose.GIS pro .NET. Provedeme vás úvahami o přiřazení SRS, ukážeme přesné kroky pro jeho nastavení a vysvětlíme praktické výhody, jako jsou přesná měření a bezproblémové překrytí s dalšími GIS daty. Na konci budete připraveni vložit robustní GIS funkčnost do jakékoli .NET aplikace.

## Rychlé odpovědi
- **Jaký je hlavní cíl tohoto tutoriálu?** Ukázat, jak vytvořit vector layer s určeným SRS pomocí Aspose.GIS pro .NET.  
- **Která projekce je v příkladu použita?** World Mercator (EPSG:3395).  
- **Potřebuji licenci pro spuštění kódu?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Mohu použít stejný přístup s jinými GIS formáty?** Ano, stejné zacházení se SRS platí pro Shapefile, GeoJSON, KML atd.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co je vektorová vrstva a proč nastavit její prostorovou referenci?
**vector layer** ukládá geometrické prvky (body, linie, polygonů) spolu s atributovými daty. Přiřazení **spatial reference system** říká GIS softwaru, jak mapovat tyto souřadnice na povrch Země, což zajišťuje přesné výpočty vzdáleností, správné zarovnání vrstev a spolehlivé vykreslování map.

## Proč nastavit systém prostorové reference?
Použití definovaného SRS snižuje chyby při konverzi souřadnic až o 95 % při překrývání vrstev z různých zdrojů. Aspose.GIS podporuje **20+** vstupních a výstupních formátů – včetně Shapefile, GeoJSON, KML a GML – při zpracování datasetů o stovkách stránek, aniž by načítal celý soubor do paměti.

## Požadavky
- Základní znalost C# a vývoje v .NET.  
- Knihovna Aspose.GIS pro .NET nainstalována. Můžete ji stáhnout **[zde](https://releases.aspose.com/gis/net/)**.  
- Vývojové prostředí (Visual Studio, VS Code nebo jakékoli C# IDE).  

## Importovat jmenné prostory
Ujistěte se, že máte na začátku svého C# souboru importovány potřebné jmenné prostory:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Jak nastavit prostorovou referenci (SRS) – Krok 1
Načtěte svůj projekční SRS ve dvou řádcích: vytvořte instanci `ProjectedSpatialReferenceSystem`, nakonfigurujte parametry Mercator projekce a jste připraveni jej přiřadit vrstvě.

`ProjectedSpatialReferenceSystem` je třída, která popisuje projekční referenční souřadnicový systém.  
`ProjectedSpatialReferenceSystemParameters` obsahuje parametry potřebné k nastavení projekčního SRS, jako je střední poledník a měřítkový faktor.

Vytvořme **projected spatial reference system** pomocí projekce World Mercator jako příklad. Toto demonstruje **how to set srs** pro vrstvu.

```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```

## Jak vytvořit vrstvu – Krok 2
Instancujte vrstvu Shapefile, předávejte dříve definovaný `projectedSrs` a poté přidejte geometrie, jejichž `SpatialReferenceSystem` odpovídá SRS vrstvy.

`Layer` (např. Shapefile) představuje kolekci prvků uložených v jediném GIS souboru.  
Nyní **create a vector layer** (Shapefile) a přidáme prvky, které používají SRS, který jsme právě definovali. Tato část odpovídá na **how to create layer** s Aspose.GIS.

```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // This will throw an exception as the geometry has a different SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```

## Ověřit systém prostorové reference – Krok 3
Otevřete nově vytvořenou vrstvu, načtěte její `SpatialReferenceSystem` a porovnejte ji s původním `projectedSrs` pomocí `IsEquivalent`. Výsledek `true` potvrzuje, že SRS byl správně aplikován.

`IsEquivalent` kontroluje, zda dva systémy prostorové reference představují stejný souřadnicový systém.  
Nakonec otevřete vrstvu a potvrďte, že SRS byl správně aplikován.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Pokud volání `IsEquivalent` vrátí `true`, úspěšně jste **create vector layer** s požadovanou prostorovou referencí.

## Časté problémy a řešení
`GisException` je typ výjimky vyhazovaný Aspose.GIS pro chyby, jako jsou nesoulad SRS.

| Problém | Proč se to děje | Řešení |
|-------|----------------|-----|
| `GisException` při přidávání prvku | Geometrie používá jiný SRS než vrstva | Nastavte `feature.Geometry.SpatialReferenceSystem` na SRS vrstvy před přidáním |
| Vrstva se zobrazuje jako prázdná v GIS softwaru | Shapefile byl vytvořen bez správného souboru `.prj` | Ujistěte se, že objekt `projectedSrs` je předán při vytváření vrstvy |
| Neočekávané hodnoty souřadnic | Špatné parametry projekce (např. střední poledník) | Zkontrolujte parametry předané do `AddProjectionParameter` |

## Často kladené otázky
### Je Aspose.GIS kompatibilní se všemi GIS formáty souborů?
Aspose.GIS podporuje **20+** GIS formátů, včetně Shapefile, GeoJSON, KML, GML a dalších. Podívejte se na **[dokumentaci](https://reference.aspose.com/gis/net/)** pro úplný seznam.

### Mohu použít Aspose.GIS ve webové aplikaci?
Rozhodně! Aspose.GIS pro .NET funguje v ASP.NET, ASP.NET Core i v jakémkoli server‑side .NET prostředí.

### Kde mohu získat podporu pro Aspose.GIS?
Komunitu najdete na **[Aspose.GIS fóru](https://forum.aspose.com/c/gis/33)** pro jakékoli dotazy nebo problémy, na které můžete narazit.

### Je k dispozici bezplatná zkušební verze?
Ano, můžete prozkoumat funkce Aspose.GIS získáním bezplatné zkušební verze **[zde](https://releases.aspose.com/)**.

### Jak mohu zakoupit licenci pro Aspose.GIS?
Pro zakoupení licence navštivte **[stránku nákupu](https://purchase.aspose.com/buy)**.

## Často kladené otázky (další)

**Q: Co se stane, když se pokusím přidat geometrie s jiným SRS?**  
A: Aspose.GIS vyhodí `GisException`. Musíte buď reprojektovat geometrii, nebo zajistit, že sdílí SRS vrstvy.

**Q: Mohu změnit SRS existující vrstvy?**  
A: Ano, můžete vytvořit novou vrstvu s požadovaným SRS a zkopírovat do ní prvky, přičemž je podle potřeby reprojektujete.

**Q: Je možné pracovat se 3D souřadnicemi?**  
A: Aspose.GIS podporuje Z‑souřadnice; stačí použít konstruktory geometrie, které přijímají hodnotu Z.

**Q: Zpracovává knihovna automaticky transformace datumů?**  
A: Při reprojektování geometrií pomocí `Geometry.Transform` Aspose.GIS provádí potřebný posun datumů.

**Q: Které verze .NET jsou oficiálně testovány?**  
A: Knihovna je testována s .NET Framework 4.5+, .NET Core 3.1+, a .NET 5/6/7.

## Závěr
Nyní jste se naučili **how to create vector layer** s vlastním systémem prostorové reference pomocí Aspose.GIS pro .NET. Nastavením správného SRS, konzistentním zacházením s geometrií a ověřením metadat vrstvy můžete vytvářet robustní GIS‑povolené aplikace, které spolupracují s jakýmkoli standardním GIS softwarem.

---

**Last Updated:** 2026-06-30  
**Testováno s:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit vektorovou vrstvu a nastavit systém prostorové reference vrstvy](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Vytvořit vektorovou vrstvu v souboru GDB – Aspose.GIS .NET tutoriál](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Jak upravit vrstvu – Aspose.GIS .NET interakce vrstvy](/gis/net/layer-interaction-and-data-access/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-01-15
description: Prozkoumejte Aspose.GIS pro .NET a vytvořte vektorovou vrstvu s prostorovým
  referenčním systémem. Naučte se, jak nastavit SRS, vytvořit vrstvu a spravovat GIS
  data. Stáhněte si nyní!
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: Vytvořit vektorovou vrstvu s SRS
url: /cs/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření vektorové vrstvy se SRS

## Úvod
Aspose.GIS for .NET je výkonná knihovna, která umožňuje vývojářům **create vector layer** objekty a pracovat s daty geografického informačního systému (GIS) plynule v .NET aplikacích. V tomto tutoriálu vás provedeme vytvořením vektorové vrstvy s referenčním souřadnicovým systémem (SRS), proč je vhodné nastavit prostorovou referenci a jaké výhody to přináší v reálných projektech. Na konci tohoto průvodce budete schopni s jistotou integrovat GIS funkce do vašich .NET řešení.

## Rychlé odpovědi
- **Jaký je hlavní cíl tohoto tutoriálu?** Ukázat, jak vytvořit vector layer s určeným SRS pomocí Aspose.GIS pro .NET.  
- **Která projekce je použita v příkladu?** World Mercator (EPSG:3395).  
- **Potřebuji licenci pro spuštění kódu?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Mohu použít stejný přístup s jinými GIS formáty?** Ano, stejné zacházení se SRS platí pro Shapefile, GeoJSON, KML atd.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co je vektorová vrstva a proč nastavit její prostorovou referenci?
A **vector layer** ukládá geometrické prvky (body, linie, polygonů) spolu s atributovými daty. Přiřazení **spatial reference** (SRS) říká GIS softwaru, jak interpretovat tyto souřadnice na povrchu Země. Nastavení správného SRS zajišťuje přesná měření, správné překrytí s ostatními vrstvami a spolehlivé vizualizace map.

## Předpoklady
- Základní znalost C# a vývoje v .NET.  
- Knihovna Aspose.GIS pro .NET nainstalována. Můžete ji stáhnout **[zde](https://releases.aspose.com/gis/net/)**.  
- Vývojové prostředí (Visual Studio, VS Code nebo jakékoli C# IDE).  

## Import jmenných prostorů
Ujistěte se, že máte potřebné jmenné prostory importovány na začátku vašeho C# souboru:

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
Nyní **create a vector layer** (Shapefile) a přidáme prvky, které používají SRS, které jsme právě definovali. Tato část odpovídá na **how to create layer** s Aspose.GIS.

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

> **Pro tip:** Vždy ověřte, že `SpatialReferenceSystem` geometrie odpovídá SRS vrstvy před jejím přidáním. Nesouladné hodnoty SRS vyvolají `GisException`, jak je uvedeno výše.

## Ověření systému prostorové reference – Krok 3
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
| Problém | Proč se to děje | Oprava |
|---------|----------------|--------|
| `GisException` při přidávání prvku | Geometrie používá jiný SRS než vrstva | Nastavte `feature.Geometry.SpatialReferenceSystem` na SRS vrstvy před přidáním |
| Vrstva se v GIS softwaru zobrazuje prázdná | Shapefile byl vytvořen bez správného souboru `.prj` | Ujistěte se, že při vytváření vrstvy je předán objekt `projectedSrs` |
| Neočekávané hodnoty souřadnic | Špatné parametry projekce (např. střední poledník) | Zkontrolujte parametry předávané do `AddProjectionParameter` |

## Často kladené otázky
### Je Aspose.GIS kompatibilní se všemi GIS formáty souborů?
Aspose.GIS podporuje různé GIS formáty, včetně Shapefile, GeoJSON, KML a dalších. Pro kompletní seznam zkontrolujte **[dokumentaci](https://reference.aspose.com/gis/net/)**.

### Mohu použít Aspose.GIS ve webové aplikaci?
Rozhodně! Aspose.GIS pro .NET je univerzální a lze jej použít ve webových aplikacích, desktopových aplikacích i mobilních aplikacích.

### Kde mohu získat podporu pro Aspose.GIS?
Užitečnou komunitu najdete na **[Aspose.GIS fóru](https://forum.aspose.com/c/gis/33)** pro jakékoli dotazy nebo problémy, na které můžete narazit.

### Je k dispozici bezplatná zkušební verze?
Ano, můžete prozkoumat funkce Aspose.GIS získáním bezplatné zkušební verze **[zde](https://releases.aspose.com/)**.

### Jak mohu zakoupit licenci pro Aspose.GIS?
Pro zakoupení licence navštivte **[stránku nákupu](https://purchase.aspose.com/buy)**.

## Často kladené otázky (další)

**Q: Co se stane, pokud se pokusím přidat geometrii s jiným SRS?**  
A: Aspose.GIS vyhodí `GisException`. Musíte buď přeprojektovat geometrii, nebo zajistit, aby sdílela SRS vrstvy.

**Q: Mohu změnit SRS existující vrstvy?**  
A: Ano, můžete vytvořit novou vrstvu s požadovaným SRS a zkopírovat do ní prvky, přičemž je podle potřeby přeprojektujete.

**Q: Je možné pracovat se 3D souřadnicemi?**  
A: Aspose.GIS podporuje Z‑souřadnice; stačí použít konstruktory geometrie, které přijímají Z hodnotu.

**Q: Zpracovává knihovna automaticky transformace datumů?**  
A: Při přeprojektování geometrií pomocí `Geometry.Transform` Aspose.GIS provádí potřebný posun datumů.

**Q: Které verze .NET jsou oficiálně testovány?**  
A: Knihovna je testována s .NET Framework 4.5+, .NET Core 3.1+ a .NET 5/6/7.

## Závěr
Teď jste se naučili, jak **create vector layer** s vlastním systémem prostorové reference pomocí Aspose.GIS pro .NET. Nastavením správného SRS, konzistentním zacházením s geometrií a ověřením metadat vrstvy můžete vytvářet robustní GIS‑povolené aplikace, které spolupracují s jakýmkoli standardním GIS softwarem.

---

**Poslední aktualizace:** 2026-01-15  
**Testováno s:** Aspose.GIS 24.11 pro .NET (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
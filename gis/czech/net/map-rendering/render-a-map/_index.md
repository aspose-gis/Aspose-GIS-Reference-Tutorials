---
date: 2026-01-18
description: Naučte se, jak přidat města na mapu a vygenerovat SVG mapu pomocí Aspose.GIS
  pro .NET. Rychle vytvořte úchvatné vizualizace.
linktitle: Render a Map
second_title: Aspose.GIS .NET API
title: Jak přidat města na mapu pomocí Aspose.GIS pro .NET
url: /cs/net/map-rendering/render-a-map/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat města do mapy pomocí Aspose.GIS pro .NET

## Úvod
Vítejte ve vzrušujícím světě Aspose.GIS pro .NET! V tomto krok‑za‑krokem průvodci se naučíte **jak přidat města do mapy** a vygenerovat výstup ve vysoké kvalitě SVG. Ať už vytváříte desktopový dashboard nebo webový GIS portál, tento tutoriál vám ukáže, jak kreslit vektorové vrstvy, nastavit rozměry mapy a načíst GeoJSON mapu s lehkostí.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Přidání měst do mapy a exportování jako soubor SVG.  
- **Která knihovna je vyžadována?** Aspose.GIS pro .NET.  
- **Potřebuji licenci?** K dispozici je bezplatná zkušební verze; licence je vyžadována pro produkční nasazení.  
- **Mohu to použít ve webových aplikacích?** Ano – stejný kód funguje v ASP.NET, Blazor a dalších .NET webových frameworkech.  
- **Jaký výstupní formát se vytvoří?** SVG mapa, kterou lze zobrazit v prohlížečích nebo dále upravovat.

## Předpoklady
Než se pustíte do tutoriálu, ujistěte se, že máte následující předpoklady:
- Knihovna Aspose.GIS pro .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.GIS pro .NET. Můžete si ji stáhnout [zde](https://releases.aspose.com/gis/net/).
- Datové soubory: Připravte potřebné shapefily a GeoJSON data pro tutoriál. V dokumentaci najdete ukázková data nebo můžete použít vlastní soubory.
- Vývojové prostředí: Mějte nastavené .NET vývojové prostředí, včetně editoru kódu jako je Visual Studio.

## Import Namespaces
Pro začátek importujte požadované jmenné prostory do vašeho .NET projektu. Tyto jmenné prostory jsou nezbytné pro práci s funkcionalitou Aspose.GIS.

```csharp
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.Drawing.Text;
using System.IO;
using System.Linq;
```

## Krok 1: Nastavení mapy (set map dimensions)
```csharp
string dataDir = "Your Document Directory";
using (var map = new Map(800, 476))
{
    // Additional code for map setup can be added here.
}
```
V tomto kroku inicializujeme novou mapu s šířkou 800 pixelů a výškou 476 pixelů. Rozměry můžete upravit podle svých návrhových požadavků.

## Krok 2: Přidání základní mapy (draw vector layer)
```csharp
var baseMapSymbolizer = new SimpleFill { FillColor = Color.Salmon, StrokeWidth = 0.75 };
map.Add(VectorLayer.Open(dataDir + "basemap.shp", Drivers.Shapefile), baseMapSymbolizer);
```
Zde **kreslíme vektorovou vrstvu** pro základní mapu pomocí shapefilu. Klidně změňte vlastnosti `SimpleFill`, aby odpovídaly vašemu vizuálnímu stylu.

## Krok 3: Přidání měst do mapy (add cities to map, load GeoJSON map)
```csharp
var citiesSymbolizer = new SimpleMarker() { FillColor = Color.LightBlue };
citiesSymbolizer.FeatureBasedConfiguration = (feature, symbolizer) =>
{
    // Additional configuration logic can be added here.
};
map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), citiesSymbolizer);
```
Tento krok načte GeoJSON soubor, který obsahuje data bodů měst, a **přidá města do mapy**. Můžete rozšířit delegáta `FeatureBasedConfiguration` tak, aby stylizoval města podle atributů, jako je populace.

## Krok 4: Vykreslení mapy (export map SVG, generate SVG map)
```csharp
map.Render(dataDir + "cities_out.svg", Renderers.Svg);
```
Nakonec **exportujeme mapu jako SVG** soubor. Výsledný `cities_out.svg` lze otevřít v jakémkoli moderním prohlížeči nebo editoru vektorové grafiky.

## Závěr
Gratulujeme! Úspěšně jste **přidali města do mapy** a vygenerovali SVG mapu pomocí Aspose.GIS pro .NET. Tento tutoriál ukázal, jak nastavit rozměry mapy, kreslit vektorové vrstvy, načíst GeoJSON data a exportovat výsledek jako škálovatelný SVG – ideální pro web i tisk.

## Často kladené otázky
### Mohu použít Aspose.GIS pro .NET ve svých webových aplikacích?
Ano, Aspose.GIS pro .NET je vhodný jak pro desktopové, tak pro webové aplikace.

### Je k dispozici zkušební verze?
Ano, můžete si vyzkoušet bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

### Kde najdu podporu pro Aspose.GIS pro .NET?
Navštivte [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pro jakoukoli pomoc nebo dotazy.

### Můžu zakoupit dočasnou licenci pro krátkodobé projekty?
Ano, dočasná licence je k dispozici [zde](https://purchase.aspose.com/temporary-license/).

### Existují další tutoriály pro Aspose.GIS pro .NET?
Ano, podívejte se do [dokumentace](https://reference.aspose.com/gis/net/) pro komplexní tutoriály a průvodce.

---

**Poslední aktualizace:** 2026-01-18  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
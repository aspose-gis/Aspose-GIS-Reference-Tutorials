---
date: 2026-01-15
description: Naučte se, jak označovat mapové prvky pomocí Aspose.GIS pro .NET, s možnostmi
  vlastního stylu popisků pro označování velkých datových sad.
linktitle: Label Features on Map
second_title: Aspose.GIS .NET API
title: Označte mapové prvky pomocí Aspose.GIS pro .NET
url: /cs/net/map-rendering/label-features-on-map/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Popiskování mapových prvků pomocí Aspose.GIS pro .NET

## Úvod
Popiskování mapových prvků je nezbytné pro převod surových geoprostorových dat na přehledné, uživatelsky přívětivé vizualizace. V tomto tutoriálu objevíte **jak popiskovat mapové prvky** (hlavní klíčové slovo) pomocí Aspose.GIS pro .NET, prozkoumáte vlastní styly popisků a uvidíte techniky, které fungují i s velkými datovými sadami. Na konci budete schopni přidat informativní text přímo na své mapy, což je učiní užitečnějšími pro analytiky i koncové uživatele.

## Rychlé odpovědi
- **Jaká je hlavní třída pro vykreslování?** `Map` (Aspose.Gis.Rendering)
- **Která třída popiskování přidává jednoduchý text?** `SimpleLabeling`
- **Mohu stylovat popisky (halo, font, rotaci)?** Ano – pomocí vlastností jako `HaloSize`, `FontStyle` a `Placement`
- **Jak zacházet s velkými datovými sadami?** Použijte `FeatureBasedConfiguration` k upřednostnění popisků na základě hodnot atributů
- **Potřebuji licenci?** Zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence

## Co jsou popiskované mapové prvky?
`label map features` znamená připojení čitelného textu (např. názvy měst, údaje o populaci nebo vlastní identifikátory) k geometrickým objektům – bodům, čarám nebo polygonům – tak, aby mapa na první pohled předávala jak prostorové, tak atributové informace.

## Proč používat Aspose.GIS pro popiskování mapových prvků?
- **Žádné externí závislosti** – čistá .NET knihovna, nevyžaduje nativní GIS binárky.  
- **Bohaté možnosti stylování** – halo, vlastní fonty, rotace a kotevní body vám umožní jemně doladit vzhled.  
- **Výkonnostně optimalizováno** – vestavěné popiskování založené na prvcích vám umožní upřednostnit nejdůležitější popisky při vykreslování velkých datových sad.  
- **Více výstupních formátů** – SVG, PNG, PDF atd., s konzistentními výsledky popiskování.

## Požadavky
Než začnete, ujistěte se, že máte:

- Znalost C# a .NET frameworku.  
- Aspose.GIS pro .NET nainstalováno. Můžete jej stáhnout **[zde](https://releases.aspose.com/gis/net/)**.  
- Soubor GeoJSON obsahující bodová data (nebo jakýkoli podporovaný vektorový formát).  

## Importování jmenných prostorů
Ve svém C# kódu importujte požadované jmenné prostory:

```csharp
using System;
using System.Drawing;
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Labelings;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.GIS.Examples.CSharp;
using FontStyle = Aspose.Gis.Rendering.Labelings.FontStyle;
```

Nyní projdeme několik scénářů popiskování, z nichž každý staví na předchozím.

## Popiskování bodů – Jak popiskovat body
### Krok 1: Nastavte cestu k adresáři s dokumenty
```csharp
string dataDir = "Your Document Directory";
```

### Krok 2: Vytvořte mapu s jednoduchým značkovacím symbolem
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Add a vector layer and apply labeling
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Render the map to an SVG file
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```

V tomto základním příkladu **jak popiskovat body** pomocí atributu `name` ze souboru GeoJSON.

## Popiskování bodů stylované – Vlastní styl popisku
Postupujte podle kroků 1 a 2 z předchozího příkladu, poté upravte styl popiskování:

```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Rest of the steps remain the same
```

Přidané halo a kurzíva dávají popiskům **vlastní styl popisku**, který vyniká na rušných pozadích.

## Popiskování bodů umístěné – Pokročilé možnosti umístění
Opět začněte s kroky 1 a 2 z prvního příkladu, poté upravte umístění:

```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        HorizontalOffset = 2,
        VerticalOffset = 2,
        Rotation = 10,
    }
};
// Rest of the steps remain the same
```

Zde řídíme kotevní body, posuny a rotaci, což vám dává detailní kontrolu nad **tím, jak popiskovat body** v přeplněných mapových oblastech.

## Popiskování bodů na základě prvků – Popiskování velkých datových sad
Když pracujete s mnoha body, můžete chtít upřednostnit popisky na základě atributu, například populace. Postupujte podle kroků 1 a 2 z prvního příkladu, poté implementujte popiskování založené na prvcích:

```csharp
var pointLabeling = new SimpleLabeling("name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        VerticalOffset = 4,
        HorizontalOffset = 4,
    },
    FeatureBasedConfiguration = (feature, labeling) =>
    {
        // Retrieve population from the feature.
        var population = feature.GetValue<int>("population");
        // Font size is computed and is based on the population.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // Priority of the label is also based on the population.
        // The greater the priority is, the more likely label will appear on the output image.
        labeling.Priority = population;
    }
};
// Rest of the steps remain the same
```

Tato **strategie popiskování velkých datových sad** zajišťuje, že nejdůležitější města (podle populace) jsou zobrazeny jako první, zatímco méně podstatné body mohou být vynechány, když je místo omezené.

## Závěr
Gratulujeme! Nyní znáte několik způsobů, jak **popiskovat mapové prvky** pomocí Aspose.GIS pro .NET – od jednoduchého popiskování bodů po sofistikované, na prvcích založené stylování pro velké datové sady. Experimentujte s halo, rotacemi a pravidly priority, abyste vytvořili mapy, které přesně komunikují to, co vaše publikum potřebuje vidět.

## Často kladené otázky

**Q: Mohu popiskovat prvky pomocí vlastních fontů?**  
A: Ano. Nastavte `FontFamily` a `FontStyle` v konfiguraci `SimpleLabeling` a použijte libovolný nainstalovaný font.

**Q: Je Aspose.GIS kompatibilní s jinými GIS formáty dat?**  
A: Rozhodně. Podporuje GeoJSON, Shapefile, KML, GML a mnoho dalších formátů.

**Q: Jak mohu zacházet s velkými datovými sadami při popiskování?**  
A: Použijte `FeatureBasedConfiguration` k přiřazení priorit a dynamickému upravování velikosti fontu na základě hodnot atributů, jak je ukázáno v příkladu založeném na prvcích.

**Q: Jsou k dispozici pokročilé možnosti umístění popisků?**  
A: Ano. Můžete jemně ladit umístění pomocí `PointLabelPlacement`, upravovat kotevní body, posuny a rotaci.

**Q: Mohu automatizovat generování popisků v dávkovém procesu?**  
A: Samozřejmě. Zabalte kód pro vykreslování mapy do smyčky nebo služby na pozadí a automaticky zpracovávejte více vrstev nebo souborů.

---

**Poslední aktualizace:** 2026-01-15  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
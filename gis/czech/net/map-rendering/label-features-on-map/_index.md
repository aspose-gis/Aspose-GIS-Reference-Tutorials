---
title: Zvládnutí označování funkcí pomocí Aspose.GIS pro .NET
linktitle: Označení prvků na mapě
second_title: Aspose.GIS .NET API
description: Prozkoumejte Aspose.GIS pro .NET a ovládněte umění označování prvků na mapách. Vylepšete své geoprostorové vizualizace bez námahy. #State #GIS
weight: 11
url: /cs/net/map-rendering/label-features-on-map/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zvládnutí označování funkcí pomocí Aspose.GIS pro .NET

## Úvod
Ve světě vizualizace geoprostorových dat hraje označování prvků na mapě zásadní roli při efektivním přenosu informací. Aspose.GIS for .NET poskytuje výkonnou sadu nástrojů, jak toho dosáhnout. V tomto tutoriálu prozkoumáme různé metody označování bodů na mapě pomocí Aspose.GIS a vylepšíme vizualizace vaší mapy o informativní štítky.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Pracovní znalost C# a .NET frameworku.
-  Aspose.GIS pro .NET nainstalován. Můžete si jej stáhnout[tady](https://releases.aspose.com/gis/net/).
- Soubor GeoJSON obsahující bodová data. Pokud jej nemáte, můžete k testování použít vzorový soubor.
## Importovat jmenné prostory
Ujistěte se, že ve svém kódu C# importujete potřebné jmenné prostory pro práci s Aspose.GIS:
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
Nyní si každý příklad rozdělíme do několika kroků ve formátu průvodce krok za krokem.
##  Označení bodů

### Krok 1: Nastavte cestu k adresáři dokumentů:
```csharp
string dataDir = "Your Document Directory";
```
### Krok 2: Vytvořte mapu s jednoduchým symbolem značky:
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Přidejte vektorovou vrstvu a použijte označení
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Vykreslete mapu do souboru SVG
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```
## Stylové značení bodů

Postupujte podle kroků 1 a 2 z předchozího příkladu.

### Krok 1: Přizpůsobte styl označení:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Zbytek kroků zůstává stejný
```
## Označení bodů umístěno

Postupujte podle kroků 1 a 2 z prvního příkladu.
### Krok 2: Přizpůsobte umístění štítku:
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
// Zbytek kroků zůstává stejný
```
## Označení bodů na základě funkce

Postupujte podle kroků 1 a 2 z prvního příkladu.

### Krok 1: Implementujte označování založené na funkcích:
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
        // Načíst populaci z objektu.
        var population = feature.GetValue<int>("population");
        // Velikost písma je vypočítána a je založena na populaci.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // Priorita označení je také založena na populaci.
        // Čím vyšší priorita, tím pravděpodobněji se štítek objeví na výstupním obrázku.
        labeling.Priority = population;
    }
};
// Zbytek kroků zůstává stejný
```
## Závěr
Gratulujeme! Naučili jste se, jak vylepšit své mapové vizualizace označením prvků pomocí Aspose.GIS pro .NET. Experimentujte s různými styly a umístěními a vytvořte působivé mapy přizpůsobené vašim datům.
## Nejčastější dotazy
### Mohu označit prvky pomocí vlastních písem?
Ano, styl a velikost písma si můžete přizpůsobit v konfiguraci štítků.
### Je Aspose.GIS kompatibilní s jinými datovými formáty GIS?
Aspose.GIS podporuje různé geoprostorové formáty, včetně GeoJSON, Shapefile a dalších.
### Jak mohu zpracovat velké soubory dat pro označování?
Aspose.GIS je optimalizován pro výkon, ale zvažte použití konfigurací založených na funkcích k upřednostnění štítků na základě atributů dat.
### Jsou k dispozici pokročilé možnosti umístění štítků?
Ano, umístění štítků můžete doladit pomocí možností, jako je rotace, kotevní body a odsazení.
### Mohu automatizovat generování štítků v dávkovém procesu?
Aspose.GIS můžete integrovat do svých automatizovaných pracovních postupů pro generování štítků v dávce.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: A jellemzők címkézésének elsajátítása az Aspose.GIS segítségével .NET-hez
linktitle: Címke jellemzők a térképen
second_title: Aspose.GIS .NET API
description: Fedezze fel az Aspose.GIS for .NET webhelyet, és sajátítsa el a térképeken a jellemzők címkézésének művészetét. Fokozza a térinformatikai vizualizációkat könnyedén. #Aspose #GIS
weight: 11
url: /hu/net/map-rendering/label-features-on-map/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# A jellemzők címkézésének elsajátítása az Aspose.GIS segítségével .NET-hez

## Bevezetés
térinformatikai adatok megjelenítésének világában a térképen található címkézési jellemzők döntő szerepet játszanak az információ hatékony közvetítésében. Az Aspose.GIS for .NET hatékony eszközkészletet biztosít ennek zökkenőmentes megvalósításához. Ebben az oktatóanyagban a pontok Aspose.GIS segítségével történő felcímkézésének különböző módszereit mutatjuk be, amelyek informatív címkékkel javítják a térkép megjelenítését.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
- C# és .NET keretrendszer gyakorlati ismerete.
-  Aspose.GIS for .NET telepítve. Letöltheti[itt](https://releases.aspose.com/gis/net/).
- Pontadatokat tartalmazó GeoJSON-fájl. Ha nem rendelkezik ilyennel, használhat egy mintafájlt a teszteléshez.
## Névterek importálása
Győződjön meg arról, hogy a C#-kódban importálja az Aspose.GIS-sel való munkához szükséges névtereket:
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
Most bontsuk le az egyes példákat több lépésre, lépésről lépésre útmutató formátumban.
##  Pontok címkézése

### 1. lépés: Állítsa be a dokumentumkönyvtár elérési útját:
```csharp
string dataDir = "Your Document Directory";
```
### 2. lépés: Készítsen térképet egy egyszerű jelölő szimbólummal:
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Adjon hozzá egy vektorréteget, és alkalmazzon címkézést
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Renderje le a térképet SVG fájlba
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```
## Pontok címkézése stílusban

Kövesse az előző példa 1. és 2. lépését.

### 1. lépés: A címkézési stílus testreszabása:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// A többi lépés ugyanaz marad
```
## Pontok címkézése elhelyezve

Kövesse az első példa 1. és 2. lépését.
### 2. lépés: A címke elhelyezésének testreszabása:
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
// A többi lépés ugyanaz marad
```
## Pontcímkézési funkció alapú

Kövesse az első példa 1. és 2. lépését.

### 1. lépés: A funkcióalapú címkézés alkalmazása:
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
        // Népesség lekérése a tereptárgyból.
        var population = feature.GetValue<int>("population");
        // A betűméret kiszámítása a populáción alapul.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // A címke prioritása szintén a populáción alapul.
        // Minél nagyobb a prioritás, annál valószínűbb, hogy címke jelenik meg a kimeneti képen.
        labeling.Priority = population;
    }
};
// A többi lépés ugyanaz marad
```
## Következtetés
Gratulálunk! Megtanulta, hogyan javíthatja térképmegjelenítését az Aspose.GIS for .NET használatával funkciók címkézésével. Kísérletezzen különböző stílusokkal és elhelyezésekkel, hogy lenyűgöző térképeket hozzon létre az adataihoz igazítva.
## GYIK
### Felcímkézhetek funkciókat egyéni betűtípusok használatával?
Igen, testreszabhatja a betűtípust és -méretet a címkézési konfigurációban.
### Az Aspose.GIS kompatibilis más GIS adatformátumokkal?
Az Aspose.GIS különféle térinformatikai formátumokat támogat, beleértve a GeoJSON-t, a Shapefile-t és egyebeket.
### Hogyan kezelhetek nagy adatkészleteket címkézéshez?
Az Aspose.GIS a teljesítményre optimalizált, de fontolja meg a szolgáltatásalapú konfigurációk használatát a címkék adatattribútumok alapján történő priorizálásához.
### Vannak speciális címkeelhelyezési lehetőségek?
Igen, finomhangolhatja a címkék elhelyezését olyan opciókkal, mint az elforgatás, a rögzítési pontok és az eltolások.
### Automatizálhatom a címkegenerálást kötegelt folyamatban?
Természetesen az Aspose.GIS integrálható az automatizált munkafolyamataiba a kötegelt címkegeneráláshoz.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

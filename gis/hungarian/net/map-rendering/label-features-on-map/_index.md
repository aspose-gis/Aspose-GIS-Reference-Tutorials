---
date: 2026-01-15
description: Ismerje meg, hogyan címkézheti a térképi elemeket az Aspose.GIS for .NET
  használatával, egyedi címkestílus-beállításokkal nagy adatkészletek címkézéséhez.
linktitle: Label Features on Map
second_title: Aspose.GIS .NET API
title: Térképfunkciók címkézése az Aspose.GIS for .NET használatával
url: /hu/net/map-rendering/label-features-on-map/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Térképi elemek címkézése az Aspose.GIS for .NET segítségével

## Bevezetés
A térképi elemek címkézése elengedhetetlen a nyers földrajzi adatok tiszta, felhasználóbarát vizualizációkká alakításához. Ebben az útmutatóban megtudja, **hogyan címkézze a térképi elemeket** (az elsődleges kulcsszó) az Aspose.GIS for .NET használatával, felfedezhet egyedi címkestílusokat, és megismerhet olyan technikákat, amelyek nagy adatállományok esetén is működnek. A végére képes lesz informatív szöveget közvetlenül a térképekre helyezni, így azok elemzők és végfelhasználók számára is átfogóbbak lesznek.

## Gyors válaszok
- **Mi a fő osztály a rendereléshez?** `Map` (Aspose.Gis.Rendering)
- **Melyik címkéző osztály ad egyszerű szöveget?** `SimpleLabeling`
- **Stílusozhatom a címkéket (halo, betűtípus, forgatás)?** Igen – a `HaloSize`, `FontStyle` és `Placement` tulajdonságok segítségével
- **Hogyan kezeljem a nagy adatállományokat?** Használja a `FeatureBasedConfiguration`-t, hogy attribútumértékek alapján priorizálja a címkéket
- **Szükségem van licencre?** A próbaverzió fejlesztéshez működik; a termeléshez kereskedelmi licenc szükséges

## Mi a label map features?
A `label map features` azt jelenti, hogy olvasható szöveget (például városneveket, népességi adatokat vagy egyedi azonosítókat) csatolunk geometriai objektumokhoz – pontokhoz, vonalakhoz vagy poligonokhoz – hogy a térkép egy pillantással térbeli és attribútum információkat is közvetítsen.

## Miért használjuk az Aspose.GIS-t a térképi elemek címkézéséhez?
- **Nulla külső függőség** – tiszta .NET könyvtár, nincs szükség natív GIS binárisokra.  
- **Gazdag stíluslehetőségek** – halo, egyedi betűtípusok, forgatás és rögzítési pontok, amelyekkel finomhangolhatja a megjelenést.  
- **Teljesítmény‑tudatos** – beépített feature‑based címkézés, amely lehetővé teszi a legfontosabb címkék priorizálását nagy adatállományok renderelésekor.  
- **Több kimeneti formátum** – SVG, PNG, PDF stb., egységes címkézési eredményekkel.

## Előkövetelmények
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

- C# és a .NET keretrendszer működő ismerete.  
- Az Aspose.GIS for .NET telepítve van. Letöltheti **[itt](https://releases.aspose.com/gis/net/)**.  
- Egy GeoJSON fájl, amely pont adatokat tartalmaz (vagy bármely támogatott vektorformátum).

## Névterek importálása
A C# kódban importálja a szükséges névtereket:

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

Most több címkézési forgatókönyvet fogunk végigjárni, mindegyik az előzőre épül.

## Pontok címkézése – Hogyan címkézzük a pontokat
### 1. lépés: Állítsa be a dokumentumok könyvtárának útvonalát
```csharp
string dataDir = "Your Document Directory";
```

### 2. lépés: Hozzon létre egy térképet egyszerű jelölő szimbólummal
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

Ebben az egyszerű példában **hogyan címkézzük a pontokat** a GeoJSON fájl `name` attribútumával.

## Pontok címkézése stílusosan – Egyedi címkestílus
Kövesse az előző példa 1. és 2. lépését, majd testreszabja a címkézési stílust:

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

A hozzáadott halo és dőlt betűtípus egy **egyedi címkestílust** kölcsönöz a címkéknek, amely kiemelkedik a zsúfolt háttérből.

## Pontok címkézése elhelyezve – Haladó elhelyezési beállítások
Ismét kezdje az első példa 1. és 2. lépésével, majd állítsa be az elhelyezést:

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

Itt szabályozhatja a rögzítési pontokat, eltolásokat és forgatást, így finomhangolt irányítást kap a **pontok címkézéséről** zsúfolt térképrészletekben.

## Pontok címkézése funkció alapúan – Nagy adatállomány címkézése
Sok pont kezelésekor előnyben részesítheti a címkéket egy attribútum, például a népesség alapján. Kövesse az első példa 1. és 2. lépését, majd valósítsa meg a funkció alapú címkézést:

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

Ez a **nagy adatállomány címkézési** stratégia biztosítja, hogy a legfontosabb városok (népesség szerint) először jelenjenek meg, míg a kevésbé fontos pontok elhagyhatók, ha a hely korlátozott.

## Összegzés
Gratulálunk! Most már többféle módot ismer a **térképi elemek címkézésére** az Aspose.GIS for .NET segítségével – az egyszerű pontcímkézéstől a kifinomult, funkció alapú stílusig nagy adatállományok esetén. Kísérletezzen halo-val, forgatással és prioritási szabályokkal, hogy olyan térképeket készítsen, amelyek pontosan azt közvetítik, amit a közönsége látni szeretne.

## Gyakran Ismételt Kérdések

**K: Címkézhetek elemeket egyedi betűtípusokkal?**  
I: Igen. Állítsa be a `FontFamily` és `FontStyle` értékeket a `SimpleLabeling` konfigurációban, hogy bármely telepített betűtípust használhasson.

**K: Az Aspose.GIS kompatibilis más GIS adatformátumokkal?**  
I: Teljesen. Támogatja a GeoJSON, Shapefile, KML, GML és még sok más formátumot.

**K: Hogyan kezelhetem a nagy adatállományokat a címkézéshez?**  
I: Használja a `FeatureBasedConfiguration`-t, hogy priorizálja a címkéket és dinamikusan állítsa a betűméreteket attribútumértékek alapján, ahogy a funkció alapú példában látható.

**K: Elérhetők haladó címkeelhelyezési beállítások?**  
I: Igen. Finomhangolhatja az elhelyezést a `PointLabelPlacement` segítségével, beállítva a rögzítési pontokat, eltolásokat és forgatást.

**K: Automatizálhatom a címkék generálását kötegelt folyamatban?**  
I: Természetesen. A térkép renderelési kódot egy ciklusba vagy háttérszolgáltatásba ágyazva automatikusan feldolgozhat több réteget vagy fájlt.

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
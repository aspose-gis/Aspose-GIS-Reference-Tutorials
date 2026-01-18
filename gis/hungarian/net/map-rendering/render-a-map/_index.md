---
date: 2026-01-18
description: Tanulja meg, hogyan adhat hozzá városokat a térképhez, és hogyan generálhat
  SVG térképet az Aspose.GIS for .NET használatával. Készítsen lenyűgöző vizualizációkat
  gyorsan.
linktitle: Render a Map
second_title: Aspose.GIS .NET API
title: Hogyan adjunk városokat a térképhez az Aspose.GIS for .NET használatával
url: /hu/net/map-rendering/render-a-map/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan adjunk hozzá városokat a térképhez az Aspose.GIS for .NET segítségével

## Bevezetés
Üdvözöljük az izgalmas Aspose.GIS for .NET világában! Ebben a lépésről‑lépésre útmutatóban megtanulja, **hogyan adjon hozzá városokat a térképhez**, és hogyan generáljon magas minőségű SVG kimenetet. Akár asztali irányítópultot, akár web‑alapú GIS portált épít, ez a tutorial megmutatja, hogyan rajzoljon vektor rétegeket, állítsa be a térkép méreteit, és könnyedén töltse be a GeoJSON térképet.

## Gyors válaszok
- **Miről szól ez a tutorial?** Városok hozzáadása a térképhez és exportálása SVG fájlként.  
- **Melyik könyvtár szükséges?** Aspose.GIS for .NET.  
- **Szükségem van licencre?** Elérhető ingyenes próba; licenc szükséges a termeléshez.  
- **Használhatom webalkalmazásokban?** Igen – ugyanaz a kód működik ASP.NET, Blazor és más .NET webkeretekben.  
- **Milyen kimeneti formátumot állít elő?** Egy SVG térkép, amely megjeleníthető böngészőkben vagy tovább szerkeszthető.

## Előkövetelmények
Mielőtt belemerülne a tutorialba, győződjön meg róla, hogy a következő előkövetelmények rendelkezésre állnak:
- Aspose.GIS for .NET könyvtár: Győződjön meg róla, hogy az Aspose.GIS for .NET könyvtár telepítve van. Letöltheti [itt](https://releases.aspose.com/gis/net/).
- Adatfájlok: Készítse elő a tutorialhoz szükséges shapefile‑okat és GeoJSON adatokat. Mintaadatokat a dokumentációban talál, vagy használhatja saját fájljait.
- Fejlesztői környezet: Állítson be .NET fejlesztői környezetet, beleértve egy kódszerkesztőt, például a Visual Studio‑t.

## Névterek importálása
A kezdéshez importálja a szükséges névtereket a .NET projektjébe. Ezek a névterek elengedhetetlenek az Aspose.GIS funkciók használatához.

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

## 1. lépés: A térkép beállítása (térkép méreteinek beállítása)
```csharp
string dataDir = "Your Document Directory";
using (var map = new Map(800, 476))
{
    // Additional code for map setup can be added here.
}
```
Ebben a lépésben egy új térképet inicializálunk 800 pixel szélességgel és 476 pixel magassággal. A méreteket a tervezési igényei szerint módosíthatja.

## 2. lépés: Alaptérkép hozzáadása (vektor réteg rajzolása)
```csharp
var baseMapSymbolizer = new SimpleFill { FillColor = Color.Salmon, StrokeWidth = 0.75 };
map.Add(VectorLayer.Open(dataDir + "basemap.shp", Drivers.Shapefile), baseMapSymbolizer);
```
Itt **vektor réteget rajzolunk** az alaptérképhez shapefile‑ segítségével. Nyugodtan módosíthatja a `SimpleFill` tulajdonságokat, hogy megfeleljenek a vizuális stílusának.

## 3. lépés: Városok hozzáadása a térképhez (városok hozzáadása, GeoJSON térkép betöltése)
```csharp
var citiesSymbolizer = new SimpleMarker() { FillColor = Color.LightBlue };
citiesSymbolizer.FeatureBasedConfiguration = (feature, symbolizer) =>
{
    // Additional configuration logic can be added here.
};
map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), citiesSymbolizer);
```
Ez a lépés betölti a várospont adatokat tartalmazó GeoJSON fájlt, és **hozzáadja a városokat a térképhez**. A `FeatureBasedConfiguration` delegáltat kibővítheti, hogy a városokat népességhez hasonló attribútumok alapján formázza.

## 4. lépés: A térkép renderelése (térkép exportálása SVG‑ként, SVG térkép generálása)
```csharp
map.Render(dataDir + "cities_out.svg", Renderers.Svg);
```
Végül **exportáljuk a térképet SVG fájlként**. Az eredményül kapott `cities_out.svg` megnyitható bármely modern böngészőben vagy vektorgrafikus szerkesztőben.

## Összegzés
Gratulálunk! Sikeresen **hozzáadta a városokat a térképhez**, és generált egy SVG térképet az Aspose.GIS for .NET használatával. Ez a tutorial bemutatta, hogyan állítsa be a térkép méreteit, rajzoljon vektor rétegeket, töltse be a GeoJSON adatokat, és exportálja az eredményt skálázható SVG‑ként – tökéletes mind webes, mind nyomtatási felhasználásra.

## GYIK
### Használhatom az Aspose.GIS for .NET‑et a webalkalmazásaimban?
Igen, az Aspose.GIS for .NET alkalmas asztali és webalkalmazásokra egyaránt.

### Elérhető próba verzió?
Igen, a ingyenes próba verziót [itt](https://releases.aspose.com/) tekintheti meg.

### Hol találok támogatást az Aspose.GIS for .NET‑hez?
Látogassa meg az [Aspose.GIS fórumot](https://forum.aspose.com/c/gis/33) bármilyen segítség vagy kérdés esetén.

### Vásárolhatok ideiglenes licencet rövid távú projektekhez?
Igen, ideiglenes licenc elérhető [itt](https://purchase.aspose.com/temporary-license/).

### Van további tutorial az Aspose.GIS for .NET‑hez?
Igen, tekintse meg a [dokumentációt](https://reference.aspose.com/gis/net/) a teljes körű tutorialok és útmutatókért.

---

**Utolsó frissítés:** 2026-01-18  
**Tesztelve:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
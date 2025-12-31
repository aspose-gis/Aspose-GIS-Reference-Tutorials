---
date: 2025-12-31
description: Ismerje meg, hogyan hozhat létre vektor réteget és állíthatja be a réteg
  térbeli hivatkozási rendszerét az Aspose.GIS for .NET segítségével. Tanulja meg
  a térbeli hivatkozás meghatározását, pontjellemző hozzáadását és az EPSG kód lekérdezését.
linktitle: Set Layer Spatial Reference System
second_title: Aspose.GIS .NET API
title: Vektor réteg létrehozása és a réteg térbeli referenciarendszerének beállítása
url: /hu/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektorréteg létrehozása és a réteg térbeli referenciarendszerének beállítása

## Bevezetés
A Geográfiai Információs Rendszerek (GIS) hatalmas világában az **Aspose.GIS for .NET** egy robusztus és sokoldalú eszköz a fejlesztők számára. Ebben az útmutatóban **vektorréteget hozunk létre**, meghatározzuk annak térbeli referenciáját, ponttípustú elemet adunk hozzá, és lekérdezzük az EPSG kódot – mindezt lépésről‑lépésre, világos útmutatással. Akár tapasztalt GIS mérnök vagy, akár csak most ismerkedsz a témával, ezek a technikák segítenek a shapefile koordináta‑rendszerének helyes beállításában és a térbeli adatok munkafolyamatainak megbízhatóságának növelésében.

## Gyors válaszok
- **Mit jelent a „vektorréteg létrehozása”?** Új GIS réteget (pl. Shapefile) hoz létre, amely pont, vonal vagy poligon geometriákat tud tárolni.  
- **Melyik EPSG kódot használja a példában?** EPSG 26918 (NAD83 / UTM 18N zóna).  
- **Hozzáadhatok ponttípustú elemet a réteg létrehozása után?** Igen – használja a `ConstructFeature()`‑t és adjon hozzá egy `Point` geometriát.  
- **Hogyan kérdezhetem le a réteg CRS‑ét?** Olvassa a `layer.SpatialReferenceSystem.EpsgCode` vagy `.Name` értékét.  
- **Szükség van licencre az Aspose.GIS‑hez?** Elérhető egy ingyenes próba, de a termeléshez licenc szükséges.

## Előfeltételek
Mielőtt elkezdené a gyakorlati részt, győződjön meg, hogy a következő előfeltételek adottak:
- .NET programozási ismeretek.  
- Telepített Visual Studio a gépén.  
- Aspose.GIS for .NET könyvtár, amely letölthető [itt](https://releases.aspose.com/gis/net/).  
- Alapvető tudás a GIS térbeli referenciarendszereiről.

## Névterek importálása
.NET projektjében importálja a szükséges névtereket az Aspose.GIS funkcióinak eléréséhez. Használja a következő kódrészletet:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## 1. lépés: A dokumentum könyvtárának megadása
Adja meg a dokumentum könyvtárának elérési útját. Ez lesz a hely, ahol a térbeli adatfájlok tárolódnak.

```csharp
string dataDir = "Your Document Directory";
```

## 2. lépés: Térbeli referenciák meghatározása és a shapefile koordináta‑rendszerének beállítása
Adja meg a Shapefile útvonalát, és **definiálja a térbeli referenciát** az EPSG kód (26918 ebben a példában) segítségével. Ez a lépés **beállítja a shapefile koordináta‑rendszerét** a réteghez.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## 3. lépés: Vektorréteg létrehozása
Most **hozza létre a vektorréteget** a megadott Shapefile útvonallal, driver típussal (Shapefile) és a korábban definiált térbeli referenciarendszerrel.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

## 4. lépés: Ponttípusú elem hozzáadása a réteghez
Hozzon létre egy új elemet és **adjon hozzá ponttípusú elemet** a geometria (`Point` 60, 24 koordinátákkal) beállításával. Ezután adja hozzá az elemet a vektorréteghez.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

## 5. lépés: Térbeli referenciarendszer információinak lekérdezése (EPSG kód lekérdezése)
Nyissa meg a vektorréteget, és kérdezze le a térbeli referenciarendszer adatait, például az EPSG kódot és az emberi olvasásra alkalmas nevet. Ez bemutatja, hogyan **lekérdezhető az EPSG kód** és hogyan **állítható be a réteg CRS**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

Ismételje meg ezeket a lépéseket a saját felhasználási esetének megfelelően, és hamarosan mesterévé válik a **vektorréteg létrehozása** és a térbeli referenciák kezelése terén az Aspose.GIS for .NET segítségével.

## Gyakori problémák és megoldások
| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| **A réteg nem nyílik meg** | Hibás driver vagy sérült fájlútvonal | Ellenőrizze a `Drivers.Shapefile` értékét, és győződjön meg arról, hogy a `path` egy létező `.shp` fájlra mutat. |
| **Helytelen CRS jelenik meg** | Rossz EPSG kód használata | Ellenőrizze a EPSG kódot egy hiteles forrásból (pl. EPSG.io). |
| **Az elem nem mentődik** | Nem hívja meg a `layer.Add(feature)`‑t a `using` blokkban | Biztosítsa, hogy az `Add` metódus lefusson, mielőtt a réteg eldobásra kerül. |

## Gyakran feltett kérdések
### Az Aspose.GIS kompatibilis más GIS könyvtárakkal?
Igen, az Aspose.GIS jól integrálható más GIS könyvtárakkal, és együtt is használható velük.

### Használhatom az Aspose.GIS‑t asztali és webalkalmazásokhoz egyaránt?
Természetesen! Az Aspose.GIS sokoldalú, és használható mind asztali, mind web‑alapú alkalmazásokban.

### Milyen licencelési lehetőségek állnak rendelkezésre az Aspose.GIS‑hez?
Igen, a licencelési lehetőségeket megtekintheti és megvásárolhatja [itt](https://purchase.aspose.com/buy).

### Van ingyenes próba az Aspose.GIS‑hez?
Természetesen! Ingyenes próba verzió letölthető [itt](https://releases.aspose.com/).

### Hol kaphatok támogatást az Aspose.GIS‑hez kapcsolódó kérdésekhez?
Bármilyen támogatás vagy kérdés esetén látogasson el az [Aspose.GIS fórumra](https://forum.aspose.com/c/gis/33).

## További gyakran feltett kérdések
**K: Hogyan változtathatom meg egy meglévő Shapefile CRS‑ét?**  
V: Nyissa meg a réteget, hozzon létre egy új `SpatialReferenceSystem`‑t a kívánt EPSG kóddal, és rendelje hozzá a `layer.SpatialReferenceSystem`‑hez a mentés előtt.

**K: Hozzáadhatok más geometria típusokat (pl. poligonok) ugyanazzal a megközelítéssel?**  
V: Igen – cserélje a `new Point(x, y)`‑t `new Polygon(...)`‑ra vagy `new LineString(...)`‑ra, ahogy szükséges.

**K: Lehet nagy adatállományokkal hatékonyan dolgozni?**  
V: Használja a streaming API‑kat (`VectorLayer.Create` `FeatureCollection`‑kel) és időben szabadítsa fel a rétegeket a források felszabadításához.

**K: Támogatja az Aspose.GIS a koordinátatranszformációt?**  
V: Igen – használja a `Geometry.Transform(targetSrs)`‑t a geometria újra‑projekciójához különböző térbeli referenciák között.

**K: Mely .NET verziók támogatottak?**  
V: Az Aspose.GIS működik .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7 verziókkal.

## Összegzés
Ebben az útmutatóban megmutattuk, hogyan **hozzunk létre vektorréteget**, definiáljuk annak térbeli referenciáját, **adjunk hozzá ponttípusú elemet**, és **lekérdezzük az EPSG kódot** az Aspose.GIS for .NET segítségével. E lépések elsajátításával magabiztosan állíthatja be a shapefile koordináta‑rendszerét, kezelheti a réteg CRS‑ét, és megbízható GIS alkalmazásokat építhet.

---

**Utolsó frissítés:** 2025-12-31  
**Tesztelve:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
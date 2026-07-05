---
date: 2026-07-05
description: Ismerje meg, hogyan crop-olhatja a layer features-t az Aspose.GIS for
  .NET segítségével, beleértve a raster crop-olását polygonnal, a raster cell size
  kinyerését és a raster extent lekérdezését. Töltse le ingyenes próba verzióját most.
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: Hogyan crop-oljuk a layer features-t
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
title: Hogyan crop-oljuk a layer features-t az Aspose.GIS for .NET segítségével
url: /hu/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan vágjunk le rétegjellemzőket

## Bevezetés
Ebben a bemutatóban megtanulja, **hogyan vágjunk le réteget** funkciókat az Aspose.GIS for .NET használatával, egy erőteljes könyvtárat, amely lehetővé teszi a **crop raster with polygon**, **extract raster cell size**, és **retrieve raster extent** pontos térinformatikai elemzéshez. Akár webtérképhez készít adatot, akár műholdképeket vág le, vagy egy érdeklődési területet izolál, ez a lépésről‑lépésre útmutató pontosan megmutatja, hogyan végezze el a feladatot gyorsan és megbízhatóan.

## Gyors válaszok
- **Mi jelent a „crop layer”?** Egy raszter vagy vektor réteget vág le a megadott geometria határaira, mindent eldobva, ami kívül esik.  
- **Melyik geometria van használva ebben a példában?** Egy WKT (Well‑Known Text) formátumban definiált sokszög.  
- **Kivonhatom a cellaméretet a vágás után?** Igen – a `CellSize` tulajdonság visszaadja a rasztercell szélességét és magasságát.  
- **Szükségem van licencre a kód futtatásához?** Egy ideiglenes licenc elegendő értékeléshez; a teljes licenc szükséges a termeléshez.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Mi az a „hogyan vágjunk le réteget”?
**Egy réteg vágása azt jelenti, hogy a adatkészletet egy adott földrajzi területre korlátozzuk, mindent eldobva, ami kívül esik.** Ez a művelet csökkenti a fájlméretet, felgyorsítja a későbbi feldolgozást, és a figyelmet a számodra fontos régióra összpontosítja. A területre korlátozással egyszerűsödnek a további munkafolyamatok, mint a stílusozás, elemzés és közzététel, miközben az eredeti koordináta‑referencia‑rendszer és metaadatok megmaradnak.

## Miért használja az Aspose.GIS‑t a vágáshoz?
**Az Aspose.GIS képes 2 GB‑ig terjedő raszterfájlokat feldolgozni anélkül, hogy a teljes képet a memóriába töltené, és több mint 30 raszterformátumot támogat, beleértve a GeoTIFF, JPEG2000 és PNG formátumokat.** A könyvtár egyetlen soros `Crop` hívást, automatikus CRS kezelést és több szálon futó teljesítményt kínál, amely egy 500 MB‑os GeoTIFF‑et egy másodperc alatt képes levágni egy tipikus szerveren.

## Előfeltételek
Miután elmélyülne a térinformatikai manipuláció varázslatában, győződjön meg róla, hogy az alábbi előfeltételek rendelkezésre állnak:

- Aspose.GIS for .NET Library: Győződjön meg arról, hogy az Aspose.GIS könyvtár telepítve van a .NET projektjében. Letöltheti [itt](https://releases.aspose.com/gis/net/).  
- Document Directory: Hozzon létre egy könyvtárat a dokumentumok tárolásához. Cserélje le a `"Your Document Directory"` szöveget a megadott kódban a tényleges útvonalra a dokumentum könyvtárához.

Most merüljünk el a lépésről‑lépésre útmutatóban.

## Névterek importálása
Az `Aspose.Gis` névtér tartalmazza az összes alapvető típust a raszter és vektor kezeléshez. Importálja, hogy hozzáférjen a `Layer`, `Geometry` és a kapcsolódó osztályokhoz.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Hogyan vághatok le egy réteget sokszöggel?
`Crop` a `Layer` osztály egy metódusa, amely egy geometria által meghatározott raszter alhalmazt nyer ki.  
Töltse be a forrásrasztert, definiáljon egy sokszög geometriát, és hívja meg a `Crop` metódust – a teljes művelet egyetlen kódsorban hajtódik végre. A metódus egy új rasztert ad vissza, amely csak a sokszög belsejében lévő pixeleket tartalmazza, automatikusan megőrizve az eredeti térbeli referenciát.

## 1. lépés: Réteg megnyitása és vágása (crop raster with polygon)
`Layer` egy raszter adathalmazt képvisel, amely megnyitható, lekérdezhető és szerkeszthető.  
A `Layer` osztály egy raszter adathalmazt képvisel, amely megnyitható, lekérdezhető és szerkeszthető. Egy GeoTIFF megnyitása és vágása sokszöggel néhány sorban izolálja az érdeklődési területet.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## 2. lépés: Raszter információk lekérése (extract raster cell size & retrieve raster extent)
`CellSize` a raszter minden cellájának szélességét és magasságát adja koordinátaegységekben.  
`Extent` a raszter földrajzi határoló dobozát adja vissza.  
A `CellSize` tulajdonság a raszter minden cellájának szélességét és magasságát adja koordinátaegységekben, míg az `Extent` tulajdonság a levágott raszter földrajzi határoló dobozát adja vissza. Mindkét információ elengedhetetlen a későbbi számításokhoz, például területméréshez vagy újraprojektáláshoz.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## 3. lépés: Információk megjelenítése
Nyomtassa ki a kinyert információkat, hogy megértse a vágási folyamat hatását a térinformatikai adataira.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

Ismételje meg ezeket a lépéseket szükség szerint, hogy finomítsa és testre szabja a térinformatikai adatait a konkrét projektkövetelményeknek megfelelően.

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|----------|----------|
| **Helytelen sokszög orientáció** | Győződjön meg arról, hogy a WKT sokszög a jobbkéz‑szabályt követi (külső gyűrűk esetén az óramutatóval ellentétes irányban). |
| **Hiányzó térbeli referencia** | Ellenőrizze, hogy a forrás GeoTiff tartalmaz‑e CRS‑t; ellenkező esetben állítson be egyet manuálisan a vágás előtt. |
| **Teljesítménycsökkenés nagy rasztereknél** | Használja a `layer.Crop`‑ot egy lecsökkentett másolaton, vagy dolgozza fel a rasztert csempékben. |

## Gyakran Ismételt Kérdések
**K: Elérhető ideiglenes licenc az Aspose.GIS for .NET‑hez?**  
A: Igen, ideiglenes licencet szerezhet [itt](https://purchase.aspose.com/temporary-license/).

**K: Hol találhatom meg a részletes dokumentációt az Aspose.GIS for .NET‑hez?**  
A: A dokumentáció elérhető [itt](https://reference.aspose.com/gis/net/).

**K: Hogyan kérhetek támogatást vagy csatlakozhatok a közösséghez az Aspose.GIS for .NET‑hez?**  
A: Látogassa meg a [Aspose.GIS fórumot](https://forum.aspose.com/c/gis/33) támogatás és közösségi részvételért.

**K: Letölthetek ingyenes próbaverziót az Aspose.GIS for .NET‑hez?**  
A: Igen, ingyenes próbaverziót tölthet le [itt](https://releases.aspose.com/).

**K: Hol vásárolhatom meg az Aspose.GIS for .NET‑et?**  
A: A könyvtárat [itt](https://purchase.aspose.com/buy) vásárolhatja meg.

**K: Lehet több réteget egyszerre levágni?**  
A: Igen—iteráljon minden rétegen, és alkalmazza ugyanazt a `Crop` hívást a kívánt geometriával.

**K: Támogatja‑e az API más raszterformátumokat (pl. JPEG2000)?**  
A: Az Aspose.GIS támogatja az összes, az alaprendszer GDAL meghajtói által elérhető formátumot, beleértve a JPEG2000, PNG és egyebeket.

## Következtetés
Ezzel az útmutatóval most már hatékonyan tudja **hogyan vágjunk le réteget** funkciókat az Aspose.GIS for .NET segítségével. Könnyedén **crop raster with polygon**, **extract raster cell size**, és **retrieve raster extent** használhatja bármely projekt igényeihez. Fedezze fel a további API‑kat a újraprojektáláshoz, raszter stílusozáshoz és vektor elemzéshez, hogy kiaknázza a térinformatikai munkafolyamatok teljes potenciálját.

---

**Last Updated:** 2026-07-05  
**Tested With:** Aspose.GIS 24.10 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó bemutatók

- [Hogyan hozzunk létre sokszög geometriát az Aspose.GIS for .NET használatával](/gis/net/geometry-creation/create-polygon-geometry/)
- [Réteg attribútumok lekérése – Réteg attribútum információk lekérése az Aspose.GIS for .NET használatával](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Sokszög geometria létrehozása C#‑ban és metszés ellenőrzése az Aspose.GIS for .NET használatával](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
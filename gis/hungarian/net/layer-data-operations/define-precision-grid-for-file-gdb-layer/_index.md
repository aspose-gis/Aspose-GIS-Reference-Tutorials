---
date: 2025-12-28
description: Ismerje meg, hogyan állíthat be rácsot egy File GDB réteghez az Aspose.GIS
  for .NET használatával, beleértve a réteghez elemek hozzáadását és a koordináta-tartomány
  ellenőrzését.
linktitle: Define Precision Grid for File GDB Layer
second_title: Aspose.GIS .NET API
title: Hogyan állítsuk be a rácsot a File GDB réteghez az Aspose.GIS-ben
url: /hu/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsunk be rácsot a File GDB réteghez az Aspose.GIS-ben

## Bevezetés
Ebben az útmutatóban megtanulja, **hogyan állítsa be a rácsot** egy File Geodatabase (GDB) réteghez az Aspose.GIS for .NET használatával. Egy pontossági rács beállítása segít **ellenőrizni a koordináta-tartományt**, megakadályozza a tartományon kívüli hibákat, és biztosítja, hogy a **réteghez hozzáadott elemek** adatai pontosak és megbízhatóak maradjanak. Lépésről lépésre végigvezetjük, megmagyarázzuk, miért fontosak a beállítások, és bemutatjuk, hogyan kezelje a gyakori buktatókat.

## Gyors válaszok
- **Mit jelent a „rács beállítása”?** Meghatározza a koordináta pontosságát és a GIS réteg érvényes tartományát.  
- **Miért használjunk pontossági rácsot?** Védelmet nyújt az érvénytelen koordináták ellen, és javítja a tárolási hatékonyságot.  
- **Melyik könyvtár biztosítja ezt a funkciót?** Aspose.GIS for .NET.  
- **Szükségem van licencre?** Elérhető próbaverzió; a kereskedelmi licenc szükséges a termeléshez.  
- **Használhatom .NET Core‑dal?** Igen, az Aspose.GIS támogatja a .NET Framework‑öt és a .NET Core‑t is.

## Mi az a pontossági rács és miért kell beállítani?
A pontossági rács olyan paraméterkészlet (origó, skála stb.), amely megmondja a GIS motornak, hogyan kerekítse és tárolja a koordinátaértékeket. A rács definiálásával **automatikusan ellenőrizhető a koordináta-tartomány**, és minden, a rácson kívül eső pont hozzáadása kivételt vált ki – ezáltal már a fejlesztés korai szakaszában **kezelhető a tartományon kívüli** helyzet.

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg róla, hogy a következők telepítve vannak:

1. **Visual Studio** – bármely friss verzió (Community, Professional vagy Enterprise).  
2. **Aspose.GIS for .NET** – letölthető a [weboldalról](https://releases.aspose.com/gis/net/).  
3. **Alapvető C# ismeretek** – kényelmesen kell tudnia .NET konzolos projektek létrehozását.

## Névterek importálása
Először importálja az Aspose.GIS használatához szükséges névtereket:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## Hogyan állítsuk be a rácsot egy File GDB rétegben
Az alábbi lépésről‑lépésre útmutató pontosan megmutatja, hogyan konfigurálja a rácsot, hozza létre a réteget, és biztonságosan **adjon hozzá elemeket a réteghez**.

### 1. lépés: Adathalmaz létrehozása
Először egy új File Geodatabase adathalmazt hozunk létre. Ebben fogja a réteg élni.

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### 2. lépés: Pontossági rács beállításainak meghatározása
Itt adjuk meg a rács paramétereit. Igazítsa az origókat és a skálákat a projekt koordináta‑rendszeréhez.

```csharp
var options = new FileGdbOptions
{
    CoordinatePrecisionGrid = new FileGdbCoordinatePrecisionGrid
    {
        XOrigin = -400,
        YOrigin = -400,
        XYScale = 1e10,
        MOrigin = 0,
        MScale = 1e4,
    },
    EnsureValidCoordinatesRange = true,
};
```

*Az `EnsureValidCoordinatesRange = true` jelző azt mondja az Aspose.GIS‑nek, hogy **ellenőrizze a koordináta‑tartományt** minden hozzáadott elemnél.*

### 3. lépés: Réteg létrehozása a rácssal
Most egy új réteget hozunk létre az adathalmazban, alkalmazva a korábban definiált rács beállításait. A WGS84 térbeli referenciarendszert fogjuk használni.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### 4. lépés: Elemek hozzáadása a réteghez
Két pont elemet hozunk létre. Az első pont a rácson belül helyezkedik el, míg a második szándékosan kívül esik, hogy bemutassa, **hogyan kezeljük a tartományon kívüli** hibákat.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### 5. lépés: Kivételek kezelése tartományon kívüli elemek hozzáadásakor
A második elem hozzáadása kivételt vált ki, mivel X koordinátája (`-410`) kívül esik a definiált rácson. Elkapjuk a kivételt, és egyértelmű üzenetet írunk ki.

```csharp
try
{
    layer.Add(feature);
}
catch (GisException e)
{
    Console.WriteLine(e.Message); // X value -410 is out of valid range.
}
```

### 6. lépés: Takarítás
A `using` utasítások automatikusan lezárják és felszabadítják az adathalmazt és a réteget, biztosítva, hogy minden erőforrás felszabaduljon.

## Gyakori problémák és megoldások
| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| **Kivétel: “X érték … a valid tartományon kívül.”** | A koordináták a pontossági rácson kívül esnek. | Igazítsa az `XOrigin`, `YOrigin` vagy `XYScale` értékeket, hogy lefedjék az adatokat, vagy győződjön meg róla, hogy a bemeneti adatok a definiált tartományon belül vannak. |
| **Az elemek nem jelennek meg a GIS nézőben** | A réteg nincs mentve vagy rossz térbeli referenciát használ. | Ellenőrizze, hogy a `SpatialReferenceSystem.Wgs84` megegyezik a néző CRS‑ével, és hogy a `Dataset.Create` sikeres volt. |
| **M értékek figyelmen kívül maradnak** | `MScale` 0‑ra vagy túl alacsonyra van állítva. | Állítson be egy ésszerű `MScale`‑t (pl. `1e4`), hogy a mérőértékek tárolódjanak. |

## Gyakran Ismételt Kérdések

**Q: Használhatom az Aspose.GIS for .NET‑et más GIS fájlformátumokkal?**  
A: Igen, az Aspose.GIS támogatja a Shapefile, GeoJSON, KML és számos egyéb formátumot.

**Q: Az Aspose.GIS for .NET kompatibilis a .NET Core‑dal?**  
A: Teljesen. A könyvtár működik .NET Framework‑ön, .NET Core‑on és .NET 5/6+ verziókon.

**Q: Végrehajthatok térbeli műveleteket, például bufferelést vagy metszést?**  
A: Igen, az API tartalmaz bufferelésre, metszésre és távolságok számítására szolgáló metódusokat.

**Q: Az Aspose.GIS biztosít koordináta‑transzformációs lehetőségeket?**  
A: Igen, beépített reprojekciós eszközökkel átalakíthatja a geometriákat különböző térbeli referenciarendszerek között.

**Q: Elérhető próba verzió?**  
A: Igen, letölthető egy ingyenes próba a [weboldalról](https://releases.aspose.com/gis/net/).

---

**Utolsó frissítés:** 2025-12-28  
**Tesztelve:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
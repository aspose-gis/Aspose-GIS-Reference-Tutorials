---
date: 2026-01-15
description: Fedezze fel az Aspose.GIS for .NET-et, hogy vektoros réteget hozzon létre
  térbeli hivatkozási rendszerrel. Tanulja meg, hogyan állíthatja be az SRS-t, hozza
  létre a réteget, és kezelje a GIS adatokat. Töltse le most!
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: Vektor réteg létrehozása SRS-sel
url: /hu/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektor réteg létrehozása SRS-sel

## Bevezetés
Aspose.GIS for .NET egy erőteljes könyvtár, amely lehetővé teszi a fejlesztők számára, hogy **vektor réteg** objektumokat hozzanak létre, és zökkenőmentesen dolgozzanak földrajzi információs rendszer (GIS) adatokkal .NET alkalmazásokban. Ebben a tutorialban végigvezetünk a vektor réteg létrehozásán egy térbeli referenciarendszerrel (SRS), megmagyarázzuk, miért érdemes beállítani a térbeli referenciát, és milyen előnyökkel jár ez a valós projektekben. A útmutató végére magabiztosan integrálhatod a GIS képességeket .NET megoldásaidba.

## Gyors válaszok
- **Mi a tutorial fő célja?** A megmutatni, hogyan hozhatunk létre vektor réteget egy megadott SRS-sel az Aspose.GIS for .NET használatával.  
- **Melyik vetületet használja a példában?** World Mercator (EPSG:3395).  
- **Szükségem van licencre a kód futtatásához?** A fejlesztéshez egy ingyenes próba verzió elegendő; a termeléshez kereskedelmi licenc szükséges.  
- **Használhatom ugyanazt a megközelítést más GIS formátumokkal?** Igen, ugyanaz a SRS kezelés alkalmazható a Shapefile, GeoJSON, KML stb. formátumokra.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Mi a vektor réteg és miért állítsuk be a térbeli referenciáját?
Egy **vektor réteg** geometriai elemeket (pontok, vonalak, poligonok) tárol attribútum adatokkal együtt. A **térbeli referenciát** (SRS) hozzárendelve a GIS szoftverek tudják, hogyan értelmezzék ezeket a koordinátákat a Föld felszínén. A helyes SRS beállítása biztosítja a pontos méréseket, a többi réteggel való helyes átfedést és a megbízható térképi megjelenítést.

## Előfeltételek
Mielőtt belevágnánk, győződj meg róla, hogy rendelkezel:

- Alapvető C# és .NET fejlesztési ismeretekkel.  
- Az Aspose.GIS for .NET könyvtár telepítve van. Letöltheted **[itt](https://releases.aspose.com/gis/net/)**.  
- Fejlesztői környezettel (Visual Studio, VS Code vagy bármely C# IDE).  

## Névterek importálása
Győződj meg róla, hogy a szükséges névterek importálva vannak a C# fájlod tetején:

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

## Hogyan állítsuk be a térbeli referenciát (SRS) – 1. lépés
Hozzunk létre egy **vetített térbeli referenciarendszert** a World Mercator vetület példaként való használatával. Ez bemutatja, **hogyan állítsuk be az srs-t** egy réteghez.

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

## Hogyan hozzunk létre réteget – 2. lépés
Most **létrehozunk egy vektor réteget** (egy Shapefile-t), és olyan elemeket adunk hozzá, amelyek a most definiált SRS-t használják. Ez a rész megválaszolja, **hogyan hozható létre réteg** az Aspose.GIS segítségével.

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

> **Pro tip:** Mindig ellenőrizd, hogy a geometria `SpatialReferenceSystem` értéke megegyezik-e a réteg SRS-ével, mielőtt hozzáadnád. A nem egyező SRS értékek `GisException`-t váltanak ki, ahogy fent is látható.

## Térbeli referenciarendszer ellenőrzése – 3. lépés
Végül nyisd meg a réteget, és erősítsd meg, hogy az SRS helyesen lett alkalmazva.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Ha az `IsEquivalent` hívás `true` értéket ad vissza, sikeresen **létrehoztad a vektor réteget** a kívánt térbeli referenciával.

## Gyakori problémák és megoldások
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| `GisException` a funkció hozzáadása során | A geometria más SRS-t használ, mint a réteg | Állítsd be a `feature.Geometry.SpatialReferenceSystem` értékét a réteg SRS-ére a hozzáadás előtt |
| A réteg üresnek jelenik meg GIS szoftverben | A shapefile megfelelő `.prj` fájl nélkül lett létrehozva | Győződj meg róla, hogy a `projectedSrs` objektum át van adva a réteg létrehozásakor |
| Váratlan koordinátaértékek | Helytelen vetületi paraméterek (pl. középpontú meridián) | Ellenőrizd újra az `AddProjectionParameter`-nek átadott paramétereket |

## Gyakran ismételt kérdések
### Az Aspose.GIS kompatibilis minden GIS fájlformátummal?
Az Aspose.GIS számos GIS formátumot támogat, beleértve a Shapefile, GeoJSON, KML és egyebeket. Tekintsd meg a **[dokumentációt](https://reference.aspose.com/gis/net/)** a teljes listáért.

### Használhatom az Aspose.GIS-t webalkalmazásban?
Természetesen! Az Aspose.GIS for .NET sokoldalú, és használható webalkalmazásokban, asztali alkalmazásokban, sőt mobil alkalmazásokban is.

### Hol kaphatok támogatást az Aspose.GIS-hez?
Segítő közösséget találsz az **[Aspose.GIS fórumon](https://forum.aspose.com/c/gis/33)** bármilyen kérdés vagy probléma esetén.

### Elérhető ingyenes próba verzió?
Igen, a Aspose.GIS funkcióit ingyenes próba verzióval **[itt](https://releases.aspose.com/)** fedezheted fel.

### Hogyan vásárolhatok licencet az Aspose.GIS-hez?
Licenc vásárlásához látogasd meg a **[vásárlási oldalt](https://purchase.aspose.com/buy)**.

## Gyakran ismételt kérdések (kiegészítő)

**K: Mi történik, ha egy másik SRS-sel rendelkező geometriát próbálok hozzáadni?**  
A: Az Aspose.GIS `GisException`-t dob. Vagy újraprojektáld a geometriát, vagy biztosítsd, hogy ugyanazt az SRS-t használja, mint a réteg.

**K: Megváltoztathatom egy meglévő réteg SRS-ét?**  
A: Igen, létrehozhatsz egy új réteget a kívánt SRS-sel, és átmásolhatod a elemeket, szükség szerint újraprojektálva őket.

**K: Lehetséges 3D koordinátákkal dolgozni?**  
A: Az Aspose.GIS támogatja a Z‑koordinátákat; egyszerűen használd az olyan geometriai konstruktorokat, amelyek Z értéket is elfogadnak.

**K: A könyvtár automatikusan kezeli a datum transzformációkat?**  
A: Amikor a `Geometry.Transform` segítségével újraprojektálod a geometriákat, az Aspose.GIS elvégzi a szükséges datumeltolást.

**K: Mely .NET verziók vannak hivatalosan tesztelve?**  
A: A könyvtár .NET Framework 4.5+, .NET Core 3.1+, és .NET 5/6/7 verziókkal van tesztelve.

## Következtetés
Most már megtanultad, hogyan **hozz létre vektor réteget** egy egyedi térbeli referenciarendszerrel az Aspose.GIS for .NET használatával. A helyes SRS beállításával, a geometria konzisztens kezelésével és a réteg metaadatainak ellenőrzésével robusztus GIS‑képességekkel rendelkező alkalmazásokat építhetsz, amelyek bármely szabványos GIS szoftverrel interoperálnak.

---

**Last Updated:** 2026-01-15  
**Tested With:** Tesztelve: Aspose.GIS 24.11 for .NET (a legújabb a írás időpontjában)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
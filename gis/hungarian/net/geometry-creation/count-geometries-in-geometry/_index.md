---
title: Geometriák számolása a geometriában az Aspose.GIS segítségével
linktitle: Számolja meg a geometriákat a geometriában
second_title: Aspose.GIS .NET API
description: Ismerje meg, hogyan számolhat geometriákat egy geometriában az Aspose.GIS for .NET használatával. Lépésről lépésre bemutató kódpéldákkal fejlesztőknek.
type: docs
weight: 23
url: /hu/net/geometry-creation/count-geometries-in-geometry/
---
## Bevezetés
Az Aspose.GIS for .NET egy hatékony eszköz azoknak a fejlesztőknek, akik térinformatikai funkciókat szeretnének beépíteni .NET-alkalmazásaikba. Legyen szó térképészeti szoftverről, helyalapú szolgáltatásokról vagy térelemző eszközökről, az Aspose.GIS az Ön igényeinek megfelelő szolgáltatások átfogó készletét kínálja. Ebben az oktatóanyagban megvizsgáljuk, hogyan számolhatunk geometriákat egy geometrián belül az Aspose.GIS for .NET használatával.
## Előfeltételek
Mielőtt belevágna ebbe az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Visual Studio: Győződjön meg arról, hogy a Visual Studio telepítve van a rendszeren.
2. Aspose.GIS for .NET: Töltse le és telepítse az Aspose.GIS for .NET webhelyről[letöltési oldal](https://releases.aspose.com/gis/net/).
3. C# alapismeretek: Ismerkedjen meg a C# programozási nyelv alapjaival.

## Névterek importálása
A kódolás megkezdése előtt importálnia kell a szükséges névtereket az Aspose.GIS funkció eléréséhez.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 2. lépés: Pontgeometria létrehozása
```csharp
Point point = new Point(40.7128, -74.006);
```
 Itt létrehozunk a`Point` geometria szélesség 40,7128 és hosszúság -74,006.
## 3. lépés: Hozzon létre LineString geometriát
```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```
 Ez a lépés létrehozza a`LineString` geometriát, és két pontot ad hozzá.
## 4. lépés: Geometria gyűjtemény létrehozása
```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```
 Ezután létrehozzuk a`GeometryCollection` és add hozzá a korábban létrehozott pont- és vonalgeometriákat.
## 5. lépés: Számolja meg a geometriákat
```csharp
int geometriesCount = geometryCollection.Count;
```
 Ez a lépés megszámolja a geometrián belüli geometriák számát`GeometryCollection`.
## 6. lépés: Jelenítse meg a számlálót
```csharp
Console.WriteLine(geometriesCount); // 2
```
 Végül kinyomtatjuk a geometriák számát, ami ebben az esetben az`2`.

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan számolhatunk geometriákat egy geometrián belül az Aspose.GIS for .NET használatával. Az alábbi lépések követésével könnyedén beépítheti a térinformatikai funkciókat .NET-alkalmazásaiba.
## GYIK
### Az Aspose.GIS for .NET alkalmas asztali és webes alkalmazásokhoz is?
Igen, az Aspose.GIS for .NET zökkenőmentesen használható asztali és webes alkalmazásokban egyaránt.
### Végezhetek térbeli lekérdezéseket az Aspose.GIS for .NET használatával?
Az Aspose.GIS for .NET határozottan támogatja a geometriákon végzett térbeli lekérdezések végrehajtását.
### Az Aspose.GIS for .NET támogatja a különböző GIS fájlformátumokat?
Igen, az Aspose.GIS for .NET GIS-fájlformátumok széles skáláját támogatja, beleértve az SHP-t, a KML-t és a GeoJSON-t.
### Létezik ingyenes próbaverzió az Aspose.GIS for .NET számára?
 Igen, letölthet egy ingyenes próbaverziót a webhelyről[weboldal](https://releases.aspose.com/).
### Hol találok támogatást az Aspose.GIS for .NET számára?
 Támogatást találhat a[Aspose.GIS fórum](https://forum.aspose.com/c/gis/33).
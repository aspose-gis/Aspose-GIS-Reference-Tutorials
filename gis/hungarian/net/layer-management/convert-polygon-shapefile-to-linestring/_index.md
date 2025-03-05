---
title: A Polygon Shapefile konvertálása vonalláncra
linktitle: A Polygon Shapefile konvertálása vonalláncra
second_title: Aspose.GIS .NET API
description: Fedezze fel az Aspose.GIS for .NET erejét, és könnyedén konvertálja a sokszög alakú fájlokat vonalláncokká. Fokozza fel térinformatikai fejlesztését még ma!
type: docs
weight: 18
url: /hu/net/layer-management/convert-polygon-shapefile-to-linestring/
---
## Bevezetés
Ha földrajzi információs rendszerekkel (GIS) dolgozik .NET-ben, az Aspose.GIS egy hatékony könyvtár, amely leegyszerűsítheti a feladatait. Ebben az oktatóanyagban végigvezetjük a Polygon Shapefile vonalláncsá alakításán az Aspose.GIS segítségével. Ez különösen akkor lehet hasznos, ha lineáris jellemzőket kell kinyernie a sokszögű adatokból különböző alkalmazásokhoz, mint például az útvonaltervezés vagy a hálózatelemzés.
## Előfeltételek
Mielőtt belevetnénk magunkat az oktatóanyagba, győződjön meg arról, hogy a helyén van a következők:
-  Aspose.GIS Library: Töltse le és telepítse az Aspose.GIS könyvtárat a[weboldal](https://releases.aspose.com/gis/net/).
- Shapefile adatok: Készítsen sokszög alakzatfájlt az átalakításra. Ha nem rendelkezik ilyennel, kereshet mintaadatokat, vagy létrehozhat sajátot.
- Fejlesztői környezet: Állítsa be .NET fejlesztői környezetét a szükséges eszközökkel.
## Névterek importálása
A C# kódban importálnia kell az Aspose.GIS névtereket a szükséges osztályok és metódusok eléréséhez. Adja hozzá a következő névtereket a kódfájl elejéhez:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## 1. lépés: Állítsa be a dokumentumkönyvtárat
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "Your Document Directory";
```
Cserélje ki a "Saját dokumentumkönyvtár" elemet annak a könyvtárnak az elérési útjával, ahol a Shapefile található.
## 2. lépés: Nyissa meg a Source Shapefile-t
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // A kód többi része ide kerül
}
```
Ez a lépés megnyitja a Polygon Shapefile forrásfájlt olvasásra.
## 3. lépés: Hozd létre a Destination Linestring Shapefile-t
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // A kód többi része ide kerül
}
```
Itt létrehozunk egy új Linestring Shapefile-t a konvertált adatok írásához.
## 4. lépés: Ismétlés a forrásfunkciókon keresztül
```csharp
foreach (Feature sourceFeature in source)
{
    // A kód többi része ide kerül
}
```
Ez a ciklus a forrás Polygon Shapefile egyes jellemzői között iterál.
## 5. lépés: Konvertálja a sokszöget vonallánctá, és írja be a célhelyre
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
Ebben a lépésben minden sokszög jellemző vonalláncmá alakul, és az eredményül kapott vonallánc jellemző a cél Shapefile-ba kerül.
## Következtetés
Ha követi ezeket a lépéseket, az Aspose.GIS for .NET segítségével könnyedén konvertálhat egy sokszög alakzatfájlt vonallánctá. Ez a folyamat új lehetőségeket nyit meg az adatok elemzésében és megjelenítésében a térinformatikai alkalmazásokban.

## GYIK
### Az Aspose.GIS kompatibilis a .NET összes verziójával?
Igen, az Aspose.GIS támogatja a .NET különféle verzióit, így biztosítja a kompatibilitást a fejlesztői környezettel.
### Használhatom az Aspose.GIS-t kereskedelmi projektekhez?
 Igen tudsz. Az Aspose.GIS kereskedelmi projektekben való használatához fontolja meg a licenc megvásárlását[itt](https://purchase.aspose.com/buy).
### Vannak-e példák vagy dokumentáció?
 Igen, átfogó dokumentációt és példákat találhat a webhelyen[dokumentációs oldal](https://reference.aspose.com/gis/net/).
### Létezik próbaverzió?
 Igen, felfedezheti az Aspose.GIS-t egy ingyenes próbaverzióval, ha ellátogat[ez a link](https://releases.aspose.com/).
### Hol kérhetek segítséget vagy támogatást?
 Meglátogatni a[Aspose.GIS fórum](https://forum.aspose.com/c/gis/33) bármilyen segítséggel vagy támogatással kapcsolatos kérdés esetén.
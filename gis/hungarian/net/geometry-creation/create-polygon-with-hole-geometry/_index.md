---
title: Hozzon létre sokszöget furatgeometriával az Aspose.GIS segítségével
linktitle: Hozzon létre sokszöget furatgeometriával
second_title: Aspose.GIS .NET API
description: Ismerje meg, hogyan hozhat létre sokszöget furatgeometriával az Aspose.GIS for .NET használatával. Lépésről lépésre bemutató oktatóprogram kódpéldákkal.
type: docs
weight: 13
url: /hu/net/geometry-creation/create-polygon-with-hole-geometry/
---
## Bevezetés
Ebben az oktatóanyagban egy lyukgeometriával rendelkező sokszög létrehozásának folyamatát mutatjuk be az Aspose.GIS for .NET használatával. Az Aspose.GIS egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy térinformatikai adatokkal dolgozzanak .NET-alkalmazásaikban. 
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Aspose.GIS for .NET Library: Letöltheti innen[itt](https://releases.aspose.com/gis/net/).
2. Fejlesztői környezet: Győződjön meg arról, hogy a Visual Studio vagy bármely más .NET IDE telepített fejlesztői környezete be van állítva.
## Névterek importálása
Először is importálnia kell a szükséges névtereket az Aspose.GIS funkcióinak használatához. Íme, hogyan kell csinálni:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Most folytassuk egy lyukgeometriás sokszög létrehozását az Aspose.GIS for .NET használatával.
## 1. lépés: Hozzon létre sokszögobjektumot
```csharp
Polygon polygon = new Polygon();
```
## 2. lépés: Határozza meg a külső gyűrűt
```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```
## 3. lépés: Határozza meg a belső gyűrűt (lyuk)
```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```
## 4. lépés: Rendelje hozzá a külső gyűrűt, és adja hozzá a belső gyűrűt a sokszöghez
```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```
## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan hozhat létre sokszöget furatgeometriával az Aspose.GIS for .NET használatával. Ez a tudás hasznos lesz különféle térinformatikai alkalmazásokban, ahol az ilyen geometriák elengedhetetlenek.
## GYIK
### 1. Mi az Aspose.GIS?
Az Aspose.GIS egy .NET-könyvtár, amely lehetővé teszi a fejlesztők számára, hogy térinformatikai adatokkal dolgozzanak, lehetővé téve számukra a különböző térinformatikai fájlformátumok létrehozását, olvasását és kezelését.
### 2. Használhatom az Aspose.GIS-t kereskedelmi projektekhez?
 Igen, licenc megvásárlásával használhatja az Aspose.GIS-t személyes és kereskedelmi projektekhez is. Látogatás[itt](https://purchase.aspose.com/buy) további részletekért.
### 3. Elérhető az Aspose.GIS ingyenes próbaverziója?
 Igen, igénybe veheti az Aspose.GIS ingyenes próbaverzióját[itt](https://releases.aspose.com/).
### 4. Hol találok támogatást az Aspose.GIS-hez?
 Az Aspose.GIS támogatását a következő oldalon találja meg[Aspose.GIS fórum](https://forum.aspose.com/c/gis/33).
### 5. Hogyan szerezhetek ideiglenes licencet az Aspose.GIS-hez?
 Ideiglenes licencet szerezhet az Aspose.GIS-hez innen[itt](https://purchase.aspose.com/temporary-license/).
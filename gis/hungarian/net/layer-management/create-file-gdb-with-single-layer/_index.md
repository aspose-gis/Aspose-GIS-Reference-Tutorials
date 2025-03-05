---
title: GDB fájl létrehozása egyrétegű
linktitle: GDB fájl létrehozása egyrétegű
second_title: Aspose.GIS .NET API
description: Használja ki a térinformatikai adatok kezelésében rejlő lehetőségeket a .NET-ben az Aspose.GIS segítségével. Ismerje meg lépésről lépésre, hogyan hozhat létre fájl geoadatbázisokat és rétegeket. Letöltés most!
type: docs
weight: 11
url: /hu/net/layer-management/create-file-gdb-with-single-layer/
---
## Bevezetés
Készen áll arra, hogy térinformatikai alkalmazásait robusztus fájl geoadatbázisokkal és rétegekkel bővítse? Ne keressen tovább az Aspose.GIS-nél a .NET számára. Ebben az oktatóanyagban végigvezetjük a fájl geoadatbázis (GDB) egyetlen rétegű létrehozásának folyamatán az Aspose.GIS for .NET használatával. Használja ki könnyedén a téradat-kezelés és -vizualizáció erejét .NET-alkalmazásaiban.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
1.  Aspose.GIS for .NET: Győződjön meg arról, hogy telepítve van az Aspose.GIS könyvtár. Letöltheti a[Aspose.GIS for .NET letöltési oldal](https://releases.aspose.com/gis/net/).
2. Fejlesztői környezet: Állítson be működő .NET fejlesztői környezetet a gépén.
3. Dokumentumkönyvtár: Válasszon vagy hozzon létre egy könyvtárat a rendszeren, ahol a térinformatikai adatfájlokat tárolni fogja.
## Névterek importálása
kezdéshez importálnia kell a szükséges névtereket a .NET-projektbe. Ezek a névterek hozzáférést biztosítanak az Aspose.GIS funkcióihoz. Adja hozzá a következő sorokat a kódfájl elejéhez:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```
## 1. lépés: Állítsa be a dokumentumkönyvtárat
```csharp
string dataDir = "Your Document Directory";
```
Cserélje ki a „Saját dokumentumkönyvtár” elemet annak a könyvtárnak az elérési útjával, amelyben a térinformatikai fájljait tárolni kívánja.
## 2. lépés: Hozzon létre egy fájl geoadatbázist egyrétegű
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Ez a kódrészlet létrehoz egy Fájl-geoadatbázist egyetlen réteggel, és egy vonalfunkciót ad hozzá.
## 3. lépés: Nyissa meg a Fájl geoadatbázist, és kérje le a rétegadatokat
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Kimenet: Funkciók száma: 1
}
```
Ebben a lépésben megnyitjuk a létrehozott Fájl-geoadatbázist, lekérjük a „réteg” nevű réteget, és kinyomtatjuk a réteg jellemzőinek számát.
## Következtetés
Gratulálunk! Sikeresen létrehozott egy Fájl-geoadatbázist egyetlen réteggel az Aspose.GIS for .NET használatával. Fedezze fel könnyedén alkalmazásaiban a téradat-kezelés hatalmas lehetőségeit.
## Gyakran Ismételt Kérdések
### Használhatom az Aspose.GIS-t .NET-hez a meglévő .NET-projektjeimben?
Igen, az Aspose.GIS for .NET zökkenőmentesen integrálható meglévő .NET-projektjeibe.
### Elérhető az Aspose.GIS .NET-hez próbaverziója?
 Igen, felfedezheti az Aspose.GIS for .NET szolgáltatásait, ha letölti a[ingyenes próbaverzió](https://releases.aspose.com/).
### Hol találom az Aspose.GIS for .NET részletes dokumentációját?
 Utal[dokumentáció](https://reference.aspose.com/gis/net/) átfogó információkért az Aspose.GIS for .NET-ről.
### Hogyan kaphatok támogatást az Aspose.GIS for .NET számára?
 Meglátogatni a[Aspose.GIS fórum](https://forum.aspose.com/c/gis/33) közösségi támogatásért és segítségért.
### Rendelkezésre állnak ideiglenes licencek az Aspose.GIS for .NET számára?
 Igen, megszerezheti a[ideiglenes engedély](https://purchase.aspose.com/temporary-license/) Aspose.GIS for .NET.
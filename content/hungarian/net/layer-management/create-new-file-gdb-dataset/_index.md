---
title: Új fájl létrehozása GDB adatkészlet
linktitle: Új fájl létrehozása GDB adatkészlet
second_title: Aspose.GIS .NET API
description: Fedezze fel az Aspose.GIS for .NET webhelyet, amellyel könnyedén hozhat létre és kezelhet GIS-adatkészleteket. Töltse le most a zökkenőmentes térinformatikai fejlesztéshez. #Aspose #GIS
type: docs
weight: 10
url: /hu/net/layer-management/create-new-file-gdb-dataset/
---
## Bevezetés
térinformatikai fejlesztés területén az Aspose.GIS for .NET kiemelkedik a földrajzi információs rendszer (GIS) adatainak kezelésére és manipulálására szolgáló hatékony eszköztárként. Akár tapasztalt fejlesztő, akár csak most kezdi el a GIS felé vezető utat, ez az oktatóanyag végigvezeti Önt egy új File Geodatabase (GDB) adatkészlet létrehozásának folyamatán az Aspose.GIS for .NET használatával.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
-  Aspose.GIS for .NET: Győződjön meg arról, hogy telepítve van az Aspose.GIS for .NET könyvtár. Letöltheti a[Aspose.GIS for .NET letöltési oldal](https://releases.aspose.com/gis/net/).
- Fejlesztői környezet: Állítsa be fejlesztői környezetét egy kompatibilis IDE-vel, például a Visual Studio-val, és ismerje meg a .NET programozást.
- Dokumentumkönyvtár: Cserélje ki a „Saját dokumentumkönyvtárat” a kódrészletben arra a megfelelő elérési útra, ahol a GDB-adatkészletet tárolni kívánja.
- A C# ismerete: Ez az oktatóanyag feltételezi, hogy ismeri a C# programozási nyelvet.
## Névterek importálása
kezdeti lépésekben importálja a szükséges névtereket, hogy kihasználja az Aspose.GIS funkcióit a .NET-alkalmazásban:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## 1. lépés: Hozzon létre egy új fájlt, GDB-adatkészletet
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Kimenet: 0
    // Folytassa a következő lépésekkel...
}
```
 Magyarázat: Ebben a lépésben egy új GDB adatkészletet hozunk létre a`Dataset.Create` módszer. Megadjuk az elérési utat és az illesztőprogramot (FileGdb) a fájl geoadatbázis létrehozásához. A konzol kimenete megjeleníti a kezdeti rétegszámot, amely ezen a ponton nulla.
## 2. lépés: Layer_1 létrehozása és feltöltése
```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```
Magyarázat: Ez a lépés egy „layer_1” nevű réteg létrehozását jelenti az adatkészleten belül. Meghatározza az egész típusú "érték" nevű attribútumot, és tíz jellemzővel tölti fel a réteget, amelyek mindegyikének pontgeometriája van.
## 3. lépés: Layer_2 létrehozása és feltöltése
```csharp
using (var layer = dataset.CreateLayer("layer_2"))
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
Magyarázat: Itt létrehozunk egy "layer_2" nevű második fóliát, és egyetlen jellemzőt adunk hozzá vonallánc-geometriával.
## 4. lépés: Ellenőrizze a frissített rétegek számát
```csharp
Console.WriteLine(dataset.LayersCount); // Kimenet: 2
```
Magyarázat: Végül ellenőrizzük a frissített rétegek számát a két réteg hozzáadása után. Ebben az esetben a kimenetnek 2-nek kell lennie.
## Következtetés
Gratulálunk! Sikeresen létrehozott egy új fájl GDB adatkészletet, és feltöltötte rétegekkel az Aspose.GIS for .NET használatával. Ez az oktatóanyag alapvető ismereteket nyújt a térinformatikai adatokkal való munkavégzésről .NET környezetben.
## Gyakran Ismételt Kérdések
### K: Használhatom az Aspose.GIS for .NET-t más GIS-könyvtárakkal?
Az Aspose.GIS for .NET egy önálló eszközkészlet; azonban a funkcionalitás javítása érdekében integrálhatja más .NET-könyvtárakba.
### K: Létezik közösségi fórum az Aspose.GIS támogatására?
 Igen, támogatást és vitákat találhat a webhelyen[Aspose.GIS fórum](https://forum.aspose.com/c/gis/33).
### K: Hogyan szerezhetek ideiglenes licencet az Aspose.GIS-hez?
 Meglátogatni a[Ideiglenes jogosítvány](https://purchase.aspose.com/temporary-license/) oldalon talál információkat az ideiglenes engedély megszerzéséről.
### K: Vannak további példák és dokumentációk?
 Fedezze fel a[Aspose.GIS dokumentáció](https://reference.aspose.com/gis/net/) további példákért és részletes információkért.
### K: Hol vásárolhatom meg az Aspose.GIS-t .NET-hez?
 Megvásárolhatja az Aspose.GIS for .NET webhelyet[vásárlási oldal](https://purchase.aspose.com/buy).
---
title: Új Shapefile létrehozása
linktitle: Új Shapefile létrehozása
second_title: Aspose.GIS .NET API
description: Ismerje meg, hogyan hozhat létre új shape fájlt az Aspose.GIS for .NET használatával. Kövesse lépésről lépésre útmutatónkat, és szabadítsa fel a téradat-manipuláció erejét.
type: docs
weight: 12
url: /hu/net/layer-management/create-new-shapefile/
---
## Bevezetés
Ha elmélyül a földrajzi információs rendszerek (GIS) fejlesztésében a .NET segítségével, az Aspose.GIS a legjobb megoldás. Ez a hatékony könyvtár lehetővé teszi a fejlesztők számára, hogy zökkenőmentesen dolgozzanak a téradatokkal, és ebben az oktatóanyagban végigvezetjük Önt az Aspose.GIS for .NET használatával új shapefile létrehozásának folyamatán.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
- A C# programozási nyelv alapvető ismerete.
- A Visual Studio telepítve van a gépedre.
-  Aspose.GIS .NET könyvtárhoz. Letöltheti[itt](https://releases.aspose.com/gis/net/).
## Névterek importálása
Kezdje a szükséges névterek importálásával, hogy kihasználja az Aspose.GIS funkcióit:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## 1. lépés: Állítsa be projektjét
Kezdje egy új C#-projekt létrehozásával a Visual Studióban, és foglalja bele az Aspose.GIS könyvtárat.
## 2. lépés: Határozza meg a dokumentumkönyvtárat
```csharp
string dataDir = "Your Document Directory";
```
Cserélje le a "Saját dokumentumkönyvtárat" arra a tényleges elérési útra, ahová menteni szeretné az új shape-fájlt.
## 3. lépés: Hozzon létre egy VectorLayert
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //attribútumok hozzáadása a funkciók hozzáadása előtt
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Ez a kódszegmens beállítja a vektorréteget, és meghatározza az attribútumokat a szolgáltatásokhoz.
## 4. lépés: Adjon hozzá funkciókat
### 1. eset: Az értékeket egyénileg állítja be
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
### 2. eset: Új értékeket állít be az összes attribútumhoz
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## Következtetés
 Gratulálunk! Sikeresen létrehozott egy új shape fájlt az Aspose.GIS for .NET használatával. Ez az oktatóanyag a projekt beállításának, az attribútumok meghatározásának és a szolgáltatások hozzáadásának alapjait ismertette. A további kutatás során tekintse meg a[dokumentáció](https://reference.aspose.com/gis/net/) fejlett funkciókhoz és funkciókhoz.
## Gyakran Ismételt Kérdések
### K: Használhatom az Aspose.GIS-t más programozási nyelvekkel?
Az Aspose.GIS elsősorban a .NET-et támogatja, de vannak Java-verziók is.
### K: Van ingyenes próbaverzió?
 Igen, hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.aspose.com/).
### K: Hol találok támogatást az Aspose.GIS-hez?
 Meglátogatni a[Aspose.GIS fórum](https://forum.aspose.com/c/gis/33) közösségi támogatásra és beszélgetésekre.
### K: Hogyan szerezhetek ideiglenes engedélyt?
 Szerezze meg ideiglenes engedélyét[itt](https://purchase.aspose.com/temporary-license/).
### K: Hol vásárolhatom meg az Aspose.GIS-t .NET-hez?
 Meg lehet vásárolni a könyvtárat[itt](https://purchase.aspose.com/buy).
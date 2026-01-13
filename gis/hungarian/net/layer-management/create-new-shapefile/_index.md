---
date: 2026-01-13
description: Ismerje meg, hogyan hozhat létre új shapefile‑t az Aspose.GIS for .NET
  segítségével. Ez a lépésről‑lépésre útmutató bemutatja, hogyan definiáljon vektor
  réteget, adjon hozzá dátum attribútumot, és kezelje a térbeli adatokat.
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
title: Új shapefile létrehozása
url: /hu/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Új Shapefile létrehozása

## Bevezetés
Ha a földrajzi információs rendszerek (GIS) fejlesztésével foglalkozik .NET környezetben, az Aspose.GIS az Ön megoldása. Ez a hatékony könyvtár lehetővé teszi a fejlesztők számára, hogy zökkenőmentesen dolgozzanak térbeli adatokkal, és ebben az útmutatóban végigvezetjük, hogyan **hozzunk létre új shapefile-t** az Aspose.GIS for .NET használatával. Meg fogja látni, miért fontos egy vektor réteg definiálása és egy dátum attribútum hozzáadása a robusztus GIS projektekhez.

## Gyors válaszok
- **Ez az útmutató mit tanít?** Hogyan hozzunk létre új shapefile-t, definiáljunk egy vektor réteget, és adjunk hozzá attribútumokat (beleértve egy dátum mezőt).  
- **Melyik könyvtár szükséges?** Aspose.GIS for .NET.  
- **Szükségem van licencre?** Egy ingyenes próba verzió elegendő a tanuláshoz; a termeléshez kereskedelmi licenc szükséges.  
- **Melyik IDE-t használjam?** Visual Studio (bármelyik újabb verzió).  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 10‑15 perc a alap példa esetén.

## Előfeltételek
Mielőtt belekezdenénk az útmutatóba, győződjön meg róla, hogy az alábbi előfeltételek rendelkezésre állnak:
- Alapvető C# programozási nyelvi ismeretek.
- Telepített Visual Studio a gépén.
- Aspose.GIS for .NET könyvtár. Letöltheti [itt](https://releases.aspose.com/gis/net/).

## Névtér importálása
Kezdje a szükséges névterek importálásával, hogy kihasználhassa az Aspose.GIS funkcionalitását:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 1. lépés: Projekt beállítása
Kezdje egy új C# projekt létrehozásával a Visual Studio-ban, és adja hozzá az Aspose.GIS könyvtárat.

## 2. lépés: Dokumentumkönyvtár meghatározása
```csharp
string dataDir = "Your Document Directory";
```
Cserélje le a *Your Document Directory* szöveget a tényleges útvonalra, ahová az új shapefile-t menteni szeretné.

## 3. lépés: VectorLayer létrehozása
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Ez a kódrészlet **definiál egy vektor réteget** és három attribútumot deklarál: egy szövegmezőt (`name`), egy egész szám mezőt (`age`) és egy dátum‑idő mezőt (`dob`). A dátum attribútum hozzáadása kulcsfontosságú a temporális GIS elemzésekhez.

## 4. lépés: Elem hozzáadása
### 1. eset: Értékek egyenkénti beállítása
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
Itt két pontot hozunk létre, minden attribútumot külön-külön állítunk be, majd az elemeket a réteghez adjuk.

### 2. eset: Új értékek beállítása minden attribútumhoz
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
Ebben a megközelítésben egy hívással töltjük fel az összes attribútum értékét egy objektum tömb segítségével – hasznos, ha sok attribútum van.

## Miért fontos ez
A shapefile programozott létrehozása lehetővé teszi az adatcsatornák automatizálását, tesztadatkészletek generálását vagy a GIS kimenet közvetlen integrálását webszolgáltatásokba. Az **shapefile létrehozásának** elsajátításával az Aspose.GIS segítségével teljes kontrollt kap a geometriai elemek, az attribútumséma és a fájlformátum megfelelőség felett.

## Gyakori hibák és tippek
- **Útvonal elválasztók:** Használja a `Path.Combine`-t a platformok közötti kompatibilitás érdekében a karakterlánc összefűzés helyett.  
- **Attribútum sorrend:** A `SetValues` értékeinek sorrendjének meg kell egyeznie az attribútumok hozzáadásának sorrendjével.  
- **Dátumkezelés:** Mindig használja a `DateTimeKind.Utc`-t, ha a GIS adatait időzónák között osztja meg.

## Összegzés
Gratulálunk! Sikeresen létrehozott egy új shapefile-t az Aspose.GIS for .NET használatával. Ez az útmutató lefedte a projekt beállításának, a vektor réteg definiálásának és az elemek hozzáadásának alapjait – beleértve a dátum attribútumot is. Ahogy tovább kutat, tekintse meg a [dokumentációt](https://reference.aspose.com/gis/net/) a fejlett funkciók és lehetőségek megismeréséhez.

## Gyakran Ismételt Kérdések
### K: Használhatom az Aspose.GIS-t más programozási nyelvekkel?
Az Aspose.GIS elsősorban a .NET-et támogatja, de elérhetőek Java verziók is.  

### K: Elérhető ingyenes próba verzió?
Igen, az ingyenes próba verziót [itt](https://releases.aspose.com/) érheti el.  

### K: Hol találok támogatást az Aspose.GIS-hez?
Látogassa meg az [Aspose.GIS fórumot](https://forum.aspose.com/c/gis/33) a közösségi támogatás és a megbeszélések miatt.  

### K: Hogyan szerezhetek ideiglenes licencet?
Szerezze meg az ideiglenes licencet [itt](https://purchase.aspose.com/temporary-license/).  

### K: Hol vásárolhatom meg az Aspose.GIS for .NET-et?
A könyvtárat [itt](https://purchase.aspose.com/buy) vásárolhatja meg.

**Utolsó frissítés:** 2026-01-13  
**Tesztelt verzió:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
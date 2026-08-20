---
date: 2026-06-30
description: Ismerje meg, hogyan hozhat létre shapefile-t az Aspose.GIS for .NET használatával.
  Ez a lépésről‑lépésre útmutató bemutatja, hogyan definiáljon egy vector layer-t,
  adjon hozzá egy date attribute-ot, és kezelje hatékonyan a spatial data-t.
keywords:
- how to create shapefile
- temporal gis shapefile
- Aspose.GIS vector layer
- GIS data automation
linktitle: Új shapefile létrehozása
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create shapefile using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to define a vector layer, add a date attribute, and manage
    spatial data efficiently.
  headline: How to Create Shapefile with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS primarily supports .NET, but there are versions available for
      Java as well.
    question: Can I use Aspose.GIS with other programming languages?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I find support for Aspose.GIS?
  - answer: Get your temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license?
  - answer: You can buy the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hogyan hozzunk létre shapefile-t az Aspose.GIS for .NET segítségével
url: /hu/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Új Shapefile létrehozása

## Bevezetés
Ha a földrajzi információs rendszerek (GIS) fejlesztésével foglalkozik .NET környezetben, az Aspose.GIS az Ön elsődleges megoldása a **shapefile létrehozására** programozott módon. Ez a könyvtár teljes irányítást biztosít a vektoros rétegek, attribútumsémák és fájlformátum‑megfelelőség felett, így percek alatt automatizálhat adatcsővezetékeket vagy generálhat tesztadatkészleteket.

## Gyors válaszok
- **Ez a tutorial mit tanít?** Hogyan hozzunk létre új shapefile‑t, definiáljunk egy vektoros réteget, és adjunk hozzá attribútumokat (beleértve egy dátummezőt).  
- **Melyik könyvtár szükséges?** Aspose.GIS for .NET.  
- **Szükségem van licencre?** A ingyenes próbaverzió tanuláshoz elegendő; a termeléshez kereskedelmi licenc szükséges.  
- **Melyik IDE-t használjam?** Visual Studio (bármelyik friss verzió).  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 10‑15 perc a alap példához.

## Hogyan hozható létre shapefile az Aspose.GIS for .NET segítségével?
Töltse be az Aspose.GIS könyvtárat, állítsa be a kimeneti mappát, hozza létre a `VectorLayer`‑t, definiálja az attribútumokat, és adjon hozzá jellemzőket – ez a teljes munkafolyamat kevesebb, mint 30 C# sorban megírható. A könyvtár automatikusan kezeli a geometria létrehozását, az attribútumok típusozását és a fájlírást, így nem kell alacsony szintű Shapefile specifikációkat kezelnie.

## Előfeltételek
Mielőtt belekezdenénk a tutorialba, győződjön meg róla, hogy a következő előfeltételek rendelkezésre állnak:
- Alapvető C# programozási nyelvi ismeretek.  
- Visual Studio telepítve van a gépén.  
- Aspose.GIS for .NET könyvtár. Letöltheti [itt](https://releases.aspose.com/gis/net/).

## Névterek importálása
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
Cserélje le a *Your Document Directory* szöveget a tényleges útvonalra, ahová az új shapefile‑t menteni szeretné.

## 3. lépés: VectorLayer létrehozása
`VectorLayer` osztály egyetlen shapefile réteget képvisel, amely geometriát és attribútum adatokat tárol.  
Ebben a lépésben definiálunk egy vektoros réteget, és három attribútumot deklarálunk: egy szövegmezőt (`name`), egy egész szám mezőt (`age`) és egy dátum‑idő mezőt (`dob`). A dátum attribútum hozzáadása kulcsfontosságú a **temporális GIS shapefile** elemzésekhez.

```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```

## 4. lépés: Jellemzők hozzáadása
### Eset 1: Értékek egyenkénti beállítása
`SetValues` metódus az attribútum értékeket rendeli egy jellemzőhöz a definiálás sorrendjében.  
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
Itt két pontot hozunk létre, minden attribútumot külön-külön állítunk be, majd a jellemzőket a réteghez adjuk.

### Eset 2: Új értékek beállítása minden attribútumhoz
Alternatívaként az összes attribútum értéket egyszerre adhatja meg a `SetValues` objektum tömb használatával.  
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
Ebben a megközelítésben egy hívással töltjük fel az összes attribútum értékét egy objektum tömb segítségével – hasznos, ha sok attribútum van.

## Miért fontos ez?
A shapefile programozott létrehozása lehetővé teszi adatcsővezetékek automatizálását, tesztadatkészletek generálását, vagy a GIS kimenet közvetlen beágyazását webszolgáltatásokba. Az Aspose.GIS **30+ vektor és raszter formátumot** támogat, és több száz oldalas shapefile‑okat képes írni anélkül, hogy a teljes fájlt memóriába töltené, így gyors és skálázható megoldást nyújt.

## Gyakori hibák és tippek
- **Útvonal elválasztók:** Használja a `Path.Combine`‑t a platformok közötti kompatibilitás érdekében a karakterlánc összefűzés helyett.  
- **Attribútum sorrend:** A `SetValues` értékeinek sorrendjének meg kell egyeznie az attribútumok hozzáadásának sorrendjével.  
- **Dátumkezelés:** Mindig használja a `DateTimeKind.Utc`‑t, ha a GIS adatait időzónák között osztja meg.

## Összegzés
Gratulálunk! Sikeresen létrehozott egy új shapefile‑t az Aspose.GIS for .NET segítségével. Ez a tutorial bemutatta a projekt beállításának, egy vektoros réteg definiálásának és a jellemzők hozzáadásának alapjait – beleértve a dátum attribútumot is. Ahogy tovább mélyed, tekintse meg a [dokumentációt](https://reference.aspose.com/gis/net/) a haladó funkciók és lehetőségek megismeréséhez.

## Gyakran Ismételt Kérdések
**Q: Használhatom az Aspose.GIS‑t más programozási nyelvekkel?**  
A: Az Aspose.GIS elsősorban .NET-et támogat, de elérhetők Java verziók is.  

**Q: Elérhető ingyenes próbaverzió?**  
A: Igen, az ingyenes próbaverziót [itt](https://releases.aspose.com/) érheti el.  

**Q: Hol találok támogatást az Aspose.GIS‑hez?**  
A: Látogassa meg az [Aspose.GIS fórumot](https://forum.aspose.com/c/gis/33) a közösségi támogatásért és megbeszélésekért.  

**Q: Hogyan szerezhetek ideiglenes licencet?**  
A: Ideiglenes licencet [itt](https://purchase.aspose.com/temporary-license/) kaphat.  

**Q: Hol vásárolhatom meg az Aspose.GIS for .NET‑et?**  
A: A könyvtárat [itt](https://purchase.aspose.com/buy) vásárolhatja meg.  

**Utolsó frissítés:** 2026-06-30  
**Tesztelve:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose

## Kapcsolódó tutorialok

- [Réteg attribútumok lekérése – Réteg attribútum információk lekérése az Aspose.GIS for .NET segítségével](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Vektoros réteg létrehozása és a réteg térbeli referencia rendszerének beállítása](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Vektoros réteg létrehozása File GDB-ben – Aspose.GIS .NET tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
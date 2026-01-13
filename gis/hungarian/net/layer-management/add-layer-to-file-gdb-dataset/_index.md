---
date: 2026-01-13
description: Ismerje meg, hogyan adhat hozzá réteget egy File GDB adathalmazhoz az
  Aspose.GIS használatával, a WGS84 térreferenciával. Kövesse ezt a lépésről‑lépésre
  útmutatót a réteg hozzáadásához a GDB-hez .NET-ben.
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: térbeli referencia wgs84 – Réteg hozzáadása GDB-hez az Aspose.GIS segítségével
url: /hu/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# spatial reference wgs84 – Réteg hozzáadása GDB-hez az Aspose.GIS használatával

## Bevezetés
Készen állsz arra, hogy felgyorsítsd GIS munkafolyamataidat az Aspose.GIS for .NET segítségével? Ebben az útmutatóban megtanulod, **hogyan adj hozzá egy réteget egy File GDB adathalmazhoz**, miközben a **spatial reference wgs84** koordináta‑rendszerrel dolgozol. Lépésről lépésre végigvezetünk, a adatkönyvtár előkészítésétől az újonnan létrehozott réteg ellenőrzéséig, hogy magabiztosan manipulálhasd a földrajzi adatokat.

## Gyors válaszok
- **Melyik a fő koordináta‑rendszer?** spatial reference wgs84 (WGS 84)  
- **Melyik könyvtár biztosítja az API‑t?** Aspose.GIS for .NET  
- **Szükségem van licencre a teszteléshez?** Igen – elérhető egy ideiglenes Aspose licenc.  
- **Hozzáadhatok attribútumokat az új réteghez?** Természetesen, bármennyi jellemző attribútumot definiálhatsz.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## Mi az a spatial reference wgs84?
A spatial reference wgs84 (World Geodetic System 1984) a legelterjedtebb földrajzi koordináta‑rendszer. Szélességi és hosszúsági fokokat definiál, és alapértelmezett CRS‑ként szolgál számos GIS adathalmaz számára, beleértve azt is, amelyet ebben az útmutatóban létrehozunk.

## Miért használjuk az Aspose.GIS‑t réteg hozzáadásához?
- **Nincs külső függőség:** Kész, tiszta .NET kóddal működik.  
- **Teljes kontroll a séma felett:** Egyedi attribútumokat és geometriai típusokat definiálhatsz.  
- **Keresztplatformos:** Kompatibilis Windows, Linux és macOS futtatókörnyezetekkel.  
- **Robusztus licencelés:** Ideiglenes licencek lehetővé teszik a gyors értékelést a kötelezettségvállalás előtt.

## Előfeltételek
Mielőtt elkezdenéd, győződj meg róla, hogy rendelkezel:

- Aspose.GIS for .NET Library: Töltsd le és telepítsd a könyvtárat a [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/) oldalról.  
- Document Directory: Hozz létre egy dedikált mappát a gépeden a GIS fájlok tárolásához.

## Namespace‑ek importálása
Add the required `using` statements to your C# project so you can access Aspose.GIS classes:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 1. lépés: Könyvtár másolása
Először másold meg azt a mappát, amely az eredeti GDB adathalmazt tartalmazza. A másolat megőrzése védi a forrásadatokat a kísérletezés során.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## 2. lépés: Adathalmaz megnyitása és a létrehozási képesség ellenőrzése
Nyisd meg az újonnan másolt adathalmazt, és erősítsd meg, hogy képes új rétegeket létrehozni. A `CanCreateLayers` tulajdonságnak **True** értéket kell visszaadnia.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## 3. lépés: Új réteg létrehozása és feltöltése spatial reference wgs84 használatával
Most létrehozunk egy **data** nevű réteget, és kifejezetten beállítjuk a térbeli hivatkozását **Wgs84**‑re. Emellett hozzáadunk egy egyszerű **Name** attribútumot, és egy pont jellemzőt illesztünk be.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## 4. lépés: Hozzáadott réteg megnyitása és ellenőrzése
Végül nyisd meg a most létrehozott réteget, és ellenőrizd a tartalmát. A konzol azt mutatja, hogy a réteg egy jellemzőt tartalmaz, és a **Name** attribútum megegyezik a beállított értékkel.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Gyakori problémák és tippek
- **Helytelen útvonal:** Győződj meg róla, hogy a `dataDir` útvonalelválasztóval (`/` vagy `\`) végződik, hogy a összefűzött karakterláncok érvényes fájlutakat alkossanak.  
- **Licenc hibák:** Ha licencfigyelmeztetéseket látsz, alkalmazz egy ideiglenes licencet az Aspose portálról a kód futtatása előtt.  
- **CRS eltérés:** Amikor később egy másik GIS eszközzel nyitod meg a réteget, ellenőrizd, hogy az eszköz felismeri‑e a WGS 84 (EPSG:4326) koordináta‑rendszert.

## Gyakran ismételt kérdések
### K: Használhatom az Aspose.GIS for .NET‑et más GIS könyvtárakkal?
Az Aspose.GIS for .NET úgy lett tervezve, hogy önállóan működjön, de más könyvtárakkal is integrálható a funkcionalitás bővítése érdekében.  

### K: Elérhető‑e ideiglenes licenc tesztelési célokra?
Igen, ideiglenes licencet szerezhetsz a [linkről](https://purchase.aspose.com/temporary-license/) teszteléshez és értékeléshez.  

### K: Milyen térbeli hivatkozási rendszereket támogat az Aspose.GIS for .NET?
Az Aspose.GIS for .NET számos térbeli hivatkozási rendszert támogat, ami rugalmasságot biztosít a földrajzi adatok kezelésében.  

### K: Hozzájárulhatok az Aspose.GIS közösséghez?
Természetesen! Csatlakozz a beszélgetésekhez és oszd meg tapasztalataidat az [Aspose.GIS fórumon](https://forum.aspose.com/c/gis/33).  

### K: Hol találhatom meg az Aspose.GIS for .NET részletes dokumentációját?
Tekintsd meg a részletes dokumentációt [itt](https://reference.aspose.com/gis/net/), ahol alapos információkat találsz az Aspose.GIS for .NET‑ről.  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Utoljára frissítve:** 2026-01-13  
**Tesztelt verzió:** Aspose.GIS for .NET (latest stable version)  
**Szerző:** Aspose
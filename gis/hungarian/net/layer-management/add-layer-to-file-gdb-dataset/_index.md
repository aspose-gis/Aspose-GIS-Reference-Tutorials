---
date: 2026-06-30
description: Tanulja meg, hogyan adhat hozzá réteget egy File GDB adathalmazhoz az
  Aspose.GIS segítségével WGS84 térbeli hivatkozással. Kövesse ezt a lépésről‑lépésre
  útmutatót a réteg .NET‑ben történő hozzáadásához.
keywords:
- how to add layer
- spatial reference wgs84
- Aspose.GIS .NET
- File GDB dataset
linktitle: Réteg hozzáadása File GDB adathalmazhoz
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to add layer to a File GDB dataset using Aspose.GIS with
    spatial reference WGS84. Follow this step‑by‑step guide to add a layer in .NET.
  headline: How to Add Layer to File GDB Dataset with spatial reference WGS84 using
    Aspose.GIS
  type: TechArticle
- questions:
  - answer: spatial reference wgs84 (WGS 84)
    question: What is the primary coordinate system used?
  - answer: Aspose.GIS for .NET
    question: Which library provides the API?
  - answer: Yes – a temporary Aspose license is available.
    question: Do I need a license for testing?
  - answer: Absolutely, you can define any number of feature attributes.
    question: Can I add attributes to the new layer?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hogyan adjunk hozzá réteget egy File GDB adathalmazhoz WGS84 térbeli hivatkozással
  az Aspose.GIS használatával
url: /hu/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# hogyan adjunk hozzá réteget – térbeli referenciavonal wgs84 az Aspose.GIS-szel

## Bevezetés
Készen állsz arra, hogy felgyorsítsd a GIS munkafolyamatodat az Aspose.GIS for .NET segítségével? Ebben az oktatóanyagban megtanulod, hogyan **adjunk hozzá réteget** egy File GDB adathalmazhoz, miközben a **térbeli referenciavonal WGS84** koordináta‑rendszerrel dolgozol. Lépésről‑lépésre végigvezetünk, a adatkönyvtár előkészítésétől az új réteg validálásáig, hogy magabiztosan és hatékonyan manipulálhasd a földrajzi adatokat.

## Gyors válaszok
- **Mi a főként használt koordináta‑rendszer?** spatial reference wgs84 (WGS 84)  
- **Melyik könyvtár biztosítja az API-t?** Aspose.GIS for .NET  
- **Szükségem van licencre a teszteléshez?** Igen – egy ideiglenes Aspose licenc elérhető.  
- **Hozzáadhatok attribútumokat az új réteghez?** Természetesen, tetszőleges számú attribútumot definiálhat a réteghez.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## Mi a térbeli referenciavonal wgs84?
A spatial reference wgs84 (World Geodetic System 1984) a legszélesebb körben használt földrajzi koordináta‑rendszer. Meghatározza a szélességet és hosszúságot fokban, és alapértelmezett CRS‑ként szolgál sok GIS adathalmaz számára, beleértve azt is, amelyet ebben az útmutatóban létrehozunk.

## Miért használjuk az Aspose.GIS‑t réteg hozzáadásához?
Töltsd be a GIS adataidat külső binárisok nélkül, és tartsd teljes kontroll alatt a séma definíciót. Az Aspose.GIS támogat **40+ spatial reference systems**, képes **2 GB**‑nál nagyobb fájlok feldolgozására anélkül, hogy az egész adathalmazt a memóriába töltené, és Windows, Linux, valamint macOS rendszereken fut. Ez megbízható, platformfüggetlen megoldássá teszi vállalati szintű GIS automatizáláshoz.

## Előfeltételek
- Aspose.GIS for .NET Library: Töltsd le és telepítsd a könyvtárat a [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Document Directory: Hozz létre egy dedikált mappát a gépeden a GIS fájlok tárolásához.  
- Egy ideiglenes Aspose licenc (opcionális értékeléshez) – lásd az alábbi GYIK‑ot a letöltési hivatkozásért.

## Névterek importálása
Add the required `using` statements to your C# project so you can access Aspose.GIS classes:

*Nem szükséges kódrészlet itt; egyszerűen add hozzá a következő sorokat a fájlod tetejéhez:*

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
using Aspose.Gis.SpatialReference;
```

## 1. lépés: Könyvtár másolása
**Definition anchor:** A File GDB dataset egy mappaalapú ESRI geodatabase, amely térbeli adatokat tárol fájlok halmazában.  
Először másold meg a mappát, amely az eredeti GDB adathalmazt tartalmazza. A másolat megtartása védi a forrásadatokat a kísérletezés során.

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

## 2. lépés: Adathalmaz megnyitása és a létrehozási képesség ellenőrzése
`Dataset` egy gyűjteményt jelent a File GDB‑ben tárolt GIS rétegekből. Nyisd meg az újonnan másolt adathalmazt, és erősítsd meg, hogy képes új rétegeket létrehozni. A `CanCreateLayers` tulajdonságnak **True** értéket kell visszaadnia. **`CanCreateLayers` egy logikai (boolean) tulajdonság, amely azt jelzi, hogy az adathalmaz támogatja‑e új rétegek létrehozását.**

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## 3. lépés: Új réteg létrehozása és feltöltése spatial reference wgs84 használatával
Most létrehozunk egy **data** nevű réteget, és kifejezetten beállítjuk a térbeli referenciáját **Wgs84**‑ra. Emellett hozzáadunk egy egyszerű attribútumot **Name** néven, és egy pont objektumot illesztünk be. **`CreateLayer` egy új réteget hoz létre az adathalmazban a megadott névvel és térbeli referenciával.** **`SpatialReference` a réteg által használt koordináta‑rendszert jelöli.** **`Feature` egy egyedi földrajzi objektum (pont, vonal vagy poligon), amely egy rétegben tárolódik.**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## 4. lépés: Hozzáadott réteg megnyitása és ellenőrzése
Végül nyisd meg a most létrehozott réteget, és ellenőrizd a tartalmát. A konzol azt mutatja, hogy a réteg egy feature‑t tartalmaz, és a **Name** attribútum megegyezik a beállított értékkel. **`Layer.Open` meglévő réteget nyit meg olvasásra vagy szerkesztésre.** Ez megerősíti, hogy a réteg helyesen lett hozzáadva, és a térbeli referenciája WGS84.

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

## Hogyan adjunk hozzá réteget egy File GDB adathalmazhoz?
Töltsd be az adathalmazt, hívd meg a `CreateLayer` metódust a kívánt névvel és térbeli referenciával, definiáld az attribútum sémát, majd illessz be funkciókat (features). Mindez néhány Aspose.GIS metódushívással elvégezhető, és az API automatikusan kezeli a fájlzárolást és a séma validálását. A folyamat biztosítja, hogy az új réteg megfeleljen az adathalmaz térbeli referenciájának, hogy az attribútumdefiníciók a réteg sémájában legyenek tárolva, és hogy az adat bármely, a File GDB‑t támogató GIS szoftverrel elérhető legyen.

## Gyakori problémák és tippek
- **Helytelen útvonal:** Győződj meg róla, hogy a `dataDir` útvonalelválasztóval (`/` vagy `\`) végződik, hogy az összefűzött karakterláncok érvényes fájlutakat alkossanak.  
- **Licenc hibák:** Ha licencfigyelmeztetéseket látsz, alkalmazz egy ideiglenes licencet az Aspose portálról a kód futtatása előtt.  
- **CRS eltérés:** Amikor később egy másik GIS eszközzel nyitod meg a réteget, ellenőrizd, hogy az eszköz felismeri‑e a WGS 84 (EPSG:4326) koordináta‑rendszert.  
- **Nagy adathalmazok:** 1 GB‑nál nagyobb adathalmazok esetén fontold meg a `Dataset.OpenReadOnly` használatát a memóriafogyasztás csökkentése érdekében.

## Gyakran feltett kérdések
### K: Használhatom az Aspose.GIS for .NET-et más GIS könyvtárakkal?
A: Igen, az Aspose.GIS önállóan működik, de kombinálható olyan könyvtárakkal, mint a GDAL vagy a NetTopologySuite a fejlett feldolgozáshoz.

### K: Elérhető ideiglenes licenc tesztelési célokra?
A: Igen, ideiglenes licencet szerezhetsz [itt](https://purchase.aspose.com/temporary-license/) teszteléshez és értékeléshez.

### K: Milyen térbeli referenciarendszereket támogat az Aspose.GIS for .NET?
A: Aspose.GIS támogat több mint **40 EPSG kódot**, beleértve a népszerű rendszereket, mint a WGS84 (EPSG:4326), Web Mercator (EPSG:3857), és NAD83 (EPSG:4269). Fedezd fel a részletes dokumentációt [here](https://reference.aspose.com/gis/net/).

### K: Hozzájárulhatok az Aspose.GIS közösséghez?
A: Természetesen! Csatlakozz a beszélgetésekhez és oszd meg tapasztalataidat a [Aspose.GIS fórumon](https://forum.aspose.com/c/gis/33).

### K: Hol találom az Aspose.GIS for .NET részletes dokumentációját?
A: Fedezd fel a részletes dokumentációt [here](https://reference.aspose.com/gis/net/) az összes osztály, metódus és legjobb gyakorlat mélyreható információiért.

---

**Legutóbb frissítve:** 2026-06-30  
**Tesztelve ezzel:** Aspose.GIS for .NET (latest stable version)  
**Szerző:** Aspose

{{< blocks/products/products-backtop-button >}}

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Kapcsolódó oktatóanyagok

- [File Geodatabase .NET adathalmaz létrehozása Aspose.GIS-szel](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Vektor réteg létrehozása File GDB-ben – Aspose.GIS .NET oktatóanyag](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [File GDB adathalmaz létrehozása és toleranciák beállítása egy réteghez](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
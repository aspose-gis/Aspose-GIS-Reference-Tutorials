---
date: 2026-04-24
description: Ismerje meg, hogyan hozhat létre fájlgeoadatbázist, és állíthat be pontossági
  rácsot egy File GDB réteghez az Aspose.GIS for .NET használatával, beleértve a réteghez
  elemek hozzáadását és a koordináta-tartomány ellenőrzését.
keywords:
- create file geodatabase
- handle out of range
- add features layer
- configure coordinate grid
- validate coordinate range
linktitle: Pontossági rács meghatározása a File GDB réteghez
second_title: Aspose.GIS .NET API
title: Fájl geoadatbázis létrehozása és rács beállítása a GDB réteghez (Aspose.GIS)
url: /hu/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk be a rácsot a File GDB réteghez az Aspose.GIS-ben

## Bevezetés
Ebben az oktatóanyagban **file geodatabase** objektumokat hozunk létre, és megtanuljuk, hogyan **állítsuk be a rácsot** egy File Geodatabase (GDB) réteghez az Aspose.GIS for .NET használatával. Egy pontossági rács definiálása lehetővé teszi a **koordináta-tartomány ellenőrzését**, megakadályozza a tartományon kívüli hibákat, és garantálja, hogy bármely **réteghez funkciók hozzáadása** művelet pontosan tárolja az adatokat. Lépésről‑lépésre végigvezetünk, elmagyarázzuk, miért fontos minden beállítás, és megmutatjuk, hogyan **kezelhetjük a tartományon kívüli** helyzeteket elegánsan.

## Gyors válaszok
- **Mi jelent a “set grid”?** A koordináta pontosságát és a GIS réteg érvényes tartományát határozza meg.  
- **Miért használjunk pontossági rácsot?** Védi az adatokat az érvénytelen koordinátáktól és javítja a tárolási hatékonyságot.  
- **Melyik könyvtár biztosítja ezt a funkciót?** Aspose.GIS for .NET.  
- **Szükségem van licencre?** Próbaverzió elérhető; a termeléshez kereskedelmi licenc szükséges.  
- **Használhatom .NET Core‑dal?** Igen, az Aspose.GIS támogatja a .NET Framework‑ot és a .NET Core‑t.

## Mi az a pontossági rács és miért állítjuk be?
A pontossági rács egy paraméterkészlet (origó, skála stb.), amely megmondja a GIS motornak, hogyan kerekítse és tárolja a koordinátaértékeket. A rács konfigurálásával automatikusan **ellenőrizheted a koordináta-tartományt**, és minden, a rácson kívül eső pont beszúrási kísérlet kivételt vált ki—segítve a **tartományon kívüli** helyzetek korai kezelését a fejlesztés során.

## Miért hozzunk létre File Geodatabase‑t pontossági rácssal?
A file geodatabase létrehozása egy hordozható, nagy teljesítményű tárolót biztosít vektoradatok számára. Pontossági rács hozzáadása a létrehozáskor biztosítja, hogy:

- **Következetes adatminőség** – minden funkció ugyanazt a numerikus pontosságot követi.  
- **Gyorsabb indexelés** – a motor hatékonyabban tudja tárolni a koordinátákat.  
- **Korai hibafelismerés** – a tartományon kívüli koordináták még a dataset sérülése előtt elkapásra kerülnek.

## Előkövetelmények
Mielőtt elkezdjük, győződj meg róla, hogy a következők telepítve vannak:

1. **Visual Studio** – bármelyik friss verzió (Community, Professional vagy Enterprise).  
2. **Aspose.GIS for .NET** – töltsd le a [weboldalról](https://releases.aspose.com/gis/net/).  
3. **Alap C# ismeretek** – kényelmesen kell tudnod .NET konzolos projektek létrehozását.

## Általános felhasználási esetek
- **Mezői adatgyűjtés**, ahol a GPS eszközök kissé a tervezett kiterjesztésen kívül eső koordinátákat generálhatnak.  
- **Adatmigráció** régi rendszerekből, amelyek eltérő koordináta-pontosságot használtak.  
- **Automatizált ETL csővezetékek**, amelyeknek a GIS adatbázisba betöltés előtt biztosítaniuk kell a térbeli integritást.

## Névterek importálása
First, import the namespaces required for working with Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## Hogyan konfiguráljuk a koordináta rácsot egy File GDB rétegben
Az alábbi lépésről‑lépésre útmutató pontosan bemutatja, hogyan konfiguráljuk a rácsot, hozzunk létre egy réteget, és biztonságosan **funkciókat adjunk a réteghez**.

### 1. lépés: Adathalmaz létrehozása
Először egy új File Geodatabase adathalmazt hozunk létre. Ebben lesz a réteg.

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### 2. lépés: Pontossági rács beállításainak meghatározása
Itt adjuk meg a rács paramétereit. Állítsd be az origókat és a skálákat, hogy megfeleljenek a projekt koordináta-rendszerének.

```csharp
var options = new FileGdbOptions
{
    CoordinatePrecisionGrid = new FileGdbCoordinatePrecisionGrid
    {
        XOrigin = -400,
        YOrigin = -400,
        XYScale = 1e10,
        MOrigin = 0,
        MScale = 1e4,
    },
    EnsureValidCoordinatesRange = true,
};
```

*Az `EnsureValidCoordinatesRange = true` jelző azt mondja az Aspose.GIS‑nek, hogy **ellenőrizze a koordináta-tartományt** minden hozzáadott funkció esetén.*

### 3. lépés: Réteg létrehozása a rácssal
Most egy új réteget hozunk létre az adathalmazban, alkalmazva a most meghatározott rács beállításokat. A WGS84 térbeli referenciarendszert fogjuk használni.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### 4. lépés: Funkciók hozzáadása a réteghez
Két pontfunkciót hozunk létre. Az első pont a rácson belül van, míg a második szándékosan kívül esik, hogy bemutassa, **hogyan kezeljük a tartományon kívüli** hibákat.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### 5. lépés: Kivételek kezelése tartományon kívüli funkciók hozzáadásakor
A második funkció hozzáadásának kísérlete kivételt vált ki, mivel az X koordinátája (`-410`) a definiált rácson kívül van. Elkapjuk a kivételt és egyértelmű üzenetet jelenítünk meg.

```csharp
try
{
    layer.Add(feature);
}
catch (GisException e)
{
    Console.WriteLine(e.Message); // X value -410 is out of valid range.
}
```

### 6. lépés: Takarítás
Az `using` utasítások automatikusan lezárják és felszabadítják az adathalmazt és a réteget, biztosítva, hogy minden erőforrás felszabaduljon.

## Gyakori problémák és megoldások
| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| **Kivétel: “X value … is out of valid range.”** | A koordináták a pontossági rácson kívül esnek. | Állítsd be a `XOrigin`, `YOrigin` vagy `XYScale` értékeket, hogy lefedjék az adataidat, vagy győződj meg róla, hogy a bemeneti adatok a definiált tartományon belül vannak. |
| **A funkciók nem jelennek meg a GIS megjelenítőben** | A réteg nincs mentve vagy a térbeli referenciája hibás. | Ellenőrizd, hogy a `SpatialReferenceSystem.Wgs84` megegyezik a megjelenítő CRS‑ével, és hogy a `Dataset.Create` sikeres volt. |
| **Az M értékek figyelmen kívül vannak hagyva** | `MScale` 0-ra vagy túl alacsonyra van állítva. | Állíts be egy ésszerű `MScale` értéket (pl. `1e4`), hogy a mérőértékek tárolhatók legyenek. |

## Hibaelhárítási tippek
- **Ellenőrizd újra a rács kiterjedéseit** nagy adatcsomagok betöltése előtt; egy kis elírás a `XOrigin`‑ban sok sor elutasításához vezethet.  
- **Naplózd a kivétel üzenetét** (ahogy a try‑catch blokkban látható) egy fájlba az automatizált importálás során; ez megkönnyíti a tartományon kívüli adatok mintáinak felismerését.  
- **Használd az `EnsureValidCoordinatesRange = false` beállítást csak megbízható adatforrásoknál** – a kikapcsolása kihagyja az ellenőrzést, és sérült geometriákhoz vezethet.

## Gyakran Ismételt Kérdések

**Q: Használhatom az Aspose.GIS for .NET-et más GIS fájlformátumokkal?**  
A: Igen, az Aspose.GIS támogatja a Shapefile, GeoJSON, KML és még sok más formátumot.

**Q: Kompatibilis az Aspose.GIS for .NET a .NET Core‑dal?**  
A: Teljes mértékben. A könyvtár működik .NET Framework, .NET Core és .NET 5/6+ környezetekkel.

**Q: Végrehajthatok térbeli műveleteket, például bufferelést vagy metszést?**  
A: Igen, az API tartalmaz módszereket bufferelésre, metszésre és távolságok számítására.

**Q: Biztosít-e az Aspose.GIS koordináta-transzformációs lehetőségeket?**  
A: Igen, a beépített újraprojektálási eszközökkel átalakíthatod a geometriákat különböző térbeli referenciarendszerek között.

**Q: Elérhető próba verzió?**  
A: Igen, letölthetsz egy ingyenes próbaverziót a [weboldalról](https://releases.aspose.com/gis/net/).

---

**Utoljára frissítve:** 2026-04-24  
**Tesztelve:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
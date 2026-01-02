---
date: 2026-01-02
description: Ismerje meg, hogyan adhat hozzá ponttípusú elemet a mezőnevek beállítása
  és az objektumazonosító olvasása közben az Aspose.GIS for .NET használatával. Lépésről
  lépésre útmutató fejlesztőknek.
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
title: Ponttípusú elem hozzáadása és az objektumazonosító és a geometriai mezőnevek
  megadása
url: /hu/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pont elem hozzáadása és az Objektumazonosító és Geometria mezőnevek megadása

## Bevezetés
Az Aspose.GIS for .NET használatával a Geográfiai Információs Rendszerek (GIS) világába való belépés rengeteg lehetőséget nyit meg a fejlesztők és a lelkesedők számára egyaránt. Ebben az útmutatóban **meg fogod tanulni, hogyan adj hozzá pont elemet**, miközben **mezőneveket állítasz be** és **olvasod az objektumazonosító** értékeket, így teljes irányítást kapsz a térbeli adataid felett.

## Gyors válaszok
- **Mi a fő célja ennek az útmutatónak?** Bemutatni, hogyan adjunk hozzá pont elemet és konfiguráljuk az Objektumazonosító és Geometria mezőneveket.  
- **Melyik könyvtárat használja?** Aspose.GIS for .NET.  
- **Szükségem van licencre?** Elérhető egy ingyenes próba, a termeléshez licenc szükséges.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Olvashatom az Objektumazonosítót a beszúrás után?** Igen – az útmutató bemutatja, hogyan olvassuk az objektumazonosítót a rétegből.

## Előfeltételek
Mielőtt belemerülnél az útmutatóba, győződj meg róla, hogy a következő előfeltételek rendelkezésre állnak:
- Aspose.GIS for .NET: Töltsd le és telepítsd a könyvtárat innen: [ide](https://releases.aspose.com/gis/net/).
- Dokumentum könyvtár: Hozz létre egy könyvtárat a dokumentumaid számára a geoadatbázisok tárolásához.
- .NET környezet: Győződj meg róla, hogy működő .NET környezeted van.

## Névterek importálása
A kezdéshez importálnod kell a szükséges névtereket a projektedbe. Ezek a névterek biztosítják a lényeges osztályokat és metódusokat az Aspose.GIS for .NET használatához.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## 1. lépés: Pont elem hozzáadása és az Objektumazonosító és Geometria mezőnevek megadása
Ebben a lépésben megtanulod, hogyan állítsd be az Objektumazonosító és Geometria mezőneveket a GIS adataidhoz. Ez elengedhetetlen a hatékony adatkezeléshez és ahhoz, hogy később **olvasni tudd az objektumazonosítót**.

### 1.1. lépés: Dokumentum könyvtár beállítása
Kezdd a dokumentum könyvtárad elérési útjának meghatározásával:

```csharp
string dataDir = "Your Document Directory";
```

### 1.2. lépés: GeoDatabase létrehozása és beállítások meghatározása
Hozz létre egy GeoDatabase-et a kívánt **mezőnevek beállításával** az Objektumazonosítóhoz és a Geometriához:

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

### 1.3. lépés: Réteg létrehozása és hozzáadása
Hozz létre egy réteget a GeoDatabase-ben, és adj hozzá egy elemet, amely pont geometriát képvisel:

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

### 1.4. lépés: Réteg megnyitása és adat lekérése
Nyisd meg a réteget, és kérd le a most hozzáadott elemet. Ez bemutatja, hogyan **olvassuk az objektumazonosítót** az adatkészletből:

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Miért állítsunk be egyedi mezőneveket?
Az Objektumazonosító és Geometria mezőneveinek testreszabása rugalmasságot biztosít a meglévő adatbázisokkal való integráció során, vagy amikor a downstream alkalmazások által megkövetelt elnevezési konvencióknak kell megfelelni. Emellett az adatok önmagukban is leíróbbá válnak, ami egyszerűsíti a karbantartást és az együttműködést.

## Gyakori hibák és hibaelhárítás
- **Hiányzó könyvtár** – Győződj meg róla, hogy a `dataDir` egy létező mappára mutat; ellenkező esetben a `Dataset.Create` kivételt dob.
- **Mezőnév ütközések** – Ha a geoadatbázisban már létezik ugyanazzal a névvel mező, a létrehozás sikertelen lesz. Válassz egyedi neveket.
- **Térbeli referenciák eltérése** – Mindig egyeztesd a térbeli referenciarendszert (pl. WGS84) a tárolni kívánt adatokkal.

## Következtetés
Gratulálunk! Sikeresen megtanultad, hogyan **adj hozzá pont elemet**, **állíts be mezőneveket**, és **olvass objektumazonosítót** az Aspose.GIS for .NET segítségével. Ez az alap lehetővé teszi, hogy robusztus GIS alkalmazásokat építs, és magabiztosan kezeld a térbeli adatokat.

## Gyakran Ismételt Kérdések
### Q: Használhatom az Aspose.GIS for .NET-et a webalkalmazásaimban?
A: Igen, az Aspose.GIS for .NET alkalmas mind asztali, mind webalkalmazásokhoz, és sokoldalú térinformatikai képességeket biztosít.

### Q: Elérhető próba verzió a vásárlás előtt?
A: Igen, a Aspose.GIS for .NET funkcióit egy ingyenes próba verzióval is kipróbálhatod, amely [ide](https://releases.aspose.com/) érhető el.

### Q: Hogyan szerezhetek ideiglenes licencet az Aspose.GIS for .NET-hez?
A: Ideiglenes licencet [ide](https://purchase.aspose.com/temporary-license/) szerezhetsz értékelési célokra.

### Q: Milyen térbeli referenciarendszereket támogat az Aspose.GIS for .NET?
A: Az Aspose.GIS for .NET különféle térbeli referenciarendszereket támogat, ami rugalmasságot biztosít különböző földrajzi adatkészletekhez.

### Q: Hol kérhetek segítséget vagy vitathatom meg az Aspose.GIS-szel kapcsolatos kérdéseket?
A: Látogasd meg az Aspose.GIS fórumot [ide](https://forum.aspose.com/c/gis/33) támogatás és megbeszélések céljából.

## További Gyakran Ismételt Kérdések

**Q: Megváltoztathatom az Objektumazonosító mezőt a réteg létrehozása után?**  
A: Nem. A mező neve a réteg létrehozásakor kerül meghatározásra; a módosításhoz új `FileGdbOptions` objektummal kell újra létrehozni a réteget.

**Q: Hogyan kérhetek le más attribútum értékeket az Objektumazonosítón kívül?**  
A: Használd a `feature.GetValue<T>("FieldName")` metódust, ahol a `FieldName` a lekérdezni kívánt attribútum neve.

**Q: Lehetséges több pont elemet egy csomagban hozzáadni?**  
A: Igen. Iterálj az adataidon, minden ponthoz hozz létre egy elemet, állítsd be a geometriáját, és hívd meg a `layer.Add(feature)` metódust ugyanabban a `using` blokkban.

**Q: Támogatja az Aspose.GIS más geometriai típusokat is?**  
A: Teljes mértékben. Használhatod a `LineString`, `Polygon`, `MultiPoint` és további típusokat a megfelelő geometriai objektumok létrehozásával.

**Q: Mi történik, ha egy nem létező Objektumazonosítót próbálok olvasni?**  
A: Egy tartományon kívüli index (pl. `layer[10]`, ha csak egy elem van) elérése `IndexOutOfRangeException` kivételt eredményez. Mindig ellenőrizd először a `layer.Count` értéket.

---

**Last Updated:** 2026-01-02  
**Tested With:** Aspose.GIS for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
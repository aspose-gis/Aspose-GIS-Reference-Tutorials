---
date: 2026-01-05
description: Tanulja meg, hogyan olvasson shapefile-t C#-ban az Aspose.GIS for .NET
  segítségével, hogyan szerezze meg az összes attribútumértéket, és hatékonyan exportálja
  az attribútumokat.
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
title: Shapefile olvasása C#‑ban – Az összes jellemző attribútumérték lekérése
url: /hu/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Az összes jellemző attribútumérték lekérése

## Bevezetés
Üdvözöljük a geospatial fejlesztés világában az Aspose.GIS for .NET segítségével! Ebben az útmutatóban megtanulja, **hogyan olvassa be a shapefile-t C#-ban**, és hogyan szerezheti meg minden attribútumértékét a jellemzőkből. Akár térképező alkalmazást épít, akár kötegelt térbeli adatfeldolgozást végez, az attribútumok kinyerésének elsajátítása elengedhetetlen. Merüljünk el, és nézzük meg a kódot működés közben.

## Gyors válaszok
- **Mit csinál ez a kód?** Megnyit egy Shapefile-t, és beolvassa az összes, néhány vagy kiürített attribútumértéket minden jellemzőből.  
- **Melyik könyvtár szükséges?** Aspose.GIS for .NET (kompatibilis a .NET Framework és a .NET Core verziókkal).  
- **Szükségem van licencre?** Egy ideiglenes licenc teszteléshez működik; a teljes licenc szükséges a termeléshez.  
- **Olvashatok más formátumokat is?** Igen – ugyanaz az API támogatja a GeoJSON, KML és még sok más formátumot.  
- **Hogyan lehet kiüríteni az attribútumokat?** Használja a `feature.GetValuesDump()` metódust, amely egy rugalmas objektumtömböt ad vissza.

## Mi az a „read shapefile C#”?
A Shapefile C#-ban történő olvasása azt jelenti, hogy megnyitja a .shp fájlt egy GIS könyvtárral, végigiterál a vektoros jellemzőkön, és eléri a hozzájuk tartozó attribútumadatokat, amelyek a mellékelt .dbf fájlban tárolódnak. Az Aspose.GIS elrejti az alacsony szintű fájlkezelést, így Ön a szükséges attribútumértékekre koncentrálhat.

## Miért használja az Aspose.GIS-t az attribútumok olvasásához?
- **Egyszerű API** – intuitív metódusok, mint a `GetValues` és a `GetValuesDump`.  
- **Keresztplatformos** – működik Windows, Linux és macOS rendszereken a .NET Core segítségével.  
- **Gazdag formátumtámogatás** – kezelje a Shapefile, GeoJSON, GML és további formátumokat extra pluginek nélkül.  
- **Teljesítmény‑optimalizált** – gyors iteráció nagy adatkészleteken.

## Előfeltételek
Mielőtt elindulnánk ezen az izgalmas úton, győződjön meg róla, hogy az alábbi előfeltételek rendelkezésre állnak:
- Aspose.GIS for .NET: Töltse le és telepítse a könyvtárat a [Aspose.GIS for .NET letöltési oldalról](https://releases.aspose.com/gis/net/).
- Fejlesztői környezet: Állítson be egy .NET fejlesztői környezetet, például a Visual Studio-t.
- Shapefile: Legyen egy mint Shapefile (pl. "InputShapeFile.shp") a dokumentum könyvtárában.

## Névterek importálása
A C# kódban kezdje a szükséges névterek importálásával az Aspose.GIS funkciók kihasználásához:
```csharp
using System;
using Aspose.Gis;
```

## 1. lépés: A dokumentum könyvtár beállítása
```csharp
string dataDir = "Your Document Directory";
```
Cserélje le a "Your Document Directory"-t a tényleges útvonalra, ahol a Shapefile található.

## 2. lépés: A VectorLayer megnyitása
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
Ez a lépés a Shapefile megnyitását jelenti az Aspose.GIS használatával, megadva a fájl útvonalát és formátumát (ebben az esetben Shapefile).

## 3. lépés: Az összes jellemző attribútumérték lekérése
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
A kódrészlet bemutatja, **hogyan olvassuk be az attribútumokat** minden jellemzőhez, egy fix méretű tömbbe betöltve.

## 4. lépés: Több jellemző attribútumérték lekérése
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
Itt bemutatjuk, **hogyan olvassuk be a specifikus attribútumértékeket**, ha csak a mezők egy részhalmazára van szükség.

## 5. lépés: Az attribútumértékek lekérése objektumok kiürítéseként
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
Ez az utolsó lépés bemutatja, **hogyan lehet kiüríteni az attribútumokat** a `GetValuesDump()` használatával, amely egy rugalmas gyűjteményt ad vissza, amelyet megtekinthet vagy sorosíthat.

## Gyakori problémák és megoldások
- **Tömbméret eltérés** – Győződjön meg róla, hogy a `GetValues`-nek átadott tömb mérete megegyezik a várt attribútumok számával; ellenkező esetben `null` bejegyzéseket kap.  
- **Fájl nem található** – Ellenőrizze, hogy a `dataDir` a megfelelő mappára mutat, és a Shapefile neve pontosan van-e leírva.  
- **Licenc kivétel** – Ha licenc hibát lát, alkalmazzon ideiglenes vagy teljes licencet, mielőtt bármilyen API metódust meghívna.

## Gyakran ismételt kérdések
### Az Aspose.GIS kompatibilis a .NET Core-val?
Igen, az Aspose.GIS teljesen kompatibilis a .NET Core-val, lehetővé téve a keresztplatformos alkalmazások építését.

### Dolgozhatok különböző GIS fájlformátumokkal az Aspose.GIS használatával?
Természetesen! Az Aspose.GIS számos formátumot támogat, beleértve a Shapefile-t, GeoJSON-t és még sok mást.

### Van közösségi fórum az Aspose.GIS támogatásához?
Igen, segítséget találhat és részt vehet az Aspose.GIS közösségben a [támogatási fórumban](https://forum.aspose.com/c/gis/33).

### Hogyan szerezhetek ideiglenes licencet az Aspose.GIS-hez?
Ideiglenes licencet tesztelési célokra [itt](https://purchase.aspose.com/temporary-license/) szerezhet.

### Hol találhatók részletes dokumentációk az Aspose.GIS-hez?
A részletes dokumentáció [itt](https://reference.aspose.com/gis/net/) érhető el.

### Hogyan kérhetem le csak a „Name” attribútumot minden jellemzőből?
Használja a `GetValues`-t egy egy elemű tömbbel, és adja át a „Name” mező indexét, vagy hívja meg közvetlenül a `feature["Name"]`-t.

### Mi a különbség a `GetValues` és a `GetValuesDump` között?
`GetValues` egy előre lefoglaltt tömböt tölt fel nyers értékekkel, míg a `GetValuesDump` egy objektumtömböt ad vissza, amelyet a séma előzetes ismerete nélkül is bejárhat.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Utoljára frissítve:** 2026-01-05  
**Tesztelve:** Aspose.GIS for .NET (legújabb kiadás)  
**Szerző:** Aspose  

---
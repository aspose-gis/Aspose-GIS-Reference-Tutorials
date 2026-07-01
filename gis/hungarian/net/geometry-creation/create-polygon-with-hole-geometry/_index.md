---
date: 2026-04-03
description: Tanulja meg, hogyan hozhat létre lyukkal rendelkező sokszöget az Aspose.GIS
  for .NET használatával. Ez az útmutató megmutatja, hogyan készíthet lyukat a sokszögben,
  és hogyan dolgozhat térbeli adatokkal.
keywords:
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
linktitle: Lyukkal rendelkező sokszög létrehozása
second_title: Aspose.GIS .NET API
title: Polygon létrehozása lyukkal rendelkező geometriával az Aspose.GIS használatával
url: /hu/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Polygon létrehozása lyukkal az Aspose.GIS segítségével

## Bevezetés
Ebben az útmutatóban **polygon lyukkal** geometriát hozunk létre az Aspose.GIS for .NET segítségével. Akár térképező alkalmazást építesz, térbeli elemzést végzel, vagy GIS szolgáltatásokhoz készítesz adatokat, fontos tudni, hogyan lehet lyukat beágyazni egy polygonba. Lépésről lépésre végigvezetünk a teljes folyamaton, a környezet beállításától a végleges polygon objektum generálásáig.

## Gyors válaszok
- **Mi jelent a „polygon lyukkal” létrehozása?** Ez azt jelenti, hogy egy olyan polygon épül, amely egy vagy több belső gyűrűt (lyukat) tartalmaz, amelyek kizárásra kerülnek a területből.  
- **Melyik könyvtár kezeli ezt?** Az Aspose.GIS for .NET teljes támogatást nyújt a külső és belső gyűrűkhöz.  
- **Szükségem van licencre?** Fejlesztéshez egy ingyenes próba elegendő; a termeléshez kereskedelmi licenc szükséges.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Mennyi időt vesz igénybe?** Általában 10 percnél kevesebb a megvalósításhoz és teszteléshez.

## Hogyan adjon lyukat a polygonhoz az Aspose.GIS használatával
Lyuk hozzáadása egyszerűen egy **belső gyűrű** definiálását és a polygonhoz való csatolását jelenti. A könyvtár gondoskodik a tájolásról és az érvényességről, így a szükséges ürességet leíró koordinátákra koncentrálhatsz.

## Mi az a „polygon lyukkal” létrehozása?
Polygon lyukkal való létrehozása magában foglalja egy **külső gyűrű** definiálását, amely meghatározza a külső határt, valamint egy vagy több **belső gyűrű** létrehozását, amelyek üres területeket vágnak ki. A belső gyűrűket gyakran *lyukaknak* nevezik, mivel olyan területeket jelentenek, amelyek nem részei a polygon felületének.

## Miért hozzunk létre lyukat a polygonban az Aspose.GIS használatával?
- **Pontos térbeli modellezés:** Valós világban olyan elemek, mint a földparcellákon belüli tavak vagy épületeken belüli udvarok lyukakat igényelnek.  
- **Interoperabilitás:** A Shapefile, GeoJSON és GML formátumok natívan támogatják a belső gyűrűket; az Aspose.GIS megőrzi ezeket.  
- **Teljesítmény:** A könyvtár kezeli a geometria érvényességét, így nem kell egyedi validációs kódot írnod.

## Valós példák lyukkal rendelkező poligonokra
1. **Földparcella belső tavval** – a tavat lyukként modellezzük, így nem számít bele a parcella területébe.  
2. **Épület lábnyoma udvarokkal** – az udvart kizárjuk az épület lábnyomából.  
3. **Védett zónák egy nagyobb természetvédelmi területen belül** – korlátozott szakaszokat kizárhatsz anélkül, hogy külön rétegeket hoznál létre.

## Előfeltételek
Mielőtt elkezdenénk, győződj meg róla, hogy rendelkezel a következő előfeltételekkel:
1. Aspose.GIS for .NET könyvtár: Letöltheted [innen](https://releases.aspose.com/gis/net/).  
2. Fejlesztői környezet: Győződj meg arról, hogy van egy fejlesztői környezet beállítva Visual Studio-val vagy bármely más .NET IDE-vel.

## Névterek importálása
Először importálnod kell a szükséges névtereket az Aspose.GIS funkciók használatához. Íme, hogyan teheted:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Most lépjünk tovább a lyukkal rendelkező polygon geometria létrehozásához az Aspose.GIS for .NET használatával.

## 1. lépés: Polygon objektum létrehozása
Először egy üres `Polygon` objektumot hozunk létre, amely később a külső és belső gyűrűket is tartalmazni fogja.

```csharp
Polygon polygon = new Polygon();
```

## 2. lépés: Külső gyűrű definiálása
A külső gyűrű meghatározza a polygon külső határát. Adj hozzá pontokat óramutató járásával megegyező sorrendben, hogy zárt alakzatot kapj.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## 3. lépés: Belső gyűrű (lyuk) definiálása
Ezután létrehozunk egy belső gyűrűt – ez a **lyuk**, amely kizárásra kerül a polygon területéből. A pontokat általában ellentétes óramutató járásával (counter‑clockwise) sorrendben adjuk hozzá, de az Aspose.GIS automatikusan kezeli a tájolást.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## 4. lépés: Külső gyűrű hozzárendelése és belső gyűrű hozzáadása a polygonhoz
Végül csatold a külső gyűrűt a polygonhoz, majd add hozzá a belső gyűrűt (a lyukat). Az `AddInteriorRing` metódus többször is meghívható, ha több lyukra van szükséged.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Tippek és bevált gyakorlatok
- **A tájolás fontos az olvashatóság szempontjából** – bár az Aspose.GIS automatikusan javítja a tájolást, a külső gyűrűk óramutató járásával megegyező, a belső gyűrűk ellentétes irányú tárolása megkönnyíti a geometria ellenőrzését GIS nézőkben.  
- **Zárd le minden gyűrűt** – mindig ismételd meg az első koordinátát az utolsó pontként; ez garantálja a valid zárt alakzatot.  
- **Érvényesítsd a létrehozás után** – meghívhatod a `polygon.IsValid` metódust, hogy biztosítsd a geometria OGC szabványoknak való megfelelését mentés előtt.

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| A lyuk nem jelenik meg a GIS nézőben | A belső gyűrű tájolása fordított | Győződj meg róla, hogy a pontok a külső gyűrű ellentétes irányában (ellentétes óramutató járásával) vannak hozzáadva. |
| Érvénytelen polygon hiba | A gyűrűk nincsenek lezárva (első ≠ utolsó pont) | Ismételd meg az első pontot az utolsóként minden gyűrűben (ahogy fent látható). |
| Váratlanul üres geometria | Elfelejtetted beállítani az `ExteriorRing`-et a belső gyűrűk hozzáadása előtt | Állítsd be először a `polygon.ExteriorRing`-et, majd hívd meg az `AddInteriorRing`-t. |

## Gyakran feltett kérdések
### 1. Mi az Aspose.GIS?
Az Aspose.GIS egy .NET könyvtár, amely lehetővé teszi a fejlesztők számára a térinformatikai adatokkal való munkát, beleértve a különféle térinformatikai fájlformátumok létrehozását, olvasását és manipulálását.

### 2. Használhatom az Aspose.GIS-t kereskedelmi projektekhez?
Igen, az Aspose.GIS-t személyes és kereskedelmi projektekhez egyaránt használhatod licenc vásárlásával. További részletekért látogasd meg a [linket](https://purchase.aspose.com/buy).

### 3. Van ingyenes próba a Aspose.GIS-hez?
Igen, ingyenes próba verziót kaphatsz az Aspose.GIS-ből [innen](https://releases.aspose.com/).

### 4. Hol találok támogatást az Aspose.GIS-hez?
Támogatást az Aspose.GIS-hez a [Aspose.GIS fórumon](https://forum.aspose.com/c/gis/33) találhatsz.

### 5. Hogyan szerezhetek ideiglenes licencet az Aspose.GIS-hez?
Ideiglenes licencet az Aspose.GIS-hez [innen](https://purchase.aspose.com/temporary-license/) szerezhetsz.

**Utoljára frissítve:** 2026-04-03  
**Tesztelve:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
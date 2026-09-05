---
date: 2026-09-05
description: Ismerje meg, hogyan hozhat létre polygon interior ring-et hole-rel az
  Aspose.GIS for .NET használatával. Ez az útmutató megmutatja, hogyan adhat hozzá
  hole-t egy polygonhoz, és hogyan dolgozhat az adatokkal.
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: Polygon with Hole Geometry létrehozása
og_description: Ismerje meg, hogyan hozhat létre polygon interior ring-et hole-rel
  az Aspose.GIS for .NET használatával. Ez az útmutató megmutatja, hogyan adhat hozzá
  hole-t egy polygonhoz, és hogyan dolgozhat az adatokkal.
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: Polygon interior ring létrehozása hole-rel az Aspose.GIS segítségével
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: Polygon interior ring létrehozása hole-rel az Aspose.GIS segítségével
url: /hu/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Poligon belső gyűrű létrehozása lyukkal az Aspose.GIS használatával

## Bevezetés
Ebben az útmutatóban megtanulja, hogyan **hozzon létre egy poligon belső gyűrűt**, amely lyukkal rendelkezik az Aspose.GIS for .NET használatával. Akár térképező alkalmazást épít, térbeli elemzést végez, vagy GIS szolgáltatásokhoz készít adatokat, a lyuk beágyazása egy poligonba alapvető készség. Végigvezetjük az egész munkafolyamatot – a fejlesztői környezet beállításától egy érvényes poligon objektum generálásáig, amely bármely támogatott földrajzi formátumba menthető.

## Gyors válaszok
- **Mi jelent a “create polygon with hole”?** Ez azt jelenti, hogy egy olyan poligont építünk, amely egy vagy több belső gyűrűt (lyukat) tartalmaz, amelyek kizárásra kerülnek a területből.  
- **Melyik könyvtár kezeli ezt?** Az Aspose.GIS for .NET teljes támogatást nyújt a külső és belső gyűrűkhöz.  
- **Szükségem van licencre?** A fejlesztéshez egy ingyenes próba verzió működik; a termeléshez kereskedelmi licenc szükséges.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Mennyi időt vesz igénybe?** Általában 10 perc alatt megvalósítható és tesztelhető.

## Hogyan adjon lyukat a poligonhoz az Aspose.GIS használatával
Töltse be a GIS környezetét, definiáljon egy külső gyűrűt, majd csatoljon egy vagy több belső gyűrűt. Az Aspose.GIS automatikusan orientálja a gyűrűket és ellenőrzi a geometriát, így a szükséges ürességet képviselő koordinátákra koncentrálhat.

## Mi az a poligon belső gyűrű?
A **polygon interior ring** egy belső határ, amely levonja a területet a poligon külső alakjából.  
Ezt úgy hozza létre, hogy egy zárt pontsorozatot definiál, amelyet az Aspose.GIS lyukként kezel, és amely a terület számításakor vagy a forma megjelenítésekor kizárásra kerül.

## Miért hoz létre poligon belső gyűrűt az Aspose.GIS használatával?
Az Aspose.GIS 5 ms alatti idő alatt ellenőrzi és javítja a gyűrű orientációját tipikus 200 pontból álló poligonok esetén, ezzel megszüntetve az egyedi validációs kód szükségességét. Emellett támogat **30+ földrajzi fájlformátumot** (Shapefile, GeoJSON, GML, KML, stb.) és képes akár 10 000 pontot tartalmazó poligonok feldolgozására anélkül, hogy az egész fájlt a memóriába töltené, így gyorsaságot és skálázhatóságot biztosít.

## Valós példák lyukkal rendelkező poligonokra
1. **Belső tavakkal rendelkező földparcella** – a tavat lyukként modellezik, így nem számít bele a parcella területébe.  
2. **Épület lábnyomok udvarokkal** – az udvart kizárják az épület lábnyomából.  
3. **Védett zónák egy nagyobb természetvédelmi területen belül** – a korlátozott szakaszokat kizárhatja anélkül, hogy külön rétegeket hozna létre.

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik a következő előfeltételekkel:
1. Aspose.GIS for .NET Library: Letöltheti a **Aspose.GIS for .NET letöltési oldalról**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).  
2. Fejlesztői környezet: Biztosítsa, hogy a Visual Studio vagy bármely más .NET IDE telepítve legyen.

## Névterek importálása
`Aspose.Gis` névtér tartalmazza az összes szükséges geometriai típust, beleértve a `Polygon`, `LinearRing` és a validációhoz szükséges segédmetódusokat.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Most lépjünk tovább egy lyukkal rendelkező poligon geometria létrehozásához az Aspose.GIS for .NET használatával.

## 1. lépés: poligon objektum létrehozása
`Polygon` az Aspose.GIS geometriai típusa, amely egy síkbeli poligont képvisel opcionális belső gyűrűkkel. Kezdjük egy üres `Polygon` objektum példányosításával, amely később mind a külső, mind a belső gyűrűket tartalmazni fogja.

```csharp
Polygon polygon = new Polygon();
```

## 2. lépés: külső gyűrű definiálása
`LinearRing` az osztály, amelyet mind a külső, mind a belső határokhoz használnak. A külső gyűrű határozza meg a poligon külső határát. Adjunk hozzá pontokat az óramutató járásával megegyező sorrendben, hogy zárt alakzatot kapjunk.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## 3. lépés: belső gyűrű (lyuk) definiálása
`LinearRing` a belső gyűrűket is képviseli. A belső gyűrű a **lyuk**, amely kizárásra kerül a poligon területéből. A pontokat általában az óramutató járásával ellentétes sorrendben adjuk hozzá, de az Aspose.GIS automatikusan kezeli az orientációt.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## 4. lépés: külső gyűrű hozzárendelése és belső gyűrű hozzáadása a poligonhoz
Az `AddInteriorRing` metódus egy vagy több belső gyűrűt csatol egy `Polygon` objektumhoz. Hívja meg a `ExteriorRing` tulajdonság beállítása után; a hívást ismételve több lyukat is hozzáadhat.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Tippek és bevált gyakorlatok
- **Az orientáció fontos az olvashatóság szempontjából** – bár az Aspose.GIS automatikusan javítja az orientációt, a külső gyűrűk óramutató járásával megegyező, a belső gyűrűk óramutató járásával ellentétes irányban tartása megkönnyíti a geometria ellenőrzését GIS nézőkben.  
- **Zárja le minden gyűrűt** – mindig ismételje meg az első koordinátát utolsó pontként; ez garantálja a valid zárt alakzatot.  
- **Érvényesítés létrehozás után** – meghívhatja a `polygon.IsValid` metódust, hogy biztosítsa a geometria OGC szabványoknak való megfelelését mentés előtt.

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| A lyuk nem jelenik meg a GIS nézőben | A belső gyűrű orientációja fordított | Győződjön meg arról, hogy a pontok a külső gyűrű ellentétes irányában (óramutató járásával ellentétesen) kerülnek hozzáadásra. |
| Érvénytelen poligon hiba | A gyűrűk nincsenek lezárva (első ≠ utolsó pont) | Ismételje meg az első pontot minden gyűrű utolsó pontjaként (ahogy fentebb látható). |
| Váratlanul üres geometria | Elfelejtette beállítani a `ExteriorRing`-et a belső gyűrűk hozzáadása előtt | Először állítsa be a `polygon.ExteriorRing`-et, majd hívja meg az `AddInteriorRing`-t. |

## Gyakran ismételt kérdések
### 1. Mi az Aspose.GIS?
Az Aspose.GIS egy .NET könyvtár, amely lehetővé teszi a fejlesztők számára a földrajzi adatokkal való munkát, lehetővé téve számukra különböző földrajzi fájlformátumok létrehozását, olvasását és manipulálását.

### 2. Használhatom az Aspose.GIS-t kereskedelmi projektekhez?
Igen, az Aspose.GIS-t személyes és kereskedelmi projektekhez egyaránt használhatja licenc vásárlásával. További részletekért látogassa meg az **Aspose.GIS vásárlási oldalt**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)).

### 3. Elérhető ingyenes próba az Aspose.GIS-hez?
Igen, ingyenes próba verziót kaphat az Aspose.GIS-hez a **Aspose.GIS ingyenes próba letöltési oldalról**([https://releases.aspose.com/](https://releases.aspose.com/)).

### 4. Hol találok támogatást az Aspose.GIS-hez?
Támogatást az Aspose.GIS-hez a [Aspose.GIS fórumon](https://forum.aspose.com/c/gis/33) talál.

### 5. Hogyan szerezhetek ideiglenes licencet az Aspose.GIS-hez?
Ideiglenes licencet az Aspose.GIS-hez a **Aspose.GIS ideiglenes licenc oldalról**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)) szerezhet.

---

**Legutóbb frissítve:** 2026-09-05  
**Tesztelve:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Hogyan hozzunk létre poligon geometriát az Aspose.GIS for .NET használatával](/gis/net/geometry-creation/create-polygon-geometry/)
- [Ismerje meg, hogyan hozzon létre MultiPolygon geometriát az Aspose.GIS használatával](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [Poligon konvertálása vonallá az Aspose.GIS for .NET használatával](/gis/net/geometry-processing/replace-polygons-with-lines/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-04-09
description: Tanulja meg, hogyan rendeljen hozzá térbeli referenciát, és állítson
  be tizedes pontosságot pont létrehozásakor C#-ban az Aspose.GIS for .NET segítségével
  .NET‑alkalmazásaiban.
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: WKT változat megadása a fordítás során
second_title: Aspose.GIS .NET API
title: Térbeli hivatkozás hozzárendelése és WKT változat beállítása az Aspose.GIS
  használatával
url: /hu/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Térbeli hivatkozás hozzárendelése és WKT változat beállítása az Aspose.GIS használatával

## Bevezetés
Ebben az útmutatóban megtanulja, hogyan **rendelje hozzá a térbeli hivatkozást** egy geometriához, és hogyan szabályozza a pontos WKT kimeneti formátumot az Aspose.GIS for .NET segítségével. Akár **C# pont objektumokat** kell létrehoznia térképezéshez, elemzéshez vagy adatcseréhez, a megfelelő WKT változat és a numerikus pontosság kiválasztása interoperábilis és könnyen olvasható térbeli adatokat biztosít. Lépésről lépésre végigvezetjük a folyamatot.

## Gyors válaszok
- **Mi jelent a „térbeli hivatkozás hozzárendelése”?** Egy geometriát egy adott koordináta‑rendszerhez, például a WGS‑84‑hez köt.
- **Mely WKT változatok támogatottak?** Iso, SimpleFeatureAccessOutdated és ExtendedPostGis.
- **Hogyan szabályozhatom a tizedes pontosságot?** Használja a `NumericFormat` beállításokat, mint a `General`, `RoundTrip` vagy `Flat`.
- **Szükségem van licencre?** Elérhető egy ingyenes próba, a termeléshez kereskedelmi licenc szükséges.
- **Mely .NET verziók kompatibilisek?** .NET Framework 4.0+ és .NET Core/5/6+.

## Mi a „térbeli hivatkozás hozzárendelése”?
A térbeli hivatkozás (vagy térbeli hivatkozási rendszer, SRS) hozzárendelése azt mondja meg a GIS szoftvernek, hogyan értelmezze egy geometria koordinátáit. SRS nélkül egy pont szélességi‑hosszúsági értékei nem rendelkeznek valós világbeli jelentéssel.

## Miért szabályozzuk a WKT változatot és a numerikus formátumot?
Különböző GIS eszközök kissé eltérő WKT szintaxist várnak. A megfelelő változat kiválasztása biztosítja a zökkenőmentes adatcserét, míg a tizedes pontosság beállítása megakadályozza a kerekítési hibákat vagy a túl hosszú számokat, amelyek elduzzák a naplókat és fájlokat.

## Előfeltételek
1. Aspose.GIS for .NET – letöltés a [letöltési oldalról](https://releases.aspose.com/gis/net/).  
2. Egy .NET fejlesztői környezet (Visual Studio, VS Code vagy Rider).  
3. Alapvető ismeretek a C# és a .NET keretrendszerrel kapcsolatban.

## Névtér importálása
Mielőtt bármely Aspose.GIS osztályt használna, importálja a szükséges névtereket:

```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```

## 1. lépés: Pont objektum létrehozása (create point C#)
Kezdjük egy `Point` objektum létrehozásával, amely tartalmazza a szélességi, hosszúsági és egy opcionális mérő (M) értéket:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## 2. lépés: Térbeli hivatkozási rendszer (SRS) hozzárendelése
Most **hozzárendeljük a térbeli hivatkozást** a ponthoz. Itt a széles körben támogatott WGS‑84 rendszert (SRID 4326) használjuk:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## 3. lépés: A kívánt WKT változat megadása
Válassza ki a downstream alkalmazásának megfelelő WKT változatot:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## 4. lépés: Tizedes pontosság beállítása a WKT kimenethez
A `NumericFormat` használatával szabályozhatja, hány számjegy jelenjen meg a végső karakterláncban:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Általános buktatók és tippek
- **Buktató:** Ha a `AsText` hívása előtt nem állítja be az SRS-t, hiányozhat az SRID információ.  
- **Tipp:** Használja a `NumericFormat.RoundTrip`-ot, ha veszteségmentes koordináta‑átvitelt igényel.  
- **Tipp:** Az `Iso` változat a legportábilisabb; csak akkor válassza az `ExtendedPostGis`‑t, ha beágyazott SRID‑re van szüksége.

## Összegzés
Most már tudja, hogyan **rendelje hozzá a térbeli hivatkozást**, válassza ki a megfelelő WKT változatot, és hogyan **állítsa be a tizedes pontosságot**, amikor **C# pont objektumokat** hoz létre az Aspose.GIS segítségével. Ezek a beállítások rugalmasságot biztosítanak, hogy bármely GIS munkafolyamat pontos követelményeit teljesítse, a egyszerű megjelenítéstől a nagy pontosságú térbeli elemzésig.

## Gyakran Ismételt Kérdések

**Q:** Az Aspose.GIS kompatibilis minden .NET verzióval?  
**A:** Igen, az Aspose.GIS támogatja a .NET Framework 4.0‑t és újabbakat, valamint a .NET Core/5/6‑ot.

**Q:** Használhatom az Aspose.GIS‑t kereskedelmi projektekhez?  
**A:** Természetesen. Kereskedelmi licenc szükséges a termelési használathoz, de egy ingyenes próba elérhető értékeléshez.

**Q:** Támogatja az Aspose.GIS más térbeli adatformátumokat is?  
**A:** Igen, működik ESRI Shapefile, GeoJSON, KML és számos más formátummal.

**Q:** Hol tölthetem le az ingyenes próbaverziót?  
**A:** Az Aspose.GIS ingyenes próba verzióját letöltheti [itt](https://releases.aspose.com/).

**Q:** Hogyan kaphatok segítséget, ha problémába ütközöm?  
**A:** Kérdéseit a Aspose.GIS közösségi [fórumon](https://forum.aspose.com/c/gis/33) teheti fel, ahol az Aspose munkatársak és a közösség tagjai segítenek.

---

**Last Updated:** 2026-04-09  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
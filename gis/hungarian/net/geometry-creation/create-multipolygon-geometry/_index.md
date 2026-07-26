---
date: 2026-03-29
description: Tanulja meg, hogyan hozhat létre multipolygon geometriát, és hogyan adhat
  hozzá poligonokat a multipolygonhoz az Aspose.GIS for .NET használatával. Lépésről‑lépésre
  útmutató ingyenes próbaverzióval.
linktitle: Create MultiPolygon Geometry
second_title: Aspose.GIS .NET API
title: Hogyan készítsünk MultiPolygon geometriát az Aspose.GIS segítségével
url: /hu/net/geometry-creation/create-multipolygon-geometry/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre MultiPolygon geometriát az Aspose.GIS segítségével

## Bevezetés
Ha **hogyan hozzunk létre multipolygon** alakzatokat keresel egy .NET környezetben, jó helyen jársz. Az Aspose.GIS for .NET tiszta, objektum‑orientált API‑t biztosít összetett földrajzi objektumok építéséhez, és ez az útmutató minden lépésen végigvezet – a könyvtár telepítésétől az egyes poligonok egyetlen MultiPolygonba kombinálásáig. A végére magabiztosan **poligonok hozzáadása a multipolygonhoz** struktúrákhoz fogsz tudni.

## Gyors válaszok
- **Mi a MultiPolygon?** Egy geometria, amely két vagy több Polygon objektumot egyetlen gyűjteménybe csoportosít.  
- **Miért használjuk az Aspose.GIS-t?** Sok GIS formátumot támogat, működik .NET Framework és .NET Core alatt, és nem igényel külső natív könyvtárakat.  
- **Mennyi időt vesz igénybe a példa?** Körülbelül 5 perc a beíráshoz és futtatáshoz.  
- **Szükségem van licencre?** A ingyenes próba verzió fejlesztéshez megfelelő; a termeléshez kereskedelmi licenc szükséges.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Mi a MultiPolygon geometria?
A MultiPolygon egy összetett geometria, amely több Polygon objektumot tartalmaz, mindegyik saját belső gyűrűkkel (lyukakkal) is rendelkezhet. Ez a struktúra ideális a szétválasztott földparcellák, szigetek vagy bármely különálló területek ábrázolására, amelyek közös attribútummal rendelkeznek.

## Miért adjunk poligonokat a MultiPolygonhoz?
Poligonok hozzáadása egy MultiPolygonhoz lehetővé teszi, hogy több független alakzatot egyetlen entitásként kezeljünk. Ez egyszerűsíti a térbeli lekérdezéseket, a megjelenítést és az adatcserét, mivel a teljes gyűjteményt egy objektummal tárolhatjuk, továbbíthatjuk és manipulálhatjuk, ahelyett, hogy minden poligont külön kezelnénk.

## Előfeltételek
Mielőtt a kódba merülnél, győződj meg róla, hogy a következők rendelkezésre állnak:

- **Aspose.GIS for .NET** telepítve (lásd az alábbi lépéseket).  
- .NET fejlesztői környezet (Visual Studio, VS Code vagy bármely kedvelt IDE).  
- Alapvető ismeretek a C# szintaxisról.

### Aspose.GIS telepítése .NET-hez
1. Aspose.GIS letöltése: Látogasson el a [letöltési oldalra](https://releases.aspose.com/gis/net/) és válassza ki a fejlesztői környezetéhez megfelelő verziót.  
2. Aspose.GIS telepítése: Kövesse a dokumentációban megadott telepítési útmutatót az Aspose.GIS .NET-re történő telepítéséhez a gépén.

## Névterek importálása
Ahhoz, hogy az Aspose.GIS-t a .NET projektedben használni tudd, importáld a szükséges névtereket:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 1. lépés: LinearRing objektumok létrehozása
Először **LinearRing** objektumokat kell létrehoznunk minden poligonhoz. A LinearRing egy zárt vonallánc, amely meghatározza a poligon külső határát (és opcionálisan a belső lyukakat).

```csharp
LinearRing firstRing = new LinearRing();
firstRing.AddPoint(8.5, -2.5);
firstRing.AddPoint(-8.5, 2.5);
firstRing.AddPoint(8.5, -2.5);
LinearRing secondRing = new LinearRing();
secondRing.AddPoint(7.6, -3.6);
secondRing.AddPoint(-9.6, 1.5);
secondRing.AddPoint(7.6, -3.6);
```

## 2. lépés: Poligonok létrehozása
Ezután minden LinearRinget **Polygon** objektummá alakítunk. Ezeket a poligonokat később a MultiPolygonhoz fogjuk hozzáadni.

```csharp
Polygon firstPolygon = new Polygon(firstRing);
Polygon secondPolygon = new Polygon(secondRing);
```

## 3. lépés: MultiPolygon létrehozása
Most kombináljuk a poligonokat egyetlen **MultiPolygon** geometriává. Itt történik a **poligonok hozzáadása a multipolygonhoz**.

```csharp
MultiPolygon multiPolygon = new MultiPolygon();
multiPolygon.Add(firstPolygon);
multiPolygon.Add(secondPolygon);
```

Gratulálunk! Sikeresen létrehozott egy MultiPolygon geometriát az Aspose.GIS for .NET segítségével.

## Gyakori problémák és megoldások
| Issue | Cause | Fix |
|-------|-------|-----|
| **A pontok nem zárják le a gyűrűt** | Az első és az utolsó pont különbözik. | Győződjön meg arról, hogy az első és az utolsó koordináta azonos; az Aspose.GIS automatikusan lezárja a gyűrűt, de a kifejezett lezárás elkerüli a félreértéseket. |
| **Helytelen koordináta sorrend (X, Y vs. Lon, Lat)** | A hosszúság és szélesség felcserélése. | Tartsa be az Aspose.GIS által használt (X, Y) sorrendet; X = hosszúság, Y = szélesség. |
| **A könyvtár nem található futásidőben** | Hiányzó NuGet hivatkozás vagy DLL. | Ellenőrizze, hogy az Aspose.GIS csomag hivatkozásként szerepel-e a projektfájlban, és a DLL a kimeneti mappába került-e. |

## Gyakran Ismételt Kérdések

**Q: Az Aspose.GIS for .NET alkalmas kezdőknek?**  
A: Teljesen! Az Aspose.GIS átfogó dokumentációt és oktatóanyagokat kínál, hogy minden szintű fejlesztő el tudjon kezdeni.

**Q: Kipróbálhatom az Aspose.GIS-t vásárlás előtt?**  
A: Igen, letölthet egy ingyenes próbaverziót [innen](https://releases.aspose.com/), hogy megismerje a funkciókat a vásárlás előtt.

**Q: Hol találok támogatást az Aspose.GIS-hez?**  
A: Látogasson el az Aspose.GIS fórumra [ide](https://forum.aspose.com/c/gis/33), ahol kérdéseket tehet fel és közösségi segítséget kaphat.

**Q: Van elérhető ideiglenes licenc az Aspose.GIS-hez?**  
A: Igen, ideiglenes licencet szerezhet [innen](https://purchase.aspose.com/temporary-license/) értékelési célokra.

**Q: Megvásárolhatom közvetlenül az Aspose.GIS-t?**  
A: Igen, megvásárolhatja az Aspose.GIS-t a weboldalon [innen](https://purchase.aspose.com/buy).

---

**Utolsó frissítés:** 2026-03-29  
**Tesztelve:** Aspose.GIS 24.12 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
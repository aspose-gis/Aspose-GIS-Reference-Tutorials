---
date: 2025-12-23
description: Ismerje meg, hogyan konvertálhatja a geometriát WKT formátumba változatos
  beállításokkal, állíthatja be a numerikus formátumot és módosíthatja a tizedes pontosságot
  az Aspose.GIS for .NET használatával.
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: Geometria konvertálása WKT változat opciókra az Aspose.GIS használatával
url: /hu/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Geometria átalakítása WKT változat opciókká az Aspose.GIS segítségével

## Bevezetés
A modern .NET alkalmazásokban a **geometria WKT‑re konvertálása** gyakori lépés, amikor térbeli adatokat kell cserélni más rendszerekkel vagy szöveges formátumban tárolni. Az Aspose.GIS for .NET könnyedén elvégzi ezt a konverziót, miközben teljes irányítást biztosít a WKT változat, a numerikus formátum és a tizedes pontosság felett. Ebben az útmutatóban megtanulja, hogyan konvertálja a geometriát WKT‑re, hogyan válassza ki a megfelelő változatot, és hogyan finomhangolja a kimenetet a projekt pontos követelményeihez.

## Gyors válaszok
- **Mi jelent a „geometria WKT‑re konvertálása”?** Átalakítja a geometriai objektumokat (pontok, vonalak, poligonok) a Well‑Known Text (WKT) ábrázolásba.  
- **Mely WKT változatok támogatottak?** `Iso`, `SimpleFeatureAccessOutdated`, és `ExtendedPostGis`.  
- **Hogyan szabályozhatom a tizedes pontosságot?** Használja a `NumericFormat` opciókat, például `General`, `RoundTrip` vagy `Flat`.  
- **Szükség van licencre a termeléshez?** Igen, kereskedelmi licenc szükséges a nem próbaverzió használatához.  
- **Mely .NET verziók kompatibilisek?** .NET Framework 4.0+ és .NET 5/6/7.

## Mi a „geometria WKT‑re konvertálása”?
A geometria WKT‑re konvertálása egy ember által olvasható karakterláncot hoz létre, amely leírja a térbeli objektumokat. Ez a formátum széles körben elfogadott a GIS eszközök, adatbázisok és webszolgáltatások által, így ideális adatcserére.

## Miért használja az Aspose.GIS‑t ehhez a konverzióhoz?
- **Pontosság szabályozása** – Válassza ki, hány tizedesjegyet adjon ki.  
- **Változat rugalmassága** – Illeszkedjen a downstream rendszer által igényelt pontos WKT dialektushoz.  
- **Nincsenek külső függőségek** – Tiszta .NET könyvtár, nincs natív bináris.

## Előkövetelmények
1. **Aspose.GIS for .NET** – Töltse le és telepítse a [letöltési oldalról](https://releases.aspose.com/gis/net/).  
2. **Fejlesztői környezet** – Bármelyik újabb verziója a Visual Studio-nak vagy a VS Code-nak .NET SDK-val.  
3. **Alap C# ismeretek** – Ismerje az osztályokat, objektumokat és a .NET keretrendszert.

## Névtér importálása
Először hozza be a szükséges névtereket a láthatóságba:

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

## 1. lépés: Pont objektum létrehozása
Hozzon létre egy `Point` objektumot, amelyet később **geometria WKT‑re konvertálására** használ. A pont tartalmazza a szélességi, hosszúsági fokot, valamint egy opcionális mérő (M) értéket:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## 2. lépés: Térbeli referenciarendszer (SRS) beállítása
Rendeljen hozzá egy térbeli referenciarendszert, hogy a WKT kimenet tudja, mely koordináta‑rendszert kell használni. Itt a gyakori WGS84 rendszert alkalmazzuk:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## 3. lépés: WKT változat megadása
Válassza ki a megfelelő WKT változatot, amikor **geometria WKT‑re konvertálásáról** van szó. Minden változat kissé másképp formázza a kimenetet:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## 4. lépés: Numerikus formátum szabályozása (Numerikus formátum beállítása és tizedes pontosság módosítása)
Finomhangolja a koordináták numerikus ábrázolását. A `NumericFormat` osztály lehetővé teszi a **numerikus formátum beállítását** és a **tizedes pontosság módosítását**, hogy megfeleljen az igényeinek:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## Gyakori problémák és tippek
- **Hiányzó M érték** – Ha nem szükséges a mérő, hagyja ki az `M` tulajdonságot; az ISO változat automatikusan eltávolítja.  
- **Váratlan pontosság** – Ellenőrizze, hogy a megfelelő `NumericFormat`-ot használja; a `General` megőrzi a teljes dupla pontosságot, míg a `Flat` a megadott számú tizedesjegyre kerekít.  
- **SRID nem jelenik meg** – Csak a `ExtendedPostGis` változat teszi előtagként a `SRID=`-t a kimenethez. Válassza ezt a változatot, ha a célrendszer SRID‑t vár.

## Összegzés
Az alábbi lépések követésével most már tudja, hogyan **konvertálja a geometriát WKT‑re**, hogyan válassza ki a megfelelő változatot, és hogyan szabályozza pontosan a numerikus kimenetet. Ez rugalmasságot biztosít az Aspose.GIS bármely GIS munkafolyamathoz, adatbázishoz vagy WKT‑t fogyasztó webszolgáltatáshoz való integrálásához.

## GYIK
### Az Aspose.GIS kompatibilis minden .NET verzióval?
Igen, az Aspose.GIS támogatja a .NET Framework 4.0 és újabb verzióit.

### Használhatom az Aspose.GIS‑t kereskedelmi projektekhez?
Igen, az Aspose.GIS használható személyes és kereskedelmi projektekhez egyaránt.

### Az Aspose.GIS támogatja-e más térbeli adatformátumokat?
Igen, az Aspose.GIS számos térbeli adatformátumot támogat, többek között az ESRI Shapefile, a GeoJSON és a KML formátumokat.

### Van ingyenes próbaverzió az Aspose.GIS‑hez?
Igen, letöltheti az Aspose.GIS ingyenes próbaverzióját [innen](https://releases.aspose.com/).

### Hol kaphatok segítséget vagy támogatást az Aspose.GIS‑hez?
Kérdéseit a Aspose.GIS közösséghez teheti fel, vagy segítséget kérhet a [fórumon](https://forum.aspose.com/c/gis/33).

## Gyakran Ismételt Kérdések
**K: Hogyan exportálhatok egy Geometry gyűjteményt egyetlen WKT karakterláncra?**  
V: Iteráljon a gyűjtemény minden geometriai elemén, és fűzze össze a `AsText` eredményeiket, opcionálisan vesszőkkel vagy újsorokkal elválasztva.

**K: Megváltoztathatom az SRID‑t anélkül, hogy a koordinátákat módosítanám?**  
V: Igen, állítsa be a `SpatialReferenceSystem` tulajdonságot a kívánt SRID‑re; a koordinátaértékek változatlanok maradnak.

**K: Mi történik, ha nem támogatott WKT változatot használok?**  
V: Az Aspose.GIS `ArgumentException`‑t dob. Mindig ellenőrizze a változatot a `WktVariant` enum értékeivel.

---

**Utolsó frissítés:** 2025-12-23  
**Tesztelve:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
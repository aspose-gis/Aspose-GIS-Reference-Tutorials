---
date: 2025-12-20
description: Tanulja meg, hogyan hozhat létre lyukkal rendelkező sokszöget az Aspose.GIS
  for .NET használatával. Ez az útmutató megmutatja, hogyan készíthet lyukat a sokszögben,
  és hogyan dolgozhat térbeli adatokkal.
linktitle: Create Polygon with Hole Geometry
second_title: Aspose.GIS .NET API
title: Polygon létrehozása lyukkal rendelkező geometriával az Aspose.GIS segítségével
url: /hu/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Polygon lyukas geometria létrehozása az Aspose.GIS segítségével

## Bevezetés
Ebben az útmutatóban **polygon lyukas** geometriát hozunk létre az Aspose.GIS for .NET segítségével. Legyen szó térképező alkalmazás fejlesztéséről, térbeli elemzésről vagy GIS szolgáltatások számára történő adat előkészítésről, a lyuk beágyazása egy polygonba alapvető tudás. Lépésről‑lépésre végigvezetünk a környezet beállításától a végleges polygon objektum generálásáig.

## Gyors válaszok
- **Mit jelent a „polygon lyukas létrehozása”?** Ez azt jelenti, hogy egy olyan polygon-t építünk, amely egy vagy több belső gyűrűt (lyukat) tartalmaz, amelyek nem számítanak a területbe.
- **Melyik könyvtár kezeli ezt?** Az Aspose.GIS for .NET teljes támogatást nyújt a külső és belső gyűrűkhöz.
- **Szükség van licencre?** Fejlesztéshez egy ingyenes próba verzió is elegendő; termeléshez kereskedelmi licenc szükséges.
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Mennyi időt vesz igénybe?** Általában 10 perc alatt megvalósítható és tesztelhető.

## Mi a „polygon lyukas létrehozása”?
A lyukas polygon létrehozása egy **külső gyűrű** (exterior ring) definiálását jelenti, amely az átfogó határt körvonalazza, valamint egy vagy több **belső gyűrű** (interior ring) hozzáadását, amelyek üres területeket vág ki. A belső gyűrűket gyakran *lyukaknak* nevezzük, mivel a polygon felületének részét nem képezik.

## Miért érdemes lyukat létrehozni a polygonban az Aspose.GIS használatával?
- **Pontos térbeli modellezés:** Valós világban előforduló elemek, például tavak földparcellákon belül vagy udvarok épületeken belül lyukakat igényelnek.
- **Interoperabilitás:** Olyan formátumok, mint a Shapefile, GeoJSON és GML natívan támogatják a belső gyűrűket; az Aspose.GIS megőrzi ezeket.
- **Teljesítmény:** A könyvtár kezeli a geometriai érvényességet, így nem kell saját validációs kódot írni.

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg róla, hogy a következő előfeltételek rendelkezésre állnak:
1. Aspose.GIS for .NET könyvtár: Letöltheti **[innen](https://releases.aspose.com/gis/net/)**.
2. Fejlesztői környezet: Telepítve legyen Visual Studio vagy bármely más .NET IDE.

## Névterek importálása
Először importálni kell a szükséges névtereket az Aspose.GIS funkciók használatához. Így tehetjük meg:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Most pedig lépjünk tovább a lyukas polygon geometria létrehozásához az Aspose.GIS for .NET segítségével.

## 1. lépés: Polygon objektum létrehozása
Először egy üres `Polygon` objektumot hozunk létre, amely később a külső és belső gyűrűket is tartalmazni fogja.

```csharp
Polygon polygon = new Polygon();
```

## 2. lépés: Külső gyűrű definiálása
A külső gyűrű határozza meg a polygon külső határát. Adjunk hozzá pontokat óramutató járásával megegyező sorrendben, hogy zárt alakzatot kapjunk.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## 3. lépés: Belső gyűrű (lyuk) definiálása
Ezután létrehozzuk a belső gyűrűt – ez lesz a **lyuk**, amely a polygon területéből ki lesz zárva. A pontokat általában az óramutató járásával ellentétes sorrendben adjuk hozzá, de az Aspose.GIS automatikusan kezeli az orientációt.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## 4. lépés: Külső gyűrű hozzárendelése és belső gyűrű hozzáadása a polygonhoz
Végül csatoljuk a külső gyűrűt a polygonhoz, majd adjuk hozzá a belső gyűrűt (a lyukat). Az `AddInteriorRing` metódus többször is meghívható, ha több lyukra van szükség.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| A lyuk nem jelenik meg a GIS nézőben | A belső gyűrű orientációja fordított | Győződjön meg róla, hogy a pontok a külső gyűrűtől ellentétes irányban vannak (óramutató járásával ellentétes). |
| Polygon érvénytelen hiba | A gyűrűk nincsenek lezárva (első ≠ utolsó pont) | Ismételje meg az első pontot az utolsóként minden gyűrűben (ahogy fent látható). |
| Váratlanul üres geometria | Elfelejtette beállítani az `ExteriorRing`‑et a belső gyűrűk hozzáadása előtt | Először állítsa be a `polygon.ExteriorRing`‑et, majd hívja meg az `AddInteriorRing`‑t. |

## Összegzés
Gratulálunk! Sikeresen megtanulta, hogyan kell **polygon lyukas** geometriát létrehozni az Aspose.GIS for .NET segítségével. Ez a technika alapvető számos térinformatikai szituációban, ahol összetett alakzatokat kell belső üregekkel ábrázolni.

## Gyakran feltett kérdések
### 1. Mi az Aspose.GIS?
Az Aspose.GIS egy .NET könyvtár, amely lehetővé teszi a fejlesztők számára a térinformatikai adatok kezelését, beleértve a különféle formátumok létrehozását, olvasását és módosítását.

### 2. Használhatom az Aspose.GIS‑t kereskedelmi projektekben?
Igen, az Aspose.GIS‑t személyes és kereskedelmi projektekben egyaránt használhatja licenc vásárlásával. További részletekért látogasson el **[ide](https://purchase.aspose.com/buy)**.

### 3. Van ingyenes próba verziója az Aspose.GIS‑nek?
Igen, ingyenes próba verziót tölthet le **[innen](https://releases.aspose.com/)**.

### 4. Hol találok támogatást az Aspose.GIS‑hez?
Támogatást a **[Aspose.GIS fórumon](https://forum.aspose.com/c/gis/33)** talál.

### 5. Hogyan szerezhetek ideiglenes licencet az Aspose.GIS‑hez?
Ideiglenes licencet igényelhet **[innen](https://purchase.aspose.com/temporary-license/)**.

---

**Utoljára frissítve:** 2025-12-20  
**Tesztelve:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
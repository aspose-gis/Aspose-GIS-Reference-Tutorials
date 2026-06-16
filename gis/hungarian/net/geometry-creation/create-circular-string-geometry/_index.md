---
date: 2026-02-15
description: Tanulja meg, hogyan hozhat létre vektor réteget és adhat hozzá körkörös
  vonalgeometriát az Aspose.GIS for .NET használatával – egy gyors módja a GIS‑alkalmazások
  építésének.
linktitle: Create Circular String Geometry
second_title: Aspose.GIS .NET API
title: Vektor réteg és kör alakú string létrehozása az Aspose.GIS .NET-hez
url: /hu/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

 shortcodes.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektoros réteg és körkörös vonal geometria létrehozása az Aspose.GIS for .NET segítségével

## Bevezetés
Ha .NET platformon GIS alkalmazást építesz, az első lépés gyakran **vektoros réteg** objektumok létrehozása, amelyek tárolják a térbeli elemeket. Az Aspose.GIS for .NET egyszerűvé teszi ezt a folyamatot, és lehetővé teszi, hogy ezeket a rétegeket fejlett geometriákkal, például körkörös vonalakkal gazdagítsd. Ebben az útmutatóban pontosan megtanulod, hogyan **hozz létre vektoros réteget**, **adj hozzá körkörös vonal** geometriát, és mentsd el az eredményt Shapefile‑ként – mindezt tiszta, termelés‑kész C# kóddal.

## Gyors válaszok
- **Mi jelent a “create vector layer”?** Új tárolót (réteget) hoz létre, amely térbeli elemeket, például pontokat, vonalakat vagy poligonokat képes tárolni.  
- **Melyik osztály képviseli a körkörös vonalat?** `CircularString` a `Aspose.Gis.Geometries`‑ból.  
- **Menthetem a réteget Shapefile‑ként?** Igen – a réteg létrehozásakor használd a `Drivers.Shapefile`‑t.  
- **Szükségem van licencre a fejlesztéshez?** Ideiglenes licenc elegendő az értékeléshez; teljes licenc szükséges a termeléshez.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Mi az a “create vector layer”?
A vektoros réteg a vektoros elemek (pontok, vonalak, poligonok) logikai csoportosítása, amely egyetlen adatforrásban tárolódik. Az Aspose.GIS‑ben egy réteget a `VectorLayer.Create` hívásával hozol létre, megadva a célfájl útvonalát és a kívánt drivert (például Shapefile). Miután a réteg létezik, hozzáadhatsz elemeket, hozzárendelhetsz geometriákat, és végrehajthatsz térbeli műveleteket.

## Miért adjunk hozzá körkörös vonalat?
A körkörös vonalak egy **lineáris geometria** típus, amely íveket közelít pontsorozattal. Hasznosak görbe utak, folyó kanyarok vagy bármely olyan elem ábrázolásához, ahol sima ív szükséges sok kis vonal szegmens helyett.

## Előfeltételek
- **.NET Framework vagy .NET Core** telepítve van a gépeden.  
- **Aspose.GIS for .NET** könyvtár – töltsd le a hivatalos oldalról **[itt](https://releases.aspose.com/gis/net/)**.  
- IDE, például **Visual Studio** vagy **JetBrains Rider**.  
- Alapvető ismeretek a **C#** programozásban.

## Névtér importálása
Add hozzá a szükséges névtereket a C# fájlodhoz:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Lépésről‑lépésre útmutató

### 1. lépés: Az output fájl útvonalának meghatározása
Állítsd be azt a helyet, ahová a Shapefile‑t írni fogja.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

Cseréld le a `"Your Document Directory"`‑t a rendszereden lévő tényleges mappára.

### 2. lépés: **Vektoros réteg létrehozása**
Nyiss egy `VectorLayer`‑t a `Create` metódussal. Ez a **create vector layer** művelet központja.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### 3. lépés: Új elem (feature) létrehozása
Egy elem egyetlen térbeli rekordot képvisel a rétegen belül.

```csharp
    var feature = layer.ConstructFeature();
```

### 4. lépés: Körkörös vonal geometria felépítése
Add hozzá a pontokat, amelyek meghatározzák a görbe alakot. A pontok sorozata egy ívet hoz létre, amely ugyanazon a helyen kezdődik és végződik, így zárt körkörös vonalat alkot.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### 5. lépés: Geometria hozzárendelése és az elem hozzáadása a réteghez
Kapcsold össze a geometriát az elemmel, és tárold a rétegben.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

Amikor a `using` blokk véget ér, a réteg automatikusan kiíródik a lemezen lévő Shapefile‑ba.

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|----------|----------|
| **Érvénytelen fájl útvonal** | Győződj meg arról, hogy a könyvtár létezik, és van írási jogosultságod. |
| **CircularString egyenes vonalként jelenik meg** | Ellenőrizd, hogy a pontok a megfelelő sorrendben vannak hozzáadva; az első és az utolsó pontnak azonosnak kell lennie egy zárt alakhoz. |
| **Licenc kivétel** | Alkalmazz ideiglenes licencet fejlesztés közben, vagy vásárolj teljes licencet a termeléshez. |

## Gyakran Ismételt Kérdések

### Az Aspose.GIS for .NET kompatibilis-e a .NET Framework minden verziójával?
Igen, az Aspose.GIS for .NET úgy van tervezve, hogy széles .NET verziók körében működjön, a Framework 4.5‑től a legújabb .NET 8 kiadásokig.

### Integrálhatom az Aspose.GIS for .NET‑t más GIS könyvtárakkal?
Természetesen! Olvashatsz adatokat más könyvtárakkal, manipulálhatod őket az Aspose.GIS‑szel, majd visszaírhatod, köszönhetően a rugalmas API‑nak.

### Támogatja az Aspose.GIS for .NET a térbeli adatok megjelenítését?
Igen, a könyvtár tartalmaz renderelési segédeszközöket, amelyekkel térképeket és vizuális ábrázolásokat hozhatsz létre a geometriáidból.

### Van közösségi fórum, ahol segítséget kérhetek az Aspose.GIS for .NET használatához?
Igen, felkeresheted az Aspose.GIS fórumot **[itt](https://forum.aspose.com/c/gis/33)** a kérdések feltevéséhez és tapasztalatok megosztásához.

### Kaphatok ideiglenes licencet az Aspose.GIS for .NET értékeléséhez?
Természetesen! Ideiglenes értékelő licenc elérhető **[itt](https://purchase.aspose.com/temporary-license/)**.

### Hogyan adhatok hozzá összetettebb geometriákat (pl. MultiLineString) ugyanahhoz a réteghez?
Hozd létre a megfelelő geometria objektumot (pl. `MultiLineString`), töltsd fel egyedi `LineString` objektumokkal, rendeld hozzá a `feature.Geometry`‑hez, és add hozzá az elemet úgy, ahogy a körkörös vonallal is tettük.

## GYIK (Gyors‑referencia)

**K:** Hogyan **hozzak létre vektoros réteget** programozottan?  
**V:** Hívd meg a `VectorLayer.Create(path, Drivers.Shapefile)`‑t (vagy más drivert) egy `using` blokkban.

**K:** Melyik metódus ad pontokat a körkörös vonalhoz?  
**V:** Használd a `circularString.AddPoint(x, y)`‑t minden koordinátához.

**K:** Tárolhatok több geometriát ugyanabban a rétegben?  
**V:** Igen, minden geometriához hozz létre egy új elemet, és add hozzá a `layer.Add(feature)`‑val.

**K:** Mit tegyek, ha a Shapefile nem jön létre?  
**V:** Ellenőrizd, hogy a kimeneti könyvtár létezik, van írási jogosultságod, és a driver (`Drivers.Shapefile`) helyesen van hivatkozva.

**K:** Szükséges licenc az értékelő verzióhoz?  
**V:** Ideiglenes licenc elegendő fejlesztéshez és teszteléshez; teljes licenc szükséges a termelési környezethez.

## Összegzés
Ezeket a lépéseket követve most már tudod, hogyan **hozz létre vektoros réteg** objektumokat, és gazdagítsd őket **körkörös vonal** geometriával az Aspose.GIS for .NET segítségével. Ez az alap lehetővé teszi, hogy gazdagabb GIS megoldásokat építs – legyen szó közlekedési hálózatok térképezéséről, környezeti adatok vizualizálásáról vagy egyedi térbeli elemző eszközök fejlesztéséről.

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
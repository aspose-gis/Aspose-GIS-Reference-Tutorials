---
date: 2025-12-21
description: Ismerje meg, hogyan hozhat létre vektor réteget, állíthatja be a linearizációs
  toleranciát, és adhat hozzá elemet a réteghez az Aspose.GIS for .NET használatával.
  Kövesse ezt a lépésről‑lépésre útmutatót a GeoJSON fájlok exportálásához.
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: Vektor réteg létrehozása és a linearizációs tolerancia beállítása az Aspose.GIS
  for .NET használatával
url: /hu/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektor réteg létrehozása és a linearizációs tolerancia beállítása az Aspose.GIS for .NET használatával

## Bevezetés
Ha **vektor réteg** fájlokat kell létrehoznod, a görbe pontosságát szabályozni, és az eredményt GeoJSON dokumentumként exportálni, az Aspose.GIS for .NET egyszerűvé teszi ezt. Ebben az útmutatóban megtanulod, hogyan konfigurálhatod a GeoJSON beállításokat, állíthatod be a linearizációs toleranciát, és **jellemzőt adhatsz a réteghez** objektumokhoz – mindezt tiszta és termelésre kész kóddal.

## Gyors válaszok
- **Mit jelent a „vektor réteg létrehozása”?** Új GIS vektor adatkészletet hoz létre (pl. GeoJSON fájlt), amely geometriákat és attribútumokat tud tárolni.  
- **Hogyan állítható be a tolerancia?** Használd a `LinearizationTolerance` tulajdonságot a `GeoJsonOptions` osztályban.  
- **Exportálhatok GeoJSON fájlt?** Igen – egyszerűen hozz létre egy `VectorLayer`‑t a `Drivers.GeoJson` meghajtóval.  
- **Szükség van licencre?** Egy érvényes Aspose.GIS licenc feloldja az összes funkciót; egy ideiglenes licenc elegendő értékeléshez.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Mi a „vektor réteg létrehozása”?
A vektor réteg létrehozása egy új GIS tároló (például GeoJSON fájl) inicializálását jelenti, amely képes pont, vonal és poligon geometriákat tartalmazni. Ez a réteg lesz a célpont minden általad épített geometria és az azokhoz csatolt attribútumok számára.

## Miért konfiguráljuk a GeoJSON beállításokat?
A GeoJSON beállítások – különösen a **linearizációs tolerancia** – konfigurálása biztosítja, hogy a görbe geometriák (pl. `CircularString`) olyan pontossággal legyenek közelítve, amely megfelel az alkalmazásod pontossági követelményeinek. Ez a lépés kulcsfontosságú, amikor később **GeoJSON fájlt exportálsz** webes térképekhez vagy térbeli elemzésekhez.

## Előkövetelmények
Mielőtt elkezdenénk, győződj meg róla, hogy a következők rendelkezésre állnak:

1. **Visual Studio** telepítve (bármely friss verzió).  
2. **Aspose.GIS licenc** (vagy ideiglenes értékelő kulcs).  
3. **Aspose.GIS for .NET** könyvtár letöltve és a projektedhez hivatkozva.  
4. Alapvető ismeretek a **C#** nyelvről.

## Névtér importálása
Először importáld a szükséges névtereket, hogy a fordító tudja, honnan származnak a GIS osztályok:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Lépésről‑lépésre útmutató

### 1. lépés: GeoJSON beállítások konfigurálása (hogyan állítsuk be a toleranciát)
Létrehozunk egy `GeoJsonOptions` objektumot, és megadjuk az Aspose.GIS‑nek, hogy mennyire legyen közel a linearizált geometria az eredeti görbéhez.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### 2. lépés: Kimeneti útvonal meghatározása (hogyan exportáljunk GeoJSON‑t)
Add meg, hogy a létrehozott fájl hová kerüljön mentésre. Cseréld le a helyőrzőt a saját mappádra.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### 3. lépés: **Vektor réteg létrehozása** a konfigurált beállításokkal
Most ténylegesen **vektor réteget hozunk létre** a `VectorLayer.Create` metódussal. A `using` blokk biztosítja az erőforrások megfelelő felszabadítását.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### 4. lépés: Geometria felépítése (pl. körív)
Itt egy mintageometriát építünk – egy `CircularString`‑et. Ezt bármely érvényes WKT‑vel helyettesítheted.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### 5. lépés: **Jellemző hozzáadása a réteghez** és mentés
Végül létrehozunk egy jellemzőt, hozzárendeljük a geometriát, és hozzáadjuk a réteghez. Ez a **jellemző hozzáadása a réteghez** művelet központja.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Amikor a `using` blokk véget ér, a réteg automatikusan a `path`‑ben megadott fájlba kerül, így egy használatra kész GeoJSON fájlt kapsz.

## Gyakori problémák és tippek
- **Helytelen útvonal** – Győződj meg róla, hogy a könyvtár létezik, és van írási jogosultságod.  
- **Túl alacsony tolerancia** – A `LinearizationTolerance` nagyon kis értékre állítása drámaian megnövelheti a fájlméretet. Állítsd a pontossági igényeidnek megfelelően.  
- **Licenc hibák** – Ha licencfigyelmeztetést látsz, ellenőrizd, hogy a licencfájl a bármely Aspose.GIS hívás előtt megfelelően be legyen töltve.

## Gyakran feltett kérdések

**Q: Az Aspose.GIS for .NET kompatibilis más .NET keretrendszerekkel?**  
A: Igen, működik .NET Framework, .NET Core és .NET 5/6/7 környezetben.

**Q: Használhatom az Aspose.GIS‑t kereskedelmi projektekben?**  
A: Természetesen. A kereskedelmi licenc eltávolítja az összes értékelési korlátozást.

**Q: Az Aspose.GIS támogat más GIS formátumokat is a GeoJSON‑on kívül?**  
A: Igen, támogatja a Shapefile, KML, GML és még sok más formátumot.

**Q: Elérhető próba verzió?**  
A: Ingyenes próbaverzió letölthető az Aspose weboldaláról.

**Q: Hol kaphatok támogatást?**  
A: Használd az Aspose fórumokat vagy a források szekcióban található támogatási linket.

## Összegzés
Ezekkel a lépésekkel most már tudod, hogyan **vektor réteget hozz létre**, hogyan állítsd be a linearizációs toleranciát, és hogyan **jellemzőt adj a réteghez** a zökkenőmentes **GeoJSON fájl exportálás** érdekében. Fedezz fel további geometria típusokat és attribútumkezelést, hogy teljes mértékben kiaknázhasd az Aspose.GIS lehetőségeit .NET GIS projektjeidben.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Utoljára frissítve:** 2025-12-21  
**Tesztelt verzió:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose  

---
---
date: 2026-08-24
description: Ismerje meg, hogyan hozhat létre vektor réteg .NET-et, és adhat hozzá
  circular string geometry-t az Aspose.GIS segítségével – egy gyors, termelésre kész
  mód GIS alkalmazások építéséhez.
keywords:
- create vector layer .net
- circular string geometry
- Aspose.GIS .NET
- GIS vector layer
- C# geometry
lastmod: 2026-08-24
linktitle: Circular String Geometry létrehozása
og_description: Ismerje meg, hogyan hozhat létre vektor réteg .NET-et, és adhat hozzá
  circular string geometry-t az Aspose.GIS segítségével – egy gyors, termelésre kész
  mód GIS alkalmazások építéséhez.
og_image_alt: Tutorial showing how to create a vector layer and circular string geometry
  in Aspose.GIS for .NET
og_title: Vektor réteg .NET létrehozása circular string geometry-val
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to create vector layer .NET and add circular string geometry
    with Aspose.GIS – a fast, production‑ready way to build GIS applications.
  headline: Create vector layer .NET with circular string geometry
  type: TechArticle
- description: Learn how to create vector layer .NET and add circular string geometry
    with Aspose.GIS – a fast, production‑ready way to build GIS applications.
  name: Create vector layer .NET with circular string geometry
  steps:
  - name: Define the output file path
    text: Set the location where the Shapefile will be written. Use an absolute or
      relative path that your application can write to. Replace `"Your Document Directory"`
      with the actual folder path on your system.
  - name: Create vector layer
    text: '`VectorLayer.Create` opens (or creates) a new vector layer backed by the
      specified driver. This is the core of the **create vector layer .NET** operation.'
  - name: Construct a new feature
    text: A feature represents a single spatial record inside the layer. The `Feature`
      class holds attribute data and a geometry object.
  - name: Build the circular string geometry
    text: '`CircularString` is the class that models an arc‑based line. You add points
      with `AddPoint(x, y)`; the first and last points should be identical for a closed
      shape.'
  - name: Assign geometry and add the feature to the layer
    text: Link the geometry to the feature and store it in the layer. When the `using`
      block ends, the layer is automatically flushed to the Shapefile on disk. When
      the `using` block ends, the layer is automatically flushed to the Shapefile
      on disk.
  type: HowTo
- questions:
  - answer: It creates a new container (layer) that can hold spatial features like
      points, lines, or polygons.
    question: What does “create vector layer” mean?
  - answer: '`CircularString` from `Aspose.Gis.Geometries`.'
    question: Which class represents a circular string?
  - answer: Yes – use `Drivers.Shapefile` when creating the layer.
    question: Can I save the layer as a Shapefile?
  - answer: A temporary license works for evaluation; a full license is required for
      production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create vector layer
- circular string
- Aspose.GIS
- .NET GIS
- C# geometry
title: Vektor réteg .NET létrehozása circular string geometry-val
url: /hu/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektor réteg létrehozása .NET-ben körkörös sztring geometriával

## Bevezetés
Ha GIS alkalmazást építesz a .NET platformon, az első lépés gyakran **vektor réteg .NET** objektumok létrehozása, amelyek tárolják a térbeli elemeket. Az Aspose.GIS for .NET egyszerűvé teszi ezt a folyamatot, és lehetővé teszi, hogy ezeket a rétegeket fejlett geometriákkal, például körkörös sztringekkel gazdagítsd. Ebben az útmutatóban pontosan megtanulod, hogyan **hozz létre vektor réteget**, **adj hozzá körkörös sztring** geometriát, és mentsd az eredményt Shapefile‑ként – mindezt tiszta, termelés‑kész C# kóddal.

## Gyors válaszok
- **Mi jelent a “create vector layer”?** Egy új tárolót (réteget) hoz létre, amely térbeli elemeket, például pontokat, vonalakat vagy poligonokat tud tárolni.  
- **Melyik osztály képviseli a körkörös sztringet?** `CircularString` a `Aspose.Gis.Geometries`‑ből.  
- **Menthetjük a réteget Shapefile‑ként?** Igen – a réteg létrehozásakor használd a `Drivers.Shapefile`‑t.  
- **Szükség van licencre a fejlesztéshez?** Egy ideiglenes licenc elegendő értékeléshez; a termeléshez teljes licenc szükséges.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Mi a “create vector layer”?
A vektor réteg a vektor elemek – pontok, vonalak vagy poligonok – logikai csoportosítása, amelyek egyetlen adatforrásban tárolódnak. Konténerként működik, amely lehetővé teszi a térbeli rekordok hatékony kezelését, lekérdezését és tárolását. Az Aspose.GIS‑ben egyet a `VectorLayer.Create` hívásával hozol létre, megadva a célfájl útvonalát és egy, például a Shapefile‑t használó drivert.

## Miért adjunk hozzá körkörös sztringet?
A körkörös sztringek lehetővé teszik, hogy sima íveket modellezzünk sokkal kevesebb csúccsal, mint egy hagyományos vonallánc. **Ideálisak ívelt utak, folyó kanyarok vagy bármely olyan elem ábrázolására, ahol valódi ív szükséges a fájlméret növelése nélkül.** A körkörös sztring használata akár 80 %-kal csökkentheti a tárolt pontok számát a sűrű vonallánc‑approximációhoz képest, ami javítja a tárolási hatékonyságot és a megjelenítési teljesítményt a legtöbb GIS nézőben.

## Előfeltételek
- **.NET Framework vagy .NET Core** telepítve van a gépeden.  
- **Aspose.GIS for .NET** könyvtár – töltsd le a hivatalos oldalról **[letöltés Aspose.GIS for .NET](https://releases.aspose.com/gis/net/)**.  
- IDE, például **Visual Studio** vagy **JetBrains Rider**.  
- Alapvető ismeretek a **C#** programozásban.

## Névterek importálása
Add the required namespaces to your C# file:

A `Aspose.Gis` névtér tartalmazza a core GIS típusokat, míg a `Aspose.Gis.Geometries` geometriák osztályait, például a `CircularString`‑t. Az importálásuk lehetővé teszi az API használatát a fájl egészében.

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

### 1. lépés: A kimeneti fájl útvonalának meghatározása
Állítsd be azt a helyet, ahová a Shapefile‑t írni fogja. Használj abszolút vagy relatív útvonalat, amelyre az alkalmazásod írási jogosultsággal rendelkezik.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

Cseréld le a `"Your Document Directory"`‑t a rendszereden lévő tényleges mappára.

### 2. lépés: Vektor réteg létrehozása
`VectorLayer.Create` megnyit (vagy létrehoz) egy új vektor réteget a megadott driverrel. Ez a **vektor réteg .NET** művelet központja.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### 3. lépés: Új elem létrehozása
Egy elem egyetlen térbeli rekordot képvisel a rétegen belül. A `Feature` osztály tárolja az attribútum adatokat és egy geometriai objektumot.

```csharp
    var feature = layer.ConstructFeature();
```

### 4. lépés: Körkörös sztring geometria felépítése
`CircularString` az az osztály, amely ív‑alapú vonalat modellez. Pontokat adsz hozzá a `AddPoint(x, y)`‑vel; a zárt alakzat esetén az első és az utolsó pontnak azonosnak kell lennie.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### 5. lépés: Geometria hozzárendelése és az elem hozzáadása a réteghez
Kapcsold össze a geometriát az elemmel, és tárold a rétegben. Amikor a `using` blokk véget ér, a réteg automatikusan kiírásra kerül a lemezen lévő Shapefile‑ba.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

Amikor a `using` blokk véget ér, a réteg automatikusan kiírásra kerül a lemezen lévő Shapefile‑ba.

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|----------|----------|
| **Érvénytelen fájl útvonal** | Győződj meg róla, hogy a könyvtár létezik, és van írási jogosultságod. |
| **CircularString egyenes vonalként jelenik meg** | Ellenőrizd, hogy a pontok a megfelelő sorrendben vannak hozzáadva; a zárt alakzat esetén az első és az utolsó pontnak azonosnak kell lennie. |
| **Licenc kivétel** | Alkalmazz ideiglenes licencet fejlesztés közben, vagy vásárolj teljes licencet a termeléshez. |
| **Teljesítménycsökkenés nagy adathalmazoknál** | Az Aspose.GIS adatfolyamot használ, így biztonságosan feldolgozhatsz 500 + elemet tartalmazó fájlokat anélkül, hogy az egész adathalmazt memóriába töltenéd. |

## Gyakran ismételt kérdések

### Az Aspose.GIS for .NET kompatibilis-e a .NET Framework minden verziójával?
Igen, az Aspose.GIS for .NET úgy van tervezve, hogy a .NET különböző verzióival működjön, a Framework 4.5‑től a legújabb .NET 8 kiadásokig.

### Integrálhatom az Aspose.GIS for .NET‑et más GIS könyvtárakkal?
Természetesen! Más könyvtárakkal beolvashatsz adatokat, az Aspose.GIS‑sel manipulálhatod őket, majd visszaírhatod, köszönhetően a rugalmas API‑nak.

### Támogatja az Aspose.GIS for .NET a térbeli adatok megjelenítését?
Igen, a könyvtár tartalmaz renderelési segédeszközöket, amelyek lehetővé teszik térképek és a geometriák vizuális ábrázolásának létrehozását.

### Van közösségi fórum, ahol segítséget kérhetek az Aspose.GIS for .NET‑hez?
Igen, felkeresheted az Aspose.GIS fórumot **[Aspose GIS fórum](https://forum.aspose.com/c/gis/33)** a kérdések feltevéséhez és tapasztalatok megosztásához.

### Kaphatok ideiglenes licencet az Aspose.GIS for .NET értékeléséhez?
Természetesen! Ideiglenes értékelő licenc érhető el **[ideiglenes licenc oldal](https://purchase.aspose.com/temporary-license/)**.

### Hogyan adhatok hozzá összetettebb geometriákat (pl. MultiLineString) ugyanahhoz a réteghez?
Hozz létre megfelelő geometriai objektumot (pl. `MultiLineString`), töltsd fel egyedi `LineString` objektumokkal, rendeld hozzá a `feature.Geometry`‑hez, és add hozzá az elemet ugyanúgy, ahogy a körkörös sztringet is.

## GYIK (gyors‑referencia)

**K:** Hogyan **hozzak létre vektor réteget** programozottan?  
**V:** Hívd meg a `VectorLayer.Create(path, Drivers.Shapefile)`‑t (vagy más drivert) egy `using` blokkban.

**K:** Melyik metódus ad pontokat egy körkörös sztringhez?  
**V:** Használd a `circularString.AddPoint(x, y)`‑t minden koordinátához.

**K:** Tárolhatok több geometriát ugyanabban a rétegben?  
**V:** Igen, hozz létre egy új elemet minden geometriához, és add hozzá a réteghez a `layer.Add(feature)`‑el.

**K:** Mit tegyek, ha a Shapefile nem jön létre?  
**V:** Ellenőrizd, hogy a kimeneti könyvtár létezik, van írási jogosultságod, és a driver (`Drivers.Shapefile`) helyesen van hivatkozva.

**K:** Szükséges licenc az értékelő verzióhoz?  
**V:** Ideiglenes licenc elegendő fejlesztéshez és teszteléshez; teljes licenc szükséges a termelési környezethez.

## Következtetés
A lépések követésével most már tudod, hogyan **hozz létre vektor réteget** objektumokat, és hogyan gazdagítsd őket **körkörös sztring** geometriával az Aspose.GIS for .NET használatával. Ez az alap lehetővé teszi, hogy gazdagabb GIS megoldásokat építs – legyen szó közlekedési hálózatok térképezéséről, környezeti adatok vizualizálásáról vagy egyedi térbeli analitikai eszközök fejlesztéséről. Következő lépésként fedezd fel a többi geometriai típust, például a `MultiPolygon`‑t, vagy kísérletezz térbeli indexeléssel a lekérdezési teljesítmény növelése érdekében.

---

**Last Updated:** 2026-08-24  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Kapcsolódó útmutatók

- [Hogyan hozzunk létre vektor réteget SRS-szel az Aspose.GIS for .NET használatával](/gis/net/layer-management/create-vector-layer-with-srs/)
- [Vektor réteg és görbe poligon létrehozása az Aspose.GIS‑szel](/gis/net/geometry-creation/create-curve-polygon-geometry/)
- [Ismerje meg, hogyan hozhat létre LineString geometriát az Aspose.GIS for .NET‑vel](/gis/net/geometry-creation/create-linestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
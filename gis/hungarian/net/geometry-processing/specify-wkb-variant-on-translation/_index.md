---
date: 2026-06-10
description: Ismerje meg, hogyan hozhat létre linestring geometriát .NET-ben, és hogyan
  konvertálhatja a geometriát WKB formátumba az Aspose.GIS for .NET használatával
  az ExtendedPostGis variánssal.
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: WKB variáns megadása fordításkor
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  headline: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  name: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  steps:
  - name: Creating a Geometry Object
    text: The `Geometry` class is Aspose.GIS's base type that represents any spatial
      object in memory. Linestring represents a series of connected points forming
      a linear geometry. In this step we instantiate a `Linestring` with a collection
      of coordinate pairs that model a simple road segment.
  - name: Generating WKB Representation
    text: '`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to
      include SRID in the output binary. Here we call the `AsBinary` method, passing
      the EWKB variant, which returns a `byte[]` containing the full binary representation.'
  - name: Writing to File
    text: '`File.WriteAllBytes` writes the binary array to disk. The resulting file
      (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB`
      function.'
  type: HowTo
- questions:
  - answer: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which
      PostGIS reads directly via `ST_GeomFromEWKB`.
    question: Can I use the EWKB file with PostGIS?
  - answer: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry
      from its binary form.
    question: Is it possible to read a WKB file back into a geometry object?
  - answer: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons,
      and many more spatial types.
    question: Does the library support other geometry types like polygons?
  - answer: Set the `SRID` property on the geometry object before calling `AsBinary`,
      e.g., `linestring.SRID = 4326;`.
    question: How do I specify a different SRID when creating the geometry?
  - answer: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6
      without modification.
    question: Will this code work on .NET Core?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Linestring geometria és WKB variáns létrehozása az Aspose.GIS for .NET-ben
url: /hu/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Líniális geometria és WKB változat létrehozása az Aspose.GIS for .NET-ben

## Bevezetés
Ha **create linestring geometry .NET**-re van szükséged, majd ezt a geometriát bináris formába szeretnéd átalakítani, az Aspose.GIS for .NET egy tiszta, nagy teljesítményű API-t biztosít, amely a .NET Framework, a .NET Core és a .NET 5/6+ környezetekben egyaránt működik. Ebben az útmutatóban minden lépést végigvezetünk – a névtér importálásától az EWKB fájl írásáig –, hogy megőrizhesd az SRID információkat, és a GIS adatokat könnyedén integráld a PostgreSQL/PostGIS vagy bármely bináris alapú munkafolyamatba.

## Gyors válaszok
- **Mi a WKB jelentése?** Well‑Known Binary, egy kompakt bináris reprezentációja a geometriai objektumoknak.  
- **Melyik WKB változat tárolja az SRID-t?** `ExtendedPostGis` (EWKB) változat közvetlenül a binárisba ágyazza be az SRID-t.  
- **Szükségem van licencre?** Ideiglenes vagy teljes Aspose.GIS licenc szükséges a termelési környezetben való használathoz.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, és .NET 5/6+.  
- **Mennyi időt vesz igénybe a megvalósítás?** Általában 10 perc alatt elkészül egy egyszerű példához.

## Mi az a Linestring geometria?
A linestring geometria egy egyszerű alakzat, amely rendezett pontlistából áll, amelyet egyenes vonal szegmensek kötnek össze. Ez a leggyakoribb ábrázolás lineáris jellemzők, például utak, csővezetékek vagy folyóvonalak számára a térbeli adatbázisokban.

## Miért kell megadni egy WKB változatot?
A megfelelő WKB változat használata garantálja, hogy a kritikus metaadatok – különösen a térbeli hivatkozási rendszer azonosítója (SRID) – együtt járnak a geometriával. A `ExtendedPostGis` (EWKB) változat a bináris payloadben tárolja az SRID-t, lehetővé téve a zökkenőmentes körkörös átvitelét a PostGIS, az Oracle Spatial vagy bármely olyan rendszer felé, amely SRID‑tudatos binárisokat vár.

## Előfeltételek
Mielőtt elkezdenéd, győződj meg róla, hogy a következőkkel rendelkezel:

### Aspose.GIS for .NET telepítése
1. Töltsd le az Aspose.GIS-t: Látogasd meg a [download link](https://releases.aspose.com/gis/net/) oldalt a legújabb csomag beszerzéséhez.  
2. Add the NuGet package to your project (pl. `Install-Package Aspose.GIS`).  

### C# programozási ismeretek
- Alapvető ismeretek a C# szintaxisról és a projekt struktúrájáról.  
- Képesség .NET konzol vagy class‑library projekt futtatására.

## Névtér importálása
`Aspose.GIS` névtér hozzáférést biztosít az összes geometriai osztályhoz.  

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Ezek a névterek biztosítják a GIS alapfunkciókat, beleértve a geometria létrehozását, átalakítását és a bináris sorosítást.

## Hogyan hozhatunk létre linestring geometriát?
A linestring létrehozásához példányosíts egy `Linestring` objektumot egy rendezett koordinátapár-listával, szükség esetén állítsd be az SRID-t, majd sorosítsd a kívánt WKB változatba. A folyamat három lépésből áll: a geometria felépítése, a `ExtendedPostGis` változat kiválasztása az SRID megőrzéséhez, és a kapott byte tömb fájlba írása.

### 1. lépés: Geometria objektum létrehozása
`Geometry` osztály az Aspose.GIS alap típusa, amely bármely térbeli objektumot ábrázol a memóriában.
Linestring egy összekapcsolt pontok sorozatát jelenti, amely lineáris geometriát alkot.  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
Ebben a lépésben egy `Linestring` példányt hozunk létre koordinátapárok gyűjteményével, amely egy egyszerű útszakaszt modellez.

### 2. lépés: WKB reprezentáció generálása
`WkbVariant.ExtendedPostGis` az az enum érték, amely azt mondja az Aspose.GIS-nek, hogy az SRID-t is belefoglalja a kimeneti binárisba.  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Itt meghívjuk az `AsBinary` metódust, átadva az EWKB változatot, amely egy `byte[]`-t ad vissza, ami a teljes bináris reprezentációt tartalmazza.

### 3. lépés: Fájlba írás
`File.WriteAllBytes` a bináris tömböt a lemezre írja.  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
Az eredményül kapott fájl (`EWkbFile.ewkb`) közvetlenül importálható egy PostGIS táblába a `ST_GeomFromEWKB` függvény segítségével.

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| **Üres fájl** | `Path.Combine` egy nem létező könyvtárra mutat. | Győződj meg róla, hogy a célkönyvtár létezik, vagy hozd létre a `Directory.CreateDirectory` segítségével. |
| **Helytelen SRID** | Az alapértelmezett `WkbVariant.Standard` használata eldobja az SRID-t. | Mindig használd a `WkbVariant.ExtendedPostGis`-t, ha az SRID megőrzése szükséges. |
| **Licenc kivétel** | Érvényes licenc nélkül futtatás termelésben. | Alkalmazz ideiglenes vagy teljes licencet a kód termelési környezetben való futtatása előtt. |

## Gyakran Ismételt Kérdések
**K: Használhatom az EWKB fájlt a PostGIS-szel?**  
A: Igen, a `ExtendedPostGis` változat EWKB-t állít elő, amely tartalmazza az SRID-t, és a PostGIS közvetlenül olvassa a `ST_GeomFromEWKB` segítségével.  

**K: Lehet WKB fájlt visszaolvasni geometria objektumba?**  
A: Természetesen. Használd a `Geometry.FromBinary(byteArray)`-t a geometria bináris formából történő helyreállításához.  

**K: Támogatja a könyvtár más geometriai típusokat, például poligonokat?**  
A: Igen, az Aspose.GIS kezeli a pontokat, linestring-eket, poligonokat, multipoligonokat és még sok más térbeli típust.  

**K: Hogyan adhatok meg másik SRID-t a geometria létrehozásakor?**  
A: Állítsd be a `SRID` tulajdonságot a geometria objektumon az `AsBinary` hívása előtt, pl. `linestring.SRID = 4326;`.  

**K: Ez a kód működik .NET Core-on?**  
A: Igen, ugyanaz az API működik a .NET Framework, a .NET Core és a .NET 5/6 környezetekben módosítás nélkül.

---

**Utolsó frissítés:** 2026-06-10  
**Tesztelve:** Aspose.GIS for .NET 23.9 (latest at time of writing)  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Geometria WKB formátumba konvertálása Aspose.GIS for .NET használatával](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [WKT változat megadása átalakításkor Aspose.GIS használatával](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [MultiLineString geometria létrehozása Aspose.GIS for .NET használatával](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
date: 2026-09-15
description: Ismerje meg, hogyan kell coordinate system hozzárendelése, a WKT Variant
  beállítása és a decimal precision szabályozása a point geometry létrehozásakor C#-ban
  az Aspose.GIS for .NET segítségével.
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: WKT Variant megadása a fordítás során
og_description: Ismerje meg, hogyan kell coordinate system hozzárendelése, a WKT Variant
  beállítása és a decimal precision szabályozása a point geometry létrehozásakor C#-ban
  az Aspose.GIS for .NET segítségével.
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: Coordinate system hozzárendelése, WKT Variant beállítása az Aspose.GIS használatával
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: Coordinate system hozzárendelése, WKT Variant beállítása az Aspose.GIS használatával
url: /hu/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Koordináta‑rendszer hozzárendelése, WKT változat beállítása az Aspose.GIS használatával

## Bevezetés
Ebben az oktatóanyagban megtanulja, hogyan **rendelje hozzá a koordináta‑rendszert**, válassza ki a megfelelő WKT változatot, és szabályozza a tizedes pontosságot, amikor **pontgeometriát hoz létre** C#‑ban az Aspose.GIS for .NET használatával. Akár térképszolgáltatást épít, térbeli elemzéseket végez, vagy adatcserét hajt végre GIS platformok között, ezek a beállítások garantálják, hogy a kimenet interoperábilis és könnyen olvasható legyen. Lépésről lépésre végigvezetjük a folyamatot.

## Gyors válaszok
- **Mi jelent a „koordináta‑rendszer hozzárendelése”?** Egy geometriát egy adott koordináta‑referencia rendszerhez, például a WGS‑84‑hez köt.  
- **Mely WKT változatok támogatottak?** Iso, SimpleFeatureAccessOutdated, és ExtendedPostGis.  
- **Hogyan szabályozhatom a tizedes pontosságot?** Használja a `NumericFormat` enumerációt (`General`, `RoundTrip`, `Flat`).  
- **Szükségem van licencre az Aspose.GIS‑hez?** Elérhető egy ingyenes próba, a kereskedelmi licenc szükséges a termelési használathoz.  
- **Mely .NET verziók kompatibilisek?** .NET Framework 4.0+ és .NET Core/5/6+.

## Mi az a „koordináta‑rendszer hozzárendelése”?
A térbeli referenciát (vagy térbeli referenciarendszert, SRS) hozzárendelése azt mondja meg a GIS szoftvernek, hogyan értelmezze a geometria koordinátaértékeit, összekapcsolva a számokat egy valós világ koordináta‑rendszerrel, például a WGS‑84‑gyel. SRS nélkül egy pont szélességi‑hosszúsági számai nem rendelkeznek valós világ jelentéssel.

## Miért kell szabályozni a WKT változatot és a numerikus formátumot?
Több mint 30 GIS eszköz specifikus WKT szintaxist vár, ezért a megfelelő változat kiválasztása megakadályozza az importálási hibákat. A numerikus formátum beállítása csökkenti a kerekítési zajt és tömöríti a kimenetet, ami különösen fontos, ha naplókat vagy fájlokat programozottan dolgoznak fel.

## Előfeltételek
1. Aspose.GIS for .NET – letöltés a [download page](https://releases.aspose.com/gis/net/) oldalról.  
2. .NET fejlesztői környezet (Visual Studio, VS Code vagy Rider).  
3. Alapvető ismeretek C#‑ban és a .NET keretrendszerben.

## Névterek importálása
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

## Hogyan kell koordináta‑rendszert hozzárendelni egy ponthoz?
Töltsön be egy `Point` példányt, majd csatolja a térbeli referenciarendszert (SRS) a `SpatialReference` osztály segítségével. Ez a kéttagú minta biztosítja, hogy a geometria exportáláskor magában hordozza a koordináta‑rendszer metaadatait, lehetővé téve a downstream eszközök számára a koordináták helyes értelmezését. A `Point` osztály egyetlen helyet reprezentál, amelyet X (hosszúság) és Y (szélesség) koordináták határoznak meg.

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## 2. lépés: térbeli referenciarendszer (SRS) hozzárendelése
Most **hozzárendeljük a térbeli referenciát** a ponthoz. A `SpatialReference` egy SRID által azonosított koordináta‑referencia rendszert képvisel. Itt a széles körben támogatott WGS‑84 rendszert használjuk (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## 3. lépés: a kívánt WKT változat megadása
Válassza ki a WKT változatot, amely megfelel az downstream alkalmazásának:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Hogyan állítsuk be a tizedes pontosságot a WKT kimenetben?
A `NumericFormat` enumeráció segítségével szabályozhatja, hány számjegy jelenjen meg a végső karakterláncban, amely olyan formázási szabályokat definiál, mint a `General`, `RoundTrip` vagy `Flat`. A `RoundTrip` kiválasztása megőrzi a koordináták teljes pontosságát a körkörös (round‑trip) esetekben, míg a `General` egy tömör ábrázolást biztosít, amely a legtöbb vizualizációs feladathoz megfelelő. A `NumericFormat` enumeráció szabályozza, hogyan formázódnak a koordináta számok a WKT kimenetben.

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Gyakori buktatók és tippek
- **Buktató:** Ha a `AsText` hívása előtt nem állítja be az SRS‑t, hiányozhat az SRID információ.  
- **Tipp:** Használja a `NumericFormat.RoundTrip`‑et, ha veszteségmentes körkörös koordináta‑átvitelt igényel.  
- **Tipp:** Az `Iso` változat a legportathatóbb; csak akkor válassza az `ExtendedPostGis`‑t, ha beágyazott SRID‑re van szükség.

## Összegzés
Most már tudja, hogyan **rendelje hozzá a koordináta‑rendszert**, válassza ki a megfelelő WKT változatot, és **állítsa be a tizedes pontosságot**, amikor **pontgeometriát hoz létre** az Aspose.GIS segítségével. Ezek a vezérlők rugalmasságot biztosítanak, hogy bármely GIS munkafolyamat pontos követelményeit teljesítse, a egyszerű vizualizációtól a nagy pontosságú térbeli elemzésig.

## Gyakran ismételt kérdések

**Q:** Az Aspose.GIS kompatibilis minden .NET verzióval?  
**A:** Igen, az Aspose.GIS támogatja a .NET Framework 4.0 és újabb verziókat, valamint a .NET Core/5/6‑ot.

**Q:** Használhatom az Aspose.GIS‑t kereskedelmi projektekhez?  
**A:** Természetesen. Kereskedelmi licenc szükséges a termelési használathoz, de ingyenes próba elérhető értékeléshez.

**Q:** Támogatja az Aspose.GIS más térbeli adatformátumokat is?  
**A:** Igen, több mint 30 formátummal működik, beleértve az ESRI Shapefile, GeoJSON, KML, CSV és még sok más formátumot.

**Q:** Hol tölthetem le az ingyenes próbaverziót?  
**A:** Az Aspose.GIS ingyenes próbaverzióját letöltheti a [Aspose.GIS free trial download page](https://releases.aspose.com/) oldalról.

**Q:** Hogyan kaphatok segítséget, ha problémáim vannak?  
**A:** Tegye fel kérdéseit az Aspose.GIS közösségi [forumon](https://forum.aspose.com/c/gis/33), ahol az Aspose munkatársai és a közösség tagjai segítenek.

---

**Last Updated:** 2026-09-15  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose

## Kapcsolódó oktatóanyagok

- [Vektor réteg létrehozása és a térbeli referenciarendszer beállítása](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Hogyan konvertáljuk a geometriát WKT‑re az Aspose.GIS for .NET használatával](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [Hogyan korlátozzuk a pontosságot a geometriák írásakor az Aspose.GIS‑szel](/gis/net/geometry-processing/limit-precision-writing-geometries/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Adja meg a WKT Variant on Translation az Aspose.GIS segítségével
linktitle: Adja meg a WKT-változatot a fordításnál
second_title: Aspose.GIS .NET API
description: Ismerje meg, hogyan adhat meg WKT-változatokat az Aspose.GIS for .NET-ben a téradat-megjelenítési formátum és a pontosság hatékony szabályozásához.
weight: 19
url: /hu/net/geometry-processing/specify-wkt-variant-on-translation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adja meg a WKT Variant on Translation az Aspose.GIS segítségével

## Bevezetés
Az Aspose.GIS for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy könnyedén dolgozzanak a földrajzi információs rendszer (GIS) adataival .NET-alkalmazásaikban. Az Aspose.GIS egyik alapvető funkciója, hogy a fordítás során megadható a jól ismert szöveg (WKT) változat, amely lehetővé teszi a felhasználók számára a térbeli adatok megjelenítésének formátumának és pontosságának szabályozását. Ebben az oktatóanyagban lépésről lépésre megvizsgáljuk, hogyan adhatunk meg WKT-változatokat az Aspose.GIS for .NET használatával.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
1. Aspose.GIS for .NET: Töltse le és telepítse az Aspose.GIS for .NET webhelyről[letöltési oldal](https://releases.aspose.com/gis/net/).
2. Fejlesztői környezet: Győződjön meg arról, hogy be van állítva .NET fejlesztői környezet.
3. Alapismeretek: C# programozási nyelv és .NET keretrendszer ismerete.

## Névterek importálása
Mielőtt az Aspose.GIS funkciót használná a kódban, importálja a szükséges névtereket:
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
## 1. lépés: Hozzon létre egy pontobjektumot
 Először hozzon létre a`Point` objektum szélességi, hosszúsági és opcionális mértékértékekkel (M):
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## 2. lépés: Térbeli referenciarendszer (SRS) beállítása
Rendeljen egy térbeli referenciarendszert (SRS) a pontobjektumhoz. Ebben a példában a WGS84 térbeli referenciarendszert használjuk:
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## 3. lépés: Adja meg a WKT-változatot
 Most adja meg a WKT változatot a fordításhoz. Az Aspose.GIS különféle WKT-változatokat támogat, beleértve`Iso`, `SimpleFeatureAccessOutdated` , és`ExtendedPostGis`. Válassza ki a megfelelő változatot az Ön igényei szerint:
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // M PONT (23,5732, 25,3421, 40,3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // PONT (23,5732, 25,3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23,5732, 25,3421, 40,3)
```
## 4. lépés: A numerikus formátum vezérlése
A WKT-ábrázolásban szabályozhatja a koordináták numerikus formátumát. Az Aspose.GIS lehetőségeket kínál a decimális pontosság megadására:
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // M PONT (23,5732 25,342099999999999 40,299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // M PONT (23,5732 25,3421 40,3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // M PONT (23,6 25,3 40,3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // M PONT (23,573 25,342 40,3)
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan adhatunk meg WKT-változatokat fordításkor az Aspose.GIS for .NET használatával. A fent vázolt lépések követésével a fejlesztők hatékonyan szabályozhatják a téradat-ábrázolások formátumát és pontosságát .NET-alkalmazásaikban, növelve a földrajzi információs rendszerek rugalmasságát és használhatóságát.
## GYIK
### Az Aspose.GIS kompatibilis a .NET összes verziójával?
Igen, az Aspose.GIS támogatja a .NET Framework 4.0 és újabb verzióit.
### Használhatom az Aspose.GIS-t kereskedelmi projektekhez?
Igen, az Aspose.GIS személyes és kereskedelmi projektekhez egyaránt használható.
### Az Aspose.GIS támogat más téradat-formátumokat?
Igen, az Aspose.GIS a téradat-formátumok széles skáláját támogatja, beleértve az ESRI Shapefile-t, a GeoJSON-t és a KML-t.
### Elérhető az Aspose.GIS ingyenes próbaverziója?
 Igen, letöltheti az Aspose.GIS ingyenes próbaverzióját a webhelyről[itt](https://releases.aspose.com/).
### Hol kaphatok segítséget vagy támogatást az Aspose.GIS-hez?
 Kérdéseit felteheti, vagy segítséget kérhet az Aspose.GIS közösségtől a címen[fórum](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

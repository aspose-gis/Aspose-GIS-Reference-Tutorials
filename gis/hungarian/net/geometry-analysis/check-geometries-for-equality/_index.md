---
title: Ellenőrizze a geometriák egyenlőségét
linktitle: Ellenőrizze a geometriák egyenlőségét
second_title: Aspose.GIS .NET API
description: Ezzel az átfogó oktatóanyaggal megtudhatja, hogyan használhatja az Aspose.GIS for .NET fájlt a .NET-alkalmazások geometriájának egyenlőségéhez.
weight: 10
url: /hu/net/geometry-analysis/check-geometries-for-equality/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ellenőrizze a geometriák egyenlőségét

## Bevezetés
Az Aspose.GIS for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy hatékonyan dolgozzanak térinformatikai adatokkal .NET-alkalmazásaikban. Akár térképészeti alkalmazásokat, akár térelemző eszközöket épít, akár térinformatikai funkciókat integrál a meglévő szoftverekbe, az Aspose.GIS biztosítja a munka elvégzéséhez szükséges eszközöket.
## Előfeltételek
Mielőtt belevágna az Aspose.GIS for .NET használatába, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
### .NET-keretrendszer telepítve
Győződjön meg arról, hogy a .NET-keretrendszer telepítve van a rendszeren. Letöltheti a Microsoft webhelyéről.
### Aspose.GIS for .NET Library
 Töltse le és telepítse az Aspose.GIS for .NET könyvtárat a[letöltési oldal](https://releases.aspose.com/gis/net/). Kövesse a dokumentációban található telepítési utasításokat.
### Fejlesztőkörnyezet
Állítsa be a kívánt fejlesztői környezetet, például a Visual Studio-t a .NET-fejlesztéshez.

## Névterek importálása
A .NET-alkalmazásban importálja a szükséges névtereket az Aspose.GIS funkció használatához:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 1. lépés: Geometriák meghatározása
Először határozza meg az összehasonlítani kívánt geometriákat. Ebben a példában két geometria van:`geometry1` és`geometry2`.
```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```
## 2. lépés: Ellenőrizze a geometriák egyenlőségét
 Most ellenőrizze, hogy a geometriák térben egyenlőek-e a`SpatiallyEquals` Az Aspose.GIS által biztosított módszer.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // Igaz
```
 Ez kinyomtatja`True` óta a konzolra`geometry1` és`geometry2` térben egyenlőek.
## 3. lépés: Módosítsa a geometriát
 Ezután módosítsuk`geometry2` új pont hozzáadásával.
```csharp
geometry2.AddPoint(3, 3);
```
## 4. lépés: Ellenőrizze újra az egyenlőséget
Most ellenőrizze újra a geometriák egyenlőségét a módosítás után.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // Hamis
```
 Ezúttal a kimenet lesz`False` mivel a geometriák térben már nem egyenlők a módosítás miatt`geometry2`.

## Következtetés
Összefoglalva, az Aspose.GIS for .NET hatékony eszközöket biztosít a térinformatikai adatok kezeléséhez .NET-alkalmazásokban. Ezt a lépésről lépésre követve könnyedén ellenőrizheti a geometriák egyenlőségét az Aspose.GIS módszerekkel.
## GYIK
### Használhatom az Aspose.GIS for .NET-et más .NET-keretrendszerekkel?
Igen, az Aspose.GIS for .NET kompatibilis a különböző .NET-keretrendszerekkel, beleértve a .NET Core-t és a .NET Standard-t.
### Létezik ingyenes próbaverzió az Aspose.GIS for .NET számára?
 Igen, letölthet egy ingyenes próbaverziót a webhelyről[kiadások oldala](https://releases.aspose.com/).
### Hol találom az Aspose.GIS for .NET dokumentációját?
 Részletes dokumentációt találhat a[Aspose.GIS dokumentációs oldal](https://reference.aspose.com/gis/net/).
### Hogyan kaphatok támogatást az Aspose.GIS for .NET számára?
 Támogatást kaphat az Aspose.GIS közösségi fórumtól[itt](https://forum.aspose.com/c/gis/33).
### Vásárolhatok ideiglenes licencet az Aspose.GIS for .NET számára?
 Igen, vásárolhat ideiglenes licencet a[vásárlási oldal](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

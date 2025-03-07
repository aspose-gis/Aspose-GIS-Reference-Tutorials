---
title: Ellenőrizze, hogy a geometria tartalmaz egy másikat
linktitle: Ellenőrizze, hogy a geometria tartalmaz egy másikat
second_title: Aspose.GIS .NET API
description: Fedezze fel az Aspose.GIS for .NET-et egy robusztus könyvtár a térinformatikai adatok zökkenőmentes integrációjához .NET-alkalmazásaiban.
weight: 14
url: /hu/net/geometry-analysis/check-geometry-contains-another/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ellenőrizze, hogy a geometria tartalmaz egy másikat

## Bevezetés
Az Aspose.GIS for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy zökkenőmentesen dolgozzanak a térinformatikai adatokkal .NET-alkalmazásaikon belül. Akár térképalkalmazást épít, akár térinformatikai elemzést végez, akár helyalapú funkciókat épít be szoftverébe, az Aspose.GIS leegyszerűsíti a folyamatot azáltal, hogy intuitív API-kat és robusztus funkcionalitást biztosít.
## Előfeltételek
Mielőtt belevágna az Aspose.GIS for .NET használatába, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
### 1. .NET fejlesztői környezet beállítása
Győződjön meg arról, hogy működő .NET fejlesztői környezet van beállítva a gépén. Ez magában foglalja a .NET SDK megfelelő telepítését és beállítását.
### 2. Aspose.GIS telepítés
 Az Aspose.GIS for .NET telepítéséhez töltse le a könyvtárat a kiadási oldalról[itt](https://releases.aspose.com/gis/net/) . Kövesse a dokumentációban található telepítési utasításokat[itt](https://reference.aspose.com/gis/net/)hogy integrálja az Aspose.GIS-t a projektjébe.
### 3. A C# alapjai
Ismerkedjen meg a C# programozási nyelvvel, mivel az Aspose.GIS for .NET elsősorban a C# nyelvvel használatos.

## Névterek importálása
A C# projektben importálja a szükséges névtereket az Aspose.GIS funkciók használatához:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 1. lépés: Geometria objektumok meghatározása
Először határozza meg a geometriai objektumokat az Aspose.GIS osztályok használatával:
```csharp
var geometry1 = new Polygon();
geometry1.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 4),
    new Point(4, 4),
    new Point(4, 0),
    new Point(0, 0),
});
geometry1.AddInteriorRing(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 3),
    new Point(3, 3),
    new Point(3, 1),
    new Point(1, 1),
}));
var geometry2 = new Point(2, 2);
```
## 2. lépés: Ellenőrizze a térbeli elzárást
Ezután ellenőrizze, hogy az egyik geometria tartalmaz-e másikat:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry2)); // Hamis
```
## 3. lépés: Adjon meg egy másik geometriát
Határozzon meg egy másik geometriai objektumot:
```csharp
var geometry3 = new Point(0.5, 0.5);
```
## 4. lépés: Ellenőrizze újra a térbeli elzárást
Ellenőrizze, hogy az újonnan definiált geometria benne van-e az első geometriában:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry3)); // Igaz
```
## 5. lépés: Egyenértékű funkcionalitás
 Értsd meg`a.SpatiallyContains(b)` egyenértékű`b.Within(a)`:
```csharp
Console.WriteLine(geometry3.Within(geometry1)); // Igaz
```

## Következtetés
Összefoglalva, az Aspose.GIS for .NET hatékony eszközöket biztosít a térinformatikai adatok kezelésére .NET-alkalmazásokban. Az útmutató követésével és a mellékelt példa felhasználásával hatékonyan végezhet térbeli elszigetelési ellenőrzéseket, és kiaknázhatja az egyéb térinformatikai funkciókat a projekteken belül.
## GYIK
### 1. kérdés: Az Aspose.GIS kompatibilis a .NET Core-al?
V: Igen, az Aspose.GIS teljes mértékben támogatja a .NET Core-t, amely lehetővé teszi térinformatikai alkalmazások fejlesztését különböző platformokon.
### 2. kérdés: Végezhetek térinformatikai elemzést az Aspose.GIS segítségével?
V: Természetesen az Aspose.GIS különféle funkciókat kínál a térinformatikai elemzéshez, beleértve a térbeli lekérdezéseket, a távolságszámításokat és a geometriai manipulációkat.
### 3. kérdés: Milyen gyakran adnak ki frissítéseket az Aspose.GIS-hez?
V: Az Aspose.GIS rendszeresen frissítéseket ad ki a teljesítmény javítása, új funkciók hozzáadása és a jelentett problémák megoldása érdekében. A kiadási oldal meglátogatásával naprakész maradhat.
### 4. kérdés: Létezik közösségi fórum az Aspose.GIS felhasználók számára?
V: Igen, csatlakozhatsz az Aspose.GIS közösségi fórumhoz[itt](https://forum.aspose.com/c/gis/33) kapcsolatba léphet más felhasználókkal, kérdéseket tehet fel, és megoszthatja tapasztalatait.
### 5. kérdés: Kipróbálhatom az Aspose.GIS-t vásárlás előtt?
 V: Természetesen felfedezheti az Aspose.GIS-t, ha letölti az ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

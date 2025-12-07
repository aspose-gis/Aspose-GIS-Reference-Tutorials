---
date: 2025-12-07
description: Tanulja meg, hogyan hajthat végre átfedési műveleteket ebben a térbeli
  átfedés oktatóanyagban az Aspose.GIS for .NET használatával. Sajátítsa el a metszetet,
  az uniót, a különbséget és a szimmetrikus különbséget.
language: hu
linktitle: Find Geometry Overlays
second_title: Aspose.GIS .NET API
title: Hogyan végezzünk átfedési műveleteket az Aspose.GIS for .NET segítségével
url: /net/geometry-analysis/find-geometry-overlays/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan végezzünk átfedés műveleteket az Aspose.GIS for .NET használatával

## Bevezetés
Az átfedés‑elemzés minden **spatial overlay tutorial** alapvető technikája – lehetővé teszi több földrajzi réteg kombinálását, összehasonlítását és a bennük rejlő információk kinyerését. Ebben az útmutatóban megtanulja, **hogyan hajtson végre átfedés** műveleteket, mint az Intersection, Union, Difference és Symmetric Difference a hatékony Aspose.GIS for .NET könyvtár segítségével. A tutorial végére képes lesz ezeket a módszereket valós GIS‑problémákra alkalmazni, például földhasználati tervezésre, környezeti hatástanulmányokra és útvonaloptimalizálásra.

## Gyors válaszok
- **Mi az átfedés művelet?** Egy térbeli módszer, amely két geometriát kombinál, és új geometriát hoz létre (metszet, unió stb.).  
- **Melyik könyvtár kezeli az átfedéseket .NET‑ben?** Aspose.GIS for .NET.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 10‑15 perc az alap példához.  
- **Szükség van licencre?** A próba verzió ingyenes; a kereskedelmi licenc a termeléshez kötelező.  
- **Futtatható .NET Core / .NET 6+ környezetben?** Igen – az Aspose.GIS támogatja az összes modern .NET futtatókörnyezetet.

## Mi az az átfedés művelet?
Egy átfedés művelet két geometriai alakzatot vesz alapul, és az ő térbeli viszonyuk alapján új alakzatot számol ki.  
- **Intersection** visszaadja a két alakzat közös területét.  
- **Union** egyetlen geometriává egyesíti az alakzatokat.  
- **Difference** az egyik alakzatot kivonja a másikból.  
- **Symmetric Difference** visszaadja azokat a részeket, amelyek valamelyik alakzathoz tartoznak, de nem mindkettőhöz.

## Miért használjuk az Aspose.GIS‑t átfedéshez?
Az Aspose.GIS tiszta, teljesen menedzselt API‑t kínál, amely elrejti az alacsony szintű matematikát, így a fejlesztő a üzleti logikára koncentrálhat. Platformfüggetlen, nagy adathalmazokat hatékonyan kezel, és zökkenőmentesen integrálható más .NET komponensekkel.

## Előfeltételek
- Működő .NET fejlesztői környezet (Visual Studio, VS Code vagy a .NET CLI).  
- Aspose.GIS for .NET könyvtár – a legújabb verzió letölthető a [hivatalos oldalról](https://releases.aspose.com/gis/net/).  

### Névtér importálása
Mielőtt elkezdené használni az Aspose.GIS for .NET‑et, importálja a szükséges névtereket a projektbe.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Hogyan végezzünk átfedés műveleteket .NET‑ben
Az alábbiakban lépésről‑lépésre bemutatjuk, hogyan hozhatunk létre két poligont, és alkalmazhatjuk az egyes átfedés módszereket.

### 1. lépés: Poligon objektumok létrehozása
Először két egyszerű négyzet alakú poligont definiálunk, amelyek részben átfedik egymást. Ezek szolgálnak tesztadatként.

```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```

### 2. lépés: Intersection művelet végrehajtása
Az **Intersection** a két poligon átfedő területét adja vissza.

```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Polygon
```

### 3. lépés: Intersection pontok kiírása
Segédmetódust (`PrintRing`) használunk a kapott poligon koordinátáinak megjelenítéséhez.

```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```

### 4. lépés: Union művelet végrehajtása
Az **Union** egyetlen alakzatba egyesíti mindkét poligont, amely lefedi az összes, bármelyik poligon által lefedett területet.

```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Polygon
```

### 5. lépés: Union pontok kiírása
A egyesített geometria koordinátáinak kiírása.

```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```

### 6. lépés: Difference művelet végrehajtása
A **Difference** a `polygon2`‑t kivonja a `polygon1`‑ből, így csak a `polygon1` azon része marad, amely nem metszik a `polygon2`‑t.

```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Polygon
```

### 7. lépés: Difference pontok kiírása
A kivonás után megmaradt csúcsok megjelenítése.

```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```

### 8. lépés: Symmetric Difference művelet végrehajtása
A **Symmetric Difference** visszaadja azokat a területeket, amelyek valamelyik poligonhoz tartoznak, de nem mindkettőhöz. Az eredmény egy `MultiPolygon`.

```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // MultiPolygon
```

### 9. lépés: Symmetric Difference poligonok kiírása
Iteráljon a `MultiPolygon` minden poligonján, és írja ki a pontjait.

```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```

## Gyakori problémák és megoldások
| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| `null` eredmény az `Intersection`‑től | A poligonok valójában nem fednek át. | Ellenőrizze a koordinátákat, vagy használja az `Intersects` ellenőrzést az `Intersection` meghívása előtt. |
| Váratlan `MultiPolygon` a `SymDifference`‑tól | A szimmetrikus különbség szétválasztott komponenseket hozhat létre. | Castolja `IMultiPolygon`‑ra, és iteráljon a példában bemutatott módon. |
| Teljesítménycsökkenés nagy adathalmazoknál | Minden művelet újra számolja a geometriát. | Használja a köztes eredményeket újra, vagy egyszerűsítse a geometriákat a `Simplify()`‑el az átfedés előtt. |

## Gyakran feltett kérdések

**Q: Használhatom az Aspose.GIS for .NET‑et kereskedelmi projektjeimben?**  
A: Igen, az Aspose.GIS for .NET használható kereskedelmi és nem‑kereskedelmi projektekben is érvényes licenccel.

**Q: Elérhető próba verzió az Aspose.GIS for .NET‑hez?**  
A: Igen, ingyenes próba verzió letölthető [innen](https://releases.aspose.com/).

**Q: Hogyan kaphatok támogatást az Aspose.GIS for .NET‑hez?**  
A: Támogatást a Aspose.GIS közösségi fórumon kaphat [itt](https://forum.aspose.com/c/gis/33).

**Q: Vannak ideiglenes licencek az Aspose.GIS for .NET‑hez?**  
A: Igen, ideiglenes licencek elérhetők teszteléshez és kiértékeléshez. Ezeket [innen](https://purchase.aspose.com/temporary-license/) szerezheti be.

**Q: Vásárolhatom közvetlenül az Aspose.GIS for .NET‑et?**  
A: Igen, megvásárolható a weboldalon [itt](https://purchase.aspose.com/buy).

---

**Utoljára frissítve:** 2025-12-07  
**Tesztelve:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
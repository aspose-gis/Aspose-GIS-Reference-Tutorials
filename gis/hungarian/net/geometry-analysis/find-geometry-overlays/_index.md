---
title: Geometriai átfedések elsajátítása az Aspose.GIS segítségével .NET-hez
linktitle: Keresse meg a geometriai lefedéseket
second_title: Aspose.GIS .NET API
description: Ismerje meg, hogyan hajthat végre geometriai átfedési műveleteket az Aspose.GIS for .NET használatával. Mester metszéspont, unió, különbség és szimmetrikus különbség műveletek.
weight: 16
url: /hu/net/geometry-analysis/find-geometry-overlays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Geometriai átfedések elsajátítása az Aspose.GIS segítségével .NET-hez

## Bevezetés
térinformatikai rendszerek (GIS) területén az overlay műveletek alapvetőek a térbeli elemzéshez. Lehetővé teszik a különböző térbeli adatkészletek összehasonlítását és kombinálását, hogy értékes betekintést nyerhessenek. Az Aspose.GIS for .NET robusztus funkciókat biztosít a geometriai átfedések hatékony végrehajtásához. Ebben az oktatóanyagban az Aspose.GIS for .NET használatával különféle átfedési műveletekbe fogunk beleásni, mint például a metszéspont, az egyesülés, a különbség és a szimmetrikus különbség.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
### 1. .NET fejlesztői környezet
Győződjön meg arról, hogy .NET fejlesztői környezet van beállítva a gépen. A .NET SDK letölthető és telepíthető a .NET webhelyről.
### 2. Aspose.GIS for .NET Library
 Töltse le és telepítse az Aspose.GIS for .NET könyvtárat a[weboldal](https://releases.aspose.com/gis/net/).
## Névterek importálása
Az Aspose.GIS for .NET használatának megkezdése előtt importálnia kell a szükséges névtereket a projektbe.
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 1. lépés: Hozzon létre sokszög objektumokat
Először definiálunk két sokszög objektumot, amelyek térbeli régiókat reprezentálnak.
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
## 2. lépés: Hajtsa végre a kereszteződés műveletet
Ezután keressük meg a két sokszög metszéspontját.
```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Poligon
```
## 3. lépés: Nyomtassa ki a metszéspontokat
Kiírjuk a metszésponti sokszög pontjait.
```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```
## 4. lépés: Végezze el az Uniós műveletet
Most keressük meg a két sokszög unióját.
```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Poligon
```
## 5. lépés: Uniós pontok nyomtatása
Nyomtassa ki az egyesülési sokszög pontjait.
```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```
## 6. lépés: Hajtsa végre a különbségi műveletet
Ezután keressük meg a különbséget a két sokszög között.
```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Poligon
```
## 7. lépés: Nyomtasson különbségi pontokat
Nyomtassa ki a különbségi sokszög pontjait.
```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```
## 8. lépés: Hajtsa végre a szimmetrikus különbség műveletet
Végül keressük meg a két sokszög közötti szimmetrikus különbséget.
```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // MultiPolygon
```
## 9. lépés: Nyomtasson szimmetrikus különbségi sokszögeket
Nyomtassa ki az egyes sokszögek pontjait a szimmetrikus különbségben.
```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```
## Következtetés
geometriai átfedések elsajátítása kulcsfontosságú a térelemzésben, és az Aspose.GIS for .NET átfogó eszközkészletet biztosít e műveletek hatékony végrehajtásához. Az oktatóanyag követésével megtanulta, hogyan használhatja az Aspose.GIS for .NET-et metszésponti, egyesülési, különbségi és szimmetrikus különbségi műveletek végrehajtására geometriai alakzatokon.
## GYIK
### K: Használhatom az Aspose.GIS-t .NET-hez kereskedelmi projektjeimben?
Igen, az Aspose.GIS for .NET használható kereskedelmi és nem kereskedelmi projektekben is.
### K: Elérhető az Aspose.GIS .NET-hez próbaverziója?
 Igen, letölthet egy ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/).
### K: Hogyan kaphatok támogatást az Aspose.GIS for .NET számára?
 Támogatást kaphat az Aspose.GIS közösségi fórumtól[itt](https://forum.aspose.com/c/gis/33).
### K: Vannak ideiglenes licencek az Aspose.GIS for .NET számára?
 Igen, tesztelési és értékelési célokra rendelkezésre állnak ideiglenes licencek. től szerezheti be őket[itt](https://purchase.aspose.com/temporary-license/).
### K: Megvásárolhatom közvetlenül az Aspose.GIS-t .NET-hez?
 Igen, megvásárolhatja az Aspose.GIS-t .NET-hez a webhelyről[itt](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

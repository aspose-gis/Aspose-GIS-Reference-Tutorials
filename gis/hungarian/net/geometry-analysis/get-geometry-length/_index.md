---
date: 2026-08-13
description: Ismerje meg, hogyan számítsa ki a geometry length .NET-et az Aspose.GIS
  segítségével a hatékony spatial data kezelés érdekében. Tartalmazza a get line length
  C# és a calculate line length C# példákat.
keywords:
- calculate geometry length .net
- Aspose.GIS length calculation
- C# geometry length
lastmod: 2026-08-13
linktitle: Geometry Length lekérése
og_description: Calculate geometry length .NET using Aspose.GIS. Get line length C#
  and polygon perimeter példák egy tömör, high‑performance útmutatóban .NET fejlesztők
  számára.
og_image_alt: Developer guide showing how to calculate geometry length in .NET with
  Aspose.GIS
og_title: Calculate geometry length .NET az Aspose.GIS segítségével – Fast spatial
  measurements
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to calculate geometry length .NET using Aspose.GIS for efficient
    spatial data handling. Includes get line length C# and calculate line length C#
    examples.
  headline: How to Calculate Geometry Length .NET with Aspose.GIS
  type: TechArticle
- description: Learn how to calculate geometry length .NET using Aspose.GIS for efficient
    spatial data handling. Includes get line length C# and calculate line length C#
    examples.
  name: How to Calculate Geometry Length .NET with Aspose.GIS
  steps:
  - name: Create geometry objects
    text: To begin with, create the geometry objects representing the shapes for which
      you want to calculate the length. This can include lines, polygons, or any other
      geometrical shapes.
  - name: Calculate line length in C#
    text: Once you have created the line geometry, you can calculate its length using
      the `GetLength()` method. This demonstrates **calculate line length c#** in
      a single line of code.
  - name: Create polygon geometry
    text: Similarly, you can create polygon geometry objects using the `Polygon` and
      `LinearRing` classes.
  - name: Get length of a polygon
    text: For polygons, the `GetLength()` method returns the perimeter, which is effectively
      the **how to get length** of the shape.
  type: HowTo
- questions:
  - answer: Aspose.GIS for .NET is compatible with .NET Framework 4.6.1 or later versions,
      as well as .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with all .NET frameworks?
  - answer: Yes, you can avail of a free trial of Aspose.GIS for .NET from [here](https://releases.aspose.com/).
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: You can find support and assistance from the Aspose.GIS community forum
      [here](https://forum.aspose.com/c/gis/33).
    question: Where can I find support for Aspose.GIS for .NET?
  - answer: You can acquire a temporary license from [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Yes, Aspose.GIS for .NET provides various formatting options to customize
      the output format as per your requirements.
    question: Can I customize the output format for geometry length calculations?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geometry length
- Aspose.GIS
- C# GIS
- spatial calculations
- line length
title: Hogyan számítsuk ki a Geometry Length .NET-et az Aspose.GIS használatával
url: /hu/net/geometry-analysis/get-geometry-length/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan számítsuk ki a geometria hosszát .NET-ben az Aspose.GIS segítségével

## Bevezetés
Ha egy világos, gyakorlati módot keres a **geometry length .NET kiszámítása** számára, jó helyen jár. Az Aspose.GIS for .NET gazdag GIS‑központú API‑készletet biztosít, amely egyszerűvé és hatékonnyá teszi a térbeli számításokat – például a vonalhossz vagy a poligon kerület mérését. Ebben az oktatóanyagban végigvezetjük a teljes folyamatot, a környezet beállításától a pontos hosszértékeket visszaadó C# kód írásáig.

## Gyors válaszok
- **Mi ad vissza a “GetLength()”?** Vonalak esetén a vonalhosszt, poligonok esetén a kerületet adja vissza.  
- **Melyik névtér szükséges?** `Aspose.Gis.Geometries`.  
- **Használhatom .NET 6-tal?** Igen, az Aspose.GIS támogatja a .NET 5, .NET 6 és újabb verziókat.  
- **Szükségem van licencre fejlesztéshez?** Egy ingyenes próba verzió elegendő értékeléshez; a termeléshez licenc szükséges.  
- **Az eredmény egységérzékeny?** A hossz a koordináta‑rendszer egységeiben (pl. méter a vetített CRS esetén) kerül visszaadásra.

## Mi a geometria hossza?
A Geometry.GetLength() a geometriai objektum összes lineáris távolságát számítja ki a koordinátaértékek alapján. LineString esetén összeadja a szomszédos csúcsok közötti távolságokat, és visszaadja a vonal hosszát. Polygonra alkalmazva az összes él hosszát adja össze, így a forma kerületét biztosítja.

## Miért használja az Aspose.GIS-t a hossz számításokhoz?
Az Aspose.GIS egy teljesen kezelt .NET könyvtárat kínál, amely térbeli számításokat végez natív binárisok nélkül, így a telepítés egyszerű Windows, Linux és macOS rendszereken egyaránt. Több mint ötven koordináta‑referencia rendszert támogat, magas pontosságú dupla pontosságú eredményeket biztosít még több száz kilométeres vonalakon is, és zökkenőmentesen integrálódik a .NET 5/6/7 projektekbe, garantálva a konzisztens teljesítményt és pontosságot.

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg róla, hogy a következőkkel rendelkezik:

### 1. Aspose.GIS for .NET könyvtár
Először is telepítenie kell az Aspose.GIS for .NET könyvtárat a fejlesztői környezetébe. Ha még nem tette meg, letöltheti a [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/) oldalról.

### 2. .NET fejlesztői környezet
Győződjön meg róla, hogy a gépén be van állítva egy .NET fejlesztői környezet. Ennek része a Visual Studio vagy bármely más kompatibilis IDE telepítése.

### 3. Alapvető C# ismeretek
Az C# programozási nyelv alapvető ismerete elengedhetetlen az oktatóanyag követéséhez.

## Névterek importálása
Az Aspose.GIS for .NET által nyújtott funkciók használatához importálnia kell a szükséges névtereket a C# projektjébe.

### Aspose.GIS névtér importálása
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Hogyan kapjuk meg a vonal hosszát C#-ban
Az Aspose.GIS-ben a `LineString` két vagy több pontból álló sorozatot képvisel, amelyet egyenes vonal szegmensek kötnek össze, és lineáris jellemzőket modellez, például utakat, folyókat vagy közművezetékeket egy adott koordináta‑referencia rendszerben. A kívánt csúcsokkal létrehozott `LineString` után a `GetLength()` metódus meghívása visszaadja a geometria CRS egységeiben mért teljes távolságot, lehetővé téve a pontos vonalmérések gyors megszerzését útvonaltervezéshez, távolság‑alapú elemzéshez vagy jelentéskészítéshez, és szükség szerint tovább feldolgozható vagy tárolható.

### 1. lépés: Geometriai objektumok létrehozása
Első lépésként hozza létre a hossz kiszámításához szükséges alakzatokat ábrázoló geometriai objektumokat. Ez magában foglalhat vonalakat, poligonokat vagy bármilyen más geometriai formát.

```csharp
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(2, 2);
line.AddPoint(2, 0);
```

### 2. lépés: Vonalhossz kiszámítása C#-ban
Miután létrehozta a vonalgeometriát, a `GetLength()` metódussal kiszámíthatja annak hosszát. Ez egyetlen kódsorban mutatja be a **calculate line length c#** példát.

```csharp
Console.WriteLine("{0:F}", line.GetLength()); // Output: 4.83
```

## Hogyan számítsuk ki a vonal hosszát C#-ban poligonok esetén
Az Aspose.GIS-ben a `Polygon` egy külső `LinearRing`‑ből áll, amely meghatározza a határait, valamint opcionális belső gyűrűket tartalmazhat lyukak számára, és területi jellemzőket ábrázol, például telkeket, tavakat vagy közigazgatási zónákat egy adott térbeli hivatkozásban. Hozza létre a külső `LinearRing`‑t a poligon sarkpontjainak megadásával, majd példányosítsa a `Polygon`‑t ezzel a gyűrűvel; a `GetLength()` hívása a poligonra a teljes kerületet számítja ki, ami hasznos például kerítés hosszának becsléséhez, határjelentéshez vagy a kerület értékek más egységekbe történő átalakításához.

### 3. lépés: Poligon geometria létrehozása
Hasonlóan, a `Polygon` és `LinearRing` osztályok segítségével hozhat létre poligon geometriai objektumokat.

```csharp
var rectangle = new Polygon(new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(1, 0),
    new Point(0, 0),
}));
```

### 4. lépés: Poligon hosszának lekérése
Poligonok esetén a `GetLength()` metódus a kerületet adja vissza, ami lényegében a **how to get length** a forma esetében.

```csharp
Console.WriteLine("{0:F}", rectangle.GetLength()); // Output: 4.00
```

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|-------|----------|
| **Váratlanul nulla hossz** | Ellenőrizze, hogy a geometria koordináta‑rendszere megegyezik a megadott adatokkal; a duplikált pontok nulla‑hosszú szegmenseket eredményezhetnek. |
| **Helytelen egységek** | Ne feledje, hogy a `GetLength()` a CRS egységeiben adja vissza az értékeket. Szükség esetén konvertáljon méterre/lábra. |
| **Teljesítmény nagy adathalmazok esetén** | Amikor csak lehetséges, újrahasználja a geometriai objektumokat, és kerülje el több ezer ideiglenes pont létrehozását szoros ciklusokban. |

## Gyakran ismételt kérdések

**K: Az Aspose.GIS for .NET kompatibilis minden .NET keretrendszerrel?**  
V: Az Aspose.GIS for .NET kompatibilis a .NET Framework 4.6.1 vagy újabb verziókkal, valamint a .NET 5/6/7‑tel.

**K: Kipróbálhatom az Aspose.GIS for .NET-et vásárlás előtt?**  
V: Igen, ingyenes próba verziót szerezhet az Aspose.GIS for .NET‑ből [itt](https://releases.aspose.com/).

**K: Hol találok támogatást az Aspose.GIS for .NET-hez?**  
V: Támogatást és segítséget az Aspose.GIS közösségi fórumon [itt](https://forum.aspose.com/c/gis/33) talál.

**K: Hogyan szerezhetek ideiglenes licencet az Aspose.GIS for .NET-hez?**  
V: Ideiglenes licencet a [itt](https://purchase.aspose.com/temporary-license/) kaphat.

**K: Testreszabhatom a kimeneti formátumot a geometria hossz számításokhoz?**  
V: Igen, az Aspose.GIS for .NET különféle formázási lehetőségeket biztosít a kimeneti formátum igényei szerint történő testreszabásához.

## Következtetés
Ebben az oktatóanyagban bemutattuk, hogyan **számítsuk ki a geometria hosszát .NET-ben** vonal és poligon geometriák esetén az Aspose.GIS for .NET használatával. A lépésről‑lépésre példákat követve most már pontos térbeli méréseket integrálhat bármely .NET alkalmazásba, legyen az asztali GIS eszköz, webszolgáltatás vagy háttér adatfeldolgozó csővezeték.

---

**Utoljára frissítve:** 2026-08-13  
**Tesztelve:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Tanulja meg, hogyan hozhat létre LineString geometriát az Aspose.GIS for .NET segítségével](/gis/net/geometry-creation/create-linestring-geometry/)
- [Hogyan számítsa ki a területet az Aspose.GIS for .NET használatával](/gis/net/geometry-analysis/get-geometry-area/)
- [Hogyan hozhat létre pontgeometriát és szerezze meg a geometria típusát az Aspose.GIS for .NET segítségével](/gis/net/geometry-analysis/get-geometry-type/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
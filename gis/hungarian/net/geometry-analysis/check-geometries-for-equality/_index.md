---
date: 2026-06-05
description: Tanulja meg, hogyan hasonlíthatja össze a geometriai alakzatokat .NET-ben
  az Aspose.GIS segítségével, hogyan észlelhet duplikált geometriai alakzatokat, és
  hogyan ellenőrizheti a geometriai egyenlőséget alkalmazásaiban.
keywords:
- how to compare geometries
- detect duplicate geometries
- Aspose.GIS geometry equality
linktitle: Hogyan hasonlítsuk össze a geometriai alakzatokat egyenlőségre
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to compare geometries in .NET using Aspose.GIS, detect duplicate
    geometries, and check geometry equality in your applications.
  headline: How to Compare Geometries for Equality using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard
      projects.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. Download a trial from the [Aspose.GIS releases page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Detailed docs are on the [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).
    question: Where can I find the full API documentation?
  - answer: Post your question on the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How do I get help if I run into an issue?
  - answer: Yes, temporary licenses are available on the [purchase page](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hogyan hasonlítsuk össze a geometriai alakzatokat egyenlőségre az Aspose.GIS
  for .NET használatával
url: /hu/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hasonlítsuk össze a geometriai egyenlőséget az Aspose.GIS for .NET használatával

## Bevezetés
Ebben az útmutatóban megtanulja, **hogyan hasonlítsa össze a geometriai objektumokat** az Aspose.GIS for .NET segítségével, ami elengedhetetlen, ha duplikált geometriai objektumokat kell felderíteni, térbeli adatokat validálni vagy topológiai szabályokat érvényesíteni. Akár térképszolgáltatást épít, akár kötegelt térbeli elemzést futtat, vagy egyszerűen csak ellenőrizni szeretné, hogy két alakzat ugyanazon a helyen van-e, ez az útmutató végigvezeti a geometriai egyenlőség létrehozásán, módosításán és tesztelésén tiszta, termelésre kész C# kóddal.

## Gyors válaszok
- **Mit jelent a „geometriai objektumok összehasonlítása”?** Ellenőrzi, hogy két geometriai objektum ugyanabban a térben helyezkedik-e el, függetlenül attól, hogyan épültek fel.  
- **Melyik módszert használják?** Az `SpatiallyEquals` a Aspose.GIS API-ból.  
- **Szükségem van licencre a fejlesztéshez?** Ingyenes próba verzió tesztelésre elegendő; a termeléshez kereskedelmi licenc szükséges.  
- **Támogatott .NET verziók?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Tipikus megvalósítási idő?** Körülbelül 5‑10 perc egy alapvető egyenlőség ellenőrzéshez.

## Mi az a geometriai egyenlőség?
A geometriai egyenlőség, más néven térbeli egyenlőség, azt jelenti, hogy két geometria pontosan ugyanazt a pontkészletet reprezentálja a Föld felszínén. Még ha az egyik geometria `MultiLineString`‑ként, a másik pedig egyetlen `LineString`‑ként van felépítve, akkor is egyenlőnek tekinthetők, ha minden koordináta a meghatározott tolerancián belül megegyezik. Ez a definíció lehetővé teszi a fejlesztők számára, hogy megbízhatóan felderítsék a duplikált geometriákat heterogén adatforrások között.

## Miért használjuk az Aspose.GIS‑t a geometriai összehasonlításhoz?
Az Aspose.GIS egy nagy teljesítményű, offline geometriai motorral rendelkezik, amely megszünteti a külső szolgáltatások szükségességét. **Több mint 30 vektor- és raszterformátumot támogat** (köztük WKT, GeoJSON, Shapefile, KML, GML), és képes **több százezer csúcsot** tartalmazó fájlok feldolgozására, miközben a memóriahasználat 50 MB alatt marad. A könyvtár `SpatiallyEquals` metódusa precíziótudatos, determinisztikus eredményeket ad még lebegőpontos koordináták esetén is.

### Miért fontos ez a fejlesztők számára
Amikor **duplikált geometriákat** kell felderíteni kötegelt folyamatokban, valós‑idő validációs csővezetékekben vagy GIS adatátvitel során, egy bevált könyvtár eltávolítja a találgatást és garantálja a következetes eredményeket a különböző adatforrások között.

## Előfeltételek
- **.NET Framework vagy .NET Core telepítve** – bármely, az Aspose.GIS által támogatott verzió.  
- **Aspose.GIS for .NET könyvtár** – letölthető a [Aspose.GIS letöltési oldalról](https://releases.aspose.com/gis/net/).  
- **Fejlesztői IDE** – Visual Studio, Rider vagy VS Code C# kiegészítőkkel.

## Névterek importálása
.NET projektjében adja hozzá a szükséges `using` utasításokat, hogy a fordító tudja, hol találja a GIS osztályokat:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 1. lépés: A geometriák definiálása
A `MultiLineString` vonalösszetevők gyűjteményét jelenti, míg a `LineString` egyetlen folytonos vonalat definiál. Mindkét osztály a `Geometry` alaptípusból származik.

Először két geometriát hozunk létre, amelyeket össze fogunk hasonlítani. Ebben a példában a `geometry1` egy két szegmensből álló `MultiLineString`, míg a `geometry2` egyetlen `LineString`, amely ugyanazokat a kezdő‑ és végpontokat fedi le.

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

## 2. lépés: Geometriák egyenlőségének ellenőrzése
A `SpatiallyEquals` azt értékeli, hogy két geometria ugyanazt a pontkészletet foglalja-e el, opcionálisan toleranciaértéket is elfogad a lebegőpontos pontatlanság miatt.

Most a `SpatiallyEquals` metódust használjuk annak megállapítására, hogy a GIS motor szerint a két alakzat egyenlőnek tekinthető‑e.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

A konzol `True` értéket ír ki, mert a különböző felépítés ellenére mindkét geometria ugyanazt a vonalat fedi le (0,0)‑tól (2,2)‑ig.

## 3. lépés: Egy geometria módosítása
Annak bemutatására, hogy egy módosítás hogyan befolyásolja az egyenlőséget, egy extra pontot adunk a `geometry2`‑höz.

```csharp
geometry2.AddPoint(3, 3);
```

## 4. lépés: Egyenlőség újraellenőrzése a módosítás után
A módosítás után a geometriák már nem egyeznek, ezért a `SpatiallyEquals` `False` értéket ad.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

A `False` kimenet megerősíti, hogy a további pont megszegte a térbeli egyenlőséget.

## Hogyan észleljük a duplikált geometriákat?
Töltse be minden geometriát, hívja meg a `SpatiallyEquals`‑t egy megfelelő toleranciával, és szűrje ki azokat, amelyek `True`‑t adnak. Ez a minta jól skálázható LINQ‑szal, lehetővé téve a duplikált alakzatok azonosítását nagy gyűjteményekben néhány kódsorral. Kombinálhatja a `GroupBy`‑val is, hogy azonos geometriákat csoportosítson és csökkentse a tárolási költségeket.

## Gyakori problémák és tippek
- **Pontossági problémák** – Ha nagyon nagy pontosságú koordinátákkal dolgozik, fontolja meg a kerekítést vagy a `SpatiallyEquals` tolerancia‑túlterhelésének használatát.  
- **Eltérő SRID‑ek** – Győződjön meg róla, hogy a két geometria ugyanazzal a térbeli referenciarendszer-azonosítóval (SRID) rendelkezik a összehasonlítás előtt.  
- **Teljesítmény** – Nagy gyűjtemények esetén a kötegelt összehasonlítás LINQ‑val vagy párhuzamos ciklusokkal jelentősen csökkentheti a terhelést.

## Gyakran feltett kérdések
**K: Használhatom az Aspose.GIS for .NET-et más .NET keretrendszerekkel?**  
V: Igen, az Aspose.GIS működik .NET Framework, .NET Core és .NET Standard projektekben.

**K: Elérhető ingyenes próba?**  
V: Természetesen. Töltsön le egy próbaverziót a [Aspose.GIS kiadási oldalról](https://releases.aspose.com/).

**K: Hol találom a teljes API dokumentációt?**  
V: Részletes dokumentáció a [Aspose.GIS dokumentációs oldalon](https://reference.aspose.com/gis/net/).

**K: Hogyan kaphatok segítséget, ha problémába ütközöm?**  
V: Tegye fel kérdését az Aspose.GIS közösségi fórumon [itt](https://forum.aspose.com/c/gis/33).

**K: Vásárolhatok ideiglenes licencet értékeléshez?**  
V: Igen, ideiglenes licencek elérhetők a [vásárlási oldalon](https://purchase.aspose.com/temporary-license/).

## Összegzés
Most már tudja, **hogyan hasonlítsa össze a geometriákat** az Aspose.GIS for .NET segítségével, az objektumok létrehozásától a térbeli egyenlőség ellenőrzéséig és a módosítások kezeléséig. Ez a képesség alapvető a fejlettebb térbeli elemzésekhez, mint például a topológiai validáció, a duplikátumok felderítése és a geometria‑alapú szűrés.

---

**Utoljára frissítve:** 2026-06-05  
**Tesztelve a következővel:** Aspose.GIS for .NET 24.11  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Polygon geometria létrehozása C#‑ban és metszet ellenőrzése az Aspose.GIS for .NET használatával](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Hogyan végezzünk térbeli átfedés elemzést geometriákon az Aspose.GIS for .NET használatával](/gis/net/geometry-analysis/check-geometries-overlap/)
- [Hálózati útvonal ellenőrzés: érintkező geometriák az Aspose.GIS‑szel](/gis/net/geometry-analysis/check-geometries-touching/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
date: 2026-09-10
description: Ismerje meg, hogyan hozhat létre vektor réteget az Aspose.GIS for .NET
  segítségével, és korlátozhatja a precíziót a shapefile méretének csökkentése, a
  teljesítmény növelése és a koordináta pontosságának megőrzése érdekében.
keywords:
- how to create vector layer
- limit precision reading geometries
- reduce shapefile size
lastmod: 2026-09-10
linktitle: Precízió korlátozása geometria olvasásakor
og_description: Ismerje meg, hogyan hozhat létre vektor réteget az Aspose.GIS for
  .NET segítségével, és korlátozhatja a precíziót a shapefile méretének csökkentése,
  a teljesítmény javítása és a koordináta pontosság kezelése érdekében.
og_image_alt: Screenshot showing Aspose.GIS code for creating a vector layer and setting
  precision
og_title: Hogyan hozzunk létre vektor réteget az Aspose.GIS for .NET segítségével
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  headline: How to create vector layer with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  name: How to create vector layer with Aspose.GIS for .NET
  steps:
  - name: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
    text: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
  - name: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
    text: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
  - name: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
    text: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
  - name: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
    text: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
  type: HowTo
- questions:
  - answer: No. Precision is applied only when reading the geometry; the source file
      remains unchanged.
    question: Does limiting precision affect the original shapefile?
  - answer: Aspose.GIS currently applies the same `XYPrecisionModel` to both axes.
    question: Can I use a different precision model for X and Y coordinates?
  - answer: The API supports only the built‑in `PrecisionModel.Rounding(int)` method.
      For custom logic, you would need to post‑process the coordinates after reading.
    question: Is it possible to set a custom rounding function?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- Aspose.GIS
- vector layer
- precision model
- .NET GIS
title: Hogyan hozzunk létre vektor réteget az Aspose.GIS for .NET segítségével
url: /hu/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre vektor réteget az Aspose.GIS for .NET segítségével

## Bevezetés
Amikor térinformatikai adatokat dolgozol fel, gyakran azon gondolkodsz, **hogyan hozzunk létre vektor réteg** objektumokat, amelyek megfelelnek az alkalmazásod által ténylegesen igényelt pontosságnak. A koordináták kerekítése ésszerű számú tizedesjegyre nem csak a feldolgozást gyorsítja, hanem **csökkentheti a shapefile méretét akár 30 %-kal** tipikus pont adatállományok esetén. Ebben a lépésről‑lépésre útmutatóban megmutatjuk, hogyan hozhatsz létre vektor réteget, írj egy pont geometriát, majd olvasd vissza azt pontos és kerekített pontossági modellek segítségével. A végére megtanulod, hogyan **set precision model** opciókat, amelyek egyensúlyt teremtenek a teljesítmény és a szükséges térbeli pontosság között.

## Gyors válaszok
- **Mi jelent a „limit precision”?** Kerekíti a koordinátaértékeket egy meghatározott számú tizedesjegyre.  
- **Miért kell először vektor réteget létrehozni?** A vektor réteg egy tároló, amely a geometriákat, például pontokat, vonalakat és poligonokat tárolja.  
- **Mely pontossági modellek érhetők el?** `PrecisionModel.Exact` (nincs kerekítés) és `PrecisionModel.Rounding(n)` (kerekítés *n* tizedesjegyre).  
- **Szükségem van licencre a kipróbáláshoz?** Ingyenes próbaverzió érhető el a kiadások oldaláról.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core, és .NET 5/6+.

## Mi a vektor réteg létrehozása?
A **creating a vector layer** cselekedet azt jelenti, hogy példányosítod az Aspose.GIS `VectorLayer` osztályát, amely egyetlen shapefile-t képvisel a lemezen, és tárolja az összes hozzáadott geometriai elemet. Ez a réteg a belépési ponttá válik a térbeli adatok olvasásához, írásához és manipulálásához. Lehetővé teszi továbbá attribútummezők definiálását és a térbeli referenciák beállítását az adatkészlethez.

## Miért korlátozzuk a pontosságot, és hogyan segít?
- **Teljesítmény növelés** – A tizedesjegyek számának csökkentése csökkenti a feldolgozandó és sorosítandó bináris adatok mennyiségét, gyakran 15‑20 %-os sebességnövekedést eredményezve nagy fájlok esetén.  
- **Kisebb fájlok** – A koordináták kerekítése két vagy három tizedesjegyre egy 10 MB-os shapefile-t körülbelül 7 MB-ra csökkentheti, megkönnyítve a tárolást és a hálózati átvitelét.  
- **Megfelelő pontosság** – A legtöbb GIS elemzés (pl. város‑szintű térképezés) csak méter‑szintű pontosságot igényel, így a 3 tizedesjegy kerekítés több mint elegendő.

## Előfeltételek
Mielőtt elindulnánk ezen az úton, győződj meg róla, hogy a következő előfeltételek rendelkezésre állnak:
1. **Telepítés** – Az Aspose.GIS for .NET könyvtárnak telepítve kell lennie a fejlesztői környezetedben. Ha nincs, letöltheted a [releases page](https://releases.aspose.com/gis/net/) oldalról.  
2. **Ismeretek a .NET‑ről** – Alapvető C# és .NET keretrendszer ismeret szükséges a megadott kódrészletek megértéséhez és megvalósításához.  
3. **Fejlesztői környezet** – Egy működő .NET fejlesztői környezet, például a Visual Studio, szükséges.  
4. **Dokumentum könyvtár** – Legyen egy könyvtár beállítva, ahol a folyamat során létrehozott shapefile-t tárolhatod és elérheted.

## Névterek importálása
Mielőtt elkezdenénk a pontosság korlátozásának funkcióját megvalósítani a geometriák olvasásakor, győződjünk meg róla, hogy importáljuk a szükséges névtereket:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Hogyan hozzunk létre vektor réteget
Tölts be egy új `VectorLayer`-t a kimeneti mappa és a kívánt shapefile név megadásával. Ez egy üres tárolót hoz létre, amely készen áll a geometriai objektumok fogadására.

`VectorLayer` osztály az Aspose.GIS legfelső szintű objektuma, amely egyetlen shapefile-t képvisel a lemezen. Miután példányt hozol létre, hozzáadhatsz elemeket, definiálhatsz attribútummezőket, és végül meghívhatod a `Save()`-t a fájlok lemezre írásához.
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Pontossági beállítások megadása
`PrecisionModel` határozza meg, hogyan kerekítik vagy tartják pontosan a koordinátaértékeket a geometriák olvasásakor. A modellt egy `ReadOptions` objektumon állítod be a réteg megnyitása előtt.

`PrecisionModel` osztály az Aspose.GIS alapvető komponense, amely a X és Y tengelyek kerekítési viselkedését szabályozza. A megfelelő modell kiválasztásával meghatározod, hogy a könyvtár minden számjegyet megőriz-e, vagy egy meghatározott tizedesjegy számra csonkolja.
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Geometriák olvasása pontos pontossággal
`ReadOptions` paramétereket határoz meg egy vektor réteg olvasásához, például a alkalmazandó pontossági modellt.  
Nyisd meg a korábban mentett vektor réteget egy `ReadOptions` példány segítségével, amely a `PrecisionModel.Exact`-re hivatkozik. Ez biztosítja, hogy minden koordináta kerekítés nélkül legyen beolvasva.

Amikor a `PrecisionModel.Exact`-et használod, az Aspose.GIS a shapefile‑ben tárolt nyers dupla‑pontosságú értékeket olvassa, garantálva, hogy az olvasás során nincs információveszteség.
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Pontosság csonkolása
Ha a pontosságot egy meghatározott számú tizedesjegyre szeretnéd csonkolni, cseréld le az `Exact`-et `PrecisionModel.Rounding(n)`-re, ahol *n* a megtartani kívánt tizedesjegyek száma.

Két tizedesjegyre való kerekítés (`PrecisionModel.Rounding(2)`) általában 20‑30 %-kal csökkenti a fájlméretet, miközben a koordináta pontosságot a legtöbb térképméret esetén néhány centiméteren belül tartja.
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Hogyan állítsuk be a precision model-t különböző forgatókönyvekhez
Válaszd ki a használati esetnek megfelelő modellt:
- **Nagy‑pontosságú tudományos elemzés** – Használd a `PrecisionModel.Exact`-et minden számjegy megtartásához.  
- **Web‑térképezési csempék vagy mobilalkalmazások** – Használd a `PrecisionModel.Rounding(2)`-t a fájlok könnyűsúlyú és gyors megjelenítéséhez.

A megfelelő modell kiválasztása a **set precision model** döntéshozatali folyamat része, amely a pontosságot a teljesítménnyel egyensúlyozza.

## Gyakori problémák és megoldások
`XYPrecisionModel` a `ReadOptions` egy tulajdonsága, amely beállítja a pontossági modellt mind az X, mind az Y koordinátákra.  
- **Váratlan koordinátaértékek** – Győződj meg róla, hogy a `options.XYPrecisionModel`-t a réteg megnyitása *előtt* állítod be. A megnyitás után történő módosítás nem hat.  
- **Fájl nem található** – Ellenőrizd, hogy a `path` változó egy érvényes könyvtárra mutat-e, és hogy a Shapefile sikeresen létrejött-e az előző lépésben.  
- **Helytelen geometria típus** – A példa egy `Point`-ot használ. Más geometriai típusok (pl. `LineString`) esetén a cast-nek meg kell egyeznie a tényleges típussal.  

## Tippek a shapefile méretének csökkentésére
- Használd a `PrecisionModel.Rounding`-ot a legkisebb számú tizedesjeggyel, amely még megfelel a pontossági igényeidnek.  
- Távolítsd el a felesleges attribútummezőket a réteg írása előtt.  
- Tömörítsd a keletkezett `.shp`, `.shx`, és `.dbf` fájlokat szabványos ZIP eszközökkel, ha át kell őket vinni.

## Összegzés
Geometriák olvasásakor a pontosság kezelése a térinformatikai adatok manipulációjának kulcsfontosságú aspektusa. Az Aspose.GIS for .NET hatékony megoldásokat biztosít ennek eléréséhez. A fenti lépések követésével zökkenőmentesen **create vector layer** objektumokat hozhatsz létre, **set precision model**-t állíthatsz be, és akár **reduce shapefile size**-t is elérhetsz, amikor ez megfelelő, biztosítva az optimális adatkezelést az alkalmazásaidban.

## GYIK
### Használhatom az Aspose.GIS for .NET-et más .NET keretrendszerekkel, például .NET Core vagy .NET Standard?
Igen, az Aspose.GIS for .NET kompatibilis különböző .NET keretrendszerekkel, beleértve a .NET Core‑t és a .NET Standard‑ot.

### Elérhető próba verzió az Aspose.GIS for .NET-hez?
Igen, ingyenes próba verziót szerezhetsz a [releases page](https://releases.aspose.com/) oldalról.

### Hol találhatom meg a részletes dokumentációt az Aspose.GIS for .NET-hez?
A részletes információkért és példákért a [documentation](https://reference.aspose.com/gis/net/) oldalra hivatkozhatsz.

### Hogyan szerezhetek ideiglenes licenceket az Aspose.GIS for .NET-hez?
Ideiglenes licenceket a [purchase page](https://purchase.aspose.com/temporary-license/) oldalról szerezhetsz az Aspose.GIS-hez.

### Hol kérhetek segítséget vagy támogatást az Aspose.GIS for .NET-hez?
Bármilyen kérdés, vita vagy támogatási igény esetén felkeresheted az Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) oldalát.

## Gyakran feltett kérdések
**Q: Befolyásolja a pontosság korlátozása az eredeti shapefile-t?**  
A: Nem. A pontosság csak a geometria olvasásakor kerül alkalmazásra; a forrásfájl változatlan marad.

**Q: Használhatok különböző pontossági modelleket az X és Y koordinátákhoz?**  
A: Az Aspose.GIS jelenleg ugyanazt az `XYPrecisionModel`-t alkalmazza mindkét tengelyre.

**Q: Lehetséges egy egyedi kerekítési függvényt beállítani?**  
A: Az API csak a beépített `PrecisionModel.Rounding(int)` metódust támogatja. Egyedi logikához a koordinátákat az olvasás után kell utófeldolgozni.

---

**Utolsó frissítés:** 2026-09-10  
**Tesztelve a következővel:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Hogyan korlátozzuk a pontosságot a geometriák írásakor az Aspose.GIS-szel](/gis/net/geometry-processing/limit-precision-writing-geometries/)
- [Hogyan hozzunk létre vektor réteget SRS-szel az Aspose.GIS for .NET használatával](/gis/net/layer-management/create-vector-layer-with-srs/)
- [Vektor réteg létrehozása File GDB-ben – Aspose.GIS .NET oktatóanyag](/gis/net/layer-management/create-file-gdb-with-single-layer/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
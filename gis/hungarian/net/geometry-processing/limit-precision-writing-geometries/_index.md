---
date: 2026-05-31
description: Ismerje meg, hogyan korlátozhatja a pontosságot a geometria írásakor
  az Aspose.GIS for .NET használatával, csökkentve a GeoJSON méretét és megőrizve
  a koordináták ellenőrzését.
keywords:
- how to limit precision
- reduce geojson size
- Aspose.GIS precision control
linktitle: Pontosság korlátozása a geometria írásakor
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  headline: How to Limit Precision Writing Geometries with Aspose.GIS
  type: TechArticle
- description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  name: How to Limit Precision Writing Geometries with Aspose.GIS
  steps:
  - name: Define Precision Options
    text: The `GeoJsonOptions` class lets you specify how many fractional digits to
      keep for X/Y and Z coordinates. `PrecisionModel` defines how coordinate values
      are rounded or kept exact during writing.
  - name: Set Output Path
    text: Specify where the resulting GeoJSON file will be saved. `VectorLayer` is
      Aspose.GIS's container for a collection of features that share the same schema;
      it writes to the path you provide using the options set earlier.
  - name: Create and Populate Geometry
    text: Open a new `VectorLayer` with the options defined above, construct a `Point`
      geometry, and add it to the layer. `Point` represents a single coordinate (X,
      Y, optional Z) in a spatial reference system. It is the simplest geometry type
      and is used here to demonstrate precision rounding.
  - name: Read and Verify Precision
    text: Open the file you just created and print the coordinates. You should see
      the X/Y values rounded to three decimal places while the Z value remains exact.
      When you read the file back, Aspose.GIS parses the rounded values directly,
      so the in‑memory `Point` reflects the precision you defined during writ
  type: HowTo
- questions:
  - answer: Yes, it supports **50+** formats—including Shapefile, GeoJSON, KML, GML,
      and CSV—allowing seamless conversion between them.
    question: Is Aspose.GIS for .NET compatible with other GIS formats?
  - answer: Absolutely. A free trial is available from the download page, giving you
      full access to all features for evaluation.
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: Temporary evaluation licenses can be generated via the Aspose license
      portal; they are valid for 30 days.
    question: How do I obtain a temporary license for testing?
  - answer: The Aspose.GIS forum and Stack Overflow tag `aspose-gis` are great places
      to ask questions and find community solutions.
    question: Where can I get help if I run into issues?
  - answer: Yes, Aspose.GIS is designed to handle everything from quick prototypes
      to high‑throughput server workloads, processing multi‑gigabyte datasets with
      low memory overhead.
    question: Does the library work for both small scripts and enterprise‑scale applications?
  type: FAQPage
second_title: Aspise.GIS .NET API
title: Hogyan korlátozzuk a pontosságot a geometria írásakor az Aspose.GIS használatával
url: /hu/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan korlátozhatja a pontosságot geometria írásakor az Aspose.GIS használatával

Ha kíváncsi vagy **hogyan korlátozhatja a pontosságot** geometria írásakor egy .NET GIS alkalmazásban, az Aspose.GIS for .NET egyszerű, nagy‑teljesítményű módot kínál a koordináta kerekítés szabályozására. Ebben az útmutatóban végigvezetünk a teljes folyamaton – a környezet beállításától a kimenet pontossági szabályainak ellenőrzéséig.

## Gyors válaszok
- **Mit jelent a “limit precision”?** Kerekíti a koordináta értékeket egy meghatározott számú tizedesjegyre a térbeli fájl írása közben.  
- **Melyik formátumot használja a példában?** GeoJSON, de ugyanazok az opciók más támogatott formátumokra is érvényesek.  
- **Szükségem van licencre a kipróbáláshoz?** Az ingyenes próba a fejlesztéshez és teszteléshez működik; a termeléshez kereskedelmi licenc szükséges.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Külön tudom‑e szabályozni a Z‑koordináta pontosságát?** Igen — használja a `ZPrecisionModel`‑t a pontos vagy kerekített értékek beállításához.

## Hogyan korlátozhatja a pontosságot geometria írásakor

Töltse be a GeoJSON íróját egy `GeoJsonOptions` objektummal, amely meghatározza a kívánt X/Y és Z pontosságot, majd írja a geometriát és olvassa vissza – ez a teljes munkafolyamat tíz sor kódban elfér, és garantálja, hogy minden koordináta pontosan úgy legyen kerekítve, ahogy definiálta.

A pontosság korlátozása elengedhetetlen, ha konzisztens koordinátaábrázolásra van szükség különböző GIS eszközök között, csökkenteni szeretné a fájlméretet, vagy adatcsere‑szabványoknak kell megfelelni. Az alábbiakban meghatározzuk a pontossági opciókat, írunk egy geometriát, majd visszaolvassuk, hogy megerősítsük a kerekítést.

## Mi a pontosság korlátozása?

A pontosság korlátozása a koordinátaértékek tört részének egy rögzített számú számjegyre való kerekítését jelenti, mielőtt a geometriát egy fájlformátumba mentenénk. Ez biztosítja, hogy a fájl minden felhasználója ugyanazokat a numerikus értékeket lássa, ami segít elkerülni a kis eltéréseket, amelyek topológiai hibákat okozhatnak.

## Miért használja az Aspose.GIS‑t a pontosság szabályozásához?

Az Aspose.GIS **50+** bemeneti és kimeneti formátumot támogat – beleértve a GeoJSON‑t, Shapefile‑t, KML‑t és GML‑t – és képes **több százezer** elemet tartalmazó fájlok feldolgozására anélkül, hogy a teljes adatkészletet a memóriába töltené. Beépített pontossági modelljei lehetővé teszik a koordináták egyetlen hívással történő kerekítését, kiküszöbölve a manuális utófeldolgozó szkriptek szükségességét.

## Előkövetelmények

### 1. Letöltés és telepítés
Töltse le a legújabb Aspose.GIS for .NET csomagot a hivatalos oldalról: [download link](https://releases.aspose.com/gis/net/). Kövesse a telepítési útmutatót a NuGet csomag projektjébe való hozzáadásához.

### 2. Névtér importálása
Adja hozzá a szükséges névtereket, hogy elérhesse a GIS osztályokat és segédseg utility‑kat.

## Lépésről‑lépésre útmutató

### 1. lépés: Pontossági beállítások meghatározása
A `GeoJsonOptions` osztály lehetővé teszi, hogy meghatározza, hány tizedesjegyet tartson meg az X/Y és Z koordináták esetén.

`PrecisionModel` meghatározza, hogyan kerekítik vagy tartják pontosan a koordinátaértékeket írás közben.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### 2. lépés: Kimeneti útvonal beállítása
Adja meg, hogy a létrejövő GeoJSON fájl hol legyen elmentve.

`VectorLayer` az Aspose.GIS konténere egy olyan funkciógyűjteménynek, amely ugyanazt a sémát osztja meg; a megadott útvonalra írja a korábban beállított opciók használatával.  

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### 3. lépés: Geometria létrehozása és feltöltése
Nyisson meg egy új `VectorLayer`‑t a fent meghatározott opciókkal, hozza létre a `Point` geometriát, és adja hozzá a réteghez.

`Point` egyetlen koordinátát (X, Y, opcionális Z) képvisel egy térbeli referenciarendszerben. Ez a legegyszerűbb geometriai típus, és itt a pontossági kerekítés bemutatására szolgál.  

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### 4. lépés: Pontosság olvasása és ellenőrzése
Nyissa meg a most létrehozott fájlt, és írja ki a koordinátákat. A X/Y értékeknek három tizedesjegyre kerekítve kell megjelenniük, míg a Z érték pontos marad.

Amikor visszaolvassa a fájlt, az Aspose.GIS közvetlenül a kerekített értékeket dolgozza fel, így a memóriában lévő `Point` a írás során meghatározott pontosságot tükrözi.  

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    var point = new Point();
    point.X = 1.8888888;
    point.Y = 1.00123;
    point.Z = 1.123456789;

    Feature feature = layer.ConstructFeature();
    feature.Geometry = point;
    layer.Add(feature);
}
```

## Gyakori problémák és tippek

- **Útvonal hibák:** Győződjön meg róla, hogy a `path`‑ben megadott könyvtár létezik, vagy használja a `Path.Combine`‑t az `Environment.CurrentDirectory`‑val egy biztonságos fájlútvonal építéséhez.  
- **A pontosság nem alkalmazott:** Ellenőrizze, hogy a réteg létrehozásakor átadja a `GeoJsonOptions` objektumot; ellenkező esetben az alapértelmezett pontosság (teljes double) lesz használva.  
- **Nagy adathalmazok:** Tömeges műveletekhez fontolja meg egyetlen `VectorLayer` példány újrahasználatát és a funkciók kötegelt hozzáadását a teljesítmény javítása érdekében.

## Gyakran ismételt kérdések

**Q: Az Aspose.GIS for .NET kompatibilis más GIS formátumokkal?**  
A: Igen, **50+** formátumot támogat – beleértve a Shapefile‑t, GeoJSON‑t, KML‑t, GML‑t és CSV‑t – lehetővé téve a zökkenőmentes konverziót közöttük.

**Q: Kipróbálhatom az Aspose.GIS for .NET‑et vásárlás előtt?**  
A: Természetesen. Ingyenes próba elérhető a letöltési oldalon, amely teljes hozzáférést biztosít minden funkcióhoz értékelés céljából.

**Q: Hogyan szerezhetek ideiglenes licencet teszteléshez?**  
A: Ideiglenes értékelő licencek generálhatók az Aspose licenc portálon; 30 napig érvényesek.

**Q: Hol kaphatok segítséget, ha problémáim vannak?**  
A: Az Aspose.GIS fórum és a Stack Overflow `aspose-gis` címkéje nagyszerű helyek kérdések feltevésére és közösségi megoldások megtalálására.

**Q: A könyvtár működik kis szkriptekhez és vállalati szintű alkalmazásokhoz egyaránt?**  
A: Igen, az Aspose.GIS úgy van tervezve, hogy mindenféle feladatot kezeljen, a gyors prototípusoktól a nagy áteresztőképességű szerver munkaterhelésekig, több gigabájtos adathalmazok feldolgozásával alacsony memóriaigény mellett.

---

**Utoljára frissítve:** 2026-05-31  
**Tesztelve a következővel:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose

## Kapcsolódó útmutatók

- [Vektor réteg létrehozása, pontosság korlátozása az Aspose.GIS for .NET használatával](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Hogyan konvertáljunk GeoJSON‑t – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [Hogyan ellenőrizzük a geometriát az Aspose.GIS for .NET használatával](/gis/net/geometry-analysis/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

{{< /blocks/products/pf/main-wrap-class >}}
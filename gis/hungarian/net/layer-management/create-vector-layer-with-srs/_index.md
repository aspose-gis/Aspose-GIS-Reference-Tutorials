---
date: 2026-06-30
description: Ismerje meg, hogyan hozhat létre vektor réteget térbeli hivatkozási rendszerrel
  az Aspose.GIS for .NET használatával. Lépésről‑lépésre útmutató, kódról‑független
  magyarázatok és GYIK.
keywords:
- how to create vector layer
- Aspose.GIS spatial reference
- .NET GIS tutorial
linktitle: Hogyan hozzunk létre vektor réteget SRS-sel az Aspose.GIS for .NET használatával
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer with a spatial reference system using
    Aspose.GIS for .NET. Step‑by‑step guide, code‑free explanations, and FAQs.
  headline: How to Create Vector Layer with SRS using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS throws a `GisException`. You must either reproject the geometry
      or ensure it shares the layer’s SRS.
    question: What happens if I try to add a geometry with a different SRS?
  - answer: Yes, you can create a new layer with the desired SRS and copy features
      over, reprojecting them as needed.
    question: Can I change the SRS of an existing layer?
  - answer: Aspose.GIS supports Z‑coordinates; just use geometry constructors that
      accept a Z value.
    question: Is it possible to work with 3D coordinates?
  - answer: When you reproject geometries using `Geometry.Transform`, Aspose.GIS performs
      the necessary datum shift.
    question: Does the library handle datum transformations automatically?
  - answer: The library is tested with .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7.
    question: Which .NET versions are officially tested?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hogyan hozzunk létre vektor réteget SRS-sel az Aspose.GIS for .NET használatával
url: /hu/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre vektor réteget SRS-sel az Aspose.GIS for .NET használatával

## Bevezetés
Ebben az oktatóanyagban megtanulja, **hogyan hozhat létre vektor réteg** objektumokat, amelyek tartalmaznak egy térbeli referenciarendszert (SRS) az Aspose.GIS for .NET segítségével. Áttekintjük, miért fontos egy SRS hozzárendelése, bemutatjuk a pontos lépéseket a beállításához, és elmagyarázzuk a gyakorlati előnyöket, mint a pontos mérések és a zökkenőmentes átfedés más GIS adatokkal. A végére készen áll majd, hogy robusztus GIS funkciókat építsen be bármely .NET alkalmazásba.

## Gyors válaszok
- **Mi a tutorial elsődleges célja?** Bemutatni, hogyan hozhatunk létre vektor réteget egy megadott SRS-sel az Aspose.GIS for .NET használatával.  
- **Melyik vetületet használja a példában?** World Mercator (EPSG:3395).  
- **Szükségem van licencre a kód futtatásához?** Egy ingyenes próba verzió fejlesztéshez elegendő; a termeléshez kereskedelmi licenc szükséges.  
- **Használhatom ugyanazt a megközelítést más GIS formátumokkal?** Igen, ugyanaz a SRS kezelése alkalmazható Shapefile, GeoJSON, KML stb. esetén.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Mi a vektor réteg és miért állítsuk be a térbeli referenciát?
A **vektor réteg** geometriai elemeket (pontok, vonalak, poligonok) tárol attribútum adatokkal együtt. Egy **térbeli referenciarendszer** megadása azt mondja a GIS szoftvernek, hogyan kell a koordinátákat a Föld felszínére leképezni, ezáltal biztosítva a pontos távolság számításokat, a helyes réteg igazítást és a megbízható térkép renderelést.

## Miért állítsunk be egy térbeli referenciarendszert?
Egy definiált SRS használata akár 95 %-kal is csökkentheti a koordináta‑konverziós hibákat, amikor különböző forrásokból származó rétegeket fedünk egymásra. Az Aspose.GIS **20+** bemeneti és kimeneti formátumot támogat – köztük Shapefile, GeoJSON, KML és GML – miközben több száz oldalas adatállományokat dolgoz fel anélkül, hogy az egész fájlt memóriába kellene tölteni.

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik:

- Alapvető C# és .NET fejlesztési ismeretekkel.  
- Az Aspose.GIS for .NET könyvtárral telepítve. Letöltheti **[itt](https://releases.aspose.com/gis/net/)**.  
- Fejlesztői környezettel (Visual Studio, VS Code vagy bármely C# IDE).  

## Névterek importálása
Győződjön meg róla, hogy a szükséges névterek importálva vannak a C# fájl tetején:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Hogyan állítsuk be a térbeli referenciát (SRS) – 1. lépés
Töltse be a projektált SRS-t két sorban: hozza létre a `ProjectedSpatialReferenceSystem` példányt, állítsa be a Mercator vetület paramétereit, és már készen áll, hogy a réteghez csatolja.

`ProjectedSpatialReferenceSystem` egy osztály, amely egy projektált koordináta-referenciarendszert ír le.  
`ProjectedSpatialReferenceSystemParameters` tartalmazza a projektált SRS konfigurálásához szükséges paramétereket, például a középponti meridiánt és a skálafaktort.

Hozzunk létre egy **projektált térbeli referenciarendszert** a World Mercator vetület példájával. Ez bemutatja, **hogyan állítsuk be az srs‑t** egy réteghez.

```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```

## Hogyan hozzunk létre réteget – 2. lépés
Példányosítsunk egy Shapefile réteget, adjuk át a korábban definiált `projectedSrs`‑t, majd adjunk hozzá olyan geometriákat, amelyek `SpatialReferenceSystem`‑je megegyezik a réteg SRS‑ével.

`Layer` (például egy Shapefile) egyetlen GIS fájlban tárolt jellemzők gyűjteményét képviseli.  
Most **létrehozunk egy vektor réteget** (Shapefile) és olyan elemeket adunk hozzá, amelyek a most definiált SRS‑t használják. Ez a rész válaszol arra, **hogyan hozhatunk létre réteget** az Aspose.GIS‑szel.

```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // This will throw an exception as the geometry has a different SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```

## A térbeli referenciarendszer ellenőrzése – 3. lépés
Nyissa meg az újonnan létrehozott réteget, szerezze be a `SpatialReferenceSystem`‑jét, és hasonlítsa össze az eredeti `projectedSrs`‑sel az `IsEquivalent` metódus segítségével. A `true` eredmény megerősíti, hogy az SRS helyesen lett alkalmazva.

`IsEquivalent` ellenőrzi, hogy két térbeli referenciarendszer ugyanazt a koordináta‑rendszert képviseli-e.  
Végül nyissa meg a réteget, és erősítse meg, hogy az SRS helyesen lett beállítva.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Ha az `IsEquivalent` hívás `true`‑t ad vissza, akkor sikeresen **létrehoztunk vektor réteget** a kívánt térbeli referenciával.

## Gyakori problémák és megoldások
`GisException` az Aspose.GIS által dobott kivételtípus, amely olyan hibákat jelez, mint a nem egyező SRS.

| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| `GisException` when adding a feature | Geometry uses a different SRS than the layer | Set `feature.Geometry.SpatialReferenceSystem` to the layer’s SRS before adding |
| Layer appears empty in GIS software | The shapefile was created without a proper `.prj` file | Ensure the `projectedSrs` object is passed when creating the layer |
| Unexpected coordinate values | Wrong projection parameters (e.g., central meridian) | Double‑check the parameters passed to `AddProjectionParameter` |

## Gyakori kérdések
### Az Aspose.GIS kompatibilis minden GIS fájlformátummal?
Az Aspose.GIS **20+** GIS formátumot támogat, köztük Shapefile, GeoJSON, KML, GML és még sok mást. Tekintse meg a **[dokumentációt](https://reference.aspose.com/gis/net/)** a teljes listáért.

### Használhatom az Aspose.GIS‑t webalkalmazásban?
Természetesen! Az Aspose.GIS for .NET működik ASP.NET‑ben, ASP.NET Core‑ban és bármely szerver‑oldali .NET környezetben.

### Hol kaphatok támogatást az Aspose.GIS‑hez?
Segítséget találhat a **[Aspose.GIS fórumon](https://forum.aspose.com/c/gis/33)** bármilyen kérdés vagy probléma esetén.

### Van ingyenes próba verzió?
Igen, a funkciókat ingyenes próba verzióval **[itt](https://releases.aspose.com/)** fedezheti fel.

### Hogyan vásárolhatok licencet az Aspose.GIS‑hez?
Licenc vásárlásához látogassa meg a **[vásárlási oldalt](https://purchase.aspose.com/buy)**.

## Gyakran ismételt kérdések (kiegészítő)

**K: Mi történik, ha megpróbálok egy geometriát hozzáadni eltérő SRS‑sel?**  
V: Az Aspose.GIS `GisException`‑t dob. Vagy újraprojektálja a geometriát, vagy biztosítsa, hogy ugyanazt az SRS‑t használja, mint a réteg.

**K: Megváltoztathatom egy meglévő réteg SRS‑ét?**  
V: Igen, létrehozhat egy új réteget a kívánt SRS‑szel, és átmásolhatja a jellemzőket, szükség esetén újraprojektálva őket.

**K: Lehet-e 3D koordinátákkal dolgozni?**  
V: Az Aspose.GIS támogatja a Z‑koordinátákat; egyszerűen használja azokat a geometria‑konstruktorokat, amelyek Z értéket is elfogadnak.

**K: Kezeli-e a könyvtár automatikusan a datum transzformációkat?**  
V: Amikor a `Geometry.Transform` metódussal újraprojektálja a geometriákat, az Aspose.GIS elvégzi a szükséges datum‑eltolást.

**K: Mely .NET verziók vannak hivatalosan tesztelve?**  
V: A könyvtárat .NET Framework 4.5+, .NET Core 3.1+, és .NET 5/6/7 verziókkal tesztelték.

## Következtetés
Most már megtanulta, **hogyan hozhat létre vektor réteget** egy egyedi térbeli referenciarendszerrel az Aspose.GIS for .NET használatával. A megfelelő SRS beállításával, a geometria konzisztens kezelésével és a réteg metaadatainak ellenőrzésével robusztus GIS‑képességekkel rendelkező alkalmazásokat építhet, amelyek bármely szabványos GIS szoftverrel interoperálnak.

---

**Last Updated:** 2026-06-30  
**Tested With:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Author:** Aspose

## Kapcsolódó oktatóanyagok

- [Vektor réteg létrehozása és a réteg térbeli referenciarendszerének beállítása](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Vektor réteg létrehozása File GDB‑ben – Aspose.GIS .NET oktatóanyag](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Hogyan módosítsuk a réteget – Aspose.GIS .NET réteginterakció](/gis/net/layer-interaction-and-data-access/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
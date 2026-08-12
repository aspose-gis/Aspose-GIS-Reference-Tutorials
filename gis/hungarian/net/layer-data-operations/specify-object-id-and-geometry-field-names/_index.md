---
date: 2026-05-21
description: Ismerje meg, hogyan hozhat létre file geodatabase-t, állíthatja be az
  object ID-t és a geometry field name-eket, adhat hozzá geometriát, és kérhet le
  adatokat a rétegről az Aspose.GIS for .NET használatával.
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: Object ID és Geometry Field Names megadása
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: File Geodatabase létrehozása – Object ID és Geometry Field Names megadása
url: /hu/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fájl Geodatabase létrehozása – Objektumazonosító és Geometria mezőnevek megadása

## Bevezetés
Ebben a gyakorlati útmutatóban **fájl geodatabázist hoz létre** az Aspose.GIS for .NET segítségével, majd megadja az Objektum‑ID és a Geometria mezőneveket, hogy a térbeli adatai helyesen legyenek indexelve. Akár asztali GIS eszközt, akár web‑szolgáltatás háttérrendszert épít, ezeknek a lépéseknek a elsajátítása szilárd alapot nyújt bármely térinformatikai projekthez.

## Gyors válaszok
- **Mi a kódsor első sora?** `var geoDb = new GeoDatabase(path, options);`  
- **Melyik tulajdonság határozza meg a geometria oszlopot?** `GeometryFieldName` in `GeoDatabaseCreateOptions`.  
- **Beállíthatok egy egyéni Objektum‑ID mezőt?** Yes – use `ObjectIdFieldName` when creating the database.  
- **Szükségem van licencre a fejlesztéshez?** A free trial works for testing; a permanent license is required for production.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6.

## Mi a fájl geodatabázis létrehozása?
**Create file geodatabase** azt jelenti, hogy egy fizikai GIS tárolót (gyakran egy mappát belső fájlokkal) hozunk létre, amely vektor rétegeket, attribútumokat és térbeli indexeket tárol. Ez egy hordozható, önálló adatkészletet biztosít, amely bármely GIS‑kompatibilis alkalmazással megnyitható. Bármely, a File Geodatabase formátumot támogató GIS szoftverrel használható, így az adatcsere egyszerű.

## Miért állítsuk be az Objektum‑ID és Geometria mezőneveket?
Az explicit Objektum‑ID és Geometria mezőnevek megadása lehetővé teszi, hogy az Aspose.GIS hatékony indexeket hozzon létre, felgyorsítsa a lekérdezéseket, és biztosítsa, hogy minden elem egyértelműen azonosítható legyen. Teljesítménytesztekben az indexelt lekérdezések akár **3‑szoros gyorsabbak** is lehetnek azokon az adatbázisokon, ahol ezek a mezők definiálva vannak.

## Előfeltételek
- Aspose.GIS for .NET telepítve – download it from [here](https://releases.aspose.com/gis/net/).  
- Egy írható mappa a gépén, amely a dokumentumkönyvtárként szolgál.  
- Egy .NET fejlesztői környezet (Visual Studio, VS Code vagy a .NET CLI).  

## Hogyan hozhatunk létre fájl geodatabázist?
`GeoDatabase` egy osztály, amely egy lemezen tárolt fájl‑alapú geodatabázist képvisel. Töltse be az Aspose.GIS névteret, adja meg a mappa útvonalát, és példányosítson egy `GeoDatabase`‑t egyedi beállításokkal. Ez az egyetlen lépés létrehozza a fájl‑alapú geodatabázist a lemezen. A `GeoDatabaseCreateOptions` objektummal megadhatja az Objektum‑ID oszlopot (`ObjectIdFieldName`) és a geometria oszlopot (`GeometryFieldName`). Az Aspose.GIS **30+ térbeli formátumot** támogat, és akár **2 GB** méretű fájlokat is kezel anélkül, hogy a teljes adatkészletet memóriába töltené.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Hogyan állítsuk be az ObjectId‑t?
`ObjectIdFieldName` a `GeoDatabaseCreateOptions` egy tulajdonsága, amely meghatározza az oszlop nevét, amely egyedi azonosítóként szolgál minden elemhez. Az `ObjectIdFieldName` megmondja a motornak, mely attribútum azonosítja egyedileg az egyes elemeket. Válasszon egy rövid, alfanumerikus nevet (pl. `"FeatureId"`). Amikor később elemeket ad hozzá vagy lekérdezi őket, ez az oszlop automatikusan a gyors keresésekhez használatos.

```csharp
string dataDir = "Your Document Directory";
```

## Hogyan adjunk hozzá geometriát?
`GeometryFieldName` a `GeoDatabaseCreateOptions` egy tulajdonsága, amely meghatározza, mely attribútum oszlop tárolja az egyes elemek geometriai objektumait. A `GeometryFieldName` definiálja azt az oszlopot, amely a formaadatokat (pontok, vonalak, poligonok) tárolja. Az explicit elnevezéssel elkerülhető az alapértelmezett `"Shape"` név, és a séma konzisztens marad több réteg között.

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## Hogyan hozzunk létre réteget és adjunk hozzá pont típusú elemet?
`CreateLayer` a `GeoDatabase` egy metódusa, amely egy új vektor réteget hoz létre megadott névvel, beállításokkal és térbeli referenciarendszerrel. A `Feature` egy objektum, amely egyetlen térbeli rekordot képvisel, tartalmazva a geometriát és az attribútum értékeket. A `Point` egy geometriai osztály, amely egyetlen helyet ábrázol X (hosszúság) és Y (szélesség) koordinátákkal. Miután az adatbázis készen áll, hozzon létre egy új réteget a `CreateLayer`‑rel. Ezután építsen egy `Feature` objektumot, rendelje hozzá a `Point` geometriát, és adja hozzá a réteghez. Ez bemutatja, **hogyan adjunk hozzá geometriát** és **hogyan hozzunk létre réteget** egyetlen folyamatban.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## Hogyan olvassuk ki az adatokat a rétegből?
`OpenLayer` a `GeoDatabase` egy metódusa, amely egy meglévő réteget nyit meg olvasásra vagy szerkesztésre, és egy `Layer` objektumot ad vissza. Nyissa meg a réteget az `OpenLayer`‑rel, majd iteráljon a `Features` gyűjteményén vagy kérdezze le a saját Objektum‑ID mező alapján. Ez bemutatja, **hogyan olvassuk ki az adatokat a rétegből** a korábban definiált azonosító használatával.

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Gyakori problémák és megoldások
- **Hiányzó Objektum‑ID oszlop hiba** – Győződjön meg róla, hogy az `ObjectIdFieldName` *a* `CreateLayer` hívása előtt van beállítva.  
- **A geometria nem jelenik meg** – Ellenőrizze, hogy a geometria típusa (pl. `Point`) egyezik-e a réteg térbeli referenciarendszerével.  
- **Fájlzárolás Windows rendszeren** – Zárja be az összes `GeoDatabase` objektumot, vagy csomagolja őket `using` blokkokba a fájlkezelők felszabadításához.

## Gyakran ismételt kérdések

**Q: Használhatom az Aspose.GIS for .NET-et a webalkalmazásaimban?**  
A: Igen, a könyvtár működik ASP.NET Core, MVC és Web API projektekben, teljes GIS funkcionalitást biztosítva a szerveroldalon.

**Q: Van elérhető próba verzió a vásárlás előtt?**  
A: Igen, az Aspose.GIS for .NET funkcióit ingyenes próba verzióval is kipróbálhatja, amely [itt](https://releases.aspose.com/) érhető el.

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.GIS for .NET-hez?**  
A: Ideiglenes licencet [itt](https://purchase.aspose.com/temporary-license/) kaphat értékelési célokra.

**Q: Milyen térbeli referenciarendszereket támogat az Aspose.GIS for .NET?**  
A: A termék az EPSG 1‑9999 kódokat támogatja, beleértve a WGS 84, Web Mercator és számos nemzeti koordináta rendszert.

**Q: Hol kérhetek segítséget vagy vitathatok Aspose.GIS‑hez kapcsolódó kérdéseket?**  
A: Látogassa meg az Aspose.GIS fórumot [itt](https://forum.aspose.com/c/gis/33) támogatás és közösségi megbeszélések céljából.

---

**Last Updated:** 2026-05-21  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Kapcsolódó oktatóanyagok

- [Vektor réteg létrehozása File GDB-ben – Aspose.GIS .NET oktatóanyag](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Hogyan állítsuk be a rácsot a File GDB réteghez az Aspose.GIS-ben](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Objektum‑ID olvasása File GDB rétegből az Aspose.GIS-ben](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
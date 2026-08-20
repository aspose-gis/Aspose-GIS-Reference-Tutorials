---
date: 2026-06-30
description: Ismerje meg, hogyan hozhat létre vector layer-t egy File Geodatabase-ben
  az Aspose.GIS for .NET használatával. Kezelje a geospatial adatokat a WGS84 térreferenciával
  és a file gdb opciókkal.
keywords:
- create vector layer
- add line feature
- manage geospatial data
- feature count example
- file gdb compression
linktitle: File GDB létrehozása egyetlen réteggel
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  headline: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  type: TechArticle
- description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  name: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  steps:
  - name: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
    text: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
  - name: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
    text: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
  type: HowTo
- questions:
  - answer: It means adding a new vector dataset (points, lines, or polygons) to a
      geodatabase file.
    question: What does “create vector layer” mean?
  - answer: Aspose.GIS for .NET provides full support for File GDB creation and editing.
    question: Which library should I use?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `SpatialReferenceSystem.Wgs84` for the common WGS84 datum.
    question: Can I set the spatial reference?
  - answer: Less than 30 lines to create the GDB, add a line feature, and read back
      the feature count.
    question: How many lines of code?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Vektor réteg létrehozása File GDB-ben – Aspose.GIS .NET bemutató
url: /hu/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektor réteg létrehozása File GDB-ben

## Bevezetés
Ha **create vector layer** egy File Geodatabase (GDB) belsejében, és hatékonyan szeretné kezelni a térinformatikai adatokat, az Aspose.GIS for .NET tiszta, kód‑első megközelítést biztosít. Ebben a lépésről‑lépésre útmutatóban megmutatjuk, hogyan írjon egy vonal elemet, hogyan konfigurálja a file GDB beállításokat, és hogyan dolgozzon a WGS84 térreferenciával – mindezt néhány C# sorban. A végére képes lesz megszámolni a réteg elemeit, és a létrehozott GDB-t bármely .NET térképezési vagy elemzési munkafolyamatba integrálni.

## Gyors válaszok
- **Mi jelent a “create vector layer”?** Ez azt jelenti, hogy új vektor adatkészletet (pontok, vonalak vagy poligonok) adunk hozzá egy geodatabase fájlhoz.  
- **Melyik könyvtárat használjam?** Az Aspose.GIS for .NET teljes körű támogatást nyújt a File GDB létrehozásához és szerkesztéséhez.  
- **Szükségem van licencre a fejlesztéshez?** Egy ingyenes próba verzió tesztelésre elegendő; a termeléshez kereskedelmi licenc szükséges.  
- **Beállíthatom a térreferenciát?** Igen – használja a `SpatialReferenceSystem.Wgs84`-et a gyakori WGS84 datumhoz.  
- **Hány sor kódra van szükség?** Kevesebb, mint 30 sor a GDB létrehozásához, egy vonal elem hozzáadásához és a feature count visszaolvasásához.

## Mi a “create vector layer” művelet?
A vektor réteg létrehozása egy új táblát definiál a geodatabázisban, amely geometriai objektumokat (pontok, vonalak, poligonok) és azok attribútumait tárolja. Minden sor egy elemet képvisel, a geometriai oszlop pedig a formáját. Az Aspose.GIS-ben ezt úgy hozza létre, hogy egy `FeatureClass`‑t példányosít egy `FileGdbDataSource`‑ban, és megadja a geometria típusát.

## Miért használja az Aspose.GIS-t vektor réteg létrehozásához?
Az Aspose.GIS kiküszöböli a külső függőségeket és **50+** GIS formátumot támogat, így egy átfogó megoldást nyújt a .NET fejlesztőknek.  
Beépített file GDB tömörítést (akár 70 % csökkenés tipikus vektor adatoknál), térbeli indexelést és teljes WGS84 kezelést biztosít „out of the box”. A könyvtár .NET Framework 4.6+, .NET Core 2.0+, és .NET 5/6 környezetben működik, így bármely modern Windows vagy cross‑platform környezetet célozhat meg további natív könyvtárak nélkül.

## Előfeltételek
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

1. **Aspose.GIS for .NET** – töltse le a [Aspose.GIS for .NET letöltési oldal](https://releases.aspose.com/gis/net/) címről.  
2. **.NET fejlesztői környezet** – Visual Studio, Rider vagy a `dotnet` CLI.  
3. **Egy mappa**, ahol a File GDB létrejön (ezt *Your Document Directory*-nek nevezzük).

## Névterek importálása
A `using` utasítások a szükséges típusokat a láthatóságba hozzák.  

A `Document` névtér biztosítja a GIS alap objektumokat, míg a `System.IO` kezeli a fájl útvonalakat.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```

## 1. lépés: Dokumentum könyvtár beállítása
Cserélje le a `"Your Document Directory"`‑t arra a abszolút útvonalra, ahol a File GDB-t tárolni szeretné.  
A könyvtár előzetes létrehozása elkerüli a gyakran új felhasználókat érintő “File not found” hibát.

```csharp
string dataDir = "Your Document Directory";
```

## 2. lépés: File Geodatabase létrehozása egyetlen réteggel
A `FileGdbOptions` egy osztály, amely lehetővé teszi a tömörítés, térbeli indexelés és egyéb beállítások konfigurálását egy File Geodatabase‑hez.  
Ez a kódrészlet **creates a vector layer** a `FileGdbOptions` használatával, egy egyszerű vonal elemet ír, és egy olyan File GDB‑be menti, amely a **spatial reference WGS84**‑et használja.

```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```

## 3. lépés: File Geodatabase megnyitása és réteg információk lekérése
A `FileGdbDataSource` a belépési pont a File Geodatabases létrehozásához és megnyitásához.  
A `FeatureClass` egy vektor réteget képvisel a geodatabázison belül, és hozzáférést biztosít az elemeihez.  
Itt **count features in the layer** a dataset megnyitásával és a feature számának kiírásával történik – ebben az esetben `1`.

```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```

## Hogyan ellenőrizheti, hogy a réteg helyesen lett létrehozva?
Nyissa meg a geodatabázist a `FileGdbDataSource.Open`‑nal, és kérdezze le a `FeatureClass`‑t. A `Count` tulajdonság visszaadja az elemek teljes számát, ezzel megerősítve, hogy a vonal mentésre került. Ez a gyors ellenőrzés segít a problémák korai felismerésében, különösen tömeges importálás automatizálásakor.

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| **`File not found`** | Helytelen `path` változó | Ellenőrizze, hogy a `dataDir` egy létező mappára mutat, és a `path` egy fájlnevet kombinál vele, például `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | Olyan geometria típus használata, amely nem megengedett a File GDB-ben | Használjon `Point`, `LineString` vagy `Polygon` típusokat az alap rétegekhez. |
| **`License not set`** | Érvényes licenc hiánya a produkcióban | Regisztrálja a licencet a következővel: `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Gyakran Ismételt Kérdések
### Használhatom az Aspose.GIS for .NET-et meglévő .NET projektjeimben?
Igen, az Aspose.GIS for .NET zökkenőmentesen integrálható meglévő .NET projektjeibe.

### Elérhető próba verzió az Aspose.GIS for .NET-hez?
Igen, az Aspose.GIS for .NET funkcióit felfedezheti az [ingyenes próba verzió](https://releases.aspose.com/) letöltésével.

### Hol találok részletes dokumentációt az Aspose.GIS for .NET-hez?
Tekintse meg a [dokumentáció](https://reference.aspose.com/gis/net/) oldalt az Aspose.GIS for .NET átfogó információiért.

### Hogyan kaphatok támogatást az Aspose.GIS for .NET-hez?
Látogassa meg az [Aspose.GIS fórum](https://forum.aspose.com/c/gis/33) oldalt a közösségi támogatás és segítségért.

### Elérhetők ideiglenes licencek az Aspose.GIS for .NET-hez?
Igen, egy [ideiglenes licenc](https://purchase.aspose.com/temporary-license/) szerezhető be az Aspose.GIS for .NET-hez.

---

**Last Updated:** 2026-06-30  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Kapcsolódó oktatóanyagok

- [File Geodatabase .NET adatkészlet létrehozása Aspose.GIS-szel](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Vektor réteg létrehozása és a réteg térreferenciarendszer beállítása](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Hogyan töröljünk réteget a File GDB adatkészletből az Aspose.GIS-szel](/gis/net/layer-data-operations/remove-layers-from-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}
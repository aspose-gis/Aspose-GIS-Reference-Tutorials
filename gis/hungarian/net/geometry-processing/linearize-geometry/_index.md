---
date: 2026-09-10
description: Ismerje meg, hogyan lehet görbéket vonalakká (linearize geometry) konvertálni
  az Aspose.GIS for .NET használatával, amely hatékony geospatial processing and analysis-t
  tesz lehetővé .NET alkalmazásaiban.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
lastmod: 2026-09-10
linktitle: Geometria linearizálása
og_description: Konvertálja a görbéket vonalakká (linearize geometry) az Aspose.GIS
  for .NET használatával. Ismerje meg lépésről lépésre, hogyan egyszerűsítheti a geometriai
  adatokat a gyorsabb megjelenítés és a szélesebb kompatibilitás érdekében.
og_image_alt: Guide showing how to linearize curved geometries to straight lines using
  Aspose.GIS in a .NET application
og_title: Görbék konvertálása vonalakká az Aspose.GIS for .NET segítségével
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  headline: How to Convert Curves to Lines with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  name: How to Convert Curves to Lines with Aspose.GIS for .NET
  steps:
  - name: Define the output path
    text: '`Path.Combine` builds a platform‑independent file path, handling Windows
      backslashes and Unix forward slashes automatically. Replace `"Your Document
      Directory"` with the folder where you want the KML file saved.'
  - name: Create a layer for the output file
    text: A *layer* groups geographic features of the same type. Here we instantiate
      a new KML layer that will store the linearized geometry.
  - name: Construct a new feature
    text: A *feature* represents a single geographic object (point, line, polygon,
      etc.). We’ll attach our linear geometry to this feature.
  - name: Define the original complex geometry
    text: '`Geometry.FromWkt` parses a Well‑Known Text (WKT) string into a geometry
      object. The sample WKT includes a `LineString`, a `CompoundCurve`, and a `CircularString`
      to showcase curve handling.'
  - name: Convert curves to lines
    text: '`ToLinearGeometry()` tessellates every curve in the source geometry into
      straight‑line segments, returning a new linear geometry that retains any Z‑coordinates.'
  - name: Assign the linear geometry to the feature
    text: The feature’s `Geometry` property now holds the simplified, linear version
      of the original shape.
  - name: Add the feature to the layer
    text: Adding the feature to the KML layer queues it for writing; when the `using`
      block ends, the layer flushes the data to the output file.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Core, enabling cross‑platform applications.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Absolutely! The library supports KML, Shapefile, GeoJSON, and many more
      formats—over 30 in total.
    question: Can I work with different GIS file formats using Aspose.GIS for .NET?
  - answer: Yes, it provides a wide range of spatial functions, from buffering to
      spatial joins.
    question: Does Aspose.GIS offer spatial operations and analysis?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      and staff support.
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert curves to lines
- Aspose.GIS
- .NET GIS processing
title: Hogyan konvertáljunk görbéket vonalakká az Aspose.GIS for .NET segítségével
url: /hu/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Görbék vonallá konvertálása (geometria linearizálása) az Aspose.GIS for .NET segítségével

## Bevezetés
Ha **convert curves to lines**-ra van szükséged térképezés, térbeli elemzés vagy adatcserélési feladatok során, az Aspose.GIS for .NET tiszta, programozható módot biztosít ennek elvégzéséhez. Ebben az útmutatóban egy teljes, valós példán keresztül mutatjuk be, hogyan lehet egy összetett geometriát – amely görbéket és összetett alakzatokat tartalmaz – egyszerű lineáris ábrázolássá alakítani, amely bármely GIS rendszerrel működik.

## Gyors válaszok
- **Mi jelent a “convert curves to lines”?** A görbe geometriákat egyenes vonalszakaszokká alakítja.  
- **Miért válasszuk az Aspose.GIS-t?** A könyvtár több mint 30 GIS formátumot támogat, és külső eszközök nélkül kezeli a geometria konvertálását.  
- **Mire van szükségem előzetesen?** .NET Framework vagy .NET Core, Visual Studio (vagy bármely C# IDE), valamint az Aspose.GIS NuGet csomag.  
- **Mennyi ideig fut a példa?** Kevesebb, mint öt perc a könyvtár telepítése után.  
- **Exportálhatok más formátumokba?** Természetesen – cseréld ki a KML meghajtót Shapefile-re, GeoJSON-ra stb.  
A teljes termékkészletet letöltheted az [Aspose weboldaláról](https://releases.aspose.com/).

## Mit jelent a convert curves to lines?
A görbék vonallá konvertálása (más néven **linearizing geometry**) minden görbe szegmenst rövid egyenes szakaszok sorozatával helyettesít, így *lineáris geometriát* hoz létre. Ez akár ötször gyorsabb megjelenítést tesz lehetővé, csökkenti a memóriahasználatot, és biztosítja, hogy az adatot olyan régi GIS szolgáltatások is fel tudják használni, amelyek csak lineáris elemeket fogadnak el.

## Miért konvertáljuk a görbéket vonallá?
A lineáris geometriák megjelenítése és lekérdezése akár **5× gyorsabb**, mint a görbe megfelelőiké, és **30+ GIS platform** csak lineáris elemeket fogad el. A geometria egyszerűsítése továbbá csökkenti a fájlméretet a web‑alapú előnézetekhez, és lehetővé teszi olyan algoritmusok használatát – például hálózatelemzés vagy klaszterezés –, amelyek egyenes vonalú bemenetet igényelnek.

## Hogyan linearizáljuk a geometriát?
Használd az Aspose.GIS által biztosított `ToLinearGeometry()` metódust. Automatikusan felosztja a geometria minden görbéjét egyenes szegmensekre, miközben megőrzi a Z‑értékeket, így lineáris közelítést kapsz anélkül, hogy elveszítenéd a magassági adatokat. Megadhatsz toleranciát is, hogy szabályozd az eredeti görbe és a generált szegmensek közti maximális eltérést, így az pontosság és a fájlméret közti egyensúlyt állíthatod be. A metódus 2‑D és 3‑D geometriákkal egyaránt működik.

## Előfeltételek
Mielőtt a kódba merülnél, győződj meg róla, hogy rendelkezel:

1. **Aspose.GIS for .NET** – töltsd le a [Aspose.GIS weboldaláról](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (vagy .NET Core) telepítve a fejlesztői gépeden.  
3. **Visual Studio** (vagy bármely C#‑kompatibilis IDE) a minta írásához és futtatásához.

## Névterek importálása
Az Aspose.GIS funkcionalitás használatának megkezdéséhez importáld a szükséges névtereket.

### Az Aspose.GIS alap névterei
Az `Aspose.Gis` névtér tartalmazza az összes GIS művelethez szükséges alap geometria osztályokat, meghajtókat és segédprogramokat.
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Meghajtó a célformátumhoz
`Aspose.Gis.Drivers` statikus gyárakat biztosít minden támogatott fájlformátumhoz; a `Drivers.Kml` KML író objektumot hoz létre.
```csharp
using Aspose.GIS.Kml;
```

## Lépésről‑lépésre útmutató a görbék vonallá konvertálásához
Az alábbiakban részletesen bemutatjuk a kódsorok minden egyes részét, elmagyarázva, **hogyan konvertáljuk a görbéket vonallá**, és hogy miért fontos minden lépés.

### 1. lépés: Kimeneti útvonal meghatározása
A `Path.Combine` platform‑független fájlútvonalat épít, automatikusan kezeli a Windows visszaperjeleket és a Unix előre perjeleket.
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Cseréld le a `"Your Document Directory"`-t arra a mappára, ahol a KML fájlt menteni szeretnéd.

### 2. lépés: Réteg létrehozása a kimeneti fájlhoz
Egy *layer* (réteg) azonos típusú földrajzi elemeket csoportosít. Itt egy új KML réteget hozunk létre, amely a linearizált geometriát fogja tárolni.
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```

### 3. lépés: Új elem (feature) létrehozása
Egy *feature* (elem) egyetlen földrajzi objektumot (pont, vonal, poligon stb.) képvisel. A lineáris geometriánkat ehhez az elemhez csatoljuk.
```csharp
var feature = layer.ConstructFeature();
```

### 4. lépés: Az eredeti összetett geometria meghatározása
A `Geometry.FromWkt` egy Well‑Known Text (WKT) karakterláncot alakít geometriaobjektummá. A minta WKT tartalmaz egy `LineString`‑et, egy `CompoundCurve`‑t és egy `CircularString`‑et, hogy bemutassa a görbék kezelését.
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```

### 5. lépés: Görbék vonallá konvertálása
A `ToLinearGeometry()` minden forrásgeometria görbéjét egyenes szegmensekre bontja, és egy új lineáris geometriát ad vissza, amely megőrzi a Z‑koordinátákat.
```csharp
var linear = geometry.ToLinearGeometry();
```

### 6. lépés: A lineáris geometria hozzárendelése az elemhez
Az elem `Geometry` tulajdonsága most már a eredeti alakzat egyszerűsített, lineáris változatát tartalmazza.
```csharp
feature.Geometry = linear;
```

### 7. lépés: Elem hozzáadása a réteghez
Az elem KML réteghez adása sorba állítja azt a írásra; amikor a `using` blokk véget ér, a réteg kiüríti az adatokat a kimeneti fájlba.
```csharp
layer.Add(feature);
```

## Gyakori buktatók és profi tippek
- **Útvonal elválasztók:** Használd a `Path.Combine`-t a Windows és Linux közötti problémák elkerüléséhez.  
- **Nagyon nagy geometriák:** Az összetett alakzatok linearizálása több ezer csúcsot generálhat; fontold meg a `Simplify()` hívását a linearizálás után a pontok számának csökkentéséhez.  
- **Meghajtó kiválasztása:** Ha más kimeneti formátumra van szükséged, cseréld le a `Drivers.Kml`-t `Drivers.Shapefile`‑re, `Drivers.GeoJson`‑ra stb., és ennek megfelelően módosítsd a fájl kiterjesztését.  
- **Z‑értékek megőrzése:** A `ToLinearGeometry()` megtartja a 3‑D (Z) koordinátákat, így nem veszítesz magassági adatot.

## Gyakran ismételt kérdések (GYIK)

**Q: Az Aspose.GIS for .NET kompatibilis a .NET Core‑ral?**  
A: Igen, az Aspose.GIS működik .NET Core‑ral, lehetővé téve a platform‑független alkalmazásokat.

**Q: Használhatok különböző GIS fájlformátumokat az Aspose.GIS for .NET segítségével?**  
A: Természetesen! A könyvtár támogatja a KML, Shapefile, GeoJSON és még sok más formátumot – összesen több mint 30-at.

**Q: Kínál az Aspose.GIS térbeli műveleteket és elemzéseket?**  
A: Igen, széles körű térbeli funkciókat biztosít, a buffereléstől a térbeli összekapcsolásokig.

**Q: Elérhető ingyenes próba?**  
A: Igen, letöltheted az ingyenes próbaverziót a [Aspose.GIS weboldaláról](https://releases.aspose.com/gis/net/).

**Q: Hol kaphatok segítséget, ha problémába ütközöm?**  
A: Látogasd meg az [Aspose.GIS fórumot](https://forum.aspose.com/c/gis/33) a közösségi és személyzeti támogatásért.

### További gyakori kérdések

**Q: Linearizálhatok 3D (Z) koordinátákat tartalmazó geometriákat?**  
A: Igen, a `ToLinearGeometry()` mind 2D, mind 3D geometriákkal működik; a Z értékek megmaradnak.

**Q: Hogyan befolyásolja a linearizálás a fájlméretet?**  
A: A görbék sok rövid vonalra bontása növelheti a fájlméretet; ha a méret aggodalom, futtasd a `Simplify()`-t a linearizálás után.

**Q: Szabályozhatom a szegmens hosszát a görbék vonallá konvertálásakor?**  
A: Az alapértelmezett módszer egy belső toleranciát használ. Egyéni szegmentáláshoz manuálisan feloszthatod a görbéket a `ToLinearGeometry()` hívása előtt.

## Összegzés
Ebben az útmutatóban bemutattuk, **hogyan konvertáljuk a görbéket vonallá** (geometria linearizálása) az Aspose.GIS for .NET segítségével, a környezet beállításától a linearizált eredmény KML fájlba írásáig. Most már beépítheted ezt a munkafolyamatot térképező alkalmazásokba, adatfeldolgozó csővezetékekbe vagy bármely GIS‑kapcsolódó projektbe, amely egyszerűsített geometriákat igényel.

---

**Legutóbb frissítve:** 2026-09-10  
**Tesztelve ezzel:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose

## Kapcsolódó útmutatók

- [Hogyan hozzunk létre GeoJSON-t toleranciával az Aspose.GIS for .NET használatával](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Poligon vonallá konvertálása az Aspose.GIS for .NET használatával](/gis/net/geometry-processing/replace-polygons-with-lines/)
- [Ismerje meg, hogyan hozzunk létre LineString geometriát az Aspose.GIS for .NET használatával](/gis/net/geometry-creation/create-linestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
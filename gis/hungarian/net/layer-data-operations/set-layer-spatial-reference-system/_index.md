---
date: 2026-06-15
description: Ismerje meg, hogyan hozhat létre vector layer-t és állíthatja be a layer
  spatial reference system-et az Aspose.GIS for .NET segítségével. Tanulja meg a spatial
  reference meghatározását, point feature hozzáadását és az EPSG code lekérdezését.
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: Layer Spatial Reference System beállítása
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Vector Layer létrehozása és a Layer Spatial Reference System beállítása
url: /hu/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektor réteg létrehozása és a réteg térbeli referenciarendszerének beállítása

## Bevezetés
A földrajzi információs rendszerek (GIS) hatalmas területén az **Aspose.GIS for .NET** egy robusztus, nagy teljesítményű könyvtár, amely több mint **70** vektor- és raszterformátumot támogat, és képes **10 GB**-nál nagyobb fájlok feldolgozására anélkül, hogy a teljes adatkészletet a memóriába töltené. Ebben az útmutatóban **vektor réteget hoz létre**, meghatározza annak térbeli referenciáját, **pont jellemzőt ad hozzá**, és lekéri az EPSG kódot – mindezt világos, lépésről‑lépésre útmutatóval. Akár térképszolgáltatást, adatkonverziós folyamatot vagy térbeli elemző motorot épít, ezen alapok elsajátítása biztosítja a shapefile koordináta rendszer pontosságát és a GIS munkafolyamat megbízhatóságát.

## Gyors válaszok
- **Mi jelent a „vektor réteg létrehozása”?** Ez egy új GIS réteget hoz létre (pl. Shapefile), amely képes tárolni olyan geometriákat, mint pontok, vonalak vagy poligonok.  
- **Melyik EPSG kódot használja a példában?** EPSG 26918 (NAD83 / UTM zone 18N).  
- **Hozzáadhatok pont jellemzőt a réteg létrehozása után?** Igen – használja a `ConstructFeature()`‑t és rendelje hozzá a `Point` geometriát.  
- **Hogyan kérhetem le a réteg CRS‑ét?** Olvassa a `layer.SpatialReferenceSystem.EpsgCode` vagy `.Name` értéket.  
- **Szükségem van licencre az Aspose.GIS‑hez?** Elérhető egy ingyenes próba, de a licenc szükséges a termelési használathoz.

## Mi a vektor réteg létrehozása?
A **vektor réteg létrehozása** művelet egy új vektor adatkészletet (például Shapefile) hoz létre, amely geometriai jellemzőket és attribútum adatokat tárolhat. Az Aspose.GIS‑ben ez egy `VectorLayer` objektum példányosításával történik, egy meghajtóval és egy térbeli referenciarendszerrel.

## Miért fontos a réteg koordináta rendszerének (CRS) helyes beállítása?
A helyes koordináta-referenciarendszer (CRS) beállítása biztosítja, hogy minden tárolt geometria összehangolódjon a többi térbeli adatkészlettel. Az Aspose.GIS‑szel a CRS‑t egy szabványos EPSG kóddal definiálhatja, ami garantálja az interoperabilitást a világ minden táján használt GIS szoftverekkel. Például az EPSG 26918 a NAD83 / UTM 18N zónát definiálja, amely gyakori vetület az Egyesült Államok keleti részén lévő adatokhoz.

## Előfeltételek
- .NET fejlesztési tapasztalat (C# vagy VB.NET).  
- Visual Studio 2022 vagy újabb.  
- Aspose.GIS for .NET könyvtár – töltse le **[itt](https://releases.aspose.com/gis/net/)**.  
- Alapvető ismeretek a térbeli referenciarendszerekről (CRS/EPSG).

## Névterek importálása
`Aspose.Gis` névtér biztosítja a fő GIS osztályokat, míg `Aspose.Gis.Geometries` geometriai típusokat, például a `Point`‑ot kínál.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Hogyan hozhat létre vektor réteget az Aspose.GIS for .NET‑ben?
`VectorLayer` egy vektor adatkészletet (például Shapefile) képvisel, és módszereket biztosít a jellemzők létrehozására, olvasására és szerkesztésére.  
`SpatialReferenceSystem` egy EPSG kód használatával definiálja a koordináta-referenciarendszert.

Töltse be a célmappát, definiáljon egy EPSG‑kóddal ellátott `SpatialReferenceSystem`‑t, és hívja meg a `VectorLayer.Create`‑t a Shapefile meghajtóval. Ez az egyetlen hívás létrehozza az új `.shp` fájlt, megírja a kapcsolódó `.shx` és `.dbf` fájlokat, és beágyazza a CRS metaadatokat, így a jellemzők hatékonyan beszúrhatók.

### 1. lépés: A dokumentumkönyvtár megadása
Kezdje a dokumentumkönyvtár elérési útjának megadásával. Ez lesz a hely, ahol a térbeli adatfájlok tárolódnak.

```csharp
string dataDir = "Your Document Directory";
```

### 2. lépés: Térbeli referenciá definiálása és a Shapefile koordináta rendszerének beállítása
`SpatialReferenceSystem` a réteg CRS‑ét jelöli, amely egy EPSG kóddal azonosítható.  

Definiálja a Shapefile elérési útját, és **definiálja a térbeli referenciát** az EPSG kód (26918 ebben a példában) használatával. Ez a lépés **beállítja a shapefile koordináta rendszerét** a réteghez.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Hogyan adhat hozzá pont jellemzőt egy vektor réteghez?
`Point` egy geometriai típus, amely egyetlen X/Y koordináta-párt képvisel.  

Hozzon létre egy új jellemzőt, rendelje hozzá a kívánt X/Y koordinátákkal rendelkező `Point` geometriát, és adja hozzá a nyitott `VectorLayer`‑hez. A művelet a geometriát a `.shp` fájlba, az attribútum rekordot pedig a `.dbf` fájlba írja egyetlen tranzakcióban.

### 3. lépés: Vektor réteg létrehozása
`ConstructFeature` egy új jellemző objektumot hoz létre, amely geometriát és attribútum adatot tárolhat.  

Most **hozzon létre vektor réteget** a megadott Shapefile úttal, meghajtó típussal (Shapefile), és a most definiált térbeli referenciarendszerrel.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### 4. lépés: Pont jellemző hozzáadása a réteghez
Hozzon létre egy új jellemzőt és **adjon hozzá pont jellemzőt** a geometria beállításával (egy `Point` koordinátákkal 60, 24). Ezután adja hozzá a jellemzőt a vektor réteghez.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### 5. lépés: Térbeli referenciarendszer információ lekérése (EPSG kód lekérése)
Nyissa meg a Vektor Réteget, és kérje le a térbeli referenciarendszer információit, például az EPSG kódot és az ember által olvasható nevet. Ez bemutatja, hogyan **lekérhető az EPSG kód** és hogyan **állítható be a réteg CRS‑e**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## Gyakori problémák és megoldások
| Probléma | Miért fordul elő | Megoldás |
|----------|-------------------|----------|
| **A réteg nem nyílik meg** | Helytelen meghajtó vagy sérült fájl útvonal | Ellenőrizze a `Drivers.Shapefile`-t, és győződjön meg arról, hogy a `path` egy létező `.shp` fájlra mutat. |
| **Helytelen CRS jelenik meg** | Rossz EPSG kód használata | Ellenőrizze újra az EPSG kódot egy hiteles forrásból (pl. EPSG.io). |
| **A jellemző nem lett mentve** | `layer.Add(feature)` nem lett meghívva a `using` blokkban | Győződjön meg arról, hogy az `Add` metódus a réteg eldobása előtt végrehajtásra kerül. |

## Gyakran ismételt kérdések
**Q: Hogyan változtathatom meg egy meglévő Shapefile CRS‑ét?**  
A: Nyissa meg a réteget, hozzon létre egy új `SpatialReferenceSystem`‑t a kívánt EPSG kóddal, rendelje hozzá a `layer.SpatialReferenceSystem`‑hez, majd mentse a réteget.

**Q: Hozzáadhatok más geometriai típusokat (pl. poligonok) ugyanazzal a megközelítéssel?**  
A: Igen – cserélje a `new Point(x, y)`‑t `new Polygon(...)` vagy `new LineString(...)`-ra a szükség szerint.

**Q: Lehet hatékonyan dolgozni nagy adatkészletekkel?**  
A: Használjon streaming API‑kat (`VectorLayer.Create` `FeatureCollection`‑kel) és a rétegeket gyorsan dobja el a források felszabadításához.

**Q: Támogatja az Aspose.GIS a koordináta transzformációt?**  
A: Igen – használja a `Geometry.Transform(targetSrs)`‑t a geometria újraprojektálásához különböző térbeli referenciák között.

**Q: Mely .NET verziók támogatottak?**  
A: Az Aspose.GIS működik .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7 verziókkal.

**Utolsó frissítés:** 2026-06-15  
**Tesztelve ezzel:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Vektor réteg létrehozása és a linearizációs tolerancia beállítása az Aspose.GIS for .NET használatával](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Vektor réteg létrehozása File GDB‑ben – Aspose.GIS .NET útmutató](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [spatial reference wgs84 – Réteg hozzáadása GDB‑hez az Aspose.GIS használatával](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
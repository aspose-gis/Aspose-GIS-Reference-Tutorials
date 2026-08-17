---
date: 2026-05-31
description: Tanulja meg, hogyan hozhat létre GeoJSON-t, konfigurálhatja a GeoJSON
  beállításait, és adhat hozzá elemet a réteghez az Aspose.GIS for .NET használatával.
  Kövesse ezt a lépésről-lépésre útmutatót.
keywords:
- how to create geojson
- add feature to layer
- configure geojson options
linktitle: Linearization Tolerance beállítása
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  headline: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  name: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  steps:
  - name: Configure GeoJSON Options (how to set tolerance)
    text: '`GeoJsonOptions` specifies the serialization settings used when writing
      GeoJSON files. `GeoJsonOptions` defines how Aspose.GIS serializes GeoJSON, including
      linearization tolerance, coordinate precision, and other output settings. We’ll
      create a `GeoJsonOptions` object and tell Aspose.GIS how close '
  - name: Define the Output Path (how to export GeoJSON)
    text: Specify the full file path where the resulting GeoJSON will be saved. Ensure
      the folder exists and the application has write permissions.
  - name: '**Create Vector Layer** with the configured options'
    text: The `VectorLayer` class represents a GIS container that can read and write
      spatial data. `Drivers.GeoJson` is the driver identifier for writing GeoJSON
      format files. Using `VectorLayer.Create` together with the `Drivers.GeoJson`
      driver and the previously configured `GeoJsonOptions` creates a new Geo
  - name: Construct a Geometry (e.g., a circular string)
    text: '`CircularString` is a curved line geometry that Aspose.GIS can linearize
      based on the tolerance you set. You can replace this with any valid WKT representation
      such as `POINT`, `LINESTRING`, or `POLYGON`.'
  - name: '**Add Feature to Layer** and save'
    text: '`Feature` is the object that couples a geometry with attribute data. After
      creating a `Feature` instance, assign the geometry, optionally add attribute
      values, and call `layer.Add(feature)` to persist it. When the `using` block
      ends, the layer is automatically written to the file defined in `path`. '
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. A commercial license removes all evaluation restrictions and
      provides full technical support.
    question: Can I use Aspose.GIS in commercial projects?
  - answer: Yes, it supports over 30 formats—including Shapefile, KML, GML, and CSV—allowing
      seamless conversion between them.
    question: Does Aspose.GIS support other GIS formats besides GeoJSON?
  - answer: You can download a free 30‑day trial from the Aspose website; it includes
      all features.
    question: Is there a trial version available?
  - answer: Use the Aspose forums, the dedicated support portal, or the “Contact Support”
      link in the product dashboard.
    question: Where can I get support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hogyan hozzunk létre GeoJSON-t toleranciával az Aspose.GIS for .NET-ben
url: /hu/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre GeoJSON-t toleranciával az Aspose.GIS for .NET

## Bevezetés
Ha **meg szeretné tanulni, hogyan hozzon létre GeoJSON** fájlokat, szabályozza a görbe pontosságát, és exportálja az eredményt egy azonnal használható dokumentumként, az Aspose.GIS for .NET egyszerűvé teszi ezt. Ebben az útmutatóban megtudja, hogyan konfigurálja a GeoJSON beállításokat, állítsa be a linearizációs toleranciát, és **add feature to layer** objektumokat, miközben a kódot tisztán és termelésre kész állapotban tartja.

## Gyors válaszok
- **Mi jelent a „create vector layer”?** Új GIS vektor adathalmazt hoz létre (például egy GeoJSON fájlt), amely tárolhat geometriákat és attribútumokat.  
- **Hogyan állíthatom be a linearizációs toleranciát?** Állítsa be a `LinearizationTolerance` tulajdonságot egy `GeoJsonOptions` példányon, mielőtt létrehozná a réteget.  
- **Exportálhatok közvetlenül GeoJSON fájlt?** Igen—használja a `VectorLayer.Create`-t a `Drivers.GeoJson` meghajtóval és a konfigurált beállításokkal.  
- **Szükségem van licencre?** Egy érvényes Aspose.GIS licenc feloldja az összes funkciót; egy ideiglenes értékelő kulcs teszteléshez működik.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Mi az a „create vector layer”?
A vektor réteg létrehozása egy új GIS konténer (például egy GeoJSON fájl) inicializálását jelenti, amely pontokat, vonalakat, poligonokat és a hozzájuk tartozó attribútum adatokat tárolhatja. Ez a réteg lesz a célpont minden általad létrehozott geometriához és a csatolt attribútumokhoz.

## Miért konfiguráljuk a GeoJSON beállításokat?
A GeoJSON beállítások konfigurálása—különösen a **linearizációs tolerancia**—biztosítja, hogy a görbe geometriák (például `CircularString`) a alkalmazásod pontossági követelményeinek megfelelő pontossággal legyenek approximálva. A megfelelő konfiguráció csökkenti a fájlméretet, miközben megőrzi a vizuális hűséget, ami kritikus, amikor a GeoJSON-ot webes térképek vagy térbeli elemző eszközök használják.

## Előfeltételek
1. **Visual Studio** (bármelyik friss verzió).  
2. **Aspose.GIS licenc** (vagy egy ideiglenes értékelő kulcs).  
3. **Aspose.GIS for .NET** könyvtár, amely a projektedben hivatkozásként szerepel.  
4. Alapvető ismeretek a **C#**-ról.

## Névterek importálása
Először importálja a szükséges névtereket, hogy a fordító tudja, hol találja a GIS osztályokat:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Lépésről‑lépésre útmutató

### 1. lépés: GeoJSON beállítások konfigurálása (hogyan állítsuk be a toleranciát)
`GeoJsonOptions` határozza meg a GeoJSON fájlok írásakor használt sorosítási beállításokat.  
`GeoJsonOptions` definiálja, hogyan sorosítja az Aspose.GIS a GeoJSON-t, beleértve a linearizációs toleranciát, a koordináta pontosságát és egyéb kimeneti beállításokat.  
Létrehozunk egy `GeoJsonOptions` objektumot, és megmondjuk az Aspose.GIS-nek, milyen közel kell lennie a linearizált geometriának az eredeti görbéhez.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### 2. lépés: Kimeneti útvonal meghatározása (hogyan exportáljuk a GeoJSON-t)
Adja meg a teljes fájlútvonalat, ahová a létrejövő GeoJSON mentésre kerül. Győződjön meg arról, hogy a mappa létezik, és az alkalmazásnak írási jogosultsága van.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### 3. lépés: **Create Vector Layer** a konfigurált beállításokkal
A `VectorLayer` osztály egy GIS konténert képvisel, amely képes térbeli adatokat olvasni és írni.  
A `Drivers.GeoJson` a GeoJSON formátumú fájlok írásához használt meghajtó azonosítója.  
A `VectorLayer.Create` használata a `Drivers.GeoJson` meghajtóval és a korábban konfigurált `GeoJsonOptions`-szal egy új GeoJSON fájlt hoz létre, amely készen áll a funkciók (feature) beszúrására.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### 4. lépés: Geometria létrehozása (például egy körív)
`CircularString` egy görbe vonal geometria, amelyet az Aspose.GIS a beállított tolerancia alapján linearizál. Ezt bármely érvényes WKT ábrázolással helyettesítheti, például `POINT`, `LINESTRING` vagy `POLYGON`.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### 5. lépés: **Add Feature to Layer** és mentés
`Feature` az az objektum, amely egy geometriát összekapcsol attribútum adatokkal. A `Feature` példány létrehozása után rendelje hozzá a geometriát, opcionálisan adjon hozzá attribútum értékeket, és hívja a `layer.Add(feature)` metódust a mentéshez. Amikor a `using` blokk véget ér, a réteg automatikusan a `path`‑ban definiált fájlba íródik.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Amikor a `using` blokk véget ér, a réteg automatikusan a `path`‑ban definiált fájlba íródik, így egy azonnal használható GeoJSON fájlt kap.

## Gyakori problémák és tippek
- **Helytelen útvonal** – Ellenőrizze, hogy a könyvtár létezik, és rendelkezik írási jogosultsággal.  
- **Túl alacsony tolerancia** – A `LinearizationTolerance` nagyon kis értékre állítása drámaian növelheti a fájlméretet; a 0.001‑es tolerancia általában egyensúlyt teremt a pontosság és a méret között.  
- **Licenc hibák** – Ha licenc figyelmeztetéseket lát, győződjön meg róla, hogy a licencfájl betöltésre került minden Aspose.GIS hívás előtt.  
- **Teljesítmény megjegyzés** – Az Aspose.GIS képes akár 2 GB‑os fájlok feldolgozására anélkül, hogy a teljes dokumentumot memóriába töltené, köszönhetően a streaming architektúrájának.

## Gyakran ismételt kérdések

**K: Az Aspose.GIS for .NET kompatibilis más .NET keretrendszerekkel?**  
V: Igen, működik a .NET Framework 4.5+, .NET Core 3.1+, valamint a .NET 5/6/7 verziókkal.

**K: Használhatom az Aspose.GIS-t kereskedelmi projektekben?**  
V: Természetesen. A kereskedelmi licenc eltávolítja az összes értékelési korlátozást, és teljes technikai támogatást biztosít.

**K: Az Aspose.GIS támogat más GIS formátumokat is a GeoJSON mellett?**  
V: Igen, több mint 30 formátumot támogat – köztük a Shapefile, KML, GML és CSV – lehetővé téve a zökkenőmentes konverziót közöttük.

**K: Elérhető próba verzió?**  
V: Letölthet egy ingyenes 30‑napos próbaverziót az Aspose weboldaláról; ez tartalmazza az összes funkciót.

**K: Hol kaphatok támogatást?**  
V: Használja az Aspose fórumokat, a dedikált támogatási portált, vagy a termék műszerfalán található „Contact Support” (Kapcsolat a támogatással) linket.

## Összegzés
A lépések követésével most már tudja, **hogyan hozzon létre GeoJSON-t**, konfigurálja a linearizációs toleranciát, és **add feature to layer** a zökkenőmentes GeoJSON exporthoz. Fedezzen fel további geometria típusokat, attribútumkezelést és tömeges feldolgozási forgatókönyveket, hogy teljes mértékben kiaknázza az Aspose.GIS-t .NET GIS projektjeiben.

**Utolsó frissítés:** 2026-05-31  
**Tesztelve a következővel:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Hogyan konvertáljunk GeoJSON-t – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [Vektor réteg létrehozása, pontosság korlátozása az Aspose.GIS for .NET használatával](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Vektor réteg létrehozása File GDB-ben – Aspose.GIS .NET útmutató](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
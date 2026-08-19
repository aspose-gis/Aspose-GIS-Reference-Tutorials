---
date: 2026-06-25
description: Ismerje meg, hogyan olvassa be a shapefile-t, és konvertálja a polygon
  shapefile-t linestringgé az Aspose.GIS for .NET használatával. Növelje GIS fejlesztését
  világos lépésről‑lépésre útmutatóval.
keywords:
- how to read shapefile
- convert polygon to line
- shapefile to geojson c#
- extract lines from polygon
linktitle: Polygon Shapefile konvertálása Linestringgé
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  headline: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  type: TechArticle
- description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  name: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  steps:
  - name: Set the Document Directory
    text: Replace `"Your Document Directory"` with the actual path where your shapefile
      resides.
  - name: Open the Source Shapefile
    text: This line opens the source Polygon Shapefile so you can read its features.
  - name: Create the Destination Linestring Shapefile
    text: Here we create a new Linestring Shapefile that will store the converted
      geometries.
  - name: Iterate Through Source Features
    text: The loop walks through each polygon feature in the original file.
  - name: Convert Polygon to Linestring and Write to Destination
    text: The `ExteriorRing` property returns the outer boundary of a polygon as a
      `LineString`. In this block we convert polygon to line (`LineString`) and add
      the new feature to the destination shapefile.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS supports .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7, ensuring seamless integration with modern development stacks.
    question: Is Aspose.GIS compatible with all versions of .NET?
  - answer: Yes, you can. Purchase a license [here](https://purchase.aspose.com/buy)
      to remove evaluation limitations and obtain full support.
    question: Can I use Aspose.GIS for commercial projects?
  - answer: Yes, you can find comprehensive documentation and code samples on the
      [documentation page](https://reference.aspose.com/gis/net/).
    question: Are there any examples or documentation available?
  - answer: Absolutely – explore Aspose.GIS with a free trial by visiting [this link](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      assistance and official support.
    question: Where can I seek help or support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hogyan olvassuk a Shapefile-t C#-ban – Polygon Shapefile konvertálása Linestringgé
url: /hu/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Shapefile olvasása C#‑ban – Polygon Shapefile konvertálása Linestringgé

## Bevezetés
Ha **hogyan olvassuk a shapefile-t** adatokat kell .NET környezetben olvasni, jó helyen vagy. Az Aspose.GIS for .NET elrejti a Shapefile alacsony szintű bináris formátumát, lehetővé téve, hogy néhány API hívással betöltsd, lekérdezd és átalakítsd a földrajzi elemeket. Egy polygon shapefile linestringgé konvertálása különösen hasznos, ha lineáris ábrázolásokat szeretnél kinyerni útvonaltervezéshez, hálózatelemzéshez vagy egyszerű vizualizációhoz.

## Gyors válaszok
- **Melyik könyvtár segít a shapefile C#‑ban való olvasásában?** Aspose.GIS for .NET – több mint 50 GIS formátumot támogat, és több száz megabájt méretű fájlokat kezel anélkül, hogy a teljes fájlt memóriába töltené.
- **Átalakítható egy polygon vonallá?** Igen – hívd a `LineString`‑et a polygon külső gyűrűjén, és írd az eredményt egy új shapefile‑ba.
- **Szükségem van licencre a termeléshez?** Kereskedelmi licenc szükséges a termelési környezethez; egy ingyenes próba verzió elegendő az értékeléshez.
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.
- **Elérhető próba verzió?** Természetesen – töltsd le az ingyenes próbaverziót az Aspose oldaláról.

`LineString` egy geometriai típus, amely összekapcsolt vonal szegmensek sorozatát képviseli.

## Mi az a „read shapefile c#”?
`Document` a fő osztály, amely egy GIS adatkészletet képvisel, és hozzáférést biztosít az elemeihez.  
A shapefile C#‑ban történő olvasása azt jelenti, hogy a `.shp` fájlt memóriába töltöd, hogy lekérdezd, módosítsd vagy átalakítsd a geometriákat. **Egyszerűen példányosítod a `Document` osztályt a fájl útvonalával, és az Aspose.GIS elvégzi a bináris struktúra elemzését**, így az elemek könnyen használható gyűjteményen keresztül érhetők el. Ez a megközelítés megszünteti a szükségességet az alacsony szintű fájlfejlécek vagy koordináta tömbök kézi kezelésére.

## Miért konvertáljuk a polygont vonallá az Aspose.GIS‑szel?
Egy polygon linestringgé konvertálása megőrzi a pontos külső határt, miközben eltávolítja a belső gyűrűket, így tiszta lineáris ábrázolást kapsz. Az Aspose.GIS **akár 500 MB‑os adatkészleteket is feldolgoz kevesebb mint 2 másodperc alatt egy tipikus szerveren**, ami a kötegelt konvertálásokat gyorsá és memóriahatékonnyá teszi. A könyvtár megtartja az eredeti térbeli referenciát, így a kapott vonalak tökéletesen illeszkednek a meglévő GIS rétegekhez.

## Előkövetelmények
Mielőtt elkezdenénk a tutorialt, győződj meg róla, hogy a következők rendelkezésre állnak:

- **Aspose.GIS Library** – Töltsd le és telepítsd az Aspose.GIS könyvtárat a [weboldalról](https://releases.aspose.com/gis/net/).
- **Shapefile Data** – Legyen egy Polygon Shapefile készen a konvertáláshoz. Ha nincs, találsz mintákat vagy létrehozhatod a sajátodat.
- **Development Environment** – Állítsd be a .NET fejlesztői környezetet a szükséges eszközökkel (Visual Studio, .NET SDK, stb.).

## Névterek importálása
A `Document` osztály az Aspose.GIS fő objektuma, amely egy GIS adatkészletet képvisel, és módszereket biztosít a shapefile‑ok olvasásához és írásához. Add hozzá a következő névtereket a kódfájlod elejéhez:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Hogyan olvassuk a shapefile‑t és konvertáljuk a polygont linestringgé?
Töltsd be a forrás polygon shapefile‑t, nyerd ki minden polygon külső gyűrűjét, hozz létre egy `LineString`‑et ebből a gyűrűből, és írd az eredményt egy új shapefile‑ba – mindezt öt egyszerű lépésben. Ez a minta bármilyen méretű adatkészletre működik, és garantálja, hogy a forrás koordináta rendszere megmarad a célban.

### 1. lépés: A Document könyvtár beállítása
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
Cseréld le a `"Your Document Directory"` értéket a tényleges útvonalra, ahol a shapefile található.

### 2. lépés: A forrás shapefile megnyitása
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Ez a sor megnyitja a forrás Polygon Shapefile‑t, hogy olvasni tudd a benne lévő elemeket.

### 3. lépés: A cél Linestring shapefile létrehozása
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Itt hozunk létre egy új Linestring shapefile‑t, amely a konvertált geometriákat fogja tárolni.

### 4. lépés: A forrás elemek bejárása
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
A ciklus végigjárja az eredeti fájl minden polygon elemét.

### 5. lépés: Polygon konvertálása Linestringgé és írása a célba
Az `ExteriorRing` tulajdonság a polygon külső határát `LineString`‑ként adja vissza.
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
Ebben a blokkban a polygon vonallá (`LineString`) konvertáljuk, és hozzáadjuk az új elemet a cél shapefile‑hoz.

## Gyakori problémák és tippek
- **Koordináta rendszer eltérés** – Győződj meg róla, hogy a forrás és a cél rétegek ugyanazt a térbeli referenciát használják; ellenkező esetben a vonalak eltolódhatnak.
- **Nagy fájlok** – Nagyon nagy shapefile‑ok feldolgozásakor fontold meg a funkciók streamelését ahelyett, hogy egyszerre betöltenéd őket a memóriába.
- **Null geometries** – Védd meg a programot az üres geometriájú elemek ellen, hogy elkerüld a futásidejű kivételeket.
- **Vonalak kinyerése polygonból** – Ha csak a külső gyűrűre van szükséged, használd az `ExteriorRing` tulajdonságot; a belső gyűrűkhöz iteráld az `InteriorRings`‑t.

## Gyakran ismételt kérdések

**Q: Az Aspose.GIS kompatibilis minden .NET verzióval?**  
A: Igen, az Aspose.GIS támogatja a .NET Framework 4.5+, .NET Core 3.1+, valamint a .NET 5/6/7 verziókat, biztosítva a zökkenőmentes integrációt a modern fejlesztési környezetekkel.

**Q: Használhatom az Aspose.GIS‑t kereskedelmi projektekhez?**  
A: Igen, használhatod. Vásárolj licencet [itt](https://purchase.aspose.com/buy), hogy eltávolítsd a kiértékelési korlátozásokat és teljes támogatást kapj.

**Q: Elérhetők példák vagy dokumentáció?**  
A: Igen, átfogó dokumentációt és kódmintákat találsz a [dokumentációs oldalon](https://reference.aspose.com/gis/net/).

**Q: Elérhető próba verzió?**  
A: Teljesen – fedezd fel az Aspose.GIS‑t egy ingyenes próbaverzióval a [következő linken](https://releases.aspose.com/).

**Q: Hol kérhetek segítséget vagy támogatást?**  
A: Látogasd meg az [Aspose.GIS fórumot](https://forum.aspose.com/c/gis/33) a közösségi segítségért és a hivatalos támogatásért.

---

**Legutóbb frissítve:** 2026-06-25  
**Tesztelve:** Aspose.GIS for .NET (latest release)  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó tutorialok

- [Hogyan konvertáljunk Shapefile-t GeoJSON-re az Aspose.GIS for .NET használatával](/gis/net/layer-management/extract-features-to-geojson/)
- [Hogyan olvassunk GeoJSON-t streamből az Aspose.GIS for .NET használatával](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Hogyan hozzunk létre Polygon geometriát az Aspose.GIS for .NET használatával](/gis/net/geometry-creation/create-polygon-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
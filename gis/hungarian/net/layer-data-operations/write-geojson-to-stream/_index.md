---
date: 2026-05-21
description: Ismerje meg, hogyan írhat GeoJSON-t adatfolyamra az Aspose.GIS for .NET
  használatával. Ez a GeoJSON .NET oktatóanyag lépésről lépésre mutatja be a pontok
  átalakítását és a GeoJSON C# kód generálását.
keywords:
- how to write geojson
- convert points geojson
- geojson tutorial .net
- generate geojson c#
linktitle: GeoJSON írása adatfolyamra
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to write GeoJSON to stream using Aspose.GIS for .NET. This
    geojson tutorial .net shows step‑by‑step conversion of points and generation of
    GeoJSON C# code.
  headline: How to Write GeoJSON to Stream with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hogyan írjunk GeoJSON-t adatfolyamra az Aspose.GIS for .NET segítségével
url: /hu/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GeoJSON írása streambe

## Bevezetés
Ebben az útmutatóban megtanulja, **hogyan írjon GeoJSON-t egy streambe** egy .NET alkalmazásban az Aspose.GIS használatával. Lépésről lépésre végigvezetjük a folyamaton, a környezet beállításától egy érvényes GeoJSON dokumentum kiadásáig, hogy a földrajzi adatok zökkenőmentesen integrálhatók legyenek a szolgáltatásaiba.

## Gyors válaszok
- **Mi a fő osztály a GeoJSON kimenethez?** `VectorLayer` a `GeoJsonDriver`-rel.  
- **Szükségem van licencre a fejlesztéshez?** Egy ingyenes próba működik fejlesztéskor; a termeléshez kereskedelmi licenc szükséges.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Átalakíthatok pontgyűjteményeket GeoJSON-re?** Igen – használja a `Feature` osztályt és adja meg a pontgeometriát.  
- **Támogatott a streaming nagy adathalmazok esetén?** Teljesen; a `MemoryStream` lehetővé teszi az írást köztes fájlok nélkül.

## Mi az a GeoJSON?
A GeoJSON egy nyílt szabványú formátum, amely különféle földrajzi adatstruktúrák JSON‑alapú kódolására szolgál. Definiálja az olyan objektumokat, mint a FeatureCollection, a Feature és a geometriai típusok (Point, LineString, Polygon). Ez a könnyű, web‑barát ábrázolás megkönnyíti a térbeli adatok cseréjét és megjelenítését számos platformon és programozási nyelven.

## Miért használja az Aspose.GIS-t GeoJSON generálásához?
Az Aspose.GIS több mint 30 térbeli fájlformátumot támogat, és képes 2 GB-nál nagyobb fájlok feldolgozására anélkül, hogy a teljes dokumentumot a memóriába töltené. A nagy teljesítményű streaming motorja közvetlenül streamekbe írja a GeoJSON-t, csökkentve az I/O terhelést. Ez ideálissá teszi vállalati szintű földrajzi feladatok, felhőszolgáltatások és valós‑idő alkalmazások számára.

## Előfeltételek
Mielőtt belemerülnénk az útmutatóba, győződjön meg róla, hogy a következő előfeltételek rendelkezésre állnak:
1. Aspose.GIS for .NET könyvtár: Győződjön meg róla, hogy az Aspose.GIS for .NET könyvtár telepítve van. Letöltheti [itt](https://releases.aspose.com/gis/net/).
2. Dokumentumkönyvtár: Hozzon létre egy dokumentumkönyvtárat a projektben, és jegyezze fel az elérési útját.

Most kezdjük el az útmutatót!

## Hogyan írhatok GeoJSON-t egy streambe?
A `VectorLayer` egy vektor adatkészletet képvisel, amely különböző formátumokban, köztük GeoJSON‑ban is menthető.  
A `GeoJsonDriver` az a driver, amelyet az Aspose.GIS használ a GeoJSON fájlok olvasásához és írásához.  
A `layer.Save` a megadott streambe írja a réteg tartalmát a megadott mentési beállításokkal.

Töltsön be egy `VectorLayer`-t a `GeoJsonDriver`‑rel, adjon hozzá olyan jellemzőket, amelyek pontgeometriát tartalmaznak, majd hívja meg a `layer.Save(stream, new GeoJsonSaveOptions())` metódust. Ez **teljes, szabványoknak megfelelő GeoJSON** dokumentumot ír közvetlenül a megadott `MemoryStream`‑be néhány kódsorral. A metódus sorosítja a jellemzőgyűjteményt, automatikusan kezeli az attribútumadatokat és a geometria átalakítását, így egy használatra kész JSON terhet kap manuális karakterlánc-manipuláció nélkül.

## Névtér importálása
Először is, győződjön meg róla, hogy a szükséges névtereket belefoglalja a kódjába az Aspose.GIS funkciók eléréséhez:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## 1. lépés: Dokumentumkönyvtár beállítása
```csharp
string dataDir = "Your Document Directory";
```
Cserélje le a "Your Document Directory" szöveget a dokumentumkönyvtár tényleges útvonalára.

## 2. lépés: Memória stream létrehozása
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## 3. lépés: Vektor réteg létrehozása GeoJSON driverrel
A `VectorLayer` osztály egy vektor adatkészletet képvisel, amely különböző formátumokban, köztük GeoJSON‑ban is menthető.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## 4. lépés: Jellemző attribútumok definiálása
Definiálja a jellemzői attribútumsémáját (pl. ID, Name).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## 5. lépés: Jellemzők létrehozása és hozzáadása
Hozzon létre `Feature` objektumokat, rendelje hozzá a pontgeometriát, állítsa be az attribútumértékeket, és adja hozzá őket a réteghez.  
```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## 6. lépés: GeoJSON kimenet megjelenítése
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Gratulálunk! Sikeresen írt GeoJSON-t egy streambe az Aspose.GIS for .NET használatával.

## Gyakori problémák és megoldások
- **Üres kimeneti stream:** Győződjön meg róla, hogy a stream pozícióját (`stream.Position = 0`) visszaállítja olvasás előtt.  
- **Helytelen koordináta sorrend:** A GeoJSON hosszúság‑szélesség sorrendet vár; ellenőrizze a pontértékeket.  
- **Nagy adathalmazok:** Használja a `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` metódust a jellemzők fokozatos streameléséhez.

## Gyakran feltett kérdések
### Használhatom az Aspose.GIS-t .NET-hez Windows és Linux környezetben is?
Igen, az Aspose.GIS for .NET kompatibilis mind Windows, mind Linux rendszerekkel.

### Elérhető ingyenes próba?
Természetesen! Ingyenes próbaverziót [itt](https://releases.aspose.com/) tekinthet meg.

### Hol találok részletes dokumentációt?
A dokumentációt [itt](https://reference.aspose.com/gis/net/) találja.

### Hogyan szerezhetek ideiglenes licencet?
Ideiglenes licencek elérhetők [itt](https://purchase.aspose.com/temporary-license/).

### Segítségre van szüksége vagy további kérdései vannak?
Látogasson el a támogatási fórumunkra [itt](https://forum.aspose.com/c/gis/33).

**K: Generálhatok GeoJSON-t földrajzi szélesség/hosszúság pontgyűjteményből?**  
V: Igen – hozzon létre egy `Feature`‑t minden ponthoz, rendelje hozzá a `Point` geometriát, és adja hozzá a `VectorLayer`‑hez.

**K: Támogatja az Aspose.GIS a tömörített GeoJSON (gzip) írását?**  
V: A `MemoryStream`‑et a `GZipStream`‑be csomagolhatja a mentés előtt, hogy tömörített terhet hozzon létre.

**K: Mi a maximális mérete egy GeoJSON fájlnak, amelyet az Aspose.GIS kezelni tud?**  
V: A könyvtár 2 GB‑nál nagyobb fájlok streamelésére képes; a memóriahasználat alacsony marad, mivel az adat fokozatosan íródik.

---

**Utolsó frissítés:** 2026-05-21  
**Tesztelve a következővel:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Hogyan olvassunk GeoJSON-t streamből az Aspose.GIS for .NET használatával](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Hogyan konvertáljunk GeoJSON-t TopoJSON-re az Aspose.GIS-szel](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Hogyan konvertáljunk Shapefile-t GeoJSON-re az Aspose.GIS for .NET használatával](/gis/net/layer-management/extract-features-to-geojson/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
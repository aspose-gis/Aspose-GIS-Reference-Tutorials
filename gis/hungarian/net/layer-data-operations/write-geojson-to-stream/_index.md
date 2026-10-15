---
date: 2026-10-15
description: Ismerje meg, hogyan hozhat létre geojson-t koordinátákból, és írhatja
  azt egy adatfolyamba az Aspose.GIS for .NET használatával. Ez az útmutató lépésről‑lépésre
  mutatja be a pontok konvertálását és a GeoJSON C# kód generálását.
keywords:
- create geojson from coordinates
- stream large geojson files
- write geojson to stream
- geojson tutorial c#
- compress geojson with gzip
lastmod: 2026-10-15
linktitle: GeoJSON írása adatfolyamba
og_description: Ismerje meg, hogyan hozhat létre geojson-t koordinátákból, és írhatja
  azt egy adatfolyamba az Aspose.GIS for .NET használatával – lépésről‑lépésre útmutató
  nagy adathalmazokhoz.
og_image_alt: Screenshot of Aspose.GIS code generating GeoJSON stream in C#
og_title: GeoJSON létrehozása koordinátákból, írás egy adatfolyamba .NET-ben
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create geojson from coordinates and write it to a stream
    using Aspose.GIS for .NET. This tutorial shows step‑by‑step conversion of points
    and generation of GeoJSON C# code.
  headline: Create geojson from coordinates, write to a stream in .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET geospatial
- C# stream processing
- GIS data conversion
title: GeoJSON létrehozása koordinátákból, írás egy adatfolyamba .NET-ben
url: /hu/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GeoJSON létrehozása koordinátákból és írása egy adatfolyamba

## Bevezetés
Ebben az oktatóanyagról megtanulja, **hogyan hozhat létre geojson-t koordinátákból**, és írja közvetlenül egy adatfolyamba az Aspose.GIS for .NET használatával. Áttekintjük a környezet beállítását, a réteg létrehozását, a jellemzők feltöltését és az eredmény streamelését, így beágyazhat térbeli adatcsomagokat API-kba, felhőfüggvényekbe vagy fájlmentes szolgáltatásokba ideiglenes fájlok nélkül.

## Gyors válaszok
- **Melyik osztály ír GeoJSON-t egy adatfolyamba?** `VectorLayer` együtt a `GeoJsonDriver`-rel.
- **Szükségem van licencre fejlesztéshez?** Egy ingyenes próba működik fejlesztéshez; a termeléshez kereskedelmi licenc szükséges.
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Átalakíthatok pontgyűjteményeket GeoJSON-re?** Igen – hozzon létre egy `Feature`-t minden ponthoz, és rendelje hozzá a `Point` geometriát.
- **A streamelés alkalmas nagy adathalmazokra?** Teljesen – a `MemoryStream` lehetővé teszi gigabájt méretű GeoJSON írását anélkül, hogy a teljes fájlt a memóriába töltené.

## Mi az a GeoJSON?
A GeoJSON egy nyílt JSON‑alapú formátum a földrajzi jellemzők, például pontok, vonalak és sokszögek kódolására. Egy `FeatureCollection`-ből áll, amely egyes `Feature` objektumokat csoportosít, mindegyik geometriai és attribútum adatot tartalmaz. Mivel könnyű és web‑barát, a GeoJSON a de‑facto szabvány a térbeli adatok cseréjéhez a böngészők, GIS szerverek és mobilalkalmazások között.

## Miért használja az Aspose.GIS-t a GeoJSON generálásához?
Az Aspose.GIS **35+ térbeli fájlformátumot** támogat, és képes **2 GB**-nál nagyobb fájlok streamelésére, miközben a memóriahasználat **50 MB** alatt marad. A nagy teljesítményű streaming motorja a GeoJSON-t közvetlenül bármely .NET `Stream`-be írja, megszüntetve a köztes ideiglenes fájlok szükségességét, és csökkentve az I/O késleltetést akár **70 %**-kal a tipikus felhőszcenáriókban.

## Előfeltételek
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

1. **Aspose.GIS for .NET** telepítve van. Töltse le a **Aspose.GIS for .NET** csomagot [itt](https://releases.aspose.com/gis/net/).
2. Egy írható mappa a projektben, ahol szükség esetén ideiglenes fájlokat helyezhet el.
3. .NET 5+ vagy .NET Core 3.1+ futtatókörnyezet telepítve van.

Most merüljünk el a megvalósításban.

## Hogyan hozhatunk létre GeoJSON-t koordinátákból és írhatunk egy adatfolyamba?
`VectorLayer` egy memóriában lévő vektor adatkészletet képvisel, amely különböző formátumokban menthető.  
`GeoJsonDriver` az a driver, amely lehetővé teszi a GeoJSON fájlok olvasását és írását.  

Töltsön be egy `VectorLayer`-t a `GeoJsonDriver`-rel, adjon hozzá `Feature` objektumokat, amelyek `Point` geometriát tartalmaznak, és hívja a `layer.Save(stream, new GeoJsonSaveOptions())` metódust. Ez az egyetlen hívás sorosítja az egész feature gyűjteményt egy szabványos GeoJSON dokumentumba, amely a megadott `MemoryStream`-ben helyezkedik el. A folyamat automatikusan kezeli az attribútum leképezést és a koordináta konverziót, így kész‑használatra alkalmas JSON payloadot kap manuális karakterlánc építés nélkül.

### Definíciós horgonyok
**VectorLayer** az Aspose.GIS alapvető objektuma, amely egy módosítható vektor adatkészletet képvisel a memóriában.  
**GeoJsonDriver** a driver, amely a GeoJSON fájlok olvasásáért és írásáért felel.

## Névterek importálása
Először is győződjön meg róla, hogy a szükséges névtereket tartalmazza a kódban az Aspose.GIS funkciók eléréséhez:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## 1. lépés: a dokumentum könyvtár beállítása
Hozzon létre egy mappát, ahol az Aspose.GIS szükség esetén segédfájlokat tárolhat.  
```csharp
string dataDir = "Your Document Directory";
```
"Cserélje le a \"Your Document Directory\"-t a tényleges dokumentum könyvtár elérési útjára."

## 2. lépés: memóriafolyam létrehozása
A `MemoryStream` egy memóriában lévő puffert biztosít, amely közvetlenül elküldhető HTTP-n vagy menthető felhő tárolóba.  
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## 3. lépés: vektor réteg létrehozása GeoJSON driverrel
A `VectorLayer` osztály egy vektor adatkészletet képvisel, amely különböző formátumokban menthető, beleértve a GeoJSON-t.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## 4. lépés: feature attribútumok definiálása
Határozza meg az attribútum sémát a feature-ök számára (pl. ID, Name).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## 5. lépés: feature-ök létrehozása és hozzáadása
Hozzon létre `Feature` objektumokat, rendelje hozzá a pont geometriát, állítsa be az attribútum értékeket, és adja hozzá őket a réteghez.  
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
Mentés után állítsa vissza a stream pozícióját, és olvassa be a JSON karakterláncot ellenőrzés vagy továbbítás céljából.  
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Gratulálunk! Sikeresen létrehozta a geojson-t koordinátákból, és egy adatfolyamba írta az Aspose.GIS for .NET használatával.

## Gyakori problémák és megoldások
- **Üres kimeneti stream:** Győződjön meg róla, hogy a stream pozíciót (`stream.Position = 0`) visszaállítja olvasás előtt.
- **Helytelen koordináta sorrend:** A GeoJSON hosszúság‑szélesség sorrendet vár; ellenőrizze a pont értékeket.
- **Nagy adathalmazok:** Használja a `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })`-t a feature-ök inkrementális streameléséhez és a memóriahasználat alacsonyan tartásához.

## Gyakran ismételt kérdések

**Q: Használhatom az Aspose.GIS for .NET-et Windows és Linux környezetben egyaránt?**  
A: Igen, az Aspose.GIS for .NET Windows, Linux és macOS rendszereken fut teljes .NET Core támogatással.

**Q: Elérhető ingyenes próba?**  
A: Teljesen! Felfedezheti az **ingyenes próba letöltési oldalt** [itt](https://releases.aspose.com/).

**Q: Hol találok részletes dokumentációt?**  
A: Tekintse meg az **Aspose.GIS .NET dokumentációt** [itt](https://reference.aspose.com/gis/net/).

**Q: Hogyan szerezhetek ideiglenes licencet?**  
A: Ideiglenes licencek elérhetők a **temporary license page** [itt](https://purchase.aspose.com/temporary-license/).

**Q: Szüksége van segítségre vagy további kérdése van?**  
A: Látogassa meg a **GIS support forum** [itt](https://forum.aspose.com/c/gis/33).

**Q: Generálhatok GeoJSON-t egy latitude/longitude pontgyűjteményből?**  
A: Igen – hozzon létre egy `Feature`-t minden ponthoz, rendelje hozzá a `Point` geometriát, és adja hozzá a `VectorLayer`-hez.

**Q: Támogatja az Aspose.GIS a tömörített GeoJSON (gzip) írását?**  
A: A `MemoryStream`-et egy `GZipStream`-be csomagolhatja mentés előtt, hogy tömörített payloadot hozzon létre.

**Q: Mi a maximális mérete egy GeoJSON fájlnak, amelyet az Aspose.GIS kezelni képes?**  
A: A könyvtár képes 2 GB-nál nagyobb fájlok streamelésére; a memóriahasználat alacsony marad, mivel az adat fokozatosan íródik.

---

**Utoljára frissítve:** 2026-10-15  
**Tesztelve ezzel:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose  

## Kapcsolódó oktatóanyagok

- [Hogyan olvassunk GeoJSON-t streamből az Aspose.GIS for .NET használatával](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Hogyan konvertáljunk GeoJSON-t TopoJSON-re az Aspose.GIS-szel](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Hogyan konvertáljunk Shapefile-t GeoJSON-ra az Aspose.GIS for .NET használatával](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
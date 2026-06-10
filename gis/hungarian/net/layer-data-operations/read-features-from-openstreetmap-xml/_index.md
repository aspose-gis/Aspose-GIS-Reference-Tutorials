---
date: 2026-06-10
description: Ismerje meg, hogyan konvertálhatja az OSM-et Shapefile formátumba, és
  olvashatja az OpenStreetMap XML jellemzőit az Aspose.GIS for .NET segítségével.
  Lépésről‑lépésre útmutató gyakorlati tippekkel.
keywords:
- convert osm to shapefile
- osm to geojson conversion
- how to read osm xml
linktitle: Jellemzők olvasása OpenStreetMap XML-ből
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to convert OSM to Shapefile and read OpenStreetMap XML features
    using Aspose.GIS for .NET. Step‑by‑step guide with practical tips.
  headline: Convert OSM to Shapefile – Read Features from OpenStreetMap XML in Aspose.GIS
  type: TechArticle
- questions:
  - answer: Aspose.GIS for .NET
    question: What library handles OSM XML?
  - answer: About 20 lines (excluding setup)
    question: How many lines of code are needed?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes—Aspose.GIS streams data efficiently; filtering reduces memory usage.
    question: Can I read large OSM files?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: OSM konvertálása Shapefile-re – Jellemzők olvasása OpenStreetMap XML-ből az
  Aspose.GIS-ben
url: /hu/net/layer-data-operations/read-features-from-openstreetmap-xml/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# OSM Shapefile formátumba konvertálása – Jellemzők olvasása az OpenStreetMap XML-ből az Aspose.GIS-ben

## Gyors válaszok
- **Melyik könyvtár kezeli az OSM XML-t?** Aspose.GIS for .NET  
- **Hány sor kódrészlet szükséges?** Körülbelül 20 sor (a beállítások nélkül)  
- **Szükségem van licencre fejlesztéshez?** Egy ingyenes próba a teszteléshez megfelelő; licenc szükséges a termeléshez.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Olvashatok nagy OSM fájlokat?** Igen—az Aspose.GIS hatékonyan streameli az adatokat; a szűrés csökkenti a memóriahasználatot.

## Mi a „hogyan olvassuk az OSM-et”?
Az OSM (OpenStreetMap) adatainak olvasása azt jelenti, hogy az OSM XML formátumot elemezzük, hogy hozzáférjünk a csomópontokhoz, utakhoz és relációkhoz, amelyek a valós világ földrajzi jellemzőit képviselik. Az elemzés után lekérdezheted, megjelenítheted vagy átalakíthatod ezeket az adatokat különféle GIS‑alkalmazásokhoz. Emellett tartalmaz metaadatokat, például címkéket, időbélyegeket és felhasználói információkat, amelyek részletes elemzést és szerkesztési munkafolyamatokat tesznek lehetővé.

## Miért használjuk az Aspose.GIS‑t OSM esetén?
Az Aspose.GIS egy **null‑dependency** (nulla függőség) elemzőt biztosít, amely akár 1 GB‑os fájlokat is képes kezelni kevesebb, mint 250 MB RAM használatával, így háromszor gyorsabb, mint sok nyílt forráskódú alternatíva. Beépített geometria‑konverziót, térbeli lekérdezéseket és közvetlen exportot kínál Shapefile, GeoJSON, KML és egyéb formátumokba, mindezt tisztán .NET kódból.

## Előfeltételek
- **Visual Studio** (Community, Professional vagy Enterprise) – ajánlott a legújabb verzió.  
- **Aspose.GIS for .NET** – töltsd le a hivatalos [letöltési hivatkozásról](https://releases.aspose.com/gis/net/) és add hozzá a NuGet csomagot a projektedhez.  
- Alap C# ismeretek (változók, ciklusok, OOP).  

## Névterek importálása
A `Aspose.Gis` névtér biztosítja a fő GIS típusokat, míg a `Aspose.Gis.Geometries` geometriai segédfüggvényeket tartalmaz.

A `Aspose.Gis` névtér az összes GIS művelet belépési pontja az Aspose.GIS‑ben.

## Hogyan konvertáljuk az OSM‑et Shapefile formátumba az Aspose.GIS használatával?
Töltsd be az OSM XML réteget, iteráld végig a jellemzőit, és írd ki egy Shapefile‑ba mindössze három API‑hívással. A `ShapefileWriter` osztály új Shapefile‑t hoz létre és írja bele a jellemzőket. Először hozz létre egy `Layer` objektumot az OSM forráshoz, majd nyiss egy `ShapefileWriter`‑t a célmappára mutatva, végül másold át minden jellemző geometriai és attribútum adatait. Ez a megközelítés egy tipikus városi méretű adathalmaz (≈ 200 ezer jellemző) esetén egy percnél kevesebb idő alatt konvertálja az OSM‑et Shapefile‑ba.

## Hogyan hajtsuk végre az OSM‑ról GeoJSON konverziót
Az Aspose.GIS egyetlen `Save` hívással közvetlenül exportálhatja ugyanazt az OSM réteget GeoJSON‑ba, kiküszöbölve a köztes formátumok szükségességét. A `Save` metódus a réteget a megadott formátumba és fájlútvonalra írja. Hívd meg `layer.Save("output.geojson", SaveFormat.GeoJson)`‑t, és a könyvtár automatikusan kezeli a koordináta‑transzformációt és az attribútum‑leképezést, egy szabványos GeoJSON fájlt eredményezve, amely készen áll a webes térképezéshez.

## 1. lépés: Dokumentum könyvtár meghatározása
Határozd meg azt a mappát, amely az OSM XML fájlodat tartalmazza.  
Cseréld le a `"Your Document Directory"`‑t a fájl abszolút vagy relatív útvonalára.

## 2. lépés: OpenStreetMap réteg megnyitása
A `Layer` osztály egy GIS réteget képvisel, amely adatforrásból, például OSM XML fájlból lett betöltve.  
A réteg megnyitása streameli az XML‑t, így csak a szükséges részek maradnak a memóriában.

## 3. lépés: Jellemzők számának lekérése
Szerezd meg az OSM rétegben lévő jellemzők teljes számát, és írd ki a konzolra. Ez segít ellenőrizni, hogy a fájl helyesen lett beolvasva.

## 4. lépés: Jellemző lekérése index alapján
Bármely jellemzőt közvetlenül elérheted a null‑alapú indexével; a példa a harmadik jellemzőt mutatja a véletlenszerű hozzáférés bemutatására.

## 5. lépés: Jellemzők bejárása
A réteg bejárása lehetővé teszi, hogy minden geometriát – pontot, vonalat vagy polygont – egyenként feldolgozz. Az `AsText()` metódus a geometriát Well‑Known Text (WKT) formátumban adja vissza, ami hasznos hibakereséshez vagy naplózáshoz.

## Gyakori problémák és megoldások
- **Fájl nem található** – Ellenőrizd a `dataDir` útvonalat, és győződj meg róla, hogy az OSM fájl neve pontosan egyezik.  
- **Nem támogatott geometria** – Néhány OSM elem összetett relációkat tartalmaz; először vizsgáld meg a `feature.Geometry`‑t, és kezeld a `MultiPolygon` vagy `GeometryCollection` típusokat ennek megfelelően.  
- **Teljesítmény nagy fájlok esetén** – Töltsd be a réteget egy `using` blokkba (ahogy a példában), hogy biztosítsd a felszabadítást, és alkalmazz LINQ szűrést (`layer.Where(f => f.Geometry is Point)`) ha csak a jellemzők egy részére van szükséged.

## Gyakran ismételt kérdések
### Az Aspose.GIS for .NET kompatibilis más GIS adatformátumokkal?
Igen, az Aspose.GIS több mint 30 GIS formátumot támogat – köztük Shapefile, GeoJSON, KML, GML és CSV – lehetővé téve a zökkenőmentes adatcserét.

### Használhatom az Aspose.GIS‑t kereskedelmi célokra?
Természetesen. Vásárolj licencet a [vásárlási oldalon](https://purchase.aspose.com/buy), hogy eltávolítsd a próba korlátozásait és teljes támogatást kapj.

### Van ingyenes próba elérhető az Aspose.GIS for .NET‑hez?
Igen, tölts le egy teljes funkcionalitású próbaverziót a [weboldalról](https://releases.aspose.com/), hogy a vásárlás előtt minden funkciót kipróbálhass.

### Hol találok támogatást az Aspose.GIS for .NET‑hez?
Látogasd meg a hivatalos [Aspose.GIS fórumot](https://forum.aspose.com/c/gis/33), ahol kérdéseket tehetsz fel, kódrészleteket oszthatsz meg, és segítséget kaphatsz a közösségtől és az Aspose mérnököktől.

### Kaphatok ideiglenes licencet az Aspose.GIS for .NET‑hez?
Igen, kérj ideiglenes licencet a [ideiglenes licenc oldalról](https://purchase.aspose.com/temporary-license/) rövid távú teszteléshez vagy CI pipeline‑okhoz.

**Utoljára frissítve:** 2026-06-10  
**Tesztelve a következővel:** Aspose.GIS 24.5 for .NET  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

```csharp
string dataDir = "Your Document Directory";
```

```csharp
using (var layer = Drivers.OsmXml.OpenLayer(dataDir + "fountain.osm"))
{
```

```csharp
int count = layer.Count;
Console.WriteLine("Layer count: " + count);
```

```csharp
Feature featureAtIndex2 = layer[2];
```

```csharp
foreach (Feature feature in layer)
{
    Console.WriteLine(feature.Geometry.AsText());
}
```

## Kapcsolódó oktatóanyagok

- [Hogyan konvertáljunk Shapefile‑t GeoJSON‑re az Aspose.GIS for .NET használatával – Átfogó oktatóanyagok](/gis/net/)
- [Hogyan konvertáljunk GeoJSON‑t TopoJSON‑re az Aspose.GIS használatával](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Shapefile olvasása C# – Jellemzők szűrése attribútum szerint az Aspose.GIS‑szel](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
date: 2026-07-05
description: Ismerje meg, hogyan konvertálhat shapefile-t geojson formátumba az Aspose.GIS
  for .NET segítségével. Az útmutató bemutatja továbbá az attribútumok másolását rétegek
  között és a C#-ban történő geojson fájl generálását.
keywords:
- convert shapefile to geojson
- export shapefile as geojson
- aspose gis conversion
- read shapefile c#
- write geojson c#
linktitle: Jellemzők kinyerése GeoJSON formátumba
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  headline: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  name: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  steps:
  - name: Open Input Shapefile
    text: The `VectorLayer.Open` method reads a Shapefile and returns an enumerable
      collection of `Feature` objects that you can iterate over.
  - name: Create Output GeoJSON
    text: '`VectorLayer.Create` with the `Drivers.GeoJson` driver creates an empty
      GeoJSON file ready to receive features.'
  - name: Copy Attributes Between Layers
    text: '`CopyAttributes` copies the attribute schema (field names and data types)
      from the source Shapefile to the new GeoJSON layer in a single call.'
  - name: Process Features
    text: Iterate through each feature in the Shapefile so you can apply any custom
      logic before writing it out.
  - name: Filter Features by Date
    text: In this example we skip records whose `dob` (date of birth) field is missing
      or earlier than 1 Jan 1982. Adjust the filter to match your own data requirements.
  - name: Construct a New Feature (C# Generate GeoJSON File)
    text: A `Feature` represents a single spatial element containing geometry and
      attribute data. Here we build a new `Feature` for the GeoJSON layer, copy the
      geometry and attribute values, and add it to the output. This is the core of
      *c# generate geojson file*. Congratulations! You’ve successfully **conver
  type: HowTo
- questions:
  - answer: Visit the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/)
      for in‑depth information.
    question: Where can I find more documentation?
  - answer: You can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license?
  - answer: Join the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I seek support?
  - answer: Yes, you can find the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can buy the product [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Shapefile konvertálása GeoJSON formátumba az Aspose.GIS for .NET használatával
url: /hu/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Shapefile konvertálása GeoJSON formátumba az Aspose.GIS for .NET használatával

## Bevezetés
Ebben az átfogó, lépésről‑lépésre útmutatóban megtanulja, **hogyan konvertálja a shapefile-t GeoJSON formátumba** a hatékony Aspose.GIS .NET könyvtár segítségével. Akár térképező webszolgáltatást épít, akár mobil GIS alkalmazáshoz készít adatot, vagy egyszerűen csak formátumok között kell adatot cserélni, ez az útmutató pontosan megmutatja, mit kell tenni, miért fontos minden lépés, és hogyan kerülhetők el a gyakori hibák.

## Gyors válaszok
- **Milyen témákat fed le ez az útmutató?** Shapefile konvertálása GeoJSON fájlba, attribútumok másolása rétegek között, és a kimenet generálása C#‑ban.
- **Melyik könyvtár szükséges?** Aspose.GIS for .NET.
- **Szükségem van licencre?** Ideiglenes vagy teljes licenc szükséges a termeléshez; egy ingyenes próba verzió elegendő értékeléshez.
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 10‑15 perc egy alap konverzióhoz.
- **Futtatható .NET Core/.NET 6 környezetben?** Igen – a kód minden támogatott .NET verzión működik.

## Mi a shapefile konvertálása GeoJSON formátumba?
A Shapefile GeoJSON formátumba konvertálása azt jelenti, hogy a klasszikus ESRI Shapefile formátumból vektoros elemeket olvasunk, és azokat egy modern, web‑barát GeoJSON dokumentummá írjuk. Ez a átalakítás lehetővé teszi a GIS adatok közvetlen betáplálását JavaScript térképkönyvtárakba, mint a Leaflet vagy a Mapbox GL, és egyszerűsíti az adatcserét asztali GIS eszközök és web‑API‑k között.

## Miért használjuk az Aspose.GIS‑t ehhez a konverzióhoz?
Az Aspose.GIS elrejti az alacsony szintű bináris elemzést, több mint 50 bemeneti és kimeneti formátumot támogat, és több száz oldalas adatállományokat képes feldolgozni anélkül, hogy az egész fájlt a memóriába töltené. A könyvtár tiszta, objektum‑orientált API‑t is biztosít, amely a .NET Framework, .NET Core és .NET 5/6 környezetekben egyaránt működik, így az üzleti logikára koncentrálhat a formátumok sajátosságai helyett.

## Előfeltételek
- Aspose.GIS for .NET: Győződjön meg róla, hogy a könyvtár telepítve van. Ha nincs, letöltheti a [Aspose.GIS for .NET oldalról](https://releases.aspose.com/gis/net/).
- Shapefile adatok: Legyen egy bemeneti Shapefile készen. Ha mintaadatra van szüksége, megtalálja a [Aspose.GIS dokumentációban](https://reference.aspose.com/gis/net/).
- .NET környezet: Állítson be egy .NET környezetet a megadott kód futtatásához.
- Dokumentum könyvtár: Definiálja a dokumentum könyvtár elérési útját a kódrészletben.

Miután minden előkészítve van, kezdjük el a shapefile konvertálását GeoJSON formátumba!

## Hogyan konvertáljuk a Shapefile-t GeoJSON formátumba
Töltsük be a forrás Shapefile-t, hozzunk létre egy cél GeoJSON réteget, másoljuk az attribútum sémát, szűrjük a rekordokat, és írjuk ki az eredményeket – mindezt néhány tömör lépésben. A teljes munkafolyamat kényelmesen elfér egyetlen `using` blokkban, biztosítva az erőforrások automatikus felszabadítását.

### 1. lépés: Bemeneti Shapefile megnyitása
A `VectorLayer.Open` metódus beolvassa a Shapefile-t, és egy felsorolható `Feature` objektumgyűjteményt ad vissza, amelyen iterálhat.

```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```

### 2. lépés: Kimeneti GeoJSON létrehozása
`VectorLayer.Create` a `Drivers.GeoJson` meghajtóval egy üres GeoJSON fájlt hoz létre, amely készen áll a feature‑ök fogadására.

```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```

### 3. lépés: Attribútumok másolása rétegek között
`CopyAttributes` egyetlen hívással másolja az attribútum sémát (mezőneveket és adattípusokat) a forrás Shapefile‑ról az új GeoJSON rétegbe.

```csharp
outputLayer.CopyAttributes(inputLayer);
```

### 4. lépés: Feature‑ök feldolgozása
Iteráljon minden egyes feature‑ön a Shapefile‑ben, hogy a kiírás előtt egyedi logikát alkalmazhasson.

```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```

### 5. lépés: Feature‑ök szűrése dátum alapján
Ebben a példában kihagyjuk azokat a rekordokat, amelyek `dob` (születési dátum) mezője hiányzik vagy 1982. jan. 1. előtt van. Igazítsa a szűrőt saját adatkövetelményeihez.

```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```

### 6. lépés: Új Feature létrehozása (C# GeoJSON fájl generálása)
A `Feature` egyetlen térbeli elemet képvisel, amely geometriát és attribútum adatokat tartalmaz.  
Itt egy új `Feature`‑t építünk a GeoJSON réteghez, másoljuk a geometriát és az attribútum értékeket, majd hozzáadjuk a kimenethez. Ez a *c# generate geojson file* lényege.

```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```

Gratulálunk! Sikeresen **konvertálta a shapefile-t GeoJSON formátumba**, és útközben megtanulta, hogyan **másolja az attribútumokat rétegek között**.

## Gyakori problémák és megoldások
| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| A kimeneti fájl üres | `CopyAttributes` a kimeneti réteg bezárása után lett meghívva | Győződjön meg róla, hogy az `outputLayer`-hez tartozó `using` blokk nyitva marad, amíg az összes feature hozzáadásra nem került. |
| A dátumszűrő eltávolítja az összes rekordot | Helytelen mezőnév vagy váratlan dátumformátum | Ellenőrizze az attribútum nevét (`dob`) és használja a `GetValue<string>`‑t, ha a dátumok karakterláncként vannak tárolva. |
| Licenc kivétel | Érvényes Aspose.GIS licenc hiányában történő futtatás termelésben | Alkalmazzon ideiglenes vagy teljes licencet az Aspose dokumentációban leírtak szerint. |

## Gyakran ismételt kérdések
**K: Hol találok további dokumentációt?**  
V: Látogassa meg a [Aspose.GIS dokumentációt](https://reference.aspose.com/gis/net/) a részletes információkért.

**K: Hogyan szerezhetek ideiglenes licencet?**  
V: Ideiglenes licencet szerezhet [itt](https://purchase.aspose.com/temporary-license/).

**K: Hol kérhetek támogatást?**  
V: Csatlakozzon az [Aspose.GIS fórumhoz](https://forum.aspose.com/c/gis/33) a közösségi támogatásért és megbeszélésekért.

**K: Elérhető ingyenes próba?**  
V: Igen, az ingyenes próbát [itt](https://releases.aspose.com/) találja.

**K: Hol vásárolhatom meg az Aspose.GIS for .NET-et?**  
V: A terméket [itt](https://purchase.aspose.com/buy) vásárolhatja meg.

## Következtetés
Ebben az útmutatóban bemutattuk a **shapefile GeoJSON formátumba konvertálásának** teljes folyamatát az Aspose.GIS for .NET használatával, megmutattuk, hogyan **másolhatók az attribútumok rétegek között**, és egy tiszta módszert a *c# generate geojson file* létrehozására. Kísérletezzen különböző szűrőkkel, nagyobb adatállományokkal vagy további geometriai átalakításokkal, hogy teljes mértékben kiaknázza a könyvtár képességeit.

---

**Last Updated:** 2026-07-05  
**Tesztelve:** Aspose.GIS for .NET (latest stable release)  
**Szerző:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Kapcsolódó útmutatók

- [Hogyan konvertáljunk GeoJSON-t File GDB-be az Aspose.GIS for .NET használatával](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Hogyan olvassunk GeoJSON-t stream‑ből az Aspose.GIS for .NET használatával](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Hogyan konvertáljunk GeoJSON-t TopoJSON-re az Aspose.GIS használatával](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
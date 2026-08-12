---
date: 2026-05-26
description: Tanulja meg, hogyan hozhat létre KML réteg C#-ban az Aspose.GIS for .NET
  használatával. Lépésről‑lépésre útmutató a geospatial data manipulálásához, code
  snippets és best practices segítségével. Töltse le a free trial most!
keywords:
- create kml layer c#
- Aspose.GIS .NET
- geospatial data C#
linktitle: KML Layer kezelése
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to create KML layer C# using Aspose.GIS for .NET. Step‑by‑step
    guide to manipulate geospatial data, with code snippets and best practices. Download
    the free trial now!
  headline: How to Create KML Layer in C# with Aspose.GIS
  type: TechArticle
- questions:
  - answer: Yes – Aspose.GIS lets you create KML layers programmatically.
    question: Can I generate KML files with C#?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: A free trial works for evaluation; a license is required for production.
    question: Do I need a license for development?
  - answer: Over 30 input and output formats, including KML, Shapefile, GeoJSON, and
      GML.
    question: How many GIS formats does Aspose.GIS handle?
  - answer: Files up to 2 GB are processed without loading the entire document into
      memory.
    question: Is there a size limit for KML files?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hogyan hozzunk létre KML réteg C#-ban az Aspose.GIS segítségével
url: /hu/net/layer-interaction-and-data-access/interact-with-kml-layer/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre KML réteget C#-ban az Aspose.GIS segítségével

## Bevezetés
Ha gyorsan és megbízhatóan szeretne **KML réteg létrehozása C#-ban** kódot készíteni, az Aspose.GIS for .NET egy teljes funkcionalitású API-t biztosít, amely bármely .NET platformon működik. Ebben az útmutatóban lépésről lépésre végigvezetjük a KML réteg felépítéséhez, attribútumok hozzáadásához, elemek feltöltéséhez és a fájl mentéséhez szükséges pontos lépéseken – mindezt anélkül, hogy elhagyná a Visual Studio-t. A végére megérti, miért egy termelésre kész megoldás a geospaciális adatok manipulálásához az Aspose.GIS.

## Gyors válaszok
- **Generálhatok KML fájlokat C#-ban?** Igen – az Aspose.GIS lehetővé teszi a KML rétegek programozott létrehozását.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Szükségem van fejlesztéshez licencre?** A ingyenes próba a kiértékeléshez használható; a termeléshez licenc szükséges.  
- **Hány GIS formátumot támogat az Aspose.GIS?** Több mint 30 bemeneti és kimeneti formátum, többek között KML, Shapefile, GeoJSON és GML.  
- **Van méretkorlát a KML fájloknál?** A 2 GB-ig terjedő fájlok feldolgozhatók anélkül, hogy a teljes dokumentumot a memóriába töltenék.

## Mi az a KML réteg?
A KML réteg egy földrajzi adatkonténer, amely a Keyhole Markup Language formátumban tárolja a helyjelölőket, stílusokat és geometriai adatokat, amelyet széles körben használnak web‑alapú térképekhez és a Google Earthhez. Tartalmazhat pontokat, vonalakat, poligonokat és kapcsolódó metaadatokat, lehetővé téve a gazdag vizualizációkat böngészőkben, GIS alkalmazásokban és a Google Earthben. A formátum XML‑alapú, így emberi olvasásra és gépi feldolgozásra egyaránt alkalmas.

## Miért használjuk az Aspose.GIS‑t KML rétegek létrehozásához?
Aspose.GIS támogatja a **30+ GIS formátumot**, és képes **több száz megabájtos fájlok** feldolgozására, miközben a memóriahasználat 100 MB alatt marad a streaming architektúra köszönhetően. A könyvtár garantálja a **100 % séma megfelelőséget**, így a generált KML hibátlanul működik minden főbb megjelenítőben. Ezen felül a könyvtár beépített validációt és a koordináta‑referencia rendszerek automatikus kezelését kínálja, így nem szükséges külső eszközt használni a megfelelőség biztosításához.

## Előfeltételek
Mielőtt elindulnánk ezen az úton, győződjön meg róla, hogy a következő előfeltételek rendelkezésre állnak:
- Aspose.GIS for .NET: Töltse le és telepítse a könyvtárat a [Aspose.GIS for .NET letöltési oldalról](https://releases.aspose.com/gis/net/).
- Fejlesztői környezet: Állítson be egy megfelelő fejlesztői környezetet, például a Visual Studio-t, hogy az Aspose.GIS zökkenőmentesen integrálódjon .NET projektjeibe.

Most merüljünk el az útmutatóban.

## Névterek importálása
Az `Aspose.Gis` névtér biztosítja a GIS adatokkal való munkához szükséges alap osztályokat. Ennek importálásával hozzáférhet a `KmlLayer`, `Feature` és attribútumkezelő segédeszközökhöz.

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Drawing;
using System.Threading;
using Aspose.Gis.Formats.Kml;
using Aspose.Gis.Formats.Kml.Styles;
using Aspose.Gis.Geometries;
using Point = Aspose.Gis.Geometries.Point;
```

## Hogyan hozzunk létre KML réteget C#-ban?
Töltse be a célkönyvtárat, hozza létre a kívánt fájlnévvel a `KmlLayer` objektumot, és hívja meg a `Save()`‑t – ennyi ahhoz, hogy érvényes KML fájlt generáljon. Az API automatikusan megírja a szükséges XML struktúrát, így nem kell alacsony szintű jelölést kézzel kezelnie.

## 1. lépés: A dokumentum könyvtár beállítása
Határozza meg a dokumentum könyvtár elérési útját, ahol a KML fájlok tárolásra kerülnek.

```csharp
string dataDir = "Your Document Directory";
```

## 2. lépés: KML réteg létrehozása
A `KmlLayer` osztály az Aspose.GIS reprezentációja a lemezen lévő KML fájlnak. Fájlúttal történő inicializálása egy üres réteget hoz létre, amely készen áll az elemekre.

```csharp
using (var layer = Drivers.Kml.CreateLayer(dataDir + "Kml_File_out.kml"))
{
```

## 3. lépés: Attribútumok meghatározása
`FeatureAttribute` egy attribútum definíciót jelent egy elemhez, megadva annak nevét és adat típusát. Adjon attribútumokat a KML réteghez, hogy különböző adat típusokat (például string, integer, boolean és double) képviseljen.

```csharp
layer.Attributes.Add(new FeatureAttribute("string_data", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("int_data", AttributeDataType.Integer));
layer.Attributes.Add(new FeatureAttribute("bool_data", AttributeDataType.Boolean));
layer.Attributes.Add(new FeatureAttribute("float_data", AttributeDataType.Double));
```

## 4. lépés: Elemek felépítése és feltöltése
`Feature` egy objektum, amely egyetlen GIS rekord geometriai és attribútum értékeit tárolja. Hozzon létre elemeket, amelyek geospaciális entitásokat képviselnek, és állítsa be a meghatározott attribútumok értékeit.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("string_data", "string value");
feature.SetValue("int_data", 10);
feature.SetValue("bool_data", true);
feature.SetValue("float_data", 3.14);
feature.Geometry = new LineString(new[] { new Point(0, 0), new Point(1, 1) });
layer.Add(feature);
```

## 5. lépés: Egy másik elem hozzáadása
Ismételje meg a folyamatot, hogy egy második elemet adjon hozzá különböző attribútum értékekkel és null geometriai értékkel.

```csharp
Feature feature2 = layer.ConstructFeature();
feature2.SetValue("string_data", "string value2");
feature2.SetValue("int_data", 100);
feature2.SetValue("bool_data", false);
feature2.SetValue("float_data", 3.1415);
feature2.Geometry = Geometry.Null;
layer.Add(feature2);
```

## Gyakori problémák és megoldások
- **Null geometria figyelmeztetés** – Ha egy elemnek nincs geometriája, győződjön meg róla, hogy a mentés előtt kifejezetten `null`‑ra állítja a geometriát; ellenkező esetben az API kivételt dobhat.  
- **Attribútum típuseltérés** – A hozzárendelt értéknek meg kell egyeznie az attribútum deklarált típusával; ellenkező esetben futásidejű hiba lép fel.  
- **Fájl útvonal hibák** – Használjon abszolút útvonalakat, vagy ellenőrizze, hogy az alkalmazásnak van‑e írási joga a célmappához.

## Gyakran feltett kérdések

### Az Aspose.GIS kompatibilis más GIS formátumokkal?
Igen, az Aspose.GIS többféle GIS formátumot támogat, többek között shapefile, GeoJSON és KML.

### Megjeleníthetem az Aspose.GIS‑szel létrehozott geospaciális adatokat?
Természetesen! Az Aspose.GIS zökkenőmentesen integrálódik a térképkönyvtárakkal, lehetővé téve a geospaciális adatok megjelenítését.

### Elérhető próba verzió az Aspose.GIS‑hez?
Igen, felfedezheti az Aspose.GIS funkcióit a [ingyenes próba verzió](https://releases.aspose.com/) letöltésével.

### Hogyan kaphatok támogatást az Aspose.GIS‑hez?
Látogassa meg az [Aspose.GIS fórumot](https://forum.aspose.com/c/gis/33) a közösségi támogatásért, vagy tekintse meg a prémium támogatási lehetőségeket [itt](https://purchase.aspose.com/buy).

### Elérhetők ideiglenes licencek az Aspose.GIS‑hez?
Igen, ideiglenes licencet szerezhet [itt](https://purchase.aspose.com/temporary-license/).

---

**Utolsó frissítés:** 2026-05-26  
**Tesztelve a következővel:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose

## Kapcsolódó útmutatók

- [Hogyan módosítsuk a réteget – Aspose.GIS .NET réteg interakció](/gis/net/layer-interaction-and-data-access/)
- [Réteg attribútumok lekérése – Réteg attribútum információk visszanyerése az Aspose.GIS for .NET segítségével](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Hogyan vágjunk le réteg elemeket az Aspose.GIS for .NET használatával](/gis/net/layer-management/crop-layer-features/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
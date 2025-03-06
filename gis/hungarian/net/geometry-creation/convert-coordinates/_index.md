---
title: Koordinálja az átalakítást az Aspose.GIS segítségével
linktitle: Koordináták konvertálása
second_title: Aspose.GIS .NET API
description: Ismerje meg, hogyan konvertálhat koordinátákat az Aspose.GIS for .NET segítségével. Lépésről lépésre útmutató, előfeltételek és GYIK biztosított.
weight: 25
url: /hu/net/geometry-creation/convert-coordinates/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Koordinálja az átalakítást az Aspose.GIS segítségével

## Bevezetés
Ebben az oktatóanyagban elmélyülünk a földrajzi információs rendszerek (GIS) világában a hatékony Aspose.GIS könyvtár segítségével .NET-hez. Az Aspose.GIS egy átfogó eszköztár, amely lehetővé teszi a fejlesztők számára, hogy könnyedén dolgozzanak téradatokkal. Akár tapasztalt fejlesztő, akár csak most kezdi, ez az oktatóanyag végigvezeti Önt az Aspose.GIS használatával a koordináták hatékony konvertálásához.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Alapvető C# ismerete: A C# programozási nyelv ismerete elengedhetetlen a megadott kódpéldák megértéséhez és megvalósításához.
  
2.  Az Aspose.GIS telepítése: Győződjön meg arról, hogy letöltötte és telepítette a .NET Aspose.GIS könyvtárát. Letöltheti a[Aspose.GIS weboldal](https://releases.aspose.com/gis/net/).

## Névterek importálása
Mielőtt elkezdenénk, importáljuk a szükséges névtereket az Aspose.GIS funkcióinak eléréséhez:
```csharp
using System;
using Aspose.Gis;
```

Bontsuk fel a példát több lépésre a világos megértés érdekében:
## 1. lépés: Indítsa el az átalakítási folyamatot
```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```
Ez a sor egyszerűen egy üzenetet jelenít meg, amely jelzi a koordinátakonverziós folyamat kezdetét.
## 2. lépés: Átalakítás decimális fokra
```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```
 Itt konvertáljuk a koordinátákat (25,5, 45,5) decimális fokos formátumba a`AsPointText` módszerrel a`PointFormats.DecimalDegrees` paraméter. Az eredmény ezután kinyomtatásra kerül a konzolra.
## 3. lépés: Átalakítás Degree decimális percre
```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```
Ez a lépés a koordinátákat fokos decimális perc formátumba konvertálja, és kinyomtatja az eredményt.
## 4. lépés: Átalakítás fokpercekre, másodpercekre
```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```
Hasonlóképpen konvertáljuk a koordinátákat fokperc másodperc formátumba, és megjelenítjük a kimenetet.
## 5. lépés: Konvertálás GeoRef
```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```
Végül konvertáljuk a koordinátákat GeoRef formátumba, és kinyomtatjuk az eredményt.

## Következtetés
Ebben az oktatóanyagban megvizsgáltuk a koordináták Aspose.GIS for .NET használatával történő konvertálásának folyamatát. A lépésenkénti útmutató követésével és az Aspose.GIS könyvtár használatával hatékonyan kezelheti a téradatokat .NET-alkalmazásaiban.
## GYIK
### Az Aspose.GIS kompatibilis más programozási nyelvekkel?
Az Aspose.GIS elsősorban a .NET-fejlesztőket célozza meg, de az Aspose.GIS for Java-n keresztül interoperabilitást kínál a Java-val.
### Kipróbálhatom az Aspose.GIS-t vásárlás előtt?
 Igen, elérheti az Aspose.GIS ingyenes próbaverzióját a webhelyről[weboldal](https://releases.aspose.com/).
### Hogyan kaphatok támogatást az Aspose.GIS-hez?
 Segítséget kérhet az Aspose.GIS közösségi fórumtól[itt](https://forum.aspose.com/c/gis/33).
### Rendelkezésre állnak ideiglenes licencek az Aspose.GIS számára?
 Igen, ideiglenes engedélyek szerezhetők be a[ideiglenes licenc oldal](https://purchase.aspose.com/temporary-license/).
### Hol vásárolhatom meg az Aspose.GIS-t?
 Az Aspose.GIS-t megvásárolhatja a[vásárlási oldal](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

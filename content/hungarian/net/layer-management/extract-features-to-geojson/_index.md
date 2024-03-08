---
title: Funkciók kibontása a GeoJSON-ba
linktitle: Funkciók kibontása a GeoJSON-ba
second_title: Aspose.GIS .NET API
description: Tekintse meg az Aspose.GIS for .NET használatáról szóló részletes útmutatót a funkciók GeoJSON-ba való kinyeréséhez. Használja ki könnyedén a GIS erejét! #Aspose #GIS
type: docs
weight: 23
url: /hu/net/layer-management/extract-features-to-geojson/
---
## Bevezetés
Üdvözöljük lépésről lépésre bemutató oktatóanyagunkban, amely a GeoJSON-ból az Aspose.GIS for .NET-hez való funkcióinak kinyerésével foglalkozik! Akár tapasztalt fejlesztő, akár csak most kezdi a térinformatikai programozást, ez az útmutató végigvezeti a folyamaton, és biztosítja, hogy az Aspose.GIS for .NET teljes erejét kihasználja.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
-  Aspose.GIS for .NET: Győződjön meg arról, hogy a könyvtár telepítve van. Ha nem, akkor letöltheti a[Aspose.GIS .NET oldalhoz](https://releases.aspose.com/gis/net/).
-  Shapefile adatok: Készítsen Shapefile-t a bevitelre. Ha mintaadatokra van szüksége, azt megtalálja a[Aspose.GIS dokumentáció](https://reference.aspose.com/gis/net/).
- .NET-környezet: Állítson be egy .NET-környezetet a megadott kód futtatásához.
- Dokumentumkönyvtár: Határozza meg a dokumentumkönyvtár elérési útját a kódrészletben.
Most, hogy minden a helyén van, kezdjük el a funkciók kibontását a GeoJSON-ba!
## Névterek importálása
Először is adja meg a szükséges névtereket a kódban:
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Ezek a névterek elengedhetetlenek az Aspose.GIS funkcióival való munkavégzéshez.
## 1. lépés: Nyissa meg a beviteli alakfájlt
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Ide kerül a bemeneti shapefájl feldolgozásához szükséges kód
}
```
 Nyissa meg a bemeneti Shapefile-t a`VectorLayer.Open` módszer.
## 2. lépés: Hozzon létre kimeneti GeoJSON-t
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Ide kerül a kimeneti GeoJSON létrehozásához szükséges kód
}
```
 Hozza létre a GeoJSON kimenetet a`VectorLayer.Create` módszer.
## 3. lépés: Attribútumok másolása
```csharp
outputLayer.CopyAttributes(inputLayer);
```
 Másolja át az attribútumokat a bemeneti rétegből a kimeneti rétegbe a segítségével`CopyAttributes` módszer.
## 4. lépés: A folyamat jellemzői
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Az egyes beviteli funkciók feldolgozásához szükséges kód itt található
}
```
Ismételje meg a beviteli réteg egyes jellemzőit, és dolgozza fel őket egyenként.
## 5. lépés: A funkciók szűrése dátum szerint
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
A funkciók szűrése dátumfeltétel alapján. Ebben a példában kihagyja az 1982 előtti születési dátumú funkciókat.
## 6. lépés: Új funkció létrehozása
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Hozzon létre egy új jellemzőt a kimeneti réteghez, másolja a geometriát és az értékeket a bemeneti jellemzőből.
Gratulálunk! Sikeresen kibontotta a szolgáltatásokat a GeoJSON-ba az Aspose.GIS for .NET használatával.
## Következtetés
Ebben az oktatóanyagban a funkciók GeoJSON-ba való kinyerésének folyamatát vizsgáltuk az Aspose.GIS for .NET használatával. Ez a nagy teljesítményű könyvtár a lehetőségek világát nyitja meg a térinformatikai fejlesztések számára. Kísérletezzen különböző adatkészletekkel és funkciókkal az Aspose.GIS teljes potenciáljának kiaknázásához.
## GYIK
### K: Hol találok további dokumentációt?
 Meglátogatni a[Aspose.GIS dokumentáció](https://reference.aspose.com/gis/net/) mélyreható tájékoztatásért.
### K: Hogyan szerezhetek ideiglenes engedélyt?
 Kaphat ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).
### K: Hol kérhetek támogatást?
 Csatlakozz a[Aspose.GIS fórum](https://forum.aspose.com/c/gis/33) közösségi támogatásra és beszélgetésekre.
### K: Van ingyenes próbaverzió?
 Igen, megtalálja az ingyenes próbaverziót[itt](https://releases.aspose.com/).
### K: Hol vásárolhatom meg az Aspose.GIS-t .NET-hez?
 Megvásárolhatja a terméket[itt](https://purchase.aspose.com/buy).
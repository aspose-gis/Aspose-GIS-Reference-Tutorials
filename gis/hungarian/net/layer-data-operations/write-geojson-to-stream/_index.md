---
title: Írjon GeoJSON-t a közvetítéshez
linktitle: Írjon GeoJSON-t a közvetítéshez
second_title: Aspose.GIS .NET API
description: Fedezze fel az Aspose.GIS erejét .NET-hez! Írjon GeoJSON-t a problémamentes adatfolyamhoz. Töltse le most a zökkenőmentes térinformatikai integráció érdekében.
weight: 25
url: /hu/net/layer-data-operations/write-geojson-to-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Írjon GeoJSON-t a közvetítéshez

## Bevezetés
Szeretné kihasználni a GeoJSON erejét .NET-alkalmazásában az Aspose.GIS használatával? Nos, jó helyen jársz! Ez a részletes útmutató végigvezeti a GeoJSON adatfolyamba való írásának folyamatán, kihasználva az Aspose.GIS for .NET robusztus képességeit.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
1. Aspose.GIS for .NET Library: Győződjön meg arról, hogy telepítve van az Aspose.GIS for .NET könyvtár. Letöltheti[itt](https://releases.aspose.com/gis/net/).
2. Dokumentumkönyvtár: Állítson be egy dokumentumkönyvtárat a projektben, és jegyezze fel annak elérési útját.
Most pedig kezdjük az oktatóanyaggal!
## Névterek importálása
Először is, győződjön meg róla, hogy tartalmazza a szükséges névtereket az Aspose.GIS funkciók eléréséhez a kódban:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```
## 1. lépés: Állítsa be a dokumentumkönyvtárat
```csharp
string dataDir = "Your Document Directory";
```
Cserélje le a „Saját dokumentumkönyvtár” elemet a dokumentumkönyvtár tényleges elérési útjával.
## 2. lépés: Hozzon létre egy memóriafolyamot
```csharp
using (var memoryStream = new MemoryStream())
{
    // A következő lépések kódja itt található
}
```
## 3. lépés: Hozzon létre egy vektorréteget a GeoJSON illesztőprogrammal
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // A következő lépések kódja itt található
}
```
## 4. lépés: Határozza meg a szolgáltatás attribútumait
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```
## 5. lépés: Építsen fel és adjon hozzá funkciókat
```csharp
// Első funkció
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Második funkció
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```
## 6. lépés: Jelenítse meg a GeoJSON kimenetet
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```
Gratulálunk! Sikeresen írtad a GeoJSON fájlt egy adatfolyamba az Aspose.GIS for .NET használatával.
## Következtetés
Ebben az oktatóanyagban bemutattuk az Aspose.GIS for .NET projektbe való integrálásának alapvető lépéseit, különös tekintettel a GeoJSON adatfolyamba írására. Ezekkel az egyszerű, de hatékony lépésekkel növelheti alkalmazása térinformatikai képességeit.
## Gyakran Ismételt Kérdések
### Használhatom az Aspose.GIS for .NET-t Windows és Linux környezetben is?
Igen, az Aspose.GIS for .NET Windows és Linux rendszerekkel is kompatibilis.
### Van ingyenes próbaverzió?
 Teljesen! Megtekintheti az ingyenes próbaverziót[itt](https://releases.aspose.com/).
### Hol találok részletes dokumentációt?
 Tekintse meg a dokumentációt[itt](https://reference.aspose.com/gis/net/).
### Hogyan szerezhetek ideiglenes engedélyt?
 Ideiglenes engedélyek rendelkezésre állnak[itt](https://purchase.aspose.com/temporary-license/).
### Segítségre van szüksége, vagy további kérdései vannak?
 Látogassa meg támogatási fórumunkat[itt](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

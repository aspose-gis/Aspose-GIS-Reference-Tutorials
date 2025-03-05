---
title: Adja meg az objektumazonosítót és a geometria mezőneveket
linktitle: Adja meg az objektumazonosítót és a geometria mezőneveket
second_title: Aspose.GIS .NET API
description: Fedezze fel a GIS varázslatot az Aspose.GIS for .NET segítségével! A térinformatikai adatok könnyed kezelése. Töltse le most, és engedje szabadjára a térbeli intelligencia erejét.
type: docs
weight: 20
url: /hu/net/layer-data-operations/specify-object-id-and-geometry-field-names/
---
## Bevezetés
Az Aspose.GIS for .NET használatával utazás a földrajzi információs rendszerek (GIS) birodalmába, lehetőségek világát nyitja meg a fejlesztők és a rajongók számára egyaránt. Ez a hatékony könyvtár lehetővé teszi a térinformatikai adatok könnyed kezelését. Ebben az oktatóanyagban végigvezetjük Önt az objektumazonosító és geometriai mezőnevek megadásának folyamatán, ezzel megalapozva térinformatikai törekvéseit.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
-  Aspose.GIS for .NET: Töltse le és telepítse a könyvtárat innen[itt](https://releases.aspose.com/gis/net/).
- Dokumentumkönyvtár: Hozzon létre egy könyvtárat dokumentumai számára a geoadatbázisok tárolására.
- .NET-környezet: Győződjön meg arról, hogy működő .NET-környezete van.
## Névterek importálása
A dolgok elindításához importálnia kell a szükséges névtereket a projektbe. Ezek a névterek biztosítják az alapvető osztályokat és módszereket az Aspose.GIS for .NET-hez való interakciójához.
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```
## 1. lépés: Adja meg az objektumazonosítót és a geometriai mezőneveket
Ebben a lépésben megtudhatja, hogyan állíthatja be az objektumazonosítót és a geometriai mezőneveket a GIS-adatokhoz. Ez elengedhetetlen a hatékony adatkezeléshez.
## 1.1. lépés: Állítsa be a dokumentumkönyvtárat
Kezdje a dokumentumkönyvtár elérési útjának meghatározásával:
```csharp
string dataDir = "Your Document Directory";
```
## 1.2. lépés: Hozzon létre egy Geoadatbázist és határozza meg a beállításokat
Hozzon létre egy Geoadatbázist megadott objektumazonosítókkal és geometriai mezőnevekkel:
```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Adja meg az objektumazonosító mező nevét
        GeometryFieldName = "POINT",       // Adja meg a Geometria mező nevét
    };
```
## 1.3. lépés: Hozzon létre és adjon hozzá egy réteget
Hozzon létre egy réteget a GeoDatabase-ban, és adjon hozzá egy adott geometriájú jellemzőt:
```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  //Adja meg a geometriát (ebben az esetben egy pontot)
    layer.Add(feature);
}
```
## 1.4. lépés: Nyissa meg és kérje le az adatokat a rétegből
Nyissa meg a réteget, és kérjen le belőle adatokat a megadott objektumazonosító alapján:
```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Kimenet: 1
}
```
## Következtetés
Gratulálunk! Sikeresen navigált az objektumazonosító és geometriai mezőnevek megadásának folyamatán az Aspose.GIS for .NET használatával. Ez szilárd alapot teremt GIS-projektjeihez, lehetővé téve a térinformatikai adatok egyszerű kezelését.
## Gyakran Ismételt Kérdések
### K: Használhatom az Aspose.GIS for .NET-et webalkalmazásaimban?
V: Igen, az Aspose.GIS for .NET alkalmas asztali és webes alkalmazásokhoz is, sokoldalú térinformatikai képességeket biztosítva.
### K: Rendelkezésre áll-e próbaverzió a vásárlás előtt?
 V: Igen, az Aspose.GIS for .NET szolgáltatásait ingyenes próbaverzióval fedezheti fel[itt](https://releases.aspose.com/).
### K: Hogyan szerezhetek ideiglenes licencet az Aspose.GIS for .NET számára?
 V: Kaphat ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/) értékelési célokra.
### K: Milyen térbeli referenciarendszereket támogat az Aspose.GIS for .NET?
V: Az Aspose.GIS for .NET különféle térbeli referenciarendszereket támogat, rugalmasságot biztosítva a különböző földrajzi adatkészletekhez.
### K: Hol kérhetek segítséget vagy vitathatom meg az Aspose.GIS-hez kapcsolódó lekérdezéseket?
 V: Látogassa meg az Aspose.GIS fórumot[itt](https://forum.aspose.com/c/gis/33) támogatásért és megbeszélésekért.
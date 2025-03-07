---
title: Hozzon létre vektorréteget az SRS-sel
linktitle: Hozzon létre vektorréteget az SRS-sel
second_title: Aspose.GIS .NET API
description: Fedezze fel az Aspose.GIS for .NET-et – ez a kulcs a zökkenőmentes GIS-integrációhoz. A megadott térbeli referenciarendszerekkel könnyedén hozhat létre vektorrétegeket. Letöltés most!
weight: 13
url: /hu/net/layer-management/create-vector-layer-with-srs/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hozzon létre vektorréteget az SRS-sel

## Bevezetés
Az Aspose.GIS for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy zökkenőmentesen dolgozzanak a földrajzi információs rendszer (GIS) adataival .NET-alkalmazásokban. Ebben az oktatóanyagban egy térbeli referenciarendszerrel (SRS) rendelkező vektorréteg létrehozására összpontosítunk. Az útmutató végére könnyedén integrálhatja a térinformatikai képességeket .NET-projektjeibe.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
- C# és .NET fejlesztési alapismeretek.
-  Aspose.GIS for .NET könyvtár telepítve. Letöltheti[itt](https://releases.aspose.com/gis/net/).
- Felállított és készen áll a fejlesztői környezet.
## Névterek importálása
Győződjön meg arról, hogy a szükséges névtereket importálta a C# fájl elejére:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## 1. lépés: A kivetített térbeli referenciarendszer beállítása
Hozzunk létre egy kivetített térbeli vonatkoztatási rendszert (SRS) a World Mercator vetülettel példaként. Kovesd ezeket a lepeseket:
```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```
## 2. lépés: Hozzon létre egy vektorréteget és adjon hozzá funkciókat
Most hozzunk létre egy shape fájlt, és adjunk hozzá funkciókat a megadott SRS-sel:
```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // Ez kivételt jelent, mivel a geometriának más SRS-je van
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## 3. lépés: Ellenőrizze a térbeli referenciarendszert
Végül nyissuk meg a réteget, és ellenőrizzük a térbeli vonatkoztatási rendszerét:
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Igaznak kell visszatérnie
}
```
Ezeket a lépéseket követve sikeresen létrehozott egy vektorréteget meghatározott térbeli referenciarendszerrel az Aspose.GIS for .NET használatával.
## Következtetés
A GIS-funkciók integrálása .NET-alkalmazásaiba még soha nem volt ilyen egyszerű az Aspose.GIS-nek köszönhetően. Azzal, hogy könnyedén hozhat létre vektorrétegeket és kezelheti a térbeli referenciarendszereket, hatékony térinformatikai képességekkel bővítheti projektjeit.
## GYIK
### Az Aspose.GIS kompatibilis az összes GIS fájlformátummal?
 Az Aspose.GIS különféle GIS-formátumokat támogat, beleértve a Shapefile-t, a GeoJSON-t, a KML-t és még sok mást. Ellenőrizd a[dokumentáció](https://reference.aspose.com/gis/net/) a teljes listához.
### Használhatom az Aspose.GIS-t webalkalmazásban?
Teljesen! Az Aspose.GIS for .NET sokoldalú, és használható webes alkalmazásokban, asztali alkalmazásokban és még mobilalkalmazásokban is.
### Hol kaphatok támogatást az Aspose.GIS-hez?
 Segítőkész közösséget találhat a[Aspose.GIS fórum](https://forum.aspose.com/c/gis/33) az esetlegesen felmerülő kérdésekre vagy problémákra.
### Van ingyenes próbaverzió?
 Igen, az Aspose.GIS szolgáltatásait ingyenes próbaverzióval fedezheti fel[itt](https://releases.aspose.com/).
### Hogyan vásárolhatok licencet az Aspose.GIS-hez?
 Licenc vásárlásához keresse fel a[vásárlási oldal](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

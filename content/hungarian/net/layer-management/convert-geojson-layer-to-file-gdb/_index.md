---
title: A GeoJSON fájlba a GDB-konverzió demystified
linktitle: Konvertálja a GeoJSON réteget GDB fájlba
second_title: Aspose.GIS .NET API
description: Fedezze fel a térinformatikai csodákat az Aspose.GIS for .NET segítségével! Könnyedén konvertálja a GeoJSON rétegeket fájl geoadatbázisokká. Probáld ki most! #Aspose #GIS
type: docs
weight: 17
url: /hu/net/layer-management/convert-geojson-layer-to-file-gdb/
---
## Bevezetés
A földrajzi információs rendszerek (GIS) dinamikus területén kulcsfontosságú az adatok zökkenőmentes konvertálása a különböző formátumok között. Az Aspose.GIS for .NET hatékony szövetségesként jelenik meg, átfogó eszköztárat kínálva a térinformatikai adatok könnyed kezelésére. Ebben az oktatóanyagban a GeoJSON-réteg Fájl-geoadatbázissá (File GDB) való konvertálásának folyamatába fogunk belemenni az Aspose.GIS for .NET használatával.
## Előfeltételek
Mielőtt elindulna erre a térinformatikai utazásra, győződjön meg arról, hogy a következő előfeltételekkel rendelkezik:
- .NET programozási ismeretek.
-  Aspose.GIS for .NET telepítve. Ha nem, töltsd le innen[itt](https://releases.aspose.com/gis/net/) és kövesse a telepítési utasításokat.
## Névterek importálása
Az átalakítási folyamat elindításához kezdje a szükséges névterek importálásával:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Most bontsuk le a folyamatot egy lépésről lépésre szóló útmutatóra:
## 1. lépés: Állítsa be a GeoJSON réteget
Kezdje egy GeoJSON-réteg létrehozásával a releváns attribútumokkal és funkciókkal. Íme egy részlet, amely eligazítja:
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Attribútumok hozzáadása
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //Építsen fel és adjon hozzá funkciókat
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```
## 2. lépés: Tesztadatkészlet másolása
A tesztadatok integritásának megőrzése érdekében hozzon létre egy másolatot az adatkészletről. Használja a következő kódrészletet:
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## 3. lépés: A GeoJSON konvertálása GDB fájlba
Most itt az ideje végrehajtani az átalakítást. Használja a következő kódot:
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Attribútumok másolása
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Adjon hozzá funkciókat
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## Következtetés
Ebben az oktatóanyagban az Aspose.GIS for .NET használatával egy GeoJSON-réteg fájl geoadatbázissá konvertálásának érdekes terepen navigáltunk. Ezzel a tudással felvértezve most már zökkenőmentesen kezelheti a térinformatikai adatokat .NET-alkalmazásaiban.
## GYIK
### Az Aspose.GIS kompatibilis a legújabb .NET keretrendszerrel?
Igen, az Aspose.GIS kompatibilis a legújabb .NET-keretrendszer-verziókkal.
### Konvertálhatok más térinformatikai formátumokat az Aspose.GIS segítségével?
Teljesen! Az Aspose.GIS a térinformatikai formátumok széles skáláját támogatja a sokoldalú adatkezelés érdekében.
### Elérhető az Aspose.GIS próbaverziója?
 Igen, felfedezheti az Aspose.GIS funkcióit a próbaverzió letöltésével[itt](https://releases.aspose.com/).
### Hogyan kaphatok támogatást az Aspose.GIS-hez kapcsolódó lekérdezésekhez?
 Irány az Aspose.GIS[fórum](https://forum.aspose.com/c/gis/33) dedikált támogatásért.
### Kaphatok ideiglenes licencet az Aspose.GIS-hez?
 Igen, biztosíthat ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).
---
title: Funkcióattribútum értékének lekérése (alapértelmezett)
linktitle: Funkcióattribútum értékének lekérése (alapértelmezett)
second_title: Aspose.GIS .NET API
description: Fedezze fel az Aspose.GIS erejét .NET-hez! Ezzel a lépésenkénti útmutatóval könnyedén lekérheti és módosíthatja a jellemző attribútumértékeit. Töltse le próbaverzióját most!
weight: 14
url: /hu/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Funkcióattribútum értékének lekérése (alapértelmezett)

## Bevezetés
Üdvözöljük az Aspose.GIS for .NET világában! Ebben az átfogó útmutatóban belevetjük magunkat az Aspose.GIS hatékony képességeinek felhasználásával a jellemző attribútumértékek lekérésének bonyolultságába. Akár tapasztalt fejlesztő, akár csak most kezdi, ez az oktatóanyag lépésről lépésre végigvezeti Önt, és biztosítja, hogy teljes mértékben kihasználja e figyelemre méltó eszközben rejlő lehetőségeket.
## Előfeltételek
Mielőtt belevágnánk ebbe a kódolási kalandba, győződjön meg arról, hogy a következő előfeltételekkel rendelkezik:
- C# és .NET keretrendszer gyakorlati ismerete.
-  Aspose.GIS for .NET telepítve. Ha nem, töltsd le innen[itt](https://releases.aspose.com/gis/net/).
- Egy kódszerkesztő, például a Visual Studio, amely zökkenőmentesen követhető.
## Névterek importálása
A C# projektben győződjön meg arról, hogy tartalmazza a szükséges névtereket:
```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Most bontsuk le az egyes példákat egy sor könnyen követhető lépésre.
## Funkcióattribútum értékének lekérése (alapértelmezett)
### 1. lépés: A környezet beállítása
Kezdje a dokumentumkönyvtár elérési útjának meghatározásával:
```csharp
string dataDir = "Your Document Directory";
```
### 2. lépés: Hozzon létre egy GeoJson réteget
Hozzon létre egy GeoJson réteget, és határozzon meg egy attribútumot alapértelmezett értékekkel:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### 3. lépés: Hozzon létre egy szolgáltatást
Hozzon létre egy jellemzőt a meghatározott attribútum használatával:
```csharp
    Feature feature = layer.ConstructFeature();
```
### 4. lépés: Értékek lekérése
Az attribútumértékek lekérése különböző forgatókönyvekkel:
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // érték == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // érték == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // érték == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## Alapértelmezett értékek beállítása
### 1. lépés: Hozzon létre egy másik GeoJson réteget
Ismételje meg a folyamatot egy másik GeoJson réteggel és egy dupla attribútummal:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### 2. lépés: Készítsen funkciót (ismét)
```csharp
    Feature feature = layer.ConstructFeature();
```
### 3. lépés: Az értékek lekérése és beállítása
Az attribútumértékek lekérése és beállítása, az alapértelmezett értékek megjelenítése:
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // érték == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // érték == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // érték == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
Gratulálunk! Sikeresen kihasználta az Aspose.GIS for .NET erejét a szolgáltatásattribútumértékek lekérésében és kezelésében.
## Következtetés
Ebben az oktatóanyagban megvizsgáltuk a szolgáltatásattribútumértékek lekérésének árnyalatait az Aspose.GIS for .NET használatával. Intuitív API-jával és robusztus képességeivel az Aspose.GIS a lehetőségek világát nyitja meg a GIS fejlesztése számára .NET környezetekben.
## Gyakran Ismételt Kérdések
### Az Aspose.GIS kompatibilis a .NET Core-al?
Igen, az Aspose.GIS teljes mértékben kompatibilis a .NET Core-al, és platformok közötti támogatást nyújt.
### Használhatom az Aspose.GIS-t kereskedelmi projektekhez?
Teljesen! Az Aspose.GIS kereskedelmi licenccel rendelkezik, amely lehetővé teszi, hogy korlátozás nélkül használja kereskedelmi alkalmazásaiban.
### Hol találhatok további támogatást és forrásokat?
 Meglátogatni a[Aspose.GIS fórum](https://forum.aspose.com/c/gis/33) közösségi támogatásért és fedezze fel a[dokumentáció](https://reference.aspose.com/gis/net/) mélyreható tájékoztatásért.
### Van ingyenes próbaverzió?
 Igen, felfedezheti az Aspose.GIS-t egy ingyenes próbaverzióval. Töltsd le[itt](https://releases.aspose.com/).
### Hogyan szerezhetek ideiglenes licencet tesztelési célból?
 Ideiglenes licencekért keresse fel a webhelyet[itt](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

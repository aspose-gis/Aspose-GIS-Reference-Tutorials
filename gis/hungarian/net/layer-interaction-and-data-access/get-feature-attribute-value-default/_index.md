---
date: 2026-01-05
description: Ismerje meg, hogyan lehet lekérni az attribútumértékeket és alapértelmezéseket
  beállítani az Aspose.GIS for .NET-ben. Ez a lépésről‑lépésre útmutató bemutatja
  a GeoJSON rétegek létrehozását és a GIS jellemzők felépítését.
linktitle: How to Get Attribute Value (Default)
second_title: Aspose.GIS .NET API
title: Hogyan kapjuk meg az attribútum értékét (alapértelmezett) az Aspose.GIS for
  .NET segítségével
url: /hu/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan kapjunk attribútum értéket (alapértelmezett) az Aspise.GIS for .NET segítségével

## Bevezetés
Ebben az átfogó oktatóanyagban megtanulja, **hogyan kapjunk attribútum** értékeket egy GIS elemhez az Aspose.GIS for .NET használatával, valamint hogyan kezelje az alapértelmezett értékeket, amikor egy attribútum hiányzik. Akár térbeli analitikai motoron, akár egyszerű térképnézőn dolgozik, az attribútumok lekérdezésének és az alapértelmezett értékek kezelésének elsajátítása elengedhetetlen a megbízható GIS alkalmazásokhoz.

## Gyors válaszok
- **Mi a fő módszer?** `Feature.GetValueOrDefault<T>()`  
- **Beállíthatok egy egyéni alapértelmezett értéket?** Igen, a túlterhelt metódus segítségével, amely alapértelmezett értéket fogad, vagy az attribútum `DefaultValue` meghatározásával.  
- **Szükségem van licencre a fejlesztéshez?** Egy ingyenes próba használható teszteléshez; a termeléshez kereskedelmi licenc szükséges.  
- **Támogatott geometriai formátumok?** GeoJSON, Shapefile, GML és sok más az Aspose.GIS meghajtókon keresztül.  
- **Működik .NET Core/.NET 6+?** Teljesen – a könyvtár platformfüggetlen.

## Előfeltételek
Mielőtt belemerülnénk, győződjön meg róla, hogy rendelkezik:

- Alapvető ismeretekkel C#-ban és a .NET ökoszisztémában.  
- Telepített Aspose.GIS for .NET verzióval. Ha még nincs, töltse le [innen](https://releases.aspose.com/gis/net/).  
- Kódszerkesztővel, például Visual Studio vagy Visual Studio Code programmal.

## Névterek importálása
Adja hozzá a szükséges `using` utasításokat a C# fájljához, hogy az API típusok elérhetők legyenek:

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

Most lépésről lépésre végigvezetjük a példákat.

## Hogyan kapjunk attribútum értéket (alapértelmezett)

### 1. lépés: A környezet beállítása
Adja meg a mappa elérési útját, amely a tesztdokumentumokat tartalmazza:

```csharp
string dataDir = "Your Document Directory";
```

### 2. lépés: GeoJSON réteg létrehozása
**Létrehozzuk a geojson réteget** — ez az első hely, ahol egy olyan attribútumot definiálunk, amely null vagy beállítatlan lehet:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```

### 3. lépés: GIS jellemző (feature) létrehozása
Most **létrehozzuk a GIS feature‑t** — ez egy friss feature példányt ad, amely tiszteletben tartja a most definiált attribútumsémát:

```csharp
    Feature feature = layer.ConstructFeature();
```

### 4. lépés: Értékek lekérése
Végül **lekérjük a feature attribútum** értékeit több szcenárióban, bemutatva, hogyan működnek az alapértelmezett értékek:

```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // value == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // value == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // value == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```

## Hogyan állítsunk be alapértelmezett értékeket

### 1. lépés: Egy másik GeoJSON réteg létrehozása
Ezúttal **az attribútum alapértelmezett értékét** állítjuk be közvetlenül a sémán:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```

### 2. lépés: GIS jellemző létrehozása (újra)

```csharp
    Feature feature = layer.ConstructFeature();
```

### 3. lépés: Értékek lekérése és beállítása
Lekérjük az alapértelmezett értéket, majd megváltoztatjuk, hogy lássuk a **hogyan állítsuk be az alapértelmezett értéket** futás közben:

```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // value == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // value == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // value == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```

## Gyakori hibák és tippek
- **Soha ne felejtse el bezárni a `using` blokkot.** A réteg automatikusan felszabadul, így a fájlkezelők is felszabadulnak.  
- **Ha a `CanBeNull` hamis, a `GetValueOrDefault` mindig visszaad egy értéket** (akár a tárolt, akár a definiált alapértelmezett).  
- **Használja a generikus túlterhelést** (`GetValueOrDefault<T>`), hogy elkerülje a value típusok dobozolását/kicsomagolását.  
- **Pro tipp:** Ha ellenőrizni szeretné, hogy egy attribútum ténylegesen be van-e állítva, használja a `feature.IsAttributeSet("attribute")` metódust a `GetValueOrDefault` hívása előtt.

## Gyakran Ismételt Kérdések

### Az Aspose.GIS kompatibilis a .NET Core‑ral?
Igen, az Aspose.GIS teljes mértékben kompatibilis a .NET Core‑ral, platformfüggetlen támogatást nyújtva.

### Használhatom az Aspose.GIS‑t kereskedelmi projektekhez?
Természetesen! Az Aspose.GIS kereskedelmi licencet tartalmaz, amely lehetővé teszi a szoftver használatát kereskedelmi alkalmazásokban korlátozások nélkül.

### Hol találok további támogatást és forrásokat?
Látogassa meg az [Aspose.GIS fórumot](https://forum.aspose.com/c/gis/33) a közösségi támogatásért, és tekintse meg a [dokumentációt](https://reference.aspose.com/gis/net/) a részletes információkért.

### Elérhető ingyenes próba?
Igen, az Aspose.GIS‑t ingyenes próba verzióval is kipróbálhatja. Töltse le [innen](https://releases.aspose.com/).

### Hogyan szerezhetek ideiglenes licencet teszteléshez?
Ideiglenes licencekért látogasson el [ide](https://purchase.aspose.com/temporary-license/).

## További GYIK

**K: Mi történik, ha a `GetValueOrDefault` metódust egy nem létező attribútumra hívom?**  
V: A metódus `ArgumentException` kivételt dob. Mindig ellenőrizze az attribútum nevét, vagy először használja a `feature.HasAttribute("name")` metódust.

**K: Módosíthatom az alapértelmezett értéket a réteg létrehozása után?**  
V: Igen, módosíthatja az `attribute.DefaultValue` értékét, majd meghívhatja a `layer.UpdateAttribute(attribute)` metódust a változás mentéséhez.

**K: Támogatja az Aspose.GIS az attribútumértékek tömeges frissítését?**  
V: Iterálhat egy feature gyűjteményen, és minden egyes feature-re meghívhatja a `SetValue` metódust; nagy adathalmazok esetén érdemes a `FeatureCursor` API‑t használni a jobb teljesítmény érdekében.

## Összegzés
Ebben az útmutatóban áttekintettük **hogyan kapjunk attribútum** értékeket, hogyan definiáljunk és felülírjunk alapértelmezett értékeket, valamint hogyan **hozzunk létre GeoJSON réteg** sémákat, amelyek megfelelnek az alkalmazás igényeinek. Ezekkel a technikákkal robusztus GIS megoldásokat építhet, amelyek elegánsan kezelik a hiányzó vagy opcionális adatokat.

---

**Last Updated:** 2026-01-05  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
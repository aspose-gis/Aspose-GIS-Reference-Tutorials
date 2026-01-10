---
date: 2026-01-10
description: Tanulja meg, hogyan hozhat létre fájlgeoadatbázis .NET adatkészleteket
  az Aspose.GIS for .NET használatával. Lépésről‑lépésre útmutató az egyszerű GIS
  adatkezeléshez.
linktitle: Create New File GDB Dataset
second_title: Aspose.GIS .NET API
title: Fájl Geodatabase .NET adatkészlet létrehozása az Aspose.GIS segítségével
url: /hu/net/layer-management/create-new-file-gdb-dataset/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# File Geodatabase .NET adathalmaz létrehozása Aspose.GIS‑szel

## Bevezetés
Ebben az útmutatóban **file geodatabase .NET** adathalmazokat hozunk létre a semmiből az Aspose.GIS for .NET használatával. Akár asztali GIS‑eszközt, akár térbeli adatokat tároló web‑szolgáltatást építesz, vagy egyszerűen megbízható módra van szükséged a File Geodatabase programozott generálásához, ez a leírás minden lépést részletes magyarázatokkal és valós példákkal mutat be.

## Gyors válaszok
- **Miről szól ez az útmutató?** Új File Geodatabase létrehozása, két réteg hozzáadása, és az adathalmaz ellenőrzése az Aspose.GIS for .NET‑tel.  
- **Mennyi időt vesz igénybe?** Körülbelül 10‑15 perc egy C#‑ban jártas fejlesztőnek.  
- **Előkövetelmények?** .NET fejlesztői környezet, Aspose.GIS for .NET könyvtár, és egy írható mappapath.  
- **Használható .NET Core / .NET 6+ alatt?** Igen – az API teljesen kompatibilis a modern .NET futtatókörnyezetekkel.  
- **Szükséges licenc?** Ideiglenes vagy állandó Aspose.GIS licenc szükséges a termelésben való használathoz.

## Mi az a File Geodatabase?
A File Geodatabase (File GDB) egy mappán alapuló adatbázis, amely GIS feature class‑okat, raszter adathalmazokat és kapcsolódó metaadatokat tárol. Gyors olvasási/írási teljesítményt nyújt, nagy adathalmazok kezelésére alkalmas, és széles körben használják az Esri ArcGIS ökoszisztémájában. Az Aspose.GIS‑szel közvetlenül .NET kódból hozhatók létre és kezelhetők ezek az adatbázisok külső GIS szoftver nélkül.

## Miért érdemes file geodatabase .NET‑et létrehozni az Aspose.GIS‑szel?
- **Nincsenek külső függőségek** – a könyvtár kezeli a fájlformátum részleteit.  
- **Keresztplatformos** – Windows, Linux és macOS .NET futtatókörnyezeteken működik.  
- **Gazdag geometriai támogatás** – pontok, vonalak, poligonok és még sok más.  
- **Teljes irányítás** – te határozod meg a sémát, attribútumokat és a térbeli referenciát.

## Előkövetelmények
Mielőtt elkezdenéd, győződj meg róla, hogy a következők rendelkezésre állnak:

- Aspose.GIS for .NET telepítve. Letöltheted a [Aspose.GIS for .NET letöltési oldalról](https://releases.aspose.com/gis/net/).  
- Fejlesztői környezet, például Visual Studio 2022 (vagy bármely .NET‑et támogató IDE).  
- Írható mappa a gépeden, ahol az új GDB-t létrehozzuk – a kódban cseréld ki a `"Your Document Directory"` értéket erre az útvonalra.  
- Alapvető C# és .NET projektstruktúra ismerete.

## Névtér importálása
Először importáld azokat a névtereket, amelyek hozzáférést biztosítanak az Aspose.GIS osztályokhoz:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Lépésről‑lépésre útmutató

### 1. lépés: Új File GDB adathalmaz létrehozása
Az alábbi kódrészlet egy üres File Geodatabase‑t hoz létre. Ez a **create file geodatabase .net** folyamat központja.

```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Output: 0
    // Continue with subsequent steps...
}
```

**Magyarázat:** A `Dataset.Create` inicializálja a GDB‑t a megadott útvonalon a `FileGdb` driver használatával. Ebben a pontban az adathalmaznak még nincsenek rétegei, így a réteg számláló nulla.

### 2. lépés: `layer_1` létrehozása és feltöltése
Most hozzáadunk egy első réteget, amely egész szám attribútumokat és pontgeometriákat tárol.

```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```

**Magyarázat:**  
- A `CreateLayer` létrehoz egy új feature class‑t **layer_1** néven.  
- Egy **value** nevű egész szám attribútum kerül definiálásra.  
- A ciklus tíz elemet ad hozzá, mindegyik egyedi egész számmal és egy *(i, i)* koordinátájú ponttal.

### 3. lépés: `layer_2` létrehozása és feltöltése
Ezután egy második réteget adunk hozzá, amely a vonalgeometria kezelését mutatja be.

```csharp
using (var layer = dataset.CreateLayer("layer_2"))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```

**Magyarázat:** Létrehozza a **layer_2**‑t, és egyetlen elemet szúr be, amelynek geometriája egy `LineString`, amely két pontot köt össze.

### 4. lépés: A frissített rétegszám ellenőrzése
Végül erősítsd meg, hogy mindkét réteg sikeresen hozzá lett adva.

```csharp
Console.WriteLine(dataset.LayersCount); // Output: 2
```

**Magyarázat:** Az adathalmaz most már két réteget jelent, ami megerősíti, hogy a **create file geodatabase .net** folyamat a várt módon befejeződött.

## Gyakori problémák és megoldások
| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| **`UnauthorizedAccessException`** a dataset létrehozásakor | A mappa csak olvasható vagy nincs megfelelő jogosultságod. | Válassz egy írható könyvtárat, vagy futtasd a Visual Studio‑t rendszergazdaként. |
| **`ArgumentException` a driverhez** | A driver neve el van gépelve, vagy a könyvtár verziója nem támogatja. | Használd pontosan a `Drivers.FileGdb`‑t, és győződj meg a legújabb Aspose.GIS csomagról. |
| **A feature‑ök nem jelennek meg az ArcGIS‑ben** | Hiányzik a térbeli referencia vagy inkompatibilis a geometria. | Állíts be térbeli referenciát a rétegen, ha szükséges, és ellenőrizd a geometria érvényességét. |

## Gyakran feltett kérdések
### K: Használhatom az Aspose.GIS for .NET‑et más GIS könyvtárakkal?
Az Aspose.GIS for .NET egy önálló eszközkészlet; azonban integrálható más .NET könyvtárakkal a funkcionalitás bővítése érdekében.

### K: Van közösségi fórum az Aspose.GIS támogatásához?
Igen, támogatást és megbeszéléseket találsz a [Aspose.GIS Fórumon](https://forum.aspose.com/c/gis/33).

### K: Hogyan szerezhetek ideiglenes licencet az Aspose.GIS‑hez?
Látogasd meg a [Temporary License](https://purchase.aspose.com/temporary-license/) oldalt az ideiglenes licenc igénylésével kapcsolatos információkért.

### K: Van további példakód és dokumentáció?
Fedezd fel az [Aspose.GIS dokumentációt](https://reference.aspose.com/gis/net/) további példák és részletes leírások miatt.

### K: Hol vásárolhatom meg az Aspose.GIS for .NET‑et?
Megvásárolhatod az Aspose.GIS for .NET-et a [vásárlási oldalon](https://purchase.aspose.com/buy).

## Összegzés
Sikeresen **létrehoztad a file geodatabase .NET** adathalmazt, két különálló réteget adtál hozzá, és ellenőrizted az eredményt az Aspose.GIS‑szel. Ez az alap lehetővé teszi, hogy gazdagabb GIS‑alkalmazásokat építs – további rétegeket adj hozzá, komplex sémákat definiálj, vagy integráld web‑szolgáltatásokkal. Fedezd fel tovább az Aspose.GIS API‑t raszter adatok, térbeli lekérdezések és fejlett geometriai műveletek kezeléséhez.

---

**Utolsó frissítés:** 2026-01-10  
**Tesztelt verzió:** Aspose.GIS for .NET 24.11 (vagy legújabb)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
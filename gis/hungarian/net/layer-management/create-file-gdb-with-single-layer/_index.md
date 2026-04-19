---
date: 2026-01-10
description: Tanulja meg, hogyan hozhat létre vektor réteget egy fájl geoadatbázisban
  az Aspose.GIS for .NET használatával. Kezelje a térinformatikai adatokat WGS84 térreferenciával
  és fájl‑gdb beállításokkal.
linktitle: Create File GDB with Single Layer
second_title: Aspose.GIS .NET API
title: Vektor réteg létrehozása File GDB-ben – Aspose.GIS .NET útmutató
url: /hu/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektor réteg létrehozása File GDB-ben

## Bevezetés
Ha **vektor réteget** kell létrehoznia egy File Geodatabase (GDB) belsejében, és hatékonyan szeretné kezelni a térbeli adatokat, az Aspose.GIS for .NET tiszta, kódelő megközelítést biztosít. Ebben a lépésről‑lépésre útmutatóban megmutatjuk, hogyan írjon egy vonal objektumot, hogyan konfigurálja a file gdb beállításokat, és hogyan dolgozzon a WGS84 térbeli referenciával – mindezt néhány C# sorban. A végére képes lesz megszámolni a rétegben lévő objektumokat, és beilleszteni a létrehozott GDB-t bármely .NET térképezési vagy elemzési munkafolyamatba.

## Gyors válaszok
- **Mi jelent a “vektor réteg létrehozása”?** Új vektor adatkészlet (pontok, vonalak vagy poligonok) hozzáadását jelenti egy geodatabase fájlhoz.  
- **Melyik könyvtárat használjam?** Az Aspose.GIS for .NET teljes támogatást nyújt a File GDB létrehozásához és szerkesztéséhez.  
- **Szükségem van licencre a fejlesztéshez?** Egy ingyenes próba verzió tesztelésre elegendő; a termeléshez kereskedelmi licenc szükséges.  
- **Beállíthatom a térbeli referenciát?** Igen – használja a `SpatialReferenceSystem.Wgs84`-et a gyakori WGS84 datumhoz.  
- **Hány sor kód?** Kevesebb, mint 30 sor a GDB létrehozásához, egy vonal objektum hozzáadásához és a objektumszám visszaolvasásához.

## Mi a “vektor réteg létrehozása” művelet?
A vektor réteg létrehozása azt jelenti, hogy egy új táblát definiálunk egy geodatabase-ben, amely geometriai objektumokat (pontok, vonalak, poligonok) és azok attribútumait tárolja. Ez a művelet minden GIS‑alapú alkalmazás alapja, amelynek **térbeli adatok kezelése** szükséges.

## Miért használja az Aspose.GIS-t vektor réteg létrehozásához?
- **Nulla külső függőség** – az API azonnal működik .NET Framework, .NET Core és .NET 5/6 környezetben.  
- **Teljes támogatás a File GDB-hez** – konfigurálhatja a `FileGdbOptions`-t a tömörítés, térbeli indexelés és egyebek vezérléséhez.  
- **Beépített térbeli referenciakezelés** – egyszerűen adja át a `SpatialReferenceSystem.Wgs84`-et a globális koordináta rendszerben való munkához.  
- **Egyszerű API** – írjon vonal objektumot, adja hozzá egy réteghez, és néhány metódushívással szerezze meg az objektumszámot.

## Előkövetelmények
1. **Aspose.GIS for .NET** – töltse le a [Aspose.GIS for .NET letöltési oldalról](https://releases.aspose.com/gis/net/).  
2. **.NET fejlesztői környezet** – Visual Studio, Rider vagy a `dotnet` CLI.  
3. **Egy mappa**, ahol a File GDB létre lesz hozva (ezt *Your Document Directory*-nek nevezzük).

## Névterek importálása
Adja hozzá a szükséges `using` utasításokat a C# fájlja tetejére:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```

## 1. lépés: A Document Directory beállítása
`"Your Document Directory"` helyettesítse a teljes elérési úttal, ahol a File GDB-t tárolni szeretné.

```csharp
string dataDir = "Your Document Directory";
```

## 2. lépés: File Geodatabase létrehozása egyetlen réteggel
Ez a kódrészlet **vektor réteget hoz létre** a `FileGdbOptions` használatával, egy egyszerű vonal objektumot ír, és egy **WGS84 térbeli referenciát** használó File GDB-be tárolja.

```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
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

## 3. lépés: A File Geodatabase megnyitása és a réteg információinak lekérdezése
Itt **megszámoljuk a réteg objektumait** az adatkészlet megnyitásával és az objektumok számának kiírásával – ebben az esetben `1`.

```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| **`File not found`** | Helytelen `path` változó | Ellenőrizze, hogy a `dataDir` egy létező mappára mutat, és a `path` egy fájlnevet kombinál vele, pl. `Path.Combine(dataDir, \"MyData.gdb\")`. |
| **`Unsupported geometry`** | Olyan geometria típus használata, amely nem engedélyezett a File GDB-ben | Maradjon a `Point`, `LineString` vagy `Polygon` típusoknál az alap rétegekhez. |
| **`License not set`** | Érvényes licenc hiányában történő futtatás termelésben | Regisztrálja licencét a `License license = new License(); license.SetLicense(\"Aspose.GIS.lic\");` kóddal. |

## Gyakran ismételt kérdések
### Használhatom az Aspose.GIS for .NET-et meglévő .NET projektjeimben?
Igen, az Aspose.GIS for .NET zökkenőmentesen integrálható a meglévő .NET projektekbe.

### Elérhető próba verzió az Aspose.GIS for .NET-hez?
Igen, a [free trial version](https://releases.aspose.com/) letöltésével felfedezheti az Aspose.GIS for .NET funkcióit.

### Hol találok részletes dokumentációt az Aspose.GIS for .NET-hez?
Tekintse meg a [documentation](https://reference.aspose.com/gis/net/) oldalt a részletes információkért.

### Hogyan kaphatok támogatást az Aspose.GIS for .NET-hez?
Látogassa meg a [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) közösségi támogatásért és segítségért.

### Elérhetők ideiglenes licencek az Aspose.GIS for .NET-hez?
Igen, egy [temporary license](https://purchase.aspose.com/temporary-license/) szerezhető az Aspose.GIS for .NET-hez.

**Legutóbb frissítve:** 2026-01-10  
**Tesztelve a következővel:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
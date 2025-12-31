---
date: 2025-12-31
description: Fedezze fel az Aspose.GIS for .NET-et, és tanulja meg, hogyan hozhat
  létre file GDB adatkészletet, valamint hogyan állíthat be toleranciákat könnyedén,
  lépésről‑lépésre útmutatóval. Fejlessze .NET alkalmazásait.
linktitle: Set Tolerances for File GDB Layer
second_title: Aspose.GIS .NET API
title: Fájl GDB adatkészlet létrehozása és toleranciák beállítása egy réteghez
url: /hu/net/layer-data-operations/set-tolerances-for-file-gdb-layer/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fájl GDB adatkészlet létrehozása és toleranciák beállítása egy réteghez

## Introduction
Ha **create file GDB dataset**-t kell létrehoznia és a pontosságát szabályoznia, jó helyen jár. Ebben az útmutatóban végigvezetjük a teljes folyamaton – a .NET projekt beállításától, a File Geodatabase (GDB) adatkészlet létrehozásáig, majd XY, Z és M toleranciák alkalmazásáig egy új rétegen. A végére egy használatra kész adatkészletet kap, amely zökkenőmentesen működik az ArcGIS eszközökkel és más GIS alkalmazásokkal.

## Quick Answers
- **Mi jelentése a “create file GDB dataset” kifejezésnek?** Új File Geodatabase tárolót hoz létre a lemezen, amely több GIS réteget is tartalmazhat.  
- **Miért kell toleranciákat beállítani?** A toleranciák meghatározzák a geometriai műveletek pontosságát, megakadályozva a kerekítési hibákat a térbeli elemzésekben.  
- **Melyik Aspose.GIS osztályt használják?** `Dataset.Create` együtt a `FileGdbOptions`-szal.  
- **Szükségem van licencre a fejlesztéshez?** Ideiglenes licenc elegendő a teszteléshez; a termeléshez teljes licenc szükséges.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is a File GDB Dataset?
A File Geodatabase (GDB) egy mappán alapuló adatáruház, amely GIS rétegeket, táblákat és kapcsolatokt tárol. Az Aspose.GIS használatával programozott módon **create file GDB dataset** hozható létre anélkül, hogy az ArcGIS telepítve lenne, így ideális automatizált folyamatokhoz vagy egyedi alkalmazásokhoz.

## Why set tolerances for a layer?
A toleranciák beállítása biztosítja, hogy a geometriai számítások (például metszetek, bufferelés vagy illesztés) a szükséges pontosságot tartsák be. Ez különösen fontos magas felbontású adatokkal dolgozva vagy más GIS platformokra való exportáláskor, ahol meghatározott toleranciaértékekre van szükség.

## Prerequisites
Mielőtt a kódba merülnénk, győződjön meg, hogy a következőkkel rendelkezik:

- **Aspose.GIS for .NET Library** – Töltse le és telepítse az Aspose.GIS könyvtárat a [download link](https://releases.aspose.com/gis/net/) címről. Ha még nem szerezte be, a [documentation](https://reference.aspose.com/gis/net/) oldalon további információkat talál.
- **Fejlesztői környezet** – Visual Studio, Rider vagy bármely .NET fejlesztést támogató IDE.
- **Érvényes licenc** – Használjon ideiglenes licencet a teszteléshez vagy teljes licencet a termeléshez (lásd a GYIK szakaszban található hivatkozásokat).

Miután minden készen áll, importáljuk a szükséges névtereket.

## Import Namespaces
A .NET alkalmazásában adja hozzá a következő névtereket az Aspose.GIS funkcióinak kihasználásához:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

A névterek megadása után elkezdhetjük az adatkészlet felépítését.

## Step‑by‑Step Guide

### Step 1: Define Your Document Directory
Először is, irányítsa a kódot arra a mappára, ahol a File GDB-t létre szeretné hozni:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tipp:** Használja a `Path.Combine`-t, ha platform‑független módon kell felépíteni az elérési utat.

### Step 2: Create a File GDB Dataset
Most már ténylegesen **create file GDB dataset**-t hozunk létre a lemezen. A `Dataset.Create` metódus a teljes elérési utat és a meghajtó típusát (`Drivers.FileGdb`) veszi át.

```csharp
var path = dataDir + "TolerancesForFileGdbLayer_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

> A `using` blokk biztosítja, hogy az adatkészlet megfelelően le legyen zárva és a lemezre legyen kiürítve, amikor befejezi.

### Step 3: Set Tolerances using `FileGdbOptions`
Mielőtt réteget hozna létre, definiálja a szükséges toleranciákat. A `FileGdbOptions` lehetővé teszi XY, Z és M toleranciák megadását.

```csharp
var options = new FileGdbOptions
{
    XYTolerance = 0.001,
    ZTolerance = 0.1,
    MTolerance = 0.1,
};
```

Ezek az értékek tipikusak a nagy pontosságú mérnöki adatokhoz, de a projekt igényei szerint módosíthatók.

### Step 4: Create a Layer with the Specified Tolerances
Végül hozzon létre egy új réteget az adatkészleten belül, átadva a most konfigurált opciók objektumát.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options))
{
    // The layer is created with the provided tolerances, ready for use in ArcGIS features/tools.
}
```

Amikor a `using` blokk befejeződik, a réteg a megadott toleranciákkal lesz mentve.

## Common Issues & Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **Az adatkészlet útvonala nem található** | A `dataDir` változó egy nem létező mappára mutat. | Győződjön meg róla, hogy a könyvtár létezik, vagy hozza létre a `Directory.CreateDirectory(dataDir)` segítségével. |
| **Érvénytelen toleranciaértékek** | A toleranciáknak nem negatív számoknak kell lenniük. | Használjon pozitív értékeket; kerülje a nullát, hacsak nem szándékosan szeretne tolerancia nélküli beállítást. |
| **Licenc hiba** | A próbaverzió vagy ideiglenes licenc lejárt. | Alkalmazzon friss ideiglenes licencet vagy frissítsen teljes licencre. |

## Frequently Asked Questions

**K: Használhatom az Aspose.GIS for .NET-et más GIS könyvtárakkal?**  
V: Igen, az Aspose.GIS támogatja az interoperabilitást, lehetővé téve integrációt olyan könyvtárakkal, mint a NetTopologySuite vagy a GDAL.

**K: Elérhető próba verzió az Aspose.GIS for .NET-hez?**  
V: Természetesen! A funkciókat a [free trial version](https://releases.aspose.com/) segítségével tekintheti meg.

**K: Hogyan kaphatok támogatást az Aspose.GIS for .NET-hez?**  
V: Látogassa meg az [Aspose.GIS fórumot](https://forum.aspose.com/c/gis/33), hogy kapcsolatba léphessen a közösséggel és segítséget kérhessen.

**K: Szükségem van ideiglenes licencre a teszteléshez?**  
V: Igen, a [temporary license](https://purchase.aspose.com/temporary-license/) segítségével szerezhet ideiglenes licencet a teszteléshez és értékeléshez.

**K: Hol vásárolhatom meg az Aspose.GIS for .NET licencet?**  
V: A licencet a [buy page](https://purchase.aspose.com/buy) oldalon vásárolhatja meg.

## Conclusion
Ebben az útmutatóban bemutattuk, hogyan **create file GDB dataset**, hogyan konfiguráljuk a geometriai toleranciákat, és hogyan mentünk egy használatra kész réteget az Aspose.GIS for .NET segítségével. Ezek a lépések pontos irányítást biztosítanak a térbeli adatok felett, így GIS alkalmazásai megbízhatóbbak és interoperábilisabbak lesznek.

---  
**Utoljára frissítve:** 2025-12-31  
**Tesztelve a következővel:** Aspose.GIS for .NET 24.11 (a legújabb a írás időpontjában)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
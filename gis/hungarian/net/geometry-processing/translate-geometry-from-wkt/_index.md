---
date: 2025-12-23
description: Ismerje meg, hogyan konvertálhatja a WKT-t geometriává, és hogyan számolhat
  pontokat az Aspose.GIS for .NET használatával. Lépésről‑lépésre útmutató fejlesztőknek.
linktitle: Translate Geometry from WKT
second_title: Aspose.GIS .NET API
title: Hogyan konvertáljuk a WKT-t geometriává az Aspose.GIS segítségével .NET-ben
url: /hu/net/geometry-processing/translate-geometry-from-wkt/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# WKT átalakítása geometriává az Aspose.GIS .NET-ben

## Introduction
Ebben az útmutatóban megtudja, **hogyan konvertálja a WKT-t geometriává** az Aspose.GIS for .NET segítségével, és egy gyakorlati példát láthat **hogyan számoljon pontokat** az eredményül kapott alakzatban. Akár térképszolgáltatást épít, GIS adatokat dolgoz fel, vagy egyszerűen csak Well‑Known Text-et kell beolvasnia egy .NET alkalmazásban, ezek a lépések gyorsan elindítják Önt.

## Quick Answers
- **Olvashatja-e az Aspose.GIS a WKT-t?** Igen – a `Geometry.FromText` metódus közvetlenül elemzi a WKT karakterláncokat.  
- **Hány kódsorra van szükség?** Körülbelül 5‑6 sor egy alap konverzióhoz és pontszámláláshoz.  
- **Szükség van licencre a termeléshez?** Igen, kereskedelmi licenc szükséges a nem‑próba használathoz.  
- **Támogatott .NET verziók?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6+.  
- **Beépített a pontszámlálás?** Teljesen – a geometria objektumok rendelkeznek `Count` tulajdonsággal.

## What is “convert WKT to geometry”?
A Well‑Known Text (WKT) egy egyszerű szöveges jelölés a geometriai objektumok ábrázolására. A WKT geometriává konvertálása azt jelenti, hogy ezt a szöveget egy objektummodellé (pl. `ILineString`, `IPolygon`) alakítjuk, amelyet programozottan manipulálhat.

## Why use Aspose.GIS for this conversion?
- **Nulla függőségű feldolgozás** – nincs szükség külső könyvtárakra.  
- **Teljes GIS funkciókészlet** – támogatja a 2D/3D koordinátákat, az SRID kezelését és számos fájlformátumot.  
- **Magas teljesítmény** – optimalizált nagy adathalmazokhoz és több szálas szcenáriókhoz.  

## Prerequisites
Az elkezdés előtt győződjön meg róla, hogy rendelkezik:

1. Aspose.GIS for .NET API – letöltheti [innen](https://releases.aspose.com/gis/net/).  
2. Alapvető C# ismeretekkel és egy .NET fejlesztői környezettel (Visual Studio, VS Code, stb.).

## Import Namespaces
Először adja hozzá a szükséges névtereket a C# fájlhoz:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step 1: Create a LineString from WKT
Most **WKT‑t konvertálunk geometriává** egy `LineString` objektum létrehozásával egy Z‑koordinátákat tartalmazó WKT karakterláncból:

```csharp
ILineString line = (ILineString)Geometry.FromText("LINESTRING Z (0.1 0.2 0.3, 1 2 1, 12 23 2)");
```

> *Pro tipp:* A `FromText` metódus automatikusan felismeri a geometria típusát, így a megfelelő interfészre (`ILineString`, `IPolygon`, stb.) tudja átkonvertálni.

## How to count points in a LineString?
A másodlagos kulcsszó, **hogyan számoljon pontokat**, megválaszolásához egyszerűen olvassa el az `ILineString` példány `Count` tulajdonságát:

```csharp
Console.WriteLine(line.Count); // Output: 3
```

A kimenet azt mutatja, hogy a vonal három csúcsot tartalmaz, ami megerősíti, hogy a konverzió sikeres volt és a pontszám helyes.

## Conclusion
Most már tudja, **hogyan konvertálja a WKT-t geometriává** az Aspose.GIS for .NET segítségével, és hogyan kérdezheti le a pontok számát egyetlen tulajdonság hívással. Ezek az alapok lehetővé teszik a GIS adatfeldolgozás integrálását bármely .NET alkalmazásba, legyen az asztali eszköz vagy felhőszolgáltatás.

## GYIK
### Can I use Aspose.GIS for .NET in my commercial projects?
Igen, használhatja. Az Aspose.GIS for .NET fejlesztőnként licencelt, így kereskedelmi projektekben korlátozás nélkül használható.

### Does Aspose.GIS for .NET support other geometric formats besides WKT?
Igen, az Aspose.GIS for .NET számos geometriai formátumot támogat, többek között WKB, GeoJSON és Shapefile.

### Is there a free trial available for Aspose.GIS for .NET?
Igen, ingyenes próbaverziót szerezhet [innen](https://releases.aspose.com/).

### Where can I find documentation for Aspose.GIS for .NET?
A dokumentációt megtalálja [itt](https://reference.aspose.com/gis/net/).

### How can I get support for Aspose.GIS for .NET?
Támogatást kaphat az Aspose.GIS fórumon [itt](https://forum.aspose.com/c/gis/33).

## Frequently Asked Questions (Additional)

**K: Mi van, ha a WKT karakterláncom érvénytelen szintaxist tartalmaz?**  
V: A `Geometry.FromText` `FormatException`-t dob. A hívást tekerje try‑catch blokkba, hogy megfelelően kezelje a hibás WKT-t.

**K: Konvertálhatok egy WKT karakterláncok gyűjteményét egyszerre?**  
V: Igen – iteráljon a karakterlánclistán, hívja meg a `Geometry.FromText`-et minden elemre, és tárolja az eredményeket egy `List<IGeometry>`-ben.

**K: Az Aspose.GIS megőrzi a Z‑értékeket konvertáláskor?**  
V: Teljesen. Ha a WKT Z koordinátát tartalmaz (ahogy a példában is látható), a kapott geometria megőrzi ezeket az értékeket.

**K: Lehetséges a geometria visszaexportálása WKT‑be a manipuláció után?**  
V: Használja a `ToText()` metódust bármely `IGeometry` példányon a WKT reprezentáció lekéréséhez.

---

**Legutóbb frissítve:** 2025-12-23  
**Tesztelve a következővel:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
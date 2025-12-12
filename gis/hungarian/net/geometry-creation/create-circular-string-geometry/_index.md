---
date: 2025-12-12
description: Tanulja meg, hogyan hozhat létre vektor réteget, és adhat hozzá kör alakú
  vonal geometriát az Aspose.GIS for .NET használatával – egy gyors mód a GIS‑alkalmazások
  építéséhez.
linktitle: Create Circular String Geometry
second_title: Aspose.GIS .NET API
title: Vektor réteg és körív létrehozása az Aspose.GIS for .NET-ben
url: /hu/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektor réteg és körkörös vonal geometria létrehozása az Aspose.GIS for .NET segítségével

## Introduction
Ha .NET platformon GIS alkalmazást építesz, az első lépés gyakran **vektor réteg** objektumok létrehozása, amelyek tárolják a térbeli elemeket. Az Aspose.GIS for .NET egyszerűvé teszi ezt a folyamatot, és lehetővé teszi, hogy ezeket a rétegeket fejlett geometriákkal, például körkörös vonalakkal gazdagítsd. Ebben az útmutatóban pontosan megtanulod, hogyan hozhatsz létre egy vektor réteget, hogyan adhatod hozzá a körkörös vonal geometriát, és hogyan mentheted az eredményt Shapefile‑ként – mindezt tiszta, termelésre kész C# kóddal.

## Quick Answers
- **Mi jelentése a „vektor réteg létrehozása”?** Új tárolót (réteget) hoz létre, amely térbeli elemeket, például pontokat, vonalakat vagy poligonokat képes tárolni.  
- **Melyik osztály képviseli a körkörös vonalat?** `CircularString` a `Aspose.Gis.Geometries`‑ből.  
- **Menthetem a réteget Shapefile‑ként?** Igen – a réteg létrehozásakor használd a `Drivers.Shapefile`‑t.  
- **Szükségem van licencre a fejlesztéshez?** Ideiglenes licenc elegendő értékeléshez; teljes licenc szükséges a termeléshez.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is “create vector layer”?
A vektor réteg a vektor elemek (pontok, vonalak, poligonok) logikai csoportosítása, amely egyetlen adatforrásban van tárolva. Az Aspose.GIS‑ben a réteget a `VectorLayer.Create` hívásával hozod létre, megadva a célfájl útvonalát és a kívánt drivert (pl. Shapefile). Miután a réteg létezik, hozzáadhatsz elemeket, hozzárendelhetsz geometriákat, és végrehajthatsz térbeli műveleteket.

## Why add a circular string?
A körkörös vonalak egy **lineáris geometria** típus, amely íveket közelít pontsorozattal. Hasznosak görbe utak, folyó kanyarok vagy bármely olyan elem ábrázolásához, ahol sima görbére van szükség sok kis vonal szegmens helyett.

## Prerequisites
Before you start, make sure you have:

- **.NET Framework vagy .NET Core** telepítve a gépeden.  
- **Aspose.GIS for .NET** könyvtár – töltsd le a hivatalos oldalról **[here](https://releases.aspose.com/gis/net/)**.  
- Egy IDE, például **Visual Studio** vagy **JetBrains Rider**.  
- Alapvető ismeretek a **C#** programozásban.

## Import Namespaces
Add the required namespaces to your C# file:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step‑by‑Step Guide

### Step 1: Define the output file path
Set the location where the Shapefile will be written.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

Replace `"Your Document Directory"` with the actual folder path on your system.

### Step 2: **Create vector layer**
Open a `VectorLayer` using the `Create` method. This is the core of the **create vector layer** operation.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### Step 3: Construct a new feature
A feature represents a single spatial record inside the layer.

```csharp
    var feature = layer.ConstructFeature();
```

### Step 4: Build the circular string geometry
Add that define the curved shape. The sequence of points creates an arc that starts and ends at the same location, forming a closed circular string.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### Step 5: Assign geometry and add the feature to the layer
Link the geometry to the feature and store it in the layer.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

When the `using` block ends, the layer is automatically flushed to the Shapefile on disk.

## Common Issues & Solutions
| Probléma | Megoldás |
|----------|----------|
| **Érvénytelen fájlútvonal** | Győződj meg arról, hogy a könyvtár létezik, és van írási jogosultságod. |
| **CircularString egyenes vonalként jelenik meg** | Ellenőrizd, hogy a pontok a megfelelő sorrendben vannak hozzáadva; az első és az utolsó pontnak azonosnak kell lennie egy zárt alakhoz. |
| **Licenckivétel** | Alkalmazz ideiglenes licencet fejlesztés közben, vagy vásárolj teljes licencet a termeléshez. |

## Frequently Asked Questions

### Is Aspose.GIS for .NET compatible with all versions of the .NET Framework?
Igen, az Aspose.GIS for .NET úgy van tervezve, hogy széles körű .NET verziókkal működjön, a Framework 4.5‑től a legújabb .NET 8 kiadásokig.

### Can I integrate Aspose.GIS for .NET with other GIS libraries?
Természetesen! Olvashatsz adatokat más könyvtárakkal, manipulálhatod őket az Aspose.GIS‑szel, majd visszaírhatod, köszönhetően a rugalmas API‑nak.

### Does Aspose.GIS for .NET support spatial data visualization?
Igen, a könyvtár tartalmaz renderelési segédeszközöket, amelyek lehetővé teszik térképek és a geometriák vizuális ábrázolásának létrehozását.

### Is there a community forum where I can seek assistance with Aspose.GIS for .NET?
Igen, felkeresheted az Aspose.GIS fórumot **[here](https://forum.aspose.com/c/gis/33)**, hogy kérdéseket tegyél fel és tapasztalatokat ossz meg.

### Can I obtain a temporary license to evaluate Aspose.GIS for .NET?
Természetesen! Ideiglenes értékelő licenc elérhető **[here](https://purchase.aspose.com/temporary-license/)**.

### How do I add more complex geometries (e.g., MultiLineString) to the same layer?
Hozd létre a megfelelő geometria objektumot (pl. `MultiLineString`), töltsd fel egyedi `LineString` objektumokkal, rendeld hozzá a `feature.Geometry`‑hez, és add hozzá az elemet ugyanúgy, ahogy a körkörös vonallal tettük.

## Conclusion
Ezeknek a lépéseknek a követésével most már tudod, hogyan **hozz létre vektor réteg** objektumokat, és hogyan gazdagítsd őket körkörös vonal geometriával az Aspose.GIS for .NET segítségével. Ez az alap lehetővé teszi, hogy gazdagabb GIS megoldásokat építs – legyen szó közlekedési hálózatok térképezéséről, környezeti adatok vizualizálásáról vagy egyedi térbeli elemző eszközök fejlesztéséről.

---

**Last Updated:** 2025-12-12  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
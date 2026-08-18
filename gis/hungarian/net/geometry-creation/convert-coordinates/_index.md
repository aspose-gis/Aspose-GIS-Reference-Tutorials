---
date: 2026-08-18
description: Konvertálja a decimal degrees-t dms-re az Aspose.GIS for .NET használatával.
  Ez a lépésről‑lépésre C# útmutató bemutatja, hogyan konvertálja a latitude/longitude,
  decimal degrees-t dms-re és egyebeket.
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: Koordináták konvertálása
og_description: A decimal degrees dms-re konvertálása egyszerű az Aspose.GIS for .NET
  segítségével. Tanulja meg, hogyan alakítsa át a latitude‑longitude értékeket DMS
  formátumba percben.
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: decimal degrees konvertálása dms-re az Aspose.GIS for .NET segítségével
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  headline: How to convert decimal degrees to dms with Aspose.GIS for .NET
  type: TechArticle
- description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  name: How to convert decimal degrees to dms with Aspose.GIS for .NET
  steps:
  - name: start the conversion process
    text: We print a friendly message so you know the demo has begun.
  - name: convert to decimal degrees
    text: Even though the final goal is DMS, we start by showing the original decimal
      representation. This also demonstrates the **decimal degrees to dms** path you’ll
      later follow.
  - name: convert to degree decimal minutes
    text: This format (`DD°MM.m'`) is a common intermediate step when you need to
      **convert lat long degree minutes**.
  - name: convert to degree minutes seconds (dms)
    text: Here’s the core of our tutorial—**convert coordinates to dms**.
  - name: convert to GeoRef
    text: For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing
      workflows.
  type: HowTo
- questions:
  - answer: Aspose.GIS primarily targets .NET developers, but a Java version is also
      available.
    question: Is Aspose.GIS compatible with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.GIS before purchasing?
  - answer: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  - answer: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert coordinates
- Aspose.GIS
- .NET GIS processing
title: Hogyan konvertáljuk a decimal degrees-t dms-re az Aspose.GIS for .NET segítségével
url: /hu/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan konvertáljuk a decimális fokokat dms-re az Aspose.GIS segítségével

## Bevezetés
Ebben az oktatóanyagról megtanulja **hogyan konvertálja a decimális fokokat dms-re** a hatékony Aspose.GIS .NET könyvtár segítségével. Akár **c# convert lat long**-ra van szüksége, jelentésekhez ember által olvasható helyszín karakterláncokat generál, vagy egyszerűen különböző koordinátaformátumokat szeretne felfedezni, ez az útmutató minden lépésen végigvezet, világos magyarázatokkal és azonnal futtatható C# kódrészletekkel.

## Gyors válaszok
- **Mit jelent a “convert coordinates to dms”?** Átalakítja a numerikus szélességi/hosszúsági értékeket a hagyományos fok‑perc‑másodperc jelölésbe.  
- **Melyik könyvtár kezeli a konverziót?** Aspose.GIS for .NET biztosítja a `GeoConvert` osztályt beépített formátumtámogatással.  
- **Szükségem van licencre a kipróbáláshoz?** Egy ingyenes próba elérhető; kereskedelmi licenc szükséges a termelésben való használathoz.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, és .NET 5/6+.  
- **Használhatom ugyanazt a kódot más formátumokhoz?** Igen — egyszerűen módosítsa a `PointFormats` enum értékét (pl. `DecimalDegrees`, `GeoRef`).  

## Mi a koordináta konverzió dms-re?
A koordináták DMS-re konvertálása átírja a decimális szélességi és hosszúsági értékeket egy olyan formátumba, mint `25°30'00"N 45°30'00"E`. A folyamat minden decimális fokot felbont egész fokokra, percekre (a fok egy hatvanad része) és másodpercekre (a perc egy hatvanad része), majd hozzáfűzi a megfelelő félgömb jelzőt (N, S, E, W). Ez az ember által olvasható forma elengedhetetlen sok örökölt adatbázis számára, és a pontos helyek közlését teszi lehetővé a decimális jelölés nélkül.

## Miért használjuk az Aspose.GIS-t a koordináta konverzióhoz?
Az Aspose.GIS **50+ bemeneti és kimeneti formátumot** támogat, és képes több száz oldalas GIS fájlok feldolgozására anélkül, hogy a teljes adathalmazt a memóriába töltené. Az API alulmilliméteres pontosságot biztosít szélsőséges esetekben, például negatív értékek és félgömb jelölők kezelésekor, és következetesen fut Windows, Linux és macOS .NET környezetekben.

## Előfeltételek
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

1. **Alapvető C# ismeretek** — változók, metódushívások és konzol kimenet ismerete.  
2. **Aspose.GIS telepítve** — töltse le a legújabb csomagot az [Aspose.GIS weboldal](https://releases.aspose.com/gis/net/)ról. A fő Aspose kiadások oldalát is felfedezheti a [Aspose kiadások weboldala](https://releases.aspose.com/) alatt.  

## Névterek importálása
Először importálja a GIS műveletekhez szükséges névtereket:

Import Namespaces placeholder remains unchanged.

## Lépésről‑lépésre útmutató

### Mi a GeoConvert osztály?
A `GeoConvert` osztály statikus metódusokat biztosít a koordinátaformátumok közötti átalakításhoz, például decimális fokok, DMS és GeoRef között. Elfogad nyers numerikus értékeket vagy `Point` objektumokat, és formázott karakterláncokat vagy új `Point` példányokat ad vissza. A negatív koordináták és a kerekítés kezelése révén az osztály garantálja, hogy a kimenet megfeleljen a szabványos GIS specifikációknak, megkönnyítve a beillesztést bármely .NET térképező alkalmazásba.

### 1. lépés: a konverziós folyamat elindítása
Barátságos üzenetet írunk ki, hogy tudja, a demó elkezdődött.

```csharp
using System;
using Aspose.Gis;
```

### 2. lépés: konvertálás decimális fokokra
Bár a végső cél a DMS, először az eredeti decimális ábrázolást mutatjuk be. Ez egyben bemutatja a **decimal degrees to dms** útvonalat, amelyet később követni fog.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### 3. lépés: konvertálás fok‑decimális percekre
Ez a formátum (`DD°MM.m'`) gyakori köztes lépés, amikor **convert lat long degree minutes**‑ra van szükség.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### 4. lépés: konvertálás fok perc másodperc (dms) formátumba
Itt van a tutorialunk középpontja — **convert coordinates to dms**.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### 5. lépés: konvertálás GeoRef formátumba
A teljesség kedvéért bemutatjuk a `GeoRef` formátumot is, amely hasznos a távérzékelési munkafolyamatokban.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## Gyakori problémák és megoldások
- **Helytelen félgömb betűk** — győződjön meg róla, hogy az északi/keleti értékek pozitívak, a déli/nyugati értékek negatívak; az API automatikusan hozzáadja a megfelelő utótagot.  
- **Váratlanul üres kimenet** — ellenőrizze, hogy a `Aspose.Gis` assembly helyesen hivatkozott‑e, és hogy a projekt egy támogatott .NET verziót céloz‑e.  
- **Licenc nem található** — helyezze a licencfájlt az alkalmazás gyökérkönyvtárába, vagy állítsa be programozottan a `License license = new License(); license.SetLicense("Aspose.GIS.lic");` kóddal.  

## Gyakran feltett kérdések

**Q: Az Aspose.GIS kompatibilis más programozási nyelvekkel?**  
A: Az Aspose.GIS elsősorban .NET fejlesztőknek készült, de egy Java verzió is elérhető.

**Q: Kipróbálhatom az Aspose.GIS‑t vásárlás előtt?**  
A: Igen, ingyenes próba hozzáférhető az [weboldalon](https://releases.aspose.com/).

**Q: Hogyan kaphatok támogatást az Aspose.GIS‑hez?**  
A: Segítséget kérhet az Aspose.GIS közösségi fórumon [itt](https://forum.aspose.com/c/gis/33).

**Q: Elérhetők ideiglenes licencek az Aspose.GIS‑hez?**  
A: Igen, ideiglenes licenceket a [temporary license page](https://purchase.aspose.com/temporary-license/) oldalon szerezhet.

**Q: Hol vásárolhatom meg az Aspose.GIS‑t?**  
A: Az Aspose.GIS megvásárolható a [purchase page](https://purchase.aspose.com/buy) oldalon.

## Összegzés
E lépések követésével most már tudja, **hogyan konvertálja a decimális fokokat dms-re** és más gyakori GIS formátumokra az Aspose.GIS for .NET segítségével. Ez a képesség lehetővé teszi, hogy ember által olvasható helyszín karakterláncokat integráljon térképező alkalmazásokba, jelentésekbe vagy bármely térbeli adatfolyamatba. Nyugodtan kísérletezzen különböző szélességi/hosszúsági értékekkel, és fedezze fel a `GeoConvert` osztály által kínált további formátumokat.

---

**Last Updated:** 2026-08-18  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Kapcsolódó oktatóanyagok

- [Hogyan hozhatunk létre pontgeometriát és kérhetjük le a geometria típusát az Aspose.GIS for .NET‑el](/gis/net/geometry-analysis/get-geometry-type/)
- [Hogyan konvertáljuk a GeoJSON‑t – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [MultiPoint geometria létrehozása .NET‑ben az Aspose.GIS‑sel](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2025-12-06
description: Ismerje meg, hogyan konvertálhatja a GeoJSON-t TopoJSON-re csoportosítással,
  állíthatja be az objektum név attribútumát, és csoportosíthatja a GeoJSON elemeket
  az Aspose.GIS for .NET használatával.
language: hu
linktitle: How to Convert GeoJSON to TopoJSON with Grouping using Aspose.GIS
second_title: Aspose.GIS .NET API
title: Hogyan konvertáljunk GeoJSON-t TopoJSON-re csoportosítással az Aspose.GIS segítségével
url: /net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Convert GeoJSON to TopoJSON with Grouping using Aspose.GIS

## Bevezetés

Ebben a lépésről‑lépésre útmutatóban megtanulja, **hogyan konvertálja a GeoJSON** fájlokat TopoJSON-re, miközben a jellemzőket egy kiválasztott attribútum alapján csoportosítja. Az Aspose.GIS .NET API használata gyors, megbízható és teljesen vezérelhető C# kódból. Akár ASP.NET GeoJSON konverziós szolgáltatást, akár asztali GIS eszközt épít, ez az útmutató pontosan megmutatja, mit kell tennie.

## Gyors válaszok
- **Melyik könyvtár kezeli a konverziót?** Aspose.GIS for .NET  
- **Mennyi időt vesz igénybe a megvalósítás?** Általában 5‑10 perc egy alap beállításhoz  
- **Szükség van licencre a termeléshez?** Igen, kereskedelmi licenc szükséges (ingyenes próba elérhető)  
- **Csoportosíthatok jellemzőket bármely attribútum szerint?** Igen – állítsa be a `ObjectNameAttribute`-ot arra a mezőre, amely szerint csoportosítani szeretne  
- **Támogatott a .NET Core?** Teljesen – az API működik .NET Core, .NET 5/6 és a klasszikus .NET Framework esetén  

## Mi az a GeoJSON és TopoJSON?

A GeoJSON egy széles körben használt JSON formátum a földrajzi jellemzők, például pontok, vonalak és poligonok kódolására. A TopoJSON a GeoJSON-t kiterjeszti a topológia (megosztott vonalszakaszok) tárolásával, ami csökkenti a fájlméretet és javítja a renderelési teljesítményt összetett térképek esetén. A kettő közötti konvertálás gyakori lépés, ha kompakt térképadatokat kell webes vizualizációkhoz használni.

## Miért csoportosítsuk a GeoJSON jellemzőket?

A csoportosítás (`group geojson features`) lehetővé teszi, hogy a kapcsolódó geometriákat egyetlen elnevezett objektumban szervezze a létrejövő TopoJSON-ben. Ez különösen hasznos, ha:
- Külön rétegeket szeretne létrehozni különböző közigazgatási területekhez.  
- A front‑end térképkönyvtára elnevezett objektumokat vár a stílushoz vagy interakcióhoz.  
- Csökkentenie kell a duplikációt azáltal, hogy a szomszédos jellemzők határait megosztja.  

## Előfeltételek

Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik a következő előfeltételekkel:

1. **Aspose.GIS for .NET** – töltse le és telepítse a hivatalos oldalról [itt](https://releases.aspose.com/gis/net/).  
2. **Fejlesztői környezet** – Visual Studio, Visual Studio Code vagy bármely IDE, amely támogatja a C#-ot.  
3. **Minta GeoJSON fájl** – egy fájl, amely a konvertálni kívánt jellemzőket tartalmazza.  

## Névterek importálása

Először adja hozzá a szükséges névtereket a projektjéhez:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```

## Lépésről‑lépésre útmutató

### 1. lépés: Fájlútvonalak meghatározása

Adja meg, hogy hol található a forrás GeoJSON, és hová kell írni a TopoJSON-t:

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

> **Pro tipp:** Használja a `Path.Combine`-t a platformok közötti útvonalépítéshez, ha .NET Core-t céloz.

### 2. lépés: Konverziós beállítások konfigurálása (Object Name Attribute beállítása)

Hozzon létre egy `ConversionOptions` példányt, és adja meg az Aspose.GIS-nek, hogyan csoportosítsa a jellemzőket:

```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // Specify the attribute in GeoJSON layer by which we are going to group into objects
        ObjectNameAttribute = "group",
        // Specify the default object name for features with unknown attribute values
        DefaultObjectName = "unnamed",
    }
};
```

Cserélje le a `"group"`-ot a GeoJSON-jában lévő tényleges mezőnevére, amelyet **geojson jellemzők csoportosításához** szeretne használni. A `DefaultObjectName` biztosítja, hogy minden jellemző egy TopoJSON objektumba kerüljön, még akkor is, ha az attribútum hiányzik.

### 3. lépés: A konverzió végrehajtása (GeoJSON konvertálása TopoJSON-re)

Hajtsa végre a konverziót egyetlen API hívással:

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

A végrehajtás után a `convertedSampleWithGrouping_out.topojson` tartalmazni fogja a TopoJSON ábrázolást, a jellemzők a megadott attribútum szerint csoportosítva.

## Gyakori problémák és hibaelhárítás

| Tünet | Valószínű ok | Javítás |
|---------|--------------|-----|
| **Minden jellemző az „unnamed” név alatt jelenik meg** | `ObjectNameAttribute` nem egyezik a GeoJSON bármelyik tulajdonságával | Ellenőrizze a pontos tulajdonságnevet (kis‑nagybetű érzékeny) és frissítse a beállítást |
| **A kimeneti fájl üres** | Helytelen fájlútvonal vagy hiányzó olvasási jogosultság | Használjon abszolút útvonalakat, vagy biztosítsa, hogy az alkalmazásnak van fájlrendszer hozzáférése |
| **A konverzió `NotSupportedException`-t dob** | Megpróbál egy olyan GeoJSON-t konvertálni, amely nem támogatott geometriai típusokat tartalmaz (pl. GeometryCollection) | Egyszerűsítse a forrásadatokat, vagy frissítse a legújabb Aspose.GIS verzióra |

## Gyakran feltett kérdések

**Q: Csoportosíthatok jellemzőket több attribútum alapján?**  
A: Igen, több mezőt összefűzhet egyetlen virtuális attribútumba, vagy több konverziós lépést futtathat különböző `ObjectNameAttribute` értékekkel.

**Q: Az Aspose.GIS kompatibilis az ASP.NET Core-val?**  
A: Teljesen – a könyvtár működik ASP.NET Core, .NET 5, .NET 6 és a klasszikus .NET Framework esetén.

**Q: Konvertálhatok más földrajzi formátumokat is a Geo kívül?**  
A: Igen, az Aspose.GIS támogatja a Shapefile, KML, GML, CSV és még sok más formátumot, mind import, mind export esetén.

**Q: Az Aspose.GIS kínál ingyenes próbaverziót?**  
A: Igen, ingyenes próbaverziót szerezhet az Aspose.GIS-ből [itt](https://releases.aspose.com/).

**Q: Hol kaphatok támogatást az Aspose.GIS-hez?**  
A: Támogatást kaphat az Aspose.GIS közösségi fórumon [itt](https://forum.aspose.com/c/gis/33).

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Utoljára frissítve:** 2025-12-06  
**Tesztelve:** Aspose.GIS for .NET (legújabb kiadás)  
**Szerző:** Aspose  

---
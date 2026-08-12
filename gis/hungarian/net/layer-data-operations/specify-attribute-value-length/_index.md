---
date: 2026-05-16
description: Vektor réteg példa, amely bemutatja, hogyan állítsuk be a mező szélességét,
  definiáljuk az attribútum szélességét, és adjuk hozzá az attribútum hosszát az Aspose.GIS
  for .NET-ben – egy teljes lépésről‑lépésre útmutató.
keywords:
- vector layer example
- how to set width
- set field width
- define attribute width
- add attribute length
linktitle: Hogyan állítsuk be a mező szélességét
schemas:
- author: Aspose
  dateModified: '2026-05-16'
  description: Vector layer example showing how to set field width, define attribute
    width, and add attribute length in Aspose.GIS for .NET – a complete step‑by‑step
    guide.
  headline: Vector Layer Example – How to Set Field Width in Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for peer‑to‑peer
      help and official responses.
    question: Where can I find community support for Aspose.GIS for .NET?
  - answer: Yes, explore the [free trial](https://releases.aspose.com/) to experience
      the full feature set without cost.
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Purchase your license [here](https://purchase.aspose.com/buy).
    question: How do I purchase a license for Aspose.GIS for .NET?
  - answer: Refer to the [documentation](https://reference.aspose.com/gis/net/) for
      comprehensive API details.
    question: Where can I access the documentation for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Vektor réteg példa – Hogyan állítsuk be a mező szélességét az Aspose.GIS for
  .NET-ben
url: /hu/net/layer-data-operations/specify-attribute-value-length/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektorréteg példa – Hogyan állítsuk be a mező szélességét az Aspose.GIS for .NET-ben

Ebben a **vektorréteg példában** megtanulja, hogyan állítsa be egy attribútum mező szélességét Shapefile létrehozásakor az Aspose.GIS for .NET használatával. Lépésről lépésre végigvezetjük a folyamatot, a névterek importálásától a jellemző hozzáadásáig, és elmagyarázzuk, miért fontos az attribútum hosszának szabályozása az adat integritás és más GIS eszközökkel való interoperabilitás szempontjából.

## Gyors válaszok
- **Mi a fő célja ennek az útmutatónak?** Az, hogy megmutassa, hogyan állítsa be a mező szélességét egy attribútumhoz egy shapefile-ban az Aspose.GIS for .NET használatával.  
- **Melyik osztály határozza meg a mező szélességét?** `FeatureAttribute.Width`.  
- **Szükségem van licencre a kód futtatásához?** Egy ideiglenes licenc elegendő értékeléshez; a teljes licenc szükséges a termeléshez.  
- **Milyen fájlformátumot használ a példa?** ESRI Shapefile (`.shp`).  
- **Módosíthatom a szélességet a réteg létrehozása után?** Nem – a szélességet a jellemzők hozzáadása előtt kell definiálni.

## Mi a mező szélessége és miért fontos?
A mező szélessége (más néven attribútumhossz) a maximális karakterek száma, amelyet egy karakterlánc mező tárolhat egy Shapefile DBF komponensében. A megfelelő szélesség beállítása megakadályozza a csendes levágást, garantálja, hogy más GIS alkalmazások pontosan úgy olvassák az adatot, ahogy azt beírták, és előre láthatóvá teszi a fájlméretet – minden egyes extra karakter egy bájtot ad hozzá rekordonként.

## Előfeltételek
- **Aspose.GIS for .NET Library** – letöltés a [download link](https://releases.aspose.com/gis/net/) címről.  
- **Development Environment** – Visual Studio 2022, Visual Studio Code vagy bármely IDE, amely támogatja a .NET 6+.  
- **Write Access** – egy mappa a lemezen, ahová a generált shapefile mentésre kerül.

## Miért használjunk vektorréteg példát meghatározott szélességgel?
Az Aspose.GIS **több mint 30 GIS fájlformátumot** támogat, többek között a Shapefile, GeoJSON, KML és GML formátumokat. Ha kifejezetten beállítja a mező szélességét, elkerüli az alapértelmezett 255 karakteres korlátot, amely feleslegesen megnövelheti a `.dbf` fájlt akár 255 × rekordszám bájttal. Nagy adathalmazok esetén ez jelentős tárhelymegtakarítást eredményez.

## Hogyan állítsuk be egy attribútum mező szélességét?
Ebben a szakaszban betöltünk vagy létrehozunk egy `VectorLayer`-t, amely a cél `.shp` fájlra mutat, definiálunk egy karakterlánc attribútumot pontos szélességgel, majd hozzáadunk jellemzőket – mindezt néhány tömör utasítással. A `VectorLayer` egy vektor adatkészletet, például egy Shapefile-t képvisel, és hozzáférést biztosít a geometriához és az attribútumtáblához. Az alábbiakban közvetlen, lépésről‑lépésre követhető receptet talál.

Betöltünk vagy létrehozunk egy `VectorLayer`-t, amely a cél `.shp` fájlra mutat, deklarálunk egy **wide** nevű karakterlánc attribútumot `Width = 120` értékkel, majd hozzáadunk egy jellemzőt, amelynek értéke betartja a 120 karakteres korlátot. Az Aspose.GIS automatikusan levágja a hosszabb karakterláncokat a meghatározott szélességre, megőrizve az adatkonzisztenciát anélkül, hogy kivételeket dobna.

### Névterek importálása
`FeatureAttribute`, `VectorLayer` és a kapcsolódó típusok az `Aspose.Gis` névtérben találhatók. Importálja őket a fájl tetején:

Az `Aspose.Gis` névtér biztosítja a fő GIS objektumokat, például a `VectorLayer`, `Feature` és `FeatureAttribute` osztályokat. Az importálás lehetővé teszi, hogy a osztályok teljesen kvalifikált név nélkül legyenek elérhetők.

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### VectorLayer létrehozása
`VectorLayer` osztály egy vektor adatforrást (pl. Shapefile) képvisel. Ez a tároló, amely a jellemzőket és azok attribútumait tartalmazza.

A `VectorLayer` osztály az Aspose.GIS vektor adatkészletének reprezentációja, amely memóriában kezeli a geometriát és az attribútumtáblákat. Hozzon létre egy példányt, amely egy új vagy meglévő `.shp` fájlra mutat.

```csharp
string dataDir = "Your Document Directory";
using (VectorLayer layer = VectorLayer.Create(dataDir + "SpecifyAttributeValueLength_out.shp", Drivers.Shapefile))
{
    // Your code for the next steps will go here.
}
```

### Attribútum hozzáadása meghatározott hosszúsággal
Definiáljon egy **wide** nevű karakterlánc attribútumot, és állítsa be a `Width` tulajdonságát 120 karakterre. Ez a **vektorréteg példa** központi lépése.

A `FeatureAttribute` objektum egy oszlopot ír le az attribútumtáblában; a `Width = 120` beállítása azt mondja a Shapefile írójának, hogy pontosan 120 bájtot foglaljon le ennek a mezőnek minden rekordjához.

```csharp
FeatureAttribute attribute = new FeatureAttribute("wide", AttributeDataType.String);
attribute.Width = 120;
layer.Attributes.Add(attribute);
```

> **Pro tipp:** A `Width` tulajdonság csak karakterlánc attribútumokra vonatkozik. Numerikus, dátum vagy Boolean mezők figyelmen kívül hagyják a `Width`-et, mivel méretük a adattípus által rögzített.

### Jellemző létrehozása és hozzáadása
Hozzon létre egy `Feature`-t, rendelje hozzá azt az értéket, amely belefér a 120 karakteres korlátba, és adja hozzá a réteghez. Ha a karakterlánc meghaladja a korlátot, az Aspose.GIS csendben levágja a meghatározott szélességre, megőrizve az adat integritását.

A `Feature` osztály magába foglalja a geometriát és az attribútum értékeket; az attribútum beállítása után a `layer.Add(feature)` hívás írja a rekordot a Shapefile-ba.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("wide", "this string can be up to 120 characters long now.");
layer.Add(feature);
```

Ha megpróbál egy hosszabb karakterláncot hozzárendelni, az Aspose.GIS levágja azt a meghatározott szélességre, megőrizve az adat integritását.

## Gyakori buktatók és hibaelhárítás
- **Elfelejtette beállítani a `Width`-et az attribútum hozzáadása előtt?** Az alapértelmezett szélesség 255 karakter; későbbi módosítás nem érinti a már létrehozott mezőket. Mindig először definiálja a szélességet.  
- **Nem karakterlánc adattípust használ?** `Width` figyelmen kívül marad numerikus vagy dátum mezőknél; győződjön meg arról, hogy az attribútum `AttributeDataType` értéke `String`.  
- **„Field not found” hiba?** Az attribútum nevek kis‑ és nagybetű érzékenyek. Ellenőrizze, hogy a `SetValue`‑ben használt név pontosan megegyezik a sémában definiált névvel.  
- **Váratlan fájlméret-növekedés?** A nagyobb szélességek lineárisan növelik a `.dbf` méretét. 10 000 rekord esetén a szélesség 50‑ről 120‑ra történő növelése körülbelül 700 KB-ot ad hozzá.

## Gyakran Ismételt Kérdések
**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.GIS for .NET-hez?**  
A: Ideiglenes licencet szerezhet [itt](https://purchase.aspose.com/temporary-license/).

**Q: Hol találhat közösségi támogatást az Aspose.GIS for .NET-hez?**  
A: Látogassa meg a [Aspose.GIS fórumot](https://forum.aspose.com/c/gis/33) a felhasználók közötti segítségért és hivatalos válaszokért.

**Q: Elérhető ingyenes próba az Aspose.GIS for .NET-hez?**  
A: Igen, tekintse meg az [ingyenes próbát](https://releases.aspose.com/), hogy költség nélkül megtapasztalja a teljes funkciókészletet.

**Q: Hogyan vásárolhatok licencet az Aspose.GIS for .NET-hez?**  
A: Vásárolja meg licencét [itt](https://purchase.aspose.com/buy).

**Q: Hol érhető el az Aspose.GIS for .NET dokumentációja?**  
A: Tekintse meg a [dokumentációt](https://reference.aspose.com/gis/net/), amely átfogó API részleteket tartalmaz.

**Q: Megváltoztathatom a mező szélességét a réteg létrehozása után?**  
A: Nem. A mező szélességét a attribútum hozzáadása előtt kell definiálni; módosításhoz újra kell létrehozni a réteget az új sémával.

**Q: Befolyásolja a nagyobb szélesség beállítása a fájlméretet?**  
A: A Shapefile-ok a karakterlánc mezőket rögzített hosszúsággal tárolják, így a szélesség növelése közvetlenül megnöveli a `.dbf` fájl méretét a rekordok számával arányosan.

## Következtetés
Ez a **vektorréteg példa** bemutatta, hogyan állítsuk be egy attribútum mező szélességét egy Shapefile-ban az Aspose.GIS for .NET használatával, és hatékonyan hogyan adjunk hozzá egy meghatározott hosszúságú attribútumot. Az attribútum szélesség szabályozásával elkerülheti az adatlevágást, optimális fájlméretet tart, és biztosíthatja a zökkenőmentes interoperabilitást más GIS platformokkal. Kísérletezzen különböző szélességekkel, fedezze fel a [dokumentációt](https://reference.aspose.com/gis/net/), és nyissa ki a térinformatikai fejlesztés teljes potenciálját az Aspose.GIS-szel.

---

**Utoljára frissítve:** 2026-05-16  
**Tesztelve a következővel:** Aspose.GIS 24.11 for .NET  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó oktatóanyagok

- [Réteg attribútumok lekérése – Réteg attribútum információk megszerzése az Aspose.GIS for .NET használatával](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Hogyan szerezzük meg az attribútum értékét (alapértelmezett) az Aspose.GIS for .NET használatával](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [Vektorréteg létrehozása File GDB-ben – Aspose.GIS .NET oktatóanyag](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
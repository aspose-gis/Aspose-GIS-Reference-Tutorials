---
description: Tanulja meg, hogyan használja a dinamikus típuskonverziót az Aspose.GIS
  for .NET-ben a shapefile attribútumértékeinek lekéréséhez. Tartalmazza a kifejezett
  típuskonverzió példáit.
linktitle: Get Feature Attribute Value using Dynamic Type Casting
second_title: Aspose.GIS .NET API
title: Jellemző attribútumérték lekérése dinamikus típuskonverzióval
url: /hu/net/layer-interaction-and-data-access/get-feature-attribute-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dinamikus típuskonverzióval történő attribútumérték lekérése

## Bevezetés
Üdvözöljük az Aspose.GIS for .NET világában, egy erőteljes könyvtárban, amely lehetővé teszi a .NET fejlesztők számára a földrajzi információs rendszer (GIS) adatok zökkenőmentes kezelését. Ebben a bemutatóban megismeri, hogyan egyszerűsíti a **dinamikus típuskonverzió** a shapefile attribútumértékeinek lekérését, miközben áttekintjük a klasszikus **explicit típuskonverzió** módszert is. Akár shapefile‑t olvas egy .NET alkalmazásban, akár **attribútumértékeket** szeretne lekérni elemzésekhez, ezek a technikák tisztábbá és rugalmasabbá teszik a kódot.

## Gyors válaszok
- **Mi az a dinamikus típuskonverzió?** Egy futásidejű módja az attribútumértékek lekérésének, anélkül, hogy előre megadná a cél típust.  
- **Miért használjam az Aspose.GIS‑t?** Egységes API‑t biztosít a shapefile‑t .NET‑ben olvasáshoz, és támogatja mindkét konverziós módszert.  
- **Szükségem van licencre?** Elérhető egy ingyenes próba; a termeléshez kereskedelmi licenc szükséges.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 és későbbi verziók.  
- **Lekérhetem az attribútumértékeket nagy fájlokból?** Igen – a példákban látható módon hatékonyan iterálhat a feature-ökön.

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg róla, hogy a következő előfeltételek teljesülnek:
- Alapvető .NET fejlesztői ismeretek.  
- Visual Studio telepítve van a gépén.  
- Aspose.GIS for .NET könyvtár, amely letölthető a [letöltési linkről](https://releases.aspose.com/gis/net/).  
- GIS koncepciók és terminológia ismerete.

## Névtér importálása
A projekt elindításához importálja a szükséges névtereket. Ez a lépés elengedhetetlen az Aspose.GIS for .NET által nyújtott funkcionalitás eléréséhez. Adja hozzá a következő névtereket a kódjához:
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Dinamikus típuskonverzió használata attribútumértékek lekéréséhez
Az alábbi lépésről‑lépésre útmutató bemutatja, hogyan állítsa be a projektet, nyissa meg a shapefile‑t, és hogyan kérje le az attribútumértékeket **explicit típuskonverzióval** és **dinamikus típuskonverzióval** egyaránt.

### 1. lépés: Projekt beállítása
Hozzon létre egy új .NET projektet a Visual Studio‑ban, és hivatkozzon az Aspose.GIS könyvtárra.

### 2. lépés: Dokumentumkönyvtár meghatározása
Állítsa be a dokumentumok könyvtárának elérési útját. Itt található a shapefile (`InputShapeFile.shp`).
```csharp
string dataDir = "Your Document Directory";
```

### 3. lépés: Vektor réteg megnyitása
Nyissa meg a vektor réteget az Aspose.GIS‑szel. Ne felejtse el megadni a drivert, ebben az esetben a Shapefile drivert.
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the vector layer goes here
}
```

### 4. lépés: Feature attribútumértékek lekérése
Most iteráljon végig a réteg minden feature‑én, és kérje le az attribútumértékeket. Az Aspose.GIS többféle módot kínál az attribútumok lekérésére.

#### 1. eset: Explicit típuskonverzió
```csharp
for (int i = 0; i < layer.Count; i++)
{
    Feature feature = layer[i];
    Console.WriteLine("Entry {0} information\n ========================", i);
    string nameValue = feature.GetValue<string>("name"); // attribute name is case-sensitive
    int ageValue = feature.GetValue<int>("age");
    string dobValue = feature.GetValue<DateTime>("dob").ToString();
    Console.WriteLine("Attribute value for feature #{0} is: {1}, {2}", nameValue, ageValue, dobValue);
}
```

#### 2. eset: Dinamikus típuskonverzió
```csharp
for (int i = 0; i < layer.Count; i++)
{
    Feature feature = layer[i];
    Console.WriteLine("Entry {0} information\n ========================", i);
    var objName = feature.GetValue("name"); // attribute name is case-sensitive
    var objAge = feature.GetValue("age");
    var objDob = feature.GetValue("dob");
    Console.WriteLine("Attribute object for feature #{0} is: {1}, {2}", objName, objAge, objDob);
}
```

> **Pro tipp:** Használja a dinamikus típuskonverziót, ha nem biztos az attribútum pontos adattípusában, vagy ha általános kódot szeretne írni, amely több shapefile‑ra is működik. Váltson explicit típuskonverzióra, ha fordítási időben szeretne típusbiztonságot.

## Gyakori problémák és megoldások
- **Attribútumnév eltérés:** A GIS attribútumnevek kis‑ és nagybetű érzékenyek. Ellenőrizze a shapefile séma pontos írásmódját.  
- **Null értékek:** A `GetValue` `null`‑t ad vissza hiányzó attribútumok esetén; kezelje ezt megfelelően a `NullReferenceException` elkerülése érdekében.  
- **Nagy adathalmazok:** Használjon `foreach`‑t vagy lapozást a memóriafogyasztás csökkentéséhez.

## Gyakran feltett kérdések
### K: Az Aspose.GIS alkalmas kezdőknek és tapasztalt fejlesztőknek egyaránt?
V: Teljes mértékben! Az Aspose.GIS minden szintű fejlesztő számára kínál intuitív API‑t a GIS adatok manipulálásához.

### K: Használhatom az Aspose.GIS‑t kereskedelmi projektjeimben?
V: Igen, az Aspose.GIS kereskedelmi termék. A licencelési részleteket megtalálja a [vásárlási oldalon](https://purchase.aspose.com/buy).

### K: Elérhetők ideiglenes licencek teszteléshez?
V: Igen, ideiglenes licencet kérhet teszteléshez [innen](https://purchase.aspose.com/temporary-license/).

### K: Hol találok közösségi támogatást az Aspose.GIS‑hez?
V: Csatlakozzon a [Aspose.GIS fórumhoz](https://forum.aspose.com/c/gis/33), ahol segítséget kérhet és más felhasználókkal léphet kapcsolatba.

### K: Van ingyenes próba verziója az Aspose.GIS‑nek?
V: Természetesen! A funkciókat ingyenes próba letöltésével is kipróbálhatja [innen](https://releases.aspose.com/).

### K: Hogyan kérhetem le a shapefile attribútumértékeit anélkül, hogy ismerném a típusukat?
V: Használja a dinamikus típuskonverziót (`feature.GetValue("attributeName")`), amely `object`‑ként adja vissza az értéket, és futásidőben konvertálható.

### K: Olvashatok shapefile‑t .NET Core alkalmazásban?
V: Igen, az Aspose.GIS for .NET teljes mértékben támogatja a .NET Core‑t, a .NET 5‑öt és a későbbi verziókat.

## Összegzés
Gratulálunk! Sikeresen megtanulta, hogyan használja az Aspose.GIS for .NET‑et a feature attribútumértékek lekérésére **explicit típuskonverzióval** és **dinamikus típuskonverzióval** egyaránt. Ezek a technikák lehetővé teszik a shapefile attribútumadatok hatékony megszerzését, legyen szó asztali GIS eszköz fejlesztéséről vagy térbeli elemzések webszolgáltatásba való integrálásáról.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Utoljára frissítve:** 2026-01-05  
**Tesztelve:** Aspose.GIS for .NET (legújabb)  
**Szerző:** Aspose
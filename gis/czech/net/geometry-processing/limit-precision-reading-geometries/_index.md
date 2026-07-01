---
date: 2026-04-03
description: Naučte se, jak vytvořit vektorovou vrstvu a omezit přesnost při čtení
  geometrií pomocí Aspose.GIS pro .NET. Krok za krokem průvodce pro optimální práci
  s geoprostorovými daty.
keywords:
- create vector layer
- reduce shapefile size
- set precision model
linktitle: Omezení přesnosti čtení geometrie
second_title: Aspose.GIS .NET API
title: Vytvořte vektorovou vrstvu, omezte přesnost pomocí Aspose.GIS pro .NET
url: /cs/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte vektorovou vrstvu, omezte přesnost pomocí Aspose.GIS pro .NET

## Úvod
Při práci s geoprostorovými daty často potřebujete **vytvořit vektorovou vrstvu** objektů a rozhodnout, kolik desetinných míst souřadnicové podrobnosti skutečně potřebujete. Omezení přesnosti nejenže urychluje zpracování, ale může také **zmenšit velikost shapefile**, což zefektivňuje ukládání a přenos. V tomto tutoriálu vás provedeme vytvořením vektorové vrstvy, zápisem jednoduché bodové geometrie a následným načtením pomocí jak přesného, tak zaokrouhleného modelu přesnosti. Na konci pochopíte, jak **nastavit model přesnosti** tak, aby vyhovoval požadavkům na přesnost vaší aplikace.

## Rychlé odpovědi
- **Co znamená „omezit přesnost“?** Zaokrouhluje hodnoty souřadnic na definovaný počet desetinných míst.  
- **Proč nejprve vytvořit vektorovou vrstvu?** Vektorová vrstva je kontejner, který ukládá geometrie jako body, čáry a polygonu.  
- **Jaké modely přesnosti jsou k dispozici?** `PrecisionModel.Exact` (bez zaokrouhlení) a `PrecisionModel.Rounding(n)` (zaokrouhlit na *n* desetinných míst).  
- **Potřebuji licenci k vyzkoušení?** Bezplatná zkušební verze je k dispozici na stránce vydání.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core a .NET 5/6+.

## Proč omezit přesnost a jak to pomáhá?
- **Zvýšení výkonu** – Méně číslic znamená méně dat k parsování a serializaci.  
- **Menší soubory** – Zaokrouhlení souřadnic může výrazně zmenšit shapefile, zejména u velkých datových sad.  
- **Dostatečná přesnost** – Mnoho GIS analýz nevyžaduje submilimetrovou přesnost, takže zaokrouhlení na 2‑3 desetinná místa je často dostačující.

## Předpoklady
Než se pustíme do tohoto postupu, ujistěte se, že máte následující předpoklady:
1. **Instalace** – Knihovna Aspose.GIS pro .NET by měla být nainstalována ve vašem vývojovém prostředí. Pokud ne, můžete si ji stáhnout ze [stránky vydání](https://releases.aspose.com/gis/net/).
2. **Znalost .NET** – Základní znalost C# a .NET frameworku je nezbytná pro pochopení a implementaci poskytnutých ukázek kódu.
3. **Vývojové prostředí** – Je vyžadováno funkční .NET vývojové prostředí, například Visual Studio.
4. **Adresář dokumentů** – Mějte připravený adresář, kde můžete ukládat a přistupovat k shapefile vytvořenému během procesu.

## Importujte jmenné prostory
Než začneme implementovat funkci pro omezení přesnosti při čtení geometrií, ujistěme se, že importujeme potřebné jmenné prostory:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Jak vytvořit vektorovou vrstvu
Prvním krokem je **vytvořit vektorovou vrstvu**, která bude obsahovat naši geometrii. Tato vrstva bude uložena jako Shapefile, abychom ji později mohli otevřít s různými nastaveními přesnosti.
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Nastavení možností přesnosti
Dále musíme definovat možnosti pro čtení geometrií, specifikovat požadovaný model přesnosti. Můžeme začít s přesnou přesností:
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Čtení geometrií s přesnou přesností
Nyní otevřeme vektorovou vrstvu s uvedenými možnostmi a načteme geometrie s přesnou přesností:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Ořezání přesnosti
Pokud chceme omezit přesnost na konkrétní počet desetinných míst, můžeme model přesnosti upravit odpovídajícím způsobem:
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Jak nastavit model přesnosti pro různé scénáře
Možná se ptáte, kdy použít `Exact` versus `Rounding`. Zde jsou dva běžné scénáře:

| Scénář | Doporučený model | Důvod |
|----------|-------------------|--------|
| Vysokopřesná vědecká analýza | `PrecisionModel.Exact` | Žádná ztráta detailu souřadnic |
| Webové mapové dlaždice nebo mobilní aplikace | `PrecisionModel.Rounding(2)` | Snižuje velikost souboru a urychluje vykreslování |

Výběr správného modelu je součástí procesu rozhodování o **nastavení modelu přesnosti**, který vyvažuje přesnost a výkon.

## Časté problémy a řešení
- **Neočekávané hodnoty souřadnic** – Ujistěte se, že nastavíte `options.XYPrecisionModel` *před* otevřením vrstvy. Změna po otevření nemá žádný efekt.  
- **Soubor nenalezen** – Ověřte, že proměnná `path` ukazuje na platný adresář a že shapefile byl úspěšně vytvořen v předchozím kroku.  
- **Nesprávný typ geometrie** – Příklad používá `Point`. Pro jiné typy geometrií (např. `LineString`) by převod měl odpovídat skutečnému typu.  

## Tipy pro zmenšení velikosti shapefile
- Použijte `PrecisionModel.Rounding` s nejmenším počtem desetinných míst, který stále splňuje vaše požadavky na přesnost.  
- Odstraňte zbytečná atributová pole před zápisem vrstvy.  
- Komprimujte výsledné soubory `.shp`, `.shx` a `.dbf` pomocí standardních ZIP nástrojů, pokud je potřebujete přenést.

## Závěr
Na závěr, správa přesnosti při čtení geometrií je klíčovým aspektem manipulace s geoprostorovými daty. Aspose.GIS pro .NET poskytuje robustní funkce pro efektivní dosažení tohoto cíle. Dodržením výše uvedených kroků můžete bez problémů **vytvořit vektorovou vrstvu**, **nastavit model přesnosti** a dokonce **zmenšit velikost shapefile**, pokud je to vhodné, což zajišťuje optimální zpracování dat ve vašich aplikacích.

## Často kladené otázky
### Můžu použít Aspose.GIS pro .NET s jinými .NET frameworky jako .NET Core nebo .NET Standard?
Ano, Aspose.GIS pro .NET je kompatibilní s různými .NET frameworky, včetně .NET Core a .NET Standard.  
### Je k dispozici zkušební verze pro Aspose.GIS pro .NET?
Ano, můžete získat bezplatnou zkušební verzi na [stránce vydání](https://releases.aspose.com/).  
### Kde najdu komplexní dokumentaci pro Aspose.GIS pro .NET?
Můžete se podívat na [dokumentaci](https://reference.aspose.com/gis/net/) pro podrobné informace a příklady.  
### Jak mohu získat dočasné licence pro Aspose.GIS pro .NET?
Dočasné licence lze získat na [stránce nákupu](https://purchase.aspose.com/temporary-license/) pro Aspose.GIS.  
### Kde mohu získat pomoc nebo podporu pro Aspose.GIS pro .NET?
Můžete navštívit [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pro jakékoli dotazy, diskuse nebo potřeby podpory.

## Často kladené otázky
**Q: Ovlivňuje omezení přesnosti původní shapefile?**  
A: Ne. Přesnost se aplikuje pouze při čtení geometrie; zdrojový soubor zůstává nezměněn.  

**Q: Mohu použít odlišný model přesnosti pro souřadnice X a Y?**  
A: Aspose.GIS v současnosti používá stejný `XYPrecisionModel` pro obě osy.  

**Q: Je možné nastavit vlastní funkci zaokrouhlování?**  
A: API podporuje pouze vestavěnou metodu `PrecisionModel.Rounding(int)`. Pro vlastní logiku byste museli po načtení souřadnice zpracovat dodatečně.

---

**Poslední aktualizace:** 2026-04-03  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
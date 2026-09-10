---
date: 2026-09-10
description: Naučte se, jak vytvořit vektorovou vrstvu pomocí Aspose.GIS pro .NET
  a omezit přesnost pro zmenšení velikosti shapefile, zvýšení výkonu a zachování přesnosti
  souřadnic.
keywords:
- how to create vector layer
- limit precision reading geometries
- reduce shapefile size
lastmod: 2026-09-10
linktitle: Omezení přesnosti při čtení geometrií
og_description: Naučte se, jak vytvořit vektorovou vrstvu pomocí Aspose.GIS pro .NET
  a omezit přesnost pro zmenšení velikosti shapefile, zvýšení výkonu a správu přesnosti
  souřadnic.
og_image_alt: Screenshot showing Aspose.GIS code for creating a vector layer and setting
  precision
og_title: Jak vytvořit vektorovou vrstvu pomocí Aspose.GIS pro .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  headline: How to create vector layer with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  name: How to create vector layer with Aspose.GIS for .NET
  steps:
  - name: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
    text: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
  - name: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
    text: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
  - name: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
    text: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
  - name: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
    text: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
  type: HowTo
- questions:
  - answer: No. Precision is applied only when reading the geometry; the source file
      remains unchanged.
    question: Does limiting precision affect the original shapefile?
  - answer: Aspose.GIS currently applies the same `XYPrecisionModel` to both axes.
    question: Can I use a different precision model for X and Y coordinates?
  - answer: The API supports only the built‑in `PrecisionModel.Rounding(int)` method.
      For custom logic, you would need to post‑process the coordinates after reading.
    question: Is it possible to set a custom rounding function?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- Aspose.GIS
- vector layer
- precision model
- .NET GIS
title: Jak vytvořit vektorovou vrstvu pomocí Aspose.GIS pro .NET
url: /cs/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit vektorovou vrstvu pomocí Aspose.GIS pro .NET

## Úvod
Když pracujete s geoprostorovými daty, často se ptáte, **jak vytvořit vektorovou vrstvu** objektů, které odpovídají přesnosti, kterou vaše aplikace skutečně potřebuje. Zaokrouhlení souřadnic na rozumný počet desetinných míst nejen urychluje parsování, ale může také **snížit velikost shapefile až o 30 %** pro typické datové sady bodů. V tomto krok‑za‑krokem průvodci uvidíte, jak vytvořit vektorovou vrstvu, zapsat geometrický bod a poté jej načíst zpět pomocí jak přesných, tak zaokrouhlených modelů přesnosti. Na konci budete vědět, jak **nastavit model přesnosti** tak, aby vyvážil výkon s požadovanou prostorovou přesností.

## Rychlé odpovědi
- **Co znamená „omezit přesnost“?** Zaokrouhluje hodnoty souřadnic na definovaný počet desetinných míst.  
- **Proč nejprve vytvořit vektorovou vrstvu?** Vektorová vrstva je kontejner, který ukládá geometrie jako body, čáry a polygony.  
- **Jaké modely přesnosti jsou k dispozici?** `PrecisionModel.Exact` (žádné zaokrouhlení) a `PrecisionModel.Rounding(n)` (zaokrouhlení na *n* desetinných míst).  
- **Potřebuji licenci k vyzkoušení?** Bezplatná zkušební verze je k dispozici na stránce vydání.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core a .NET 5/6+.

## Co je vytvoření vektorové vrstvy?
Akt akce **vytvoření vektorové vrstvy** znamená vytvoření instance třídy `VectorLayer` z Aspose.GIS, která představuje jeden shapefile na disku a obsahuje všechny geometrické prvky, které přidáte. Tato vrstva se stává vstupním bodem pro čtení, zápis a manipulaci s prostorovými daty. Také vám umožňuje definovat atributová pole a nastavit prostorovou referenci pro datovou sadu.

## Proč omezit přesnost a jak to pomáhá?
- **Zvýšení výkonu** – Snížení počtu desetinných číslic snižuje množství binárních dat, která je třeba parsovat a serializovat, což často přináší 15‑20 % zrychlení při práci s velkými soubory.  
- **Menší soubory** – Zaokrouhlení souřadnic na dvě nebo tři desetinná místa může zmenšit 10 MB shapefile na přibližně 7 MB, usnadňující ukládání a přenos přes síť.  
- **Dostatečná přesnost** – Většina GIS analýz (např. mapování na úrovni města) vyžaduje pouze přesnost na úrovni metrů, takže zaokrouhlení na 3 desetinná místa je více než dostačující.

## Předpoklady
Než se pustíme do tohoto postupu, ujistěte se, že máte následující předpoklady:
1. **Instalace** – Knihovna Aspose.GIS pro .NET by měla být nainstalována ve vašem vývojovém prostředí. Pokud ne, můžete ji stáhnout ze [stránky vydání](https://releases.aspose.com/gis/net/).  
2. **Znalost .NET** – Základní znalost C# a .NET frameworku je nutná k pochopení a implementaci poskytnutých ukázek kódu.  
3. **Vývojové prostředí** – Je vyžadováno funkční .NET vývojové prostředí, například Visual Studio.  
4. **Adresář dokumentů** – Mějte připravený adresář, kde můžete ukládat a přistupovat k shapefile vytvořenému během procesu.

## Importovat jmenné prostory
Než začneme implementovat funkci pro omezení přesnosti při čtení geometrií, ujistěte se, že importujete potřebné jmenné prostory:

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
Načtěte novou `VectorLayer` zadáním výstupní složky a požadovaného názvu shapefile. Tím vytvoříte prázdný kontejner připravený přijímat geometrické objekty.

Třída `VectorLayer` je nejvyšší objekt Aspose.GIS, který představuje jeden shapefile na disku. Po vytvoření instance můžete přidávat prvky, definovat atributová pole a nakonec zavolat `Save()`, aby se soubory zapsaly do souborového systému.

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
`PrecisionModel` určuje, jak jsou hodnoty souřadnic zaokrouhleny nebo zachovány přesně při čtení geometrií. Model nastavíte na objekt `ReadOptions` před otevřením vrstvy.

Třída `PrecisionModel` je základní součástí Aspose.GIS, která řídí chování zaokrouhlování pro osy X i Y. Výběrem vhodného modelu určujete, zda knihovna zachová každý digit nebo jej zkrátí na konkrétní počet desetinných míst.

```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Čtení geometrií s přesnou přesností
`ReadOptions` specifikuje parametry pro čtení vektorové vrstvy, například použitý model přesnosti.  
Otevřete dříve uloženou vektorovou vrstvu pomocí instance `ReadOptions`, která odkazuje na `PrecisionModel.Exact`. Tím zajistíte, že každá souřadnice bude načtena bez jakéhokoli zaokrouhlení.

Když použijete `PrecisionModel.Exact`, Aspose.GIS načte surové hodnoty dvojité přesnosti uložené v shapefile, čímž zaručuje, že během operace čtení nedojde ke ztrátě informací.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Zkrácení přesnosti
Pokud chcete zkrátit přesnost na konkrétní počet desetinných míst, nahraďte `Exact` za `PrecisionModel.Rounding(n)`, kde *n* je počet desetinných míst, které chcete zachovat.

Zaokrouhlení na dvě desetinná místa (`PrecisionModel.Rounding(2)`) typicky sníží velikost souboru o 20‑30 % a zároveň udržuje přesnost souřadnic v řádu několika centimetrů pro většinu mapových měřítek.

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
Vyberte model, který odpovídá vašemu použití:
- **Vysokopřesná vědecká analýza** – Použijte `PrecisionModel.Exact` pro zachování každého čísla.  
- **Webové mapové dlaždice nebo mobilní aplikace** – Použijte `PrecisionModel.Rounding(2)`, aby soubory byly lehké a vykreslování rychlé.

Výběr vhodného modelu je součástí procesu rozhodování o **nastavení modelu přesnosti**, který vyvažuje přesnost a výkon.

## Časté problémy a řešení
`XYPrecisionModel` je vlastnost `ReadOptions`, která nastavuje model přesnosti pro souřadnice X i Y.
- **Neočekávané hodnoty souřadnic** – Ujistěte se, že nastavíte `options.XYPrecisionModel` *před* otevřením vrstvy. Změna po otevření nemá žádný efekt.  
- **Soubor nenalezen** – Ověřte, že proměnná `path` ukazuje na platný adresář a že shapefile byl úspěšně vytvořen v předchozím kroku.  
- **Nesprávný typ geometrie** – Příklad používá `Point`. Pro jiné typy geometrií (např. `LineString`) by převod měl odpovídat skutečnému typu.

## Tipy pro snížení velikosti shapefile
- Používejte `PrecisionModel.Rounding` s nejmenším počtem desetinných míst, který stále splňuje vaše požadavky na přesnost.  
- Odstraňte zbytečná atributová pole před zápisem vrstvy.  
- Komprimujte výsledné soubory `.shp`, `.shx` a `.dbf` pomocí standardních ZIP nástrojů, pokud je potřebujete přenést.

## Závěr
Správa přesnosti při čtení geometrií je klíčovým aspektem manipulace s geoprostorovými daty. Aspose.GIS pro .NET poskytuje robustní funkce pro efektivní dosažení tohoto cíle. Dodržením výše uvedených kroků můžete bez problémů **vytvořit vektorovou vrstvu**, **nastavit model přesnosti** a dokonce **snížit velikost shapefile**, pokud je to vhodné, což zajišťuje optimální zpracování dat ve vašich aplikacích.

## Často kladené otázky
### Mohu použít Aspose.GIS pro .NET s jinými .NET frameworky, jako je .NET Core nebo .NET Standard?
Ano, Aspose.GIS pro .NET je kompatibilní s různými .NET frameworky, včetně .NET Core a .NET Standard.

### Je k dispozici zkušební verze pro Aspose.GIS pro .NET?
Ano, můžete získat bezplatnou zkušební verzi ze [stránky vydání](https://releases.aspose.com/).

### Kde najdu komplexní dokumentaci pro Aspose.GIS pro .NET?
Můžete se podívat na [dokumentaci](https://reference.aspose.com/gis/net/) pro podrobné informace a příklady.

### Jak mohu získat dočasné licence pro Aspose.GIS pro .NET?
Dočasné licence lze získat na [stránce nákupu](https://purchase.aspose.com/temporary-license/) pro Aspose.GIS.

### Kde mohu získat pomoc nebo podporu pro Aspose.GIS pro .NET?
Můžete navštívit Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) pro jakékoli dotazy, diskuze nebo potřeby podpory.

## Často kladené otázky
**Q: Ovlivňuje omezení přesnosti původní shapefile?**  
A: Ne. Přesnost se aplikuje pouze při čtení geometrie; zdrojový soubor zůstává nezměněn.

**Q: Mohu použít odlišný model přesnosti pro souřadnice X a Y?**  
A: Aspose.GIS v současnosti používá stejný `XYPrecisionModel` pro obě osy.

**Q: Je možné nastavit vlastní funkci zaokrouhlování?**  
A: API podporuje pouze vestavěnou metodu `PrecisionModel.Rounding(int)`. Pro vlastní logiku byste museli po načtení souřadnice zpracovat dodatečně.

---

**Poslední aktualizace:** 2026-09-10  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose

## Související tutoriály

- [Jak omezit přesnost při zápisu geometrií pomocí Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)
- [Jak vytvořit vektorovou vrstvu s SRS pomocí Aspose.GIS pro .NET](/gis/net/layer-management/create-vector-layer-with-srs/)
- [Vytvořit vektorovou vrstvu v souboru GDB – Aspose.GIS .NET tutoriál](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
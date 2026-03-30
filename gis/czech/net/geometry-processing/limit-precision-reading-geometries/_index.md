---
date: 2025-12-20
description: Naučte se, jak vytvořit vektorovou vrstvu a omezit přesnost při čtení
  geometrií pomocí Aspose.GIS pro .NET. Krok za krokem průvodce pro optimální zpracování
  geoprostorových dat.
linktitle: Limit Precision Reading Geometries
second_title: Aspose.GIS .NET API
title: Vytvořte vektorovou vrstvu, omezte přesnost pomocí Aspose.GIS pro .NET
url: /cs/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření vektorové vrstvy, omezení přesnosti pomocí Aspose.GIS pro .NET

## Úvod
Když pracujete s geoprostorovými daty, často potřebujete **create vector layer** objekty a řídit, kolik číselných detailů se při čtení zachová. Aspose.GIS pro .NET to usnadňuje omezit přesnost, což může zlepšit výkon a snížit velikost úložiště, když není vyžadována ultra‑vysoká přesnost. V tomto tutoriálu uvidíte přesně, jak vytvořit vektorovou vrstvu, zapsat jednoduchou bodovou geometrii a poté ji načíst zpět s přesnou i zkrácenou přesností.

## Rychlé odpovědi
- **Co znamená „limit precision“?** Zaokrouhluje hodnoty souřadnic na definovaný počet desetinných míst.  
- **Proč nejprve vytvořit vektorovou vrstvu?** Vektorová vrstva je kontejner, který ukládá geometrie jako body, čáry a polygony.  
- **Které modely přesnosti jsou k dispozici?** `PrecisionModel.Exact` (žádné zaokrouhlení) a `PrecisionModel.Rounding(n)` (zaokrouhlení na *n* desetinných míst).  
- **Potřebuji licenci k vyzkoušení?** Bezplatná zkušební verze je k dispozici na stránce vydání.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core a .NET 5/6+.

## Požadavky
Než se pustíme do tohoto postupu, ujistěte se, že máte následující požadavky:
1. **Instalace** – Knihovna Aspose.GIS pro .NET by měla být nainstalována ve vašem vývojovém prostředí. Pokud ne, můžete ji stáhnout ze [stránky vydání](https://releases.aspose.com/gis/net/).
2. **Znalost .NET** – Základní znalost C# a .NET frameworku je nutná pro pochopení a implementaci poskytnutých ukázek kódu.
3. **Vývojové prostředí** – Je vyžadováno funkční .NET vývojové prostředí, například Visual Studio.
4. **Adresář dokumentů** – Mějte připravený adresář, kde můžete ukládat a přistupovat k shapefile vytvořenému během procesu.

## Import jmenných prostor
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
Prvním krokem je **create vector layer**, která bude obsahovat naši geometrii. Tato vrstva bude uložena jako Shapefile, abychom ji později mohli otevřít s různými nastaveními přesnosti.
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
Nyní otevřeme vektorovou vrstvu s určenými možnostmi, abychom načetli geometrie s přesnou přesností:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Zkrácení přesnosti
Pokud chceme zkrátit přesnost na konkrétní počet desetinných míst, můžeme podle toho upravit model přesnosti:
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Časté problémy a řešení
- **Neočekávané hodnoty souřadnic** – Ujistěte se, že nastavíte `options.XYPrecisionModel` *před* otevřením vrstvy. Změna po otevření nemá žádný efekt.
- **Soubor nenalezen** – Ověřte, že proměnná `path` ukazuje na platný adresář a že shapefile byl úspěšně vytvořen v předchozím kroku.
- **Nesprávný typ geometrie** – Příklad používá `Point`. Pro jiné typy geometrií (např. `LineString`) by převod měl odpovídat skutečnému typu.

## Závěr
Na závěr, správa přesnosti při čtení geometrií je klíčovým aspektem manipulace s geoprostorovými daty. Aspose.GIS pro .NET poskytuje robustní funkce pro efektivní dosažení tohoto cíle. Dodržením kroků uvedených v tomto tutoriálu můžete bez problémů **create vector layer** objekty a omezit přesnost podle svých požadavků, což zajišťuje optimální zpracování dat ve vašich aplikacích.

## Často kladené otázky
### Mohu používat Aspose.GIS pro .NET s jinými .NET frameworky, jako je .NET Core nebo .NET Standard?
Ano, Aspose.GIS pro .NET je kompatibilní s různými .NET frameworky, včetně .NET Core a .NET Standard.  
### Je k dispozici zkušební verze pro Aspose.GIS pro .NET?
Ano, můžete získat bezplatnou zkušební verzi ze [stránky vydání](https://releases.aspose.com/).  
### Kde najdu komplexní dokumentaci pro Aspose.GIS pro .NET?
Můžete se podívat na [dokumentaci](https://reference.aspose.com/gis/net/) pro podrobné informace a příklady.  
### Jak mohu získat dočasné licence pro Aspose.GIS pro .NET?
Dočasné licence lze získat na [stránce nákupu](https://purchase.aspose.com/temporary-license/) pro Aspose.GIS.  
### Kde mohu získat pomoc nebo podporu pro Aspose.GIS pro .NET?
Můžete navštívit fórum Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) pro dotazy, diskuze nebo potřeby podpory.

## Často kladené otázky
**Q: Ovlivňuje omezení přesnosti původní shapefile?**  
A: Ne. Přesnost se aplikuje pouze při čtení geometrie; zdrojový soubor zůstává nezměněn.  

**Q: Mohu použít odlišný model přesnosti pro souřadnice X a Y?**  
A: Aspose.GIS v současnosti používá stejný `XYPrecisionModel` pro oba osy.  

**Q: Je možné nastavit vlastní funkci zaokrouhlování?**  
A: API podporuje pouze vestavěnou metodu `PrecisionModel.Rounding(int)`. Pro vlastní logiku byste museli po načtení souřadnice zpracovat dodatečně.

---

**Poslední aktualizace:** 2025-12-20  
**Testováno s:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-01-13
description: Naučte se, jak převést shapefile na geojson pomocí Aspose.GIS pro .NET.
  Průvodce také pokrývá kopírování atributů mezi vrstvami a generování geojson souboru
  v C#.
linktitle: Extract Features to GeoJSON
second_title: Aspose.GIS .NET API
title: Jak převést Shapefile na GeoJSON pomocí Aspose.GIS pro .NET
url: /cs/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod Shapefile na GeoJSON pomocí Aspose.GIS pro .NET

## Úvod
V tomto komplexním, krok‑za‑krokem tutoriálu se naučíte **jak převést shapefile na geojson** pomocí výkonné knihovny Aspose.GIS pro .NET. Ať už vytváříte mapovou webovou službu, připravujete data pro mobilní GIS aplikaci, nebo jednoduše potřebujete vyměňovat data mezi formáty, tento průvodce vám ukáže přesně, co dělat, proč je každý krok důležitý a jak se vyhnout běžným úskalím.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Převod Shapefile na soubor GeoJSON, kopírování atributů mezi vrstvami a generování výstupu pomocí C#.
- **Která knihovna je vyžadována?** Aspose.GIS pro .NET.
- **Potřebuji licenci?** Pro produkční nasazení je vyžadována dočasná nebo plná licence; pro hodnocení stačí bezplatná zkušební verze.
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní převod.
- **Mohu to spustit na .NET Core/.NET 6?** Ano – kód funguje na všech podporovaných verzích .NET.

## Předpoklady
Než se pustíme do práce, ujistěte se, že máte následující:

- Aspose.GIS pro .NET: Ujistěte se, že máte knihovnu nainstalovanou. Pokud ne, můžete ji stáhnout ze [stránky Aspose.GIS pro .NET](https://releases.aspose.com/gis/net/).
- Shapefile Data: Mějte připravený Shapefile jako vstup. Pokud potřebujete ukázková data, najdete je v [dokumentaci Aspose.GIS](https://reference.aspose.com/gis/net/).
- .NET Environment: Nastavte .NET prostředí pro spuštění poskytnutého kódu.
- Document Directory: Definujte cestu k vašemu adresáři s dokumenty v ukázkovém kódu.

Nyní, když máte vše připravené, pojďme začít převádět shapefile na geojson!

## Co je „převod shapefile na geojson“?
Převod Shapefile na GeoJSON znamená načtení vektorových prvků z klasického formátu ESRI Shapefile a jejich zápis do moderního, web‑přátelského dokumentu GeoJSON. GeoJSON je široce používán v JavaScriptových mapových knihovnách (Leaflet, Mapbox GL) a API, což činí tento převod častým úkolem v GIS vývoji.

## Proč použít Aspose.GIS pro tento převod?
Aspose.GIS abstrahuje nízkoúrovňové detaily formátů souborů, umožňuje snadno kopírovat tabulky atributů a poskytuje čisté, objektově orientované API, které funguje napříč .NET Framework, .NET Core a .NET 5/6. To vám umožní soustředit se na obchodní logiku místo parsování binárních souborů.

## Importovat jmenné prostory
Nejprve zahrňte potřebné jmenné prostory do svého kódu:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Tyto jmenné prostory jsou nezbytné pro práci s funkcionalitou Aspose.GIS.

## Jak převést Shapefile na GeoJSON
Níže je kompletní workflow rozdělený do přehledných kroků. Každý krok obsahuje krátké vysvětlení následované přesným blokem kódu, který je potřeba zkopírovat do projektu.

### Krok 1: Otevřít vstupní Shapefile
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```
Otevřete vstupní Shapefile pomocí metody `VectorLayer.Open`. Tím získáte iterovatelnou kolekci objektů `Feature`.

### Krok 2: Vytvořit výstupní GeoJSON
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```
Vytvořte výstupní soubor pomocí metody `VectorLayer.Create` a specifikujte ovladač `Drivers.GeoJson`.

### Krok 3: Kopírovat atributy mezi vrstvami
```csharp
outputLayer.CopyAttributes(inputLayer);
```
Tento jediný řádek zkopíruje schéma atributů (názvy polí, typy) ze zdrojového Shapefile do nové vrstvy GeoJSON – přesně to, co popisuje sekundární klíčové slovo *copy attributes between layers*.

### Krok 4: Zpracovat prvky
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```
Iterujte přes každý prvek ve Shapefile, abyste mohli aplikovat libovolnou vlastní logiku před jeho zápisem.

### Krok 5: Filtrovat prvky podle data
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
V tomto příkladu přeskočíme záznamy, jejichž pole `dob` (date of birth) chybí nebo je starší než 1 ledna 1982. Přizpůsobte filtr podle svých požadavků na data.

### Krok 6: Vytvořit nový prvek (C# Generate GeoJSON File)
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Zde vytvoříme nový `Feature` pro vrstvu GeoJSON, zkopírujeme geometrii a hodnoty atributů a přidáme jej do výstupu. Toto je jádro *c# generate geojson file*.

Gratulujeme! Úspěšně jste **převzeli shapefile na geojson** a během toho se naučili, jak kopírovat atributy mezi vrstvami.

## Časté problémy a řešení
| Problém | Proč se to děje | Řešení |
|-------|----------------|-----|
| Výstupní soubor je prázdný | `CopyAttributes` byl zavolán po uzavření výstupní vrstvy | Ujistěte se, že blok `using` pro `outputLayer` zůstane otevřený až do přidání všech prvků. |
| Filtr podle data odstraňuje všechny záznamy | Špatný název pole nebo neočekávaný formát data | Ověřte název atributu (`dob`) a použijte `GetValue<string>`, pokud jsou data uložena jako řetězce. |
| Výjimka licence | Spuštění bez platné licence Aspose.GIS v produkci | Použijte dočasnou nebo plnou licenci, jak je popsáno v dokumentaci Aspose. |

## Často kladené otázky
**Q: Kde najdu další dokumentaci?**  
A: Navštivte [Aspose.GIS documentation](https://reference.aspose.com/gis/net/) pro podrobné informace.

**Q: Jak získat dočasnou licenci?**  
A: Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

**Q: Kde mohu získat podporu?**  
A: Připojte se k [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) pro komunitní podporu a diskuze.

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano, bezplatnou zkušební verzi najdete [zde](https://releases.aspose.com/).

**Q: Kde si mohu zakoupit Aspose.GIS pro .NET?**  
A: Produkt si můžete zakoupit [zde](https://purchase.aspose.com/buy).

## Závěr
V tomto tutoriálu jsme prozkoumali kompletní proces **převodu shapefile na geojson** pomocí Aspose.GIS pro .NET, ukázali, jak kopírovat atributy mezi vrstvami, a představili čistý způsob *c# generate geojson file*. Vyzkoušejte různé filtry, větší datové sady nebo další geometrické transformace, abyste plně využili možnosti knihovny.

---

**Poslední aktualizace:** 2026-01-13  
**Testováno s:** Aspose.GIS pro .NET (nejnovější stabilní verze)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
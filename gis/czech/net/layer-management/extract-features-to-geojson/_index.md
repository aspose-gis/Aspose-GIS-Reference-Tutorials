---
date: 2026-07-05
description: Naučte se, jak převést shapefile na geojson pomocí Aspose.GIS pro .NET.
  Průvodce také zahrnuje kopírování atributů mezi vrstvami a generování geojson souboru
  v C#.
keywords:
- convert shapefile to geojson
- export shapefile as geojson
- aspose gis conversion
- read shapefile c#
- write geojson c#
linktitle: Extrahovat prvky do GeoJSON
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  headline: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  name: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  steps:
  - name: Open Input Shapefile
    text: The `VectorLayer.Open` method reads a Shapefile and returns an enumerable
      collection of `Feature` objects that you can iterate over.
  - name: Create Output GeoJSON
    text: '`VectorLayer.Create` with the `Drivers.GeoJson` driver creates an empty
      GeoJSON file ready to receive features.'
  - name: Copy Attributes Between Layers
    text: '`CopyAttributes` copies the attribute schema (field names and data types)
      from the source Shapefile to the new GeoJSON layer in a single call.'
  - name: Process Features
    text: Iterate through each feature in the Shapefile so you can apply any custom
      logic before writing it out.
  - name: Filter Features by Date
    text: In this example we skip records whose `dob` (date of birth) field is missing
      or earlier than 1 Jan 1982. Adjust the filter to match your own data requirements.
  - name: Construct a New Feature (C# Generate GeoJSON File)
    text: A `Feature` represents a single spatial element containing geometry and
      attribute data. Here we build a new `Feature` for the GeoJSON layer, copy the
      geometry and attribute values, and add it to the output. This is the core of
      *c# generate geojson file*. Congratulations! You’ve successfully **conver
  type: HowTo
- questions:
  - answer: Visit the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/)
      for in‑depth information.
    question: Where can I find more documentation?
  - answer: You can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license?
  - answer: Join the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I seek support?
  - answer: Yes, you can find the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can buy the product [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Převod shapefile na GeoJSON pomocí Aspose.GIS pro .NET
url: /cs/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod shapefile na GeoJSON pomocí Aspose.GIS pro .NET

## Úvod
V tomto komplexním, krok‑za‑krokem tutoriálu se naučíte **jak převést shapefile na geojson** pomocí výkonné knihovny Aspose.GIS pro .NET. Ať už vytváříte mapovou webovou službu, připravujete data pro mobilní GIS aplikaci, nebo jednoduše potřebujete vyměňovat data mezi formáty, tento průvodce vám ukáže přesně, co dělat, proč je každý krok důležitý a jak se vyhnout běžným úskalím.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Převod Shapefile na soubor GeoJSON, kopírování atributů mezi vrstvami a generování výstupu pomocí C#.
- **Která knihovna je vyžadována?** Aspose.GIS pro .NET.
- **Potřebuji licenci?** Pro produkci je vyžadována dočasná nebo plná licence; pro hodnocení funguje bezplatná zkušební verze.
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní převod.
- **Mohu to spustit na .NET Core/.NET 6?** Ano – kód funguje na všech podporovaných verzích .NET.

## Co je převod shapefile na geojson?
Převod Shapefile na GeoJSON znamená načtení vektorových prvků z klasického formátu ESRI Shapefile a jejich zápis do moderního, web‑přátelského dokumentu GeoJSON. Tato transformace vám umožní přímo vložit GIS data do JavaScriptových mapovacích knihoven, jako jsou Leaflet nebo Mapbox GL, a zjednodušuje výměnu dat mezi desktopovými GIS nástroji a webovými API.

## Proč použít Aspose.GIS pro tento převod?
Aspose.GIS abstrahuje nízkoúrovňové binární parsování, podporuje více než 50 vstupních a výstupních formátů a dokáže zpracovat dataset o stovkách stránek, aniž by načítala celý soubor do paměti. Knihovna také poskytuje čisté, objektově orientované API, které funguje napříč .NET Framework, .NET Core a .NET 5/6, takže můžete věnovat čas obchodní logice místo zvláštnostem formátů.

## Požadavky
Než se pustíme dál, ujistěte se, že máte následující:

- Aspose.GIS pro .NET: Ujistěte se, že máte knihovnu nainstalovanou. Pokud ne, můžete si ji stáhnout ze stránky [Aspose.GIS for .NET page](https://releases.aspose.com/gis/net/).
- Shapefile data: Mějte připravený Shapefile pro vstup. Pokud potřebujete ukázková data, najdete je v [Aspose.GIS documentation](https://reference.aspose.com/gis/net/).
- .NET prostředí: Nastavte .NET prostředí pro spuštění poskytnutého kódu.
- Dokumentový adresář: Definujte cestu k vašemu dokumentovému adresáři v úryvku kódu.

Nyní, když máte vše připravené, pojďme začít převádět shapefile na geojson!

## Jak převést Shapefile na GeoJSON
Načtěte zdrojový Shapefile, vytvořte cílovou vrstvu GeoJSON, zkopírujte schéma atributů, filtrujte záznamy a zapište výsledky – vše v několika stručných krocích. Kompletní workflow se pohodlně vejde do jediného `using` bloku, což zajišťuje automatické uvolnění prostředků.

### Krok 1: Otevřít vstupní Shapefile
`VectorLayer.Open` metoda načte Shapefile a vrátí výčtovou kolekci objektů `Feature`, přes které můžete iterovat.

```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```

### Krok 2: Vytvořit výstupní GeoJSON
`VectorLayer.Create` s ovladačem `Drivers.GeoJson` vytvoří prázdný soubor GeoJSON připravený přijímat prvky.

```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```

### Krok 3: Kopírovat atributy mezi vrstvami
`CopyAttributes` zkopíruje schéma atributů (názvy polí a datové typy) ze zdrojového Shapefile do nové vrstvy GeoJSON jedním voláním.

```csharp
outputLayer.CopyAttributes(inputLayer);
```

### Krok 4: Zpracovat prvky
Iterujte přes každý prvek v Shapefile, abyste mohli před zápisem aplikovat libovolnou vlastní logiku.

```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```

### Krok 5: Filtrovat prvky podle data
V tomto příkladu přeskočíme záznamy, jejichž pole `dob` (datum narození) chybí nebo je starší než 1 ledna 1982. Přizpůsobte filtr podle vlastních požadavků na data.

```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```

### Krok 6: Vytvořit nový prvek (C# generování souboru GeoJSON)
`Feature` představuje jeden prostorový prvek obsahující geometrii a atributová data.  
Zde vytvoříme nový `Feature` pro vrstvu GeoJSON, zkopírujeme geometrii a hodnoty atributů a přidáme jej do výstupu. Toto je jádro *c# generate geojson file*.

```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```

Gratulujeme! Úspěšně jste **převáděli shapefile na geojson** a během toho se naučili **kopírovat atributy mezi vrstvami**.

## Časté problémy a řešení
| Problém | Proč se to děje | Oprava |
|---------|----------------|--------|
| Výstupní soubor je prázdný | `CopyAttributes` byl zavolán po uzavření výstupní vrstvy | Zajistěte, aby `using` blok pro `outputLayer` zůstal otevřený až po přidání všech prvků. |
| Filtr podle data odstraní všechny záznamy | Špatný název pole nebo neočekávaný formát data | Ověřte název atributu (`dob`) a použijte `GetValue<string>`, pokud jsou data uložena jako řetězce. |
| Výjimka licence | Spuštění bez platné licence Aspose.GIS v produkci | Aplikujte dočasnou nebo plnou licenci podle popisu v dokumentaci Aspose. |

## Často kladené otázky
**Q: Kde najdu další dokumentaci?**  
A: Navštivte [Aspose.GIS documentation](https://reference.aspose.com/gis/net/) pro podrobné informace.

**Q: Jak získat dočasnou licenci?**  
A: Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

**Q: Kde mohu získat podporu?**  
A: Připojte se k [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) pro komunitní podporu a diskuze.

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano, bezplatnou zkušební verzi najdete [zde](https://releases.aspose.com/).

**Q: Kde mohu zakoupit Aspose.GIS pro .NET?**  
A: Produkt můžete zakoupit [zde](https://purchase.aspose.com/buy).

## Závěr
V tomto tutoriálu jsme prozkoumali kompletní proces **převodu shapefile na geojson** pomocí Aspose.GIS pro .NET, ukázali, jak **kopírovat atributy mezi vrstvami**, a představili čistý způsob *c# generate geojson file*. Experimentujte s různými filtry, většími datasetty nebo dalšími geometrickými transformacemi, abyste plně využili možnosti knihovny.

---

**Poslední aktualizace:** 2026-07-05  
**Testováno s:** Aspose.GIS pro .NET (nejnovější stabilní verze)  
**Autor:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Související tutoriály

- [Jak převést GeoJSON na File GDB pomocí Aspose.GIS pro .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Jak načíst GeoJSON ze streamu pomocí Aspose.GIS pro .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Jak převést GeoJSON na TopoJSON pomocí Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
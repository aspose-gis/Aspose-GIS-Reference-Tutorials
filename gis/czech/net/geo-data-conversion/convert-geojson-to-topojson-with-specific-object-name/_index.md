---
date: 2026-07-19
description: Naučte se, jak převést GeoJSON na TopoJSON s konkrétním názvem objektu
  pomocí Aspose.GIS for .NET – kompletní průvodce konverzí Aspose GIS.
keywords:
- convert geojson to topojson
- reduce geojson file size
- aspose gis conversion
- how to convert geojson
lastmod: 2026-07-19
linktitle: Jak převést GeoJSON na TopoJSON s konkrétním názvem objektu
og_description: převod geojson na topojson s vlastním názvem objektu pomocí Aspose.GIS
  for .NET. Snižte velikost souboru, pracujte s velkými datovými sadami a zjednodušte
  přípravu webových map.
og_image_alt: 'Tutorial: Convert GeoJSON to TopoJSON with Aspose.GIS for .NET'
og_title: převod geojson na topojson – podrobný průvodce s Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to convert GeoJSON to TopoJSON with a specific object name
    using Aspose.GIS for .NET – a complete guide for Aspose GIS conversion.
  headline: How to Convert GeoJSON to TopoJSON with Specific Object Name
  type: TechArticle
- description: Learn how to convert GeoJSON to TopoJSON with a specific object name
    using Aspose.GIS for .NET – a complete guide for Aspose GIS conversion.
  name: How to Convert GeoJSON to TopoJSON with Specific Object Name
  steps:
  - name: Define File Paths
    text: Replace `"Your Document Directory"` with the actual folder where your input
      GeoJSON lives and where you want the TopoJSON result saved.
  - name: Set Conversion Options (Aspose GIS conversion)
    text: The `ConversionOptions` class lets you fine‑tune the conversion process.
      **Definition anchor:** `ConversionOptions` is a configuration object that controls
      output format, precision, and object naming for Aspose.GIS conversions. Here
      we create a `ConversionOptions` instance and set `DefaultObjectName
  - name: Perform the Conversion (convert geojson to topojson)
    text: The `VectorLayer.Convert` method does the heavy lifting. **Definition anchor:**
      `VectorLayer.Convert` is a static method that reads a source vector file, applies
      the supplied `ConversionOptions`, and writes the target format. The method reads
      the source GeoJSON, applies the options defined above, an
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS for .NET can be used in both commercial and personal applications
      with a valid license.
    question: Can I use Aspose.GIS for .NET in commercial projects?
  - answer: Yes, you can get a free trial from [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Support is available through the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).
    question: Where can I find support for Aspose.GIS for .NET?
  - answer: Licenses can be purchased from [here](https://purchase.aspose.com/buy).
    question: How do I purchase a license for Aspose.GIS for .NET?
  - answer: Yes, a temporary evaluation license is available from [here](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert geojson
- Aspose.GIS
- .NET data conversion
- TopoJSON
title: Jak převést GeoJSON na TopoJSON s konkrétním názvem objektu
url: /cs/net/geo-data-conversion/convert-geojson-to-topojson-with-specific-object-name/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak převést GeoJSON na TopoJSON s konkrétním názvem objektu

## Úvod
V tomto tutoriálu se dozvíte **jak převést GeoJSON** soubory na TopoJSON a při tom přiřadit vlastní název objektu pomocí **Aspose.GIS for .NET**. Ať už vytváříte mapovou službu, připravujete data pro webové vizualizace, nebo jen potřebujete jednoduchý způsob, jak přejmenovat výstupní objekt, tento krok‑za‑krokem průvodce vám ukáže přesně, co dělat. Konverze nejen mění formát, ale také **snižuje velikost souboru GeoJSON až o 70 %** díky sdílenému kódování hran v TopoJSON.

## Rychlé odpovědi
- **Co konverze dělá?** Převádí kolekci feature GeoJSON na topologii TopoJSON a umožňuje nastavit název kořenového objektu.  
- **Která knihovna provádí konverzi?** Aspose.GIS for .NET (součást sady Aspose GIS conversion).  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Jak dlouho trvá implementace?** Přibližně 5‑10 minut, jakmile je prostředí připravené.  

## Co je převod GeoJSON na TopoJSON?
Načtěte svůj zdrojový GeoJSON a zavolejte API pro konverzi Aspose.GIS – knihovna načte feature, vytvoří topologii se sdílenými hranami a zapíše soubor TopoJSON s názvem, který zadáte. Tato jednorázová operace zachovává přesnost geometrie a zároveň výrazně zmenšuje objem dat.

## Proč použít Aspose.GIS .NET pro tuto konverzi?
Aspose.GIS zpracovává soubory až do **2 GB** bez načítání celého dokumentu do paměti a podporuje **více než 50** vstupních a výstupních formátů – včetně Shapefile, KML, CSV a GeoPackage. API poskytuje vestavěné možnosti pro přesnost souřadnic, pojmenování objektů a zjednodušení topologie, což z něj činí nejspolehlivější volbu pro podnikové geospatial pipeline.

## Předpoklady
Než začneme, ujistěte se, že máte následující:

### 1. Instalace Aspose.GIS pro .NET
Navštivte [stránku ke stažení](https://releases.aspose.com/gis/net/) a stáhněte si nejnovější verzi Aspose.GIS pro .NET.

### 2. Nastavte vývojové prostředí
Visual Studio, Rider nebo jakékoli IDE kompatibilní s .NET bude fungovat. Ujistěte se, že váš projekt cílí na .NET Framework 4.5+ nebo .NET Core 3.1+.

### 3. Připravte soubor GeoJSON
Mějte připravený soubor GeoJSON, který chcete převést. Pokud jej nemáte, můžete vytvořit jednoduchý nebo použít libovolný ukázkový soubor GeoJSON pro tento tutoriál.

## Importujte jmenné prostory
Než začneme proces konverze, naimportujme potřebné jmenné prostory:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Jak převést GeoJSON na TopoJSON
Převod GeoJSON na TopoJSON znamená převzít standardní kolekci feature GeoJSON a zakódovat ji jako topologii TopoJSON. TopoJSON snižuje velikost souboru sdílením geometrických hran a s pomocí Aspose.GIS vám umožňuje specifikovat **DefaultObjectName**, takže výstupní soubor obsahuje pojmenovaný objekt dle vašeho výběru.

## Průvodce krok za krokem

### Krok 1: Definujte cesty k souborům
```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithObjectName_out.topojson";
```  
Nahraďte `"Your Document Directory"` skutečnou složkou, kde se nachází váš vstupní GeoJSON a kam chcete uložit výsledek TopoJSON.

### Krok 2: Nastavte možnosti konverze (Aspose GIS conversion)
Třída `ConversionOptions` vám umožňuje jemně doladit proces konverze.  
**Definiční kotva:** `ConversionOptions` je konfigurační objekt, který řídí výstupní formát, přesnost a pojmenování objektů pro konverze Aspose.GIS.  
```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // specify the name of the object where features should be written
        DefaultObjectName = "name_of_the_object",
    }
};
```  
Zde vytváříme instanci `ConversionOptions` a nastavujeme `DefaultObjectName`. Toto říká Aspose.GIS, aby zapisoval všechny feature pod objektem pojmenovaným **name_of_the_object** v generovaném souboru TopoJSON.

### Krok 3: Proveďte konverzi (convert geojson to topojson)
Metoda `VectorLayer.Convert` provádí těžkou práci.  
**Definiční kotva:** `VectorLayer.Convert` je statická metoda, která načte zdrojový vektorový soubor, použije poskytnuté `ConversionOptions` a zapíše cílový formát.  
```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```  
Metoda načte zdrojový GeoJSON, použije výše definované možnosti a zapíše soubor TopoJSON s vlastním názvem objektu.

## Jak pracovat s velkými soubory GeoJSON
Načtěte velké datové sady efektivně pomocí streamování zdrojového souboru a zvýšení limitu paměti procesu. Aspose.GIS dokáže zpracovat soubory větší než 1 GB čtením po částech, což zabraňuje výjimkám typu out‑of‑memory na typických serverových konfiguracích.

## Časté problémy a tipy
- **Chyby cest** – Použijte `Path.Combine` pro bezpečnou konstrukci cest k souborům a vyhněte se chybějícím oddělovačům.  
- **Správa paměti** – Pro velmi velké soubory GeoJSON zvyšte limit paměti procesu nebo data streamujte místo načítání celého souboru najednou.  
- **Konflikty názvů objektů** – Ujistěte se, že `DefaultObjectName` je v souboru TopoJSON jedinečný; duplicitní názvy mohou způsobit přepsání.  

Tyto postupy vám pomohou **efektivně pracovat s velkými soubory GeoJSON** při jejich převodu na TopoJSON.

## Často kladené otázky

**Q: Mohu používat Aspose.GIS pro .NET v komerčních projektech?**  
A: Ano, Aspose.GIS pro .NET může být používán jak v komerčních, tak osobních aplikacích s platnou licencí.

**Q: Je k dispozici bezplatná zkušební verze pro Aspose.GIS pro .NET?**  
A: Ano, bezplatnou zkušební verzi můžete získat [zde](https://releases.aspose.com/).

**Q: Kde mohu najít podporu pro Aspose.GIS pro .NET?**  
A: Podpora je k dispozici prostřednictvím [fóra Aspose.GIS](https://forum.aspose.com/c/gis/33).

**Q: Jak si mohu zakoupit licenci pro Aspose.GIS pro .NET?**  
A: Licence lze zakoupit [zde](https://purchase.aspose.com/buy).

**Q: Potřebuji dočasnou licenci pro hodnocení?**  
A: Ano, dočasná evaluační licence je k dispozici [zde](https://purchase.aspose.com/temporary-license/).

**Q: Můžu převést velmi velké datové sady GeoJSON bez vyčerpání paměti?**  
A: Ano—streamováním zdroje nebo zvýšením alokace paměti aplikace můžete velké soubory efektivně zpracovat.

**Last Updated:** 2026-07-19  
**Testováno s:** Aspose.GIS for .NET (latest release)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak převést GeoJSON na TopoJSON pomocí Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Jak převést GeoJSON na TopoJSON se seskupením pomocí Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/)
- [Převod TopoJSON na GeoJSON](/gis/net/geo-data-conversion/convert-topojson-to-geojson/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
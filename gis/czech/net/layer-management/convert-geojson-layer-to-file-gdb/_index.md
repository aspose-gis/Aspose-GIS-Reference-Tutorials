---
date: 2026-06-20
description: Naučte se, jak převést geojson na gdb pomocí Aspose.GIS pro .NET. Tento
  podrobný návod pokrývá čtení GeoJSON v C#, vytváření File Geodatabase a řešení běžných
  problémů.
keywords:
- convert geojson to gdb
- how to convert geojson
- read geojson c#
- asp.net geojson conversion
linktitle: Převést vrstvu GeoJSON na GDB
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to convert geojson to gdb with Aspose.GIS for .NET. This
    step‑by‑step guide covers reading GeoJSON in C#, creating a File Geodatabase,
    and handling common issues.
  headline: How to Convert GeoJSON to GDB Using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Converting a GeoJSON layer to a GDB with Aspose.GIS for .NET.
    question: What does this guide teach?
  - answer: '*convert geojson to gdb*.'
    question: Which primary keyword is targeted?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Supported .NET versions?
  - answer: Roughly 10‑15 minutes for a basic conversion.
    question: Implementation time?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Jak převést GeoJSON na GDB pomocí Aspose.GIS pro .NET
url: /cs/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak převést GeoJSON na GDB pomocí Aspose.GIS pro .NET

## Úvod
Pokud chcete **convert geojson to gdb** rychle a spolehlivě, jste na správném místě. Tento návod vás provede každým krokem – od načtení souboru GeoJSON v C# po vytvoření File Geodatabase (GDB) pomocí Aspose.GIS. Uvidíte, proč je Aspose.GIS preferovanou knihovnou pro konverzi geoprostorových dat, jak nastavit prostředí a jak spustit konverzi během několika minut.

## Rychlé odpovědi
- **Co tento průvodce učí?** Převod vrstvy GeoJSON do GDB pomocí Aspose.GIS pro .NET.  
- **Jaké primární klíčové slovo je cíleno?** *convert geojson to gdb*.  
- **Potřebuji licenci?** Bezplatná zkušební verze stačí pro testování; pro produkci je vyžadována komerční licence.  
- **Podporované verze .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Doba implementace?** Přibližně 10‑15 minut pro základní konverzi.

## Co je GeoJSON a File GDB?
GeoJSON je lehký textový formát pro geografické prvky, zatímco File GDB je složková vysoce výkonná ESRI geodatabáze.  
GeoJSON ukládá body, linie a polygony jako prostý text, což usnadňuje sdílení a úpravy, zatímco File GDB uchovává data v binárních souborech, které poskytují rychlé prostorové dotazy a robustní správu atributů. Společně pokrývají jak web‑přátelskou výměnu, tak vysokorychlostní desktopové GIS zpracování.

## Proč použít Aspose.GIS pro konverzi geoprostorových dat?
Aspose.GIS poskytuje jednotné API, které skrývá specifické nuance formátů. Podporuje **30+ geoprostorových formátů**, dokáže zpracovat soubory až do **2 GB** bez načítání celého datasetu do paměti a automaticky zachovává souřadnicové referenční systémy. To znamená méně času stráveného psaním parserů a více času na vývoj logiky aplikace.

## Požadavky
- Znalost C# a struktury .NET projektu.  
- Aspose.GIS pro .NET nainstalován. Pokud jste jej ještě neinstalovali, stáhněte jej [zde](https://releases.aspose.com/gis/net/) a postupujte podle instalačního průvodce. Další produkty Aspose můžete prozkoumat [zde](https://releases.aspose.com/).

## Importovat jmenné prostory
Prvním krokem je přidat požadované jmenné prostory do rozsahu.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Jak načíst GeoJSON v C#?
Načtěte soubor GeoJSON pomocí třídy `GeoJsonReader`, která parsuje JSON a vytvoří v‑paměti `FeatureCollection`. Čtečka automaticky detekuje souřadnicový referenční systém, takže nemusíte ručně zpracovávat CRS. Podporuje také streamování velkých souborů, zachování typů atributů a může být kombinována s vlastními transformacemi geometrie, pokud je to potřeba.

```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Add attributes
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    // Construct and add features
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```

## Krok 1: Nastavit GeoJSON vrstvu
Vytvořte dočasný soubor GeoJSON, který obsahuje atributy a prvky, jež chcete převést. Tento příklad přidává dva jednoduché bodové prvky.

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## Krok 2: Zkopírovat testovací dataset
Aby originální testovací data zůstala nedotčena, duplikujte existující dataset File GDB. Tím zajistíte čisté prostředí pro konverzi.

```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copy attributes
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Add features
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```

## Krok 3: Převést GeoJSON na GDB
`FileGdb` představuje kontejner File Geodatabase a poskytuje metody pro správu vrstev. Otevřete vrstvu GeoJSON, vytvořte novou vrstvu v zkopírovaném File GDB, zkopírujte atributy a přeneste každý prvek. Toto je jádro procesu **Aspose.GIS conversion**.

CODE_BLOCK_PLACEHOLDER_4_END

## Jak převést GeoJSON na GDB?
Načtěte GeoJSON pomocí `GeoJsonReader`, vytvořte objekt `FileGdb` ukazující na cílovou složku, vytvořte novou vrstvu prvků a poté iterujte přes každý prvek a vložte jej. V praxi jde o tříkrokový tok – načíst, vytvořit, zkopírovat – který dokončí převod za méně než minutu pro typické datasety.

## Časté problémy a řešení
- **Chybějící prostorová reference:** Ujistěte se, že zdrojový GeoJSON obsahuje definici CRS nebo explicitně nastavte `SpatialReferenceSystem.Wgs84` při vytváření vrstvy GDB.  
- **Neshoda typů atributů:** Datové typy atributů v GeoJSON musí odpovídat cílovému schématu; jinak Aspose.GIS vyhodí výjimku.  
- **Chyby přístupu k souboru:** Ověřte, že cílová složka má oprávnění k zápisu a že žádný jiný proces neblokuje soubory GDB.

## Často kladené otázky
### Je Aspose.GIS kompatibilní s nejnovějším .NET Frameworkem?
Ano, Aspose.GIS funguje s .NET Framework 4.5+, .NET Core 3.1+, .NET 5 a .NET 6+.

### Mohu pomocí Aspose.GIS převádět i jiné geoprostorové formáty?
Rozhodně! Aspose.GIS podporuje více než 30 vstupních a výstupních formátů, včetně Shapefile, KML, GML a SQLite.

### Je k dispozici zkušební verze pro Aspose.GIS?
Ano, můžete si vyzkoušet funkce Aspose.GIS stažením zkušební verze [zde](https://releases.aspose.com/).

### Jak mohu získat podporu pro dotazy související s Aspose.GIS?
Navštivte Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) pro specializovanou pomoc od komunity a produktového týmu.

### Mohu získat dočasnou licenci pro Aspose.GIS?
Ano, dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-06-20  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Související návody

- [Vytvořit .NET dataset File Geodatabase s Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Číst prvky z File Geodatabase v Aspose.GIS](/gis/net/layer-data-operations/read-features-from-file-geodatabase/)
- [Vytvořit vektorovou vrstvu v File GDB – Aspose.GIS .NET tutoriál](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
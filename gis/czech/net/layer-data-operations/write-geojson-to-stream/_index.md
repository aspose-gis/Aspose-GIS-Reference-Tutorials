---
date: 2026-05-21
description: Naučte se, jak zapisovat GeoJSON do proudu pomocí Aspose.GIS pro .NET.
  Tento geojson tutoriál .net ukazuje krok za krokem převod bodů a generování GeoJSON
  C# kódu.
keywords:
- how to write geojson
- convert points geojson
- geojson tutorial .net
- generate geojson c#
linktitle: Zapsat GeoJSON do proudu
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to write GeoJSON to stream using Aspose.GIS for .NET. This
    geojson tutorial .net shows step‑by‑step conversion of points and generation of
    GeoJSON C# code.
  headline: How to Write GeoJSON to Stream with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Jak zapisovat GeoJSON do proudu pomocí Aspose.GIS pro .NET
url: /cs/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zapsat GeoJSON do proudu

## Úvod
V tomto tutoriálu se naučíte **jak zapsat GeoJSON do proudu** v .NET aplikaci pomocí Aspose.GIS. Provedeme vás každým krokem, od nastavení prostředí až po výstup platného GeoJSON dokumentu, abyste mohli bezproblémově integrovat geoprostorová data do svých služeb.

## Rychlé odpovědi
- **Jaká třída je primární pro výstup GeoJSON?** `VectorLayer` s `GeoJsonDriver`.
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Mohu převést kolekce bodů na GeoJSON?** Ano – použijte třídu `Feature` a definujte geometrii bodu.
- **Je streamování podporováno pro velké datové sady?** Rozhodně; `MemoryStream` vám umožní zapisovat bez mezisouborů.

## Co je GeoJSON?
GeoJSON je otevřený standardní formát pro kódování různých geografických datových struktur pomocí JSON. Definuje objekty jako FeatureCollection, Feature a typy geometrie (Point, LineString, Polygon). Toto lehké, web‑přátelské reprezentace umožňuje snadnou výměnu a vizualizaci prostorových dat napříč mnoha platformami a programovacími jazyky.

## Proč použít Aspose.GIS pro generování GeoJSON?
Aspose.GIS podporuje více než 30 prostorových formátů souborů a dokáže zpracovávat soubory větší než 2 GB, aniž by načítal celý dokument do paměti. Jeho výkonný streamingový engine zapisuje GeoJSON přímo do proudů, čímž snižuje I/O režii. To jej činí ideálním pro podnikovou úroveň geoprostorových úloh, cloudové služby a aplikace v reálném čase.

## Předpoklady
Než se ponoříme do tutoriálu, ujistěte se, že máte následující předpoklady:
1. Aspose.GIS pro .NET Library: Ujistěte se, že máte nainstalovanou knihovnu Aspose.GIS pro .NET. Můžete si ji stáhnout [zde](https://releases.aspose.com/gis/net/).
2. Dokumentový adresář: Mějte v projektu nastavený dokumentový adresář a poznamenejte si jeho cestu.

Nyní začněme s tutoriálem!

## Jak zapsat GeoJSON do proudu?
VectorLayer představuje vektorovou datovou sadu, kterou lze uložit v různých formátech, včetně GeoJSON.  
GeoJsonDriver je ovladač používaný Aspose.GIS pro čtení a zápis souborů GeoJSON.  
`layer.Save` zapisuje obsah vrstvy do poskytnutého proudu pomocí specifikovaných možností uložení.

Načtěte `VectorLayer` s `GeoJsonDriver`, přidejte prvky, které obsahují geometrii bodu, a poté zavolejte `layer.Save(stream, new GeoJsonSaveOptions())`. Tím se kompletní, standardy‑vyhovující GeoJSON dokument zapíše přímo do poskytnutého `MemoryStream` během několika řádků kódu. Metoda serializuje kolekci prvků, automaticky zpracovává atributová data a konverzi geometrie, takže získáte připravený JSON payload bez ruční manipulace s řetězci.

## Importujte jmenné prostory
Nejprve se ujistěte, že zahrnujete potřebné jmenné prostory pro přístup k funkcím Aspose.GIS ve vašem kódu:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Krok 1: Nastavte dokumentový adresář
```csharp
string dataDir = "Your Document Directory";
```
Nahraďte „Your Document Directory“ skutečnou cestou k vašemu dokumentovému adresáři.

## Krok 2: Vytvořte Memory Stream
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Krok 3: Vytvořte Vector Layer s GeoJSON ovladačem
Třída `VectorLayer` představuje vektorovou datovou sadu, kterou lze uložit v různých formátech, včetně GeoJSON.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Krok 4: Definujte atributy prvku
Definujte schéma atributů pro vaše prvky (např. ID, Name).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Krok 5: Vytvořte a přidejte prvky
Vytvořte objekty `Feature`, přiřaďte geometrii bodu, nastavte hodnoty atributů a přidejte je do vrstvy.  
```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## Krok 6: Zobrazte výstup GeoJSON
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Gratulujeme! Úspěšně jste zapsali GeoJSON do proudu pomocí Aspose.GIS pro .NET.

## Časté problémy a řešení
- **Prázdný výstupní proud:** Ujistěte se, že před čtením resetujete pozici proudu (`stream.Position = 0`).
- **Nesprávné pořadí souřadnic:** GeoJSON očekává pořadí longitude‑latitude; ověřte hodnoty vašich bodů.
- **Velké datové sady:** Použijte `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` pro postupné streamování prvků.

## Často kladené otázky
### Mohu použít Aspose.GIS pro .NET jak v prostředí Windows, tak Linux?
Ano, Aspose.GIS pro .NET je kompatibilní jak s Windows, tak s Linux systémy.  

### Je k dispozici bezplatná zkušební verze?
Rozhodně! Bezplatnou zkušební verzi můžete vyzkoušet [zde](https://releases.aspose.com/).  

### Kde najdu podrobnou dokumentaci?
Podívejte se na dokumentaci [zde](https://reference.aspose.com/gis/net/).  

### Jak získat dočasnou licenci?
Dočasné licence jsou k dispozici [zde](https://purchase.aspose.com/temporary-license/).  

### Potřebujete pomoc nebo máte další otázky?
Navštivte naše fórum podpory [zde](https://forum.aspose.com/c/gis/33).  

**Q: Mohu generovat GeoJSON ze sbírky bodů latitude/longitude?**  
**A: Ano – vytvořte `Feature` pro každý bod, přiřaďte geometrii `Point` a přidejte jej do `VectorLayer`.**  

**Q: Podporuje Aspose.GIS zápis komprimovaného GeoJSON (gzip)?**  
**A: Můžete obalit `MemoryStream` do `GZipStream` před uložením, abyste vytvořili komprimovaný payload.**  

**Q: Jaká je maximální velikost souboru GeoJSON, kterou Aspose.GIS zvládne?**  
**A: Knihovna může streamovat soubory přesahující 2 GB; využití paměti zůstává nízké, protože data jsou zapisována postupně.**  

---

**Poslední aktualizace:** 2026-05-21  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak číst GeoJSON ze streamu s Aspose.GIS pro .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Jak převést GeoJSON na TopoJSON pomocí Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Jak převést Shapefile na GeoJSON pomocí Aspose.GIS pro .NET](/gis/net/layer-management/extract-features-to-geojson/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
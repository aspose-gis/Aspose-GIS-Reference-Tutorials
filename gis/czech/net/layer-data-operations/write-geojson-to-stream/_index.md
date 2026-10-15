---
date: 2026-10-15
description: Naučte se, jak vytvořit GeoJSON ze souřadnic a zapsat jej do proudu pomocí
  Aspose.GIS pro .NET. Tento tutoriál ukazuje krok za krokem převod bodů a generování
  kódu GeoJSON v C#.
keywords:
- create geojson from coordinates
- stream large geojson files
- write geojson to stream
- geojson tutorial c#
- compress geojson with gzip
lastmod: 2026-10-15
linktitle: Zapsat GeoJSON do proudu
og_description: Naučte se, jak vytvořit GeoJSON ze souřadnic a zapsat jej do proudu
  pomocí Aspose.GIS pro .NET – krok za krokem průvodce pro velké datové sady.
og_image_alt: Screenshot of Aspose.GIS code generating GeoJSON stream in C#
og_title: Vytvořte GeoJSON ze souřadnic, zapište do proudu v .NET
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create geojson from coordinates and write it to a stream
    using Aspose.GIS for .NET. This tutorial shows step‑by‑step conversion of points
    and generation of GeoJSON C# code.
  headline: Create geojson from coordinates, write to a stream in .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET geospatial
- C# stream processing
- GIS data conversion
title: Vytvořte GeoJSON ze souřadnic, zapište do proudu v .NET
url: /cs/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte geojson ze souřadnic a zapište jej do proudu

## Úvod
V tomto tutoriálu se naučíte **jak vytvořit geojson ze souřadnic** a zapsat jej přímo do proudu pomocí Aspose.GIS pro .NET. Provedeme vás nastavením prostředí, vytvořením vrstvy, naplněním prvků a streamováním výsledku, abyste mohli vkládat geoprostorová data do API, cloudových funkcí nebo služeb bez souborů, bez dočasných souborů.

## Rychlé odpovědi
- **Jaká třída zapisuje GeoJSON do proudu?** `VectorLayer` together with the `GeoJsonDriver`.
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Mohu převést kolekce bodů na GeoJSON?** Ano – vytvořte `Feature` pro každý bod a přiřaďte geometrii `Point`.
- **Je streamování vhodné pro velké datové sady?** Rozhodně – `MemoryStream` vám umožní zapisovat GeoJSON v gigabajtovém měřítku, aniž byste načítali celý soubor do paměti.

## Co je GeoJSON?
GeoJSON je otevřený formát založený na JSON pro kódování geografických prvků, jako jsou body, linie a polygonů. Skládá se z `FeatureCollection`, která seskupuje jednotlivé objekty `Feature`, z nichž každý obsahuje geometrii a atributová data. Díky své lehkosti a webové přívětivosti je GeoJSON de‑facto standardem pro výměnu prostorových dat mezi prohlížeči, GIS servery a mobilními aplikacemi.

## Proč použít Aspose.GIS pro generování geojson?
Aspose.GIS podporuje **35+ prostorových formátů souborů** a může streamovat soubory větší než **2 GB**, přičemž využití paměti zůstává pod **50 MB**. Jeho vysoce výkonný streamingový engine zapisuje GeoJSON přímo do libovolného .NET `Stream`, čímž eliminuje potřebu mezilehlých dočasných souborů a snižuje latenci I/O až o **70 %** v typických cloudových scénářích.

## Předpoklady
Než začnete, ujistěte se, že máte:

1. **Aspose.GIS for .NET** nainstalováno. Stáhněte balíček **Aspose.GIS for .NET** [zde](https://releases.aspose.com/gis/net/).
2. Zapisovatelný adresář ve vašem projektu, kam můžete umístit dočasné soubory, pokud bude potřeba.
3. Nainstalované runtime .NET 5+ nebo .NET Core 3.1+.

Nyní se ponořme do implementace.

## Jak vytvořit geojson ze souřadnic a zapsat jej do proudu?
`VectorLayer` představuje v‑paměti vektorový dataset, který lze uložit v různých formátech.  
`GeoJsonDriver` je ovladač, který umožňuje čtení a zápis souborů GeoJSON.  

Načtěte `VectorLayer` pomocí `GeoJsonDriver`, přidejte objekty `Feature`, které obsahují geometrii `Point`, a zavolejte `layer.Save(stream, new GeoJsonSaveOptions())`. Tento jediný volání serializuje celou kolekci prvků do standardům vyhovujícího GeoJSON dokumentu, který se nachází v předaném `MemoryStream`. Proces automaticky zpracuje mapování atributů a konverzi souřadnic, takže získáte připravený JSON payload bez ručního sestavování řetězců.

### Definice ukotvení
**VectorLayer** je hlavní objekt Aspose.GIS, který představuje měnitelný vektorový dataset v paměti.  
**GeoJsonDriver** je ovladač zodpovědný za čtení a zápis souborů GeoJSON.

## Importujte jmenné prostory
Nejprve se ujistěte, že zahrnujete potřebné jmenné prostory pro přístup k funkcím Aspose.GIS ve vašem kódu:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Krok 1: nastavení adresáře dokumentů
Vytvořte cestu k adresáři, kde může Aspose.GIS uložit pomocné soubory, pokud je to potřeba.  
```csharp
string dataDir = "Your Document Directory";
```
Nahraďte „Your Document Directory“ skutečnou cestou k vašemu adresáři dokumentů.

## Krok 2: vytvoření paměťového proudu
`MemoryStream` poskytuje paměťový buffer, který může být odeslán přímo přes HTTP nebo uložen do cloudového úložiště.  
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Krok 3: vytvoření vektorové vrstvy s GeoJSON ovladačem
Třída `VectorLayer` představuje vektorový dataset, který lze uložit v různých formátech, včetně GeoJSON.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Krok 4: definování atributů prvků
Definujte schéma atributů pro vaše prvky (např. ID, Název).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Krok 5: vytvoření a přidání prvků
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

## Krok 6: zobrazení výstupu GeoJSON
Po uložení resetujte pozici proudu a přečtěte JSON řetězec pro ověření nebo přenos.  
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Gratulujeme! Úspěšně jste vytvořili geojson ze souřadnic a zapsali jej do proudu pomocí Aspose.GIS pro .NET.

## Časté problémy a řešení
- **Prázdný výstupní proud:** Ujistěte se, že před čtením resetujete pozici proudu (`stream.Position = 0`).
- **Nesprávné pořadí souřadnic:** GeoJSON očekává pořadí longitude‑latitude; ověřte hodnoty vašich bodů.
- **Velké datové sady:** Použijte `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` pro inkrementální streamování prvků a udržení nízké spotřeby paměti.

## Často kladené otázky

**Q: Mohu použít Aspose.GIS pro .NET jak v prostředí Windows, tak Linux?**  
A: Ano, Aspose.GIS pro .NET běží na Windows, Linuxu i macOS s plnou podporou .NET Core.

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Rozhodně! Můžete prozkoumat **stránku ke stažení bezplatné zkušební verze** [zde](https://releases.aspose.com/).

**Q: Kde najdu podrobnou dokumentaci?**  
A: Podívejte se na **dokumentaci Aspose.GIS .NET** [zde](https://reference.aspose.com/gis/net/).

**Q: Jak získat dočasnou licenci?**  
A: Dočasné licence jsou k dispozici na **stránce dočasné licence** [zde](https://purchase.aspose.com/temporary-license/).

**Q: Potřebujete pomoc nebo máte další otázky?**  
A: Navštivte naše **GIS fórum podpory** [zde](https://forum.aspose.com/c/gis/33).

**Q: Mohu generovat GeoJSON ze sbírky bodů latitude/longitude?**  
A: Ano – vytvořte `Feature` pro každý bod, přiřaďte geometrii `Point` a přidejte jej do `VectorLayer`.

**Q: Podporuje Aspose.GIS zápis komprimovaného GeoJSON (gzip)?**  
A: Můžete obalit `MemoryStream` do `GZipStream` před uložením, abyste vytvořili komprimovaný payload.

**Q: Jaká je maximální velikost souboru GeoJSON, kterou Aspose.GIS dokáže zpracovat?**  
A: Knihovna může streamovat soubory přesahující 2 GB; využití paměti zůstává nízké, protože data jsou zapisována inkrementálně.

---

**Poslední aktualizace:** 2026-10-15  
**Testováno s:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

## Související tutoriály

- [Jak číst GeoJSON ze streamu s Aspose.GIS pro .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Jak převést GeoJSON na TopoJSON s Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Jak převést Shapefile na GeoJSON pomocí Aspose.GIS pro .NET](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
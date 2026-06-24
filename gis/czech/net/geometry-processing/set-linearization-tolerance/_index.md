---
date: 2026-05-31
description: Naučte se, jak vytvořit GeoJSON, nakonfigurovat možnosti GeoJSON a přidat
  prvek do vrstvy pomocí Aspose.GIS pro .NET. Postupujte podle tohoto krok‑za‑krokem
  průvodce.
keywords:
- how to create geojson
- add feature to layer
- configure geojson options
linktitle: Nastavit toleranci linearizace
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  headline: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  name: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  steps:
  - name: Configure GeoJSON Options (how to set tolerance)
    text: '`GeoJsonOptions` specifies the serialization settings used when writing
      GeoJSON files. `GeoJsonOptions` defines how Aspose.GIS serializes GeoJSON, including
      linearization tolerance, coordinate precision, and other output settings. We’ll
      create a `GeoJsonOptions` object and tell Aspose.GIS how close '
  - name: Define the Output Path (how to export GeoJSON)
    text: Specify the full file path where the resulting GeoJSON will be saved. Ensure
      the folder exists and the application has write permissions.
  - name: '**Create Vector Layer** with the configured options'
    text: The `VectorLayer` class represents a GIS container that can read and write
      spatial data. `Drivers.GeoJson` is the driver identifier for writing GeoJSON
      format files. Using `VectorLayer.Create` together with the `Drivers.GeoJson`
      driver and the previously configured `GeoJsonOptions` creates a new Geo
  - name: Construct a Geometry (e.g., a circular string)
    text: '`CircularString` is a curved line geometry that Aspose.GIS can linearize
      based on the tolerance you set. You can replace this with any valid WKT representation
      such as `POINT`, `LINESTRING`, or `POLYGON`.'
  - name: '**Add Feature to Layer** and save'
    text: '`Feature` is the object that couples a geometry with attribute data. After
      creating a `Feature` instance, assign the geometry, optionally add attribute
      values, and call `layer.Add(feature)` to persist it. When the `using` block
      ends, the layer is automatically written to the file defined in `path`. '
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. A commercial license removes all evaluation restrictions and
      provides full technical support.
    question: Can I use Aspose.GIS in commercial projects?
  - answer: Yes, it supports over 30 formats—including Shapefile, KML, GML, and CSV—allowing
      seamless conversion between them.
    question: Does Aspose.GIS support other GIS formats besides GeoJSON?
  - answer: You can download a free 30‑day trial from the Aspose website; it includes
      all features.
    question: Is there a trial version available?
  - answer: Use the Aspose forums, the dedicated support portal, or the “Contact Support”
      link in the product dashboard.
    question: Where can I get support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Jak vytvořit GeoJSON s tolerancí pomocí Aspose.GIS pro .NET
url: /cs/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit GeoJSON s tolerancí Aspose.GIS pro .NET

## Úvod
Pokud chcete **naučit se, jak vytvořit GeoJSON** soubory, řídit přesnost křivek a exportovat výsledek jako připravený dokument, Aspose.GIS pro .NET to usnadňuje. V tomto tutoriálu zjistíte, jak konfigurovat možnosti GeoJSON, nastavit toleranci linearizace a **add feature to layer** objekty, přičemž kód zůstane čistý a připravený pro produkci.

## Rychlé odpovědi
- **Co znamená „create vector layer“?** Vytváří nový GIS vektorový dataset (např. soubor GeoJSON), který může ukládat geometrie a atributy.  
- **Jak nastavit toleranci linearizace?** Nastavte vlastnost `LinearizationTolerance` na instanci `GeoJsonOptions` před vytvořením vrstvy.  
- **Mohu exportovat soubor GeoJSON přímo?** Ano—použijte `VectorLayer.Create` s ovladačem `Drivers.GeoJson` a nakonfigurovanými možnostmi.  
- **Potřebuji licenci?** Platná licence Aspose.GIS odemkne všechny funkce; dočasný evaluační klíč funguje pro testování.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co znamená „create vector layer“?
Vytvoření vektorové vrstvy znamená inicializaci nového GIS kontejneru (např. souboru GeoJSON), který může obsahovat body, linie, polygonové tvary a související atributová data. Tato vrstva se stane cílem pro jakoukoli geometrii, kterou vytvoříte, a pro všechny atributy, které připojíte.

## Proč konfigurovat možnosti GeoJSON?
Konfigurace možností GeoJSON—zejména **linearization tolerance**—zajišťuje, že zakřivené geometrie (např. `CircularString`) jsou aproximovány s přesností, která splňuje požadavky na přesnost vaší aplikace. Správná konfigurace snižuje velikost souboru při zachování vizuální věrnosti, což je kritické, když je GeoJSON používán webovými mapami nebo nástroji pro prostorovou analytiku.

## Požadavky
Před zahájením se ujistěte, že máte:

1. **Visual Studio** (jakoukoli nedávnou verzi).  
2. **Licenci Aspose.GIS** (nebo dočasný evaluační klíč).  
3. Knihovnu **Aspose.GIS for .NET** přidanou do vašeho projektu.  
4. Základní znalost **C#**.

## Importovat jmenné prostory
Nejprve importujte požadované jmenné prostory, aby kompilátor věděl, kde najít GIS třídy:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Postupný návod

### Krok 1: Konfigurace možností GeoJSON (jak nastavit toleranci)
`GeoJsonOptions` určuje nastavení serializace používané při zápisu souborů GeoJSON.  
`GeoJsonOptions` definuje, jak Aspose.GIS serializuje GeoJSON, včetně tolerance linearizace, přesnosti souřadnic a dalších výstupních nastavení.  
Vytvoříme objekt `GeoJsonOptions` a řekneme Aspose.GIS, jak blízko musí být linearizovaná geometrie k původní křivce.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Krok 2: Definování výstupní cesty (jak exportovat GeoJSON)
Zadejte úplnou cestu k souboru, kam bude výsledný GeoJSON uložen. Ujistěte se, že složka existuje a aplikace má oprávnění k zápisu.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Krok 3: **Create Vector Layer** s nakonfigurovanými možnostmi
Třída `VectorLayer` představuje GIS kontejner, který může číst a zapisovat prostorová data.  
`Drivers.GeoJson` je identifikátor ovladače pro zápis souborů ve formátu GeoJSON.  
Použití `VectorLayer.Create` spolu s ovladačem `Drivers.GeoJson` a dříve nakonfigurovanými `GeoJsonOptions` vytvoří nový soubor GeoJSON připravený pro vkládání prvků.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Krok 4: Vytvoření geometrie (např. kruhový řetězec)
`CircularString` je zakřivená linie, kterou Aspose.GIS může linearizovat na základě nastavené tolerance. Můžete ji nahradit libovolnou platnou WKT reprezentací, jako je `POINT`, `LINESTRING` nebo `POLYGON`.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Krok 5: **Add Feature to Layer** a uložit
`Feature` je objekt, který spojuje geometrii s atributovými daty. Po vytvoření instance `Feature` přiřaďte geometrii, volitelně přidejte hodnoty atributů a zavolejte `layer.Add(feature)`, aby se uložila. Když se ukončí blok `using`, vrstva se automaticky zapíše do souboru definovaného v `path`.

Když se ukončí blok `using`, vrstva se automaticky zapíše do souboru definovaného v `path`, což vám poskytne připravený GeoJSON soubor.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

## Časté problémy a tipy
- **Nesprávná cesta** – Ověřte, že adresář existuje a máte oprávnění k zápisu.  
- **Příliš nízká tolerance** – Nastavení `LinearizationTolerance` na velmi malou hodnotu může dramaticky zvýšit velikost souboru; tolerance 0,001 obvykle vyvažuje přesnost a velikost.  
- **Chyby licence** – Pokud vidíte varování o licenci, ujistěte se, že soubor licence je načten před jakýmikoli voláními Aspose.GIS.  
- **Poznámka k výkonu** – Aspose.GIS podporuje zpracování souborů až do 2 GB bez načítání celého dokumentu do paměti díky své streamovací architektuře.

## Často kladené otázky

**Q: Je Aspose.GIS pro .NET kompatibilní s jinými .NET frameworky?**  
A: Ano, funguje s .NET Framework 4.5+, .NET Core 3.1+ a .NET 5/6/7.

**Q: Mohu používat Aspose.GIS v komerčních projektech?**  
A: Rozhodně. Komerční licence odstraňuje všechna omezení hodnocení a poskytuje plnou technickou podporu.

**Q: Podporuje Aspose.GIS i jiné GIS formáty kromě GeoJSON?**  
A: Ano, podporuje více než 30 formátů – včetně Shapefile, KML, GML a CSV – což umožňuje bezproblémovou konverzi mezi nimi.

**Q: Je k dispozici zkušební verze?**  
A: Můžete si stáhnout bezplatnou 30‑denní zkušební verzi z webu Aspose; obsahuje všechny funkce.

**Q: Kde mohu získat podporu?**  
A: Použijte fóra Aspose, vyhrazený portál podpory nebo odkaz „Contact Support“ v přehledu produktu.

## Závěr
Po provedení těchto kroků nyní víte **jak vytvořit GeoJSON**, nakonfigurovat toleranci linearizace a **add feature to layer** pro bezproblémový export GeoJSON. Prozkoumejte další typy geometrie, práci s atributy a scénáře hromadného zpracování, abyste plně využili Aspose.GIS ve svých .NET GIS projektech.

---

**Poslední aktualizace:** 2026-05-31  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak převést GeoJSON – Aspose.GIS pro .NET](/gis/net/geo-data-conversion/)
- [Vytvořit vektorovou vrstvu, omezit přesnost pomocí Aspose.GIS pro .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Vytvořit vektorovou vrstvu v souboru GDB – Aspose.GIS .NET tutoriál](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
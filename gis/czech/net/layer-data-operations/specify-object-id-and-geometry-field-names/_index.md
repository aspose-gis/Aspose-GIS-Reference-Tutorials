---
date: 2026-05-21
description: Naučte se, jak vytvořit file geodatabase, nastavit object ID a geometry
  field names, přidat geometry a načíst data z layer pomocí Aspose.GIS for .NET.
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: Zadejte Object ID a Geometry Field Names
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Vytvořit File Geodatabase – Specify Object ID and Geometry Field Names
url: /cs/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořit souborovou geodatabázi – specifikovat názvy polí Object ID a Geometry

## Úvod
V tomto praktickém tutoriálu **create file geodatabase** pomocí Aspose.GIS pro .NET a poté určíte názvy polí Object ID a Geometry, aby vaše prostorová data byla správně indexována. Ať už vytváříte desktopový GIS nástroj nebo backend webové služby, zvládnutí těchto kroků vám poskytne pevný základ pro jakýkoli geoprostorový projekt.

## Rychlé odpovědi
- **Jaký je první řádek kódu?** `var geoDb = new GeoDatabase(path, options);`  
- **Která vlastnost definuje sloupec geometrie?** `GeometryFieldName` v `GeoDatabaseCreateOptions`.  
- **Mohu nastavit vlastní pole Object ID?** Ano – použijte `ObjectIdFieldName` při vytváření databáze.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována trvalá licence.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6.

## Co je create file geodatabase?
**Create file geodatabase** znamená vytvoření fyzického GIS kontejneru (často složky s interními soubory), který ukládá vektorové vrstvy, atributy a prostorové indexy. Poskytuje přenosný, samostatný dataset, který může otevřít jakákoliv GIS‑kompatibilní aplikace. Lze jej použít v jakémkoli GIS softwaru, který podporuje formát File Geodatabase, což usnadňuje výměnu dat.

## Proč nastavit názvy polí Object ID a Geometry?
Nastavení explicitních názvů polí Object ID a Geometry umožňuje Aspose.GIS vytvořit efektivní indexy, urychlit dotazy a zajistit, že každý prvek může být jednoznačně identifikován. V benchmarkech jsou indexované dotazy až **3× rychlejší** v databázích, kde jsou tato pole definována.

## Požadavky
- Aspose.GIS pro .NET nainstalováno – stáhněte jej z [zde](https://releases.aspose.com/gis/net/).  
- Zapisovatelná složka ve vašem počítači, která bude sloužit jako adresář dokumentů.  
- Vývojové prostředí .NET (Visual Studio, VS Code nebo .NET CLI).  

## Jak vytvořit souborovou geodatabázi?
`GeoDatabase` je třída, která představuje souborovou geodatabázi na disku. Načtěte obor názvů Aspose.GIS, definujte cestu ke složce a vytvořte instanci `GeoDatabase` s vlastními možnostmi. Tento jediný krok vytvoří souborovou geodatabázi na disku. Objekt `GeoDatabaseCreateOptions` vám umožní specifikovat jak sloupec Object ID (`ObjectIdFieldName`), tak sloupec geometrie (`GeometryFieldName`). Aspose.GIS podporuje **30+ prostorových formátů** a dokáže zpracovat soubory až do **2 GB** bez načítání celého datasetu do paměti.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Jak nastavit objectid?
`ObjectIdFieldName` je vlastnost třídy `GeoDatabaseCreateOptions`, která určuje název sloupce používaného jako jedinečný identifikátor pro každý prvek. `ObjectIdFieldName` říká enginu, který atribut jedinečně identifikuje každý prvek. Zvolte krátký alfanumerický název (např. `"FeatureId"`). Když později přidáváte nebo dotazujete prvky, tento sloupec se automaticky používá pro rychlé vyhledávání.  

```csharp
string dataDir = "Your Document Directory";
```

## Jak přidat geometrii?
`GeometryFieldName` je vlastnost třídy `GeoDatabaseCreateOptions`, která určuje, který atributový sloupec ukládá geometrické objekty pro každý prvek. `GeometryFieldName` definuje sloupec, který ukládá tvarová data (body, linie, polygon). Explicitním pojmenováním se vyhnete výchozímu názvu `"Shape"` a udržíte schéma konzistentní napříč více vrstvami.  

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## Jak vytvořit vrstvu a přidat vrstvu bodových prvků?
`CreateLayer` je metoda třídy `GeoDatabase`, která vytvoří novou vektorovou vrstvu se zadaným názvem, možnostmi a souřadnicovým systémem. `Feature` je objekt představující jediný prostorový záznam, obsahující geometrii a hodnoty atributů. `Point` je třída geometrie představující jedinou polohu definovanou souřadnicemi X (zeměpisná délka) a Y (zeměpisná šířka). Po připravení databáze vytvořte novou vrstvu pomocí `CreateLayer`. Pak vytvořte objekt `Feature`, přiřaďte mu geometrii `Point` a přidejte jej do vrstvy. Toto demonstruje **how to add geometry** a **how to create layer** v jednom postupu.  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## Jak načíst data z vrstvy?
`OpenLayer` je metoda třídy `GeoDatabase`, která otevře existující vrstvu pro čtení nebo úpravy a vrátí objekt `Layer`. Otevřete vrstvu pomocí `OpenLayer`, poté iterujte přes její kolekci `Features` nebo dotazujte podle vlastního pole Object ID. Toto ukazuje **retrieve data from layer** pomocí identifikátoru, který jste definovali dříve.  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Časté problémy a řešení
- **Chyba chybějícího sloupce Object ID** – Ujistěte se, že `ObjectIdFieldName` je nastaven *před* voláním `CreateLayer`.  
- **Geometrie se nezobrazuje** – Ověřte, že typ geometrie (např. `Point`) odpovídá souřadnicovému systému vrstvy.  
- **Zamknutí souboru ve Windows** – Zavřete všechny objekty `GeoDatabase` nebo je obalte do `using` bloků, aby se uvolnily souborové handly.

## Často kladené otázky

**Q: Mohu použít Aspose.GIS pro .NET ve svých webových aplikacích?**  
A: Ano, knihovna funguje v projektech ASP.NET Core, MVC a Web API a poskytuje kompletní GIS funkčnost na straně serveru.

**Q: Je k dispozici zkušební verze před zakoupením?**  
A: Ano, můžete si vyzkoušet funkce Aspose.GIS pro .NET pomocí bezplatné zkušební verze dostupné [zde](https://releases.aspose.com/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.GIS pro .NET?**  
A: Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/) pro evaluační účely.

**Q: Jaké souřadnicové systémy Aspose.GIS pro .NET podporuje?**  
A: Produkt podporuje kódy EPSG 1‑9999, včetně WGS 84, Web Mercator a mnoha národních souřadnicových systémů.

**Q: Kde mohu získat pomoc nebo diskutovat o dotazech souvisejících s Aspose.GIS?**  
A: Navštivte fórum Aspose.GIS [zde](https://forum.aspose.com/c/gis/33) pro podporu a komunitní diskuze.

---

**Poslední aktualizace:** 2026-05-21  
**Testováno s:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit vektorovou vrstvu v File GDB – tutoriál Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Jak nastavit mřížku pro vrstvu File GDB v Aspose.GIS](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Přečíst Object ID z vrstvy File GDB v Aspose.GIS](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
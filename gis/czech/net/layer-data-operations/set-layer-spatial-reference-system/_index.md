---
date: 2026-06-15
description: Naučte se, jak vytvořit vektorovou vrstvu a nastavit prostorový referenční
  systém vrstvy pomocí Aspose.GIS for .NET. Ovládněte definování prostorového referenčního
  systému, přidání bodové funkce a získání kódu EPSG.
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: Nastavení prostorového referenčního systému vrstvy
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Vytvoření vektorové vrstvy a nastavení prostorového referenčního systému vrstvy
url: /cs/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření vektorové vrstvy a nastavení prostorového referenčního systému vrstvy

## Úvod
V rozsáhlém prostředí geografických informačních systémů (GIS) **Aspose.GIS pro .NET** vyniká jako robustní, vysoce výkonná knihovna, která podporuje **více než 70** vektorových a rastrových formátů a dokáže zpracovávat soubory větší než **10 GB** bez načítání celého datasetu do paměti. V tomto tutoriálu **vytvoříte vektorovou vrstvu**, definujete její prostorovou referenci, **přidáte bodový prvek** a získáte EPSG kód – vše s jasným, krok za krokem vedením. Ať už budujete mapovou službu, datovou konverzní pipeline nebo engine pro prostorovou analytiku, zvládnutí těchto základů zajistí přesnost souřadnicového systému shapefile a spolehlivost vašeho GIS workflow.

## Rychlé odpovědi
- **Co znamená „vytvoření vektorové vrstvy“?** Vytváří novou GIS vrstvu (např. Shapefile), která může ukládat geometrie jako body, linie nebo polygony.  
- **Kód EPSG použitý v příkladu?** EPSG 26918 (NAD83 / UTM zóna 18N).  
- **Mohu po vytvoření vrstvy přidat bodový prvek?** Ano – použijte `ConstructFeature()` a přiřaďte geometrii `Point`.  
- **Jak získám CRS vrstvy?** Přečtěte `layer.SpatialReferenceSystem.EpsgCode` nebo `.Name`.  
- **Potřebuji licenci pro Aspose.GIS?** Je k dispozici bezplatná zkušební verze; licence je vyžadována pro produkční použití.

## Co je vytvoření vektorové vrstvy?
Operace **vytvoření vektorové vrstvy** vytváří nový vektorový dataset (např. Shapefile), který může obsahovat geometrické prvky a atributová data. V Aspose.GIS se to provádí vytvořením objektu `VectorLayer` s ovladačem a prostorovým referenčním systémem.

## Proč nastavit souřadnicový systém vrstvy (CRS) správně?
Nastavení správného souřadnicového referenčního systému (CRS) zajišťuje, že každá uložená geometrie se slaďuje s ostatními prostorovými datasety. S Aspose.GIS můžete definovat CRS pomocí standardního kódu EPSG, což zaručuje interoperabilitu s GIS softwarem po celém světě. Například EPSG 26918 definuje NAD83 / UTM zóna 18N, běžnou projekci pro data ve východních Spojených státech.

## Požadavky
- Zkušenosti s vývojem v .NET (C# nebo VB.NET).  
- Visual Studio 2022 nebo novější.  
- Knihovna Aspose.GIS pro .NET – stáhněte ji **[zde](https://releases.aspose.com/gis/net/)**.  
- Základní povědomí o prostorových referenčních systémech (CRS/EPSG).

## Import jmenných prostorů
Jmenný prostor `Aspose.Gis` poskytuje základní GIS třídy, zatímco `Aspose.Gis.Geometries` nabízí typy geometrie, jako je `Point`.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Jak vytvořit vektorovou vrstvu v Aspose.GIS pro .NET?
`VectorLayer` představuje vektorový dataset, jako je Shapefile, a poskytuje metody pro vytváření, čtení a úpravu prvků.  
`SpatialReferenceSystem` definuje souřadnicový referenční systém pomocí kódu EPSG.  

Načtěte cílový adresář, definujte EPSG‑kódovaný `SpatialReferenceSystem` a zavolejte `VectorLayer.Create` s ovladačem Shapefile. Tento jediný volání vytvoří nový soubor `.shp`, zapíše přidružené soubory `.shx` a `.dbf` a vloží metadata CRS, připravené pro efektivní vkládání prvků.

### Krok 1: Zadejte adresář dokumentu
Začněte zadáním cesty k vašemu adresáři dokumentů. Toto bude místo, kde budou uloženy soubory s prostorovými daty.

```csharp
string dataDir = "Your Document Directory";
```

### Krok 2: Definujte prostorovou referenci a nastavte souřadnicový systém shapefile
`SpatialReferenceSystem` představuje CRS vrstvy, identifikovaný kódem EPSG.  

Definujte cestu k Shapefile a **definujte prostorovou referenci** pomocí kódu EPSG (26918 v tomto příkladu). Tento krok **nastavuje souřadnicový systém shapefile** pro vrstvu.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Jak přidat bodový prvek do vektorové vrstvy?
`Point` je typ geometrie představující jeden pár souřadnic X/Y.  

Vytvořte nový prvek, přiřaďte mu geometrii `Point` s požadovanými souřadnicemi X/Y a přidejte prvek do otevřené `VectorLayer`. Operace zapíše geometrii do souboru `.shp` a atributový záznam do souboru `.dbf` v jedné transakci.

### Krok 3: Vytvořit vektorovou vrstvu
`ConstructFeature` vytváří nový objekt prvku, který může obsahovat geometrii a atributová data.  

Nyní **vytvořte vektorovou vrstvu** s určenou cestou k Shapefile, typem ovladače (Shapefile) a prostorovým referenčním systémem, který jste právě definovali.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### Krok 4: Přidat bodový prvek do vrstvy
Vytvořte nový prvek a **přidejte bodový prvek** nastavením jeho geometrie (`Point` s souřadnicemi 60, 24). Poté přidejte prvek do vektorové vrstvy.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### Krok 5: Získat informace o prostorovém referenčním systému (získat EPSG kód)
Otevřete vektorovou vrstvu a získejte informace o prostorovém referenčním systému, jako je EPSG kód a čitelný název. Toto ukazuje, jak **získat EPSG kód** a **nastavit CRS vrstvy**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## Časté problémy a řešení
| Problém | Proč k tomu dochází | Řešení |
|-------|----------------|-----|
| **Vrstva se nepodařilo otevřít** | Špatný ovladač nebo poškozená cesta k souboru | Ověřte `Drivers.Shapefile` a ujistěte se, že `path` ukazuje na existující soubor `.shp`. |
| **Zobrazený CRS je nesprávný** | Použití špatného kódu EPSG | Zkontrolujte kód EPSG u autoritativního zdroje (např. EPSG.io). |
| **Prvek nebyl uložen** | Nevolání `layer.Add(feature)` uvnitř bloku `using` | Zajistěte, aby metoda `Add` byla vykonána před uvolněním vrstvy. |

## Často kladené otázky
**Q: Jak změním CRS existujícího Shapefile?**  
A: Otevřete vrstvu, vytvořte nový `SpatialReferenceSystem` s požadovaným kódem EPSG, přiřaďte jej k `layer.SpatialReferenceSystem` a poté vrstvu uložte.

**Q: Mohu pomocí stejného přístupu přidat jiné typy geometrie (např. polygony)?**  
A: Ano – nahraďte `new Point(x, y)` za `new Polygon(...)` nebo `new LineString(...)` podle potřeby.

**Q: Je možné efektivně pracovat s velkými datasety?**  
A: Použijte streamingové API (`VectorLayer.Create` s `FeatureCollection`) a vrstvu uvolňujte co nejdříve, aby se uvolnily zdroje.

**Q: Podporuje Aspose.GIS transformaci souřadnic?**  
A: Ano – použijte `Geometry.Transform(targetSrs)` k reprojekci geometrie mezi různými prostorovými referencemi.

**Q: Jaké verze .NET jsou podporovány?**  
A: Aspose.GIS funguje s .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

**Poslední aktualizace:** 2026-06-15  
**Testováno s:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Vytvoření vektorové vrstvy a nastavení tolerance linearizace pomocí Aspose.GIS pro .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Vytvoření vektorové vrstvy v File GDB – Aspose.GIS .NET tutoriál](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [spatial reference wgs84 – Přidání vrstvy do GDB pomocí Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
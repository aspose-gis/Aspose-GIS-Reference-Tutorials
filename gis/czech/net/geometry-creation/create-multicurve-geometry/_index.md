---
date: 2026-09-25
description: Zjistěte, jak převést WKT na compound curve geometry a přidat line string
  v .NET pomocí Aspose.GIS. Tento průvodce ukazuje geometrii vytvořenou z WKT pomocí
  MultiCurve.
keywords:
- compound curve geometry
- geometry from wkt
- add line string .net
lastmod: 2026-09-25
linktitle: Vytvořit MultiCurve geometrii
og_description: Zjistěte, jak převést WKT na compound curve geometry a přidat line
  string v .NET pomocí Aspose.GIS. Tento průvodce ukazuje geometrii vytvořenou z WKT
  pomocí MultiCurve.
og_image_alt: 'Tutorial: Convert WKT to compound curve geometry using Aspose.GIS in
  .NET'
og_title: Převést WKT na compound curve geometry pomocí Aspose.GIS pro .NET
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  headline: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  name: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  steps:
  - name: Define the document directory and file name
    text: Set the folder where the shapefile will be saved. Replace `"Your Document
      Directory"` with the actual path on your machine.
  - name: Initialize a `VectorLayer` with the Shapefile driver
    text: VectorLayer represents a vector dataset such as a shapefile and enables
      reading and writing of geometries. The `VectorLayer` object represents a vector
      dataset (in this case, a shapefile) that you can write geometries to.
  - name: Construct a new feature
    text: Feature is a container that holds a geometry and its attribute values. A
      feature is a container for geometry and attribute data.
  - name: Create a `MultiCurve` geometry instance
    text: '`MultiCurve` is a geometry type that aggregates multiple curve components
      into a single spatial object. `MultiCurve` can hold several curve geometries,
      allowing you to combine them into a single spatial object.'
  - name: Add curve geometries to the `MultiCurve`
    text: 'Here we **convert WKT to geometry** for three different curve types: *
      a simple **line string**, * a circular arc (`CircularString`), * and a compound
      curve that mixes straight segments with a circular arc.'
  - name: Assign the `MultiCurve` to the feature
    text: Now the feature’s geometry is the composite `MultiCurve` we just built.
  - name: Add the feature to the `VectorLayer`
    text: The feature is persisted to the shapefile when the `using` block ends.
  type: HowTo
- questions:
  - answer: Yes, it supports .NET Framework, .NET Core, .NET Standard, and .NET 5/6+.
    question: Is Aspose.GIS for .NET compatible with all versions of the .NET Framework?
  - answer: Absolutely. The API lets you read, write, and transform many standard
      formats, and you can extend it for proprietary ones.
    question: Can I create custom spatial data formats using Aspose.GIS for .NET?
  - answer: Yes, it includes distance calculations, intersection detection, buffering,
      and other geometric operations.
    question: Does Aspose.GIS provide spatial analysis capabilities?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/)
      to explore its features before purchasing.
    question: Is there a trial version available for Aspose.GIS for .NET?
  - answer: Reach out via the Aspose.GIS community forums or consult the official
      support resources included with your license.
    question: How can I get help if I encounter problems?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- compound curve geometry
- Aspose.GIS
- C# GIS
- MultiCurve
- WKT conversion
title: Převést WKT na compound curve geometry pomocí Aspose.GIS pro .NET
url: /cs/net/geometry-creation/create-multicurve-geometry/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod WKT na složenou křivku geometrie pomocí Aspose.GIS pro .NET

## Úvod
Pokud potřebujete **převést WKT na složenou křivku geometrie** v .NET GIS aplikaci, Aspose.GIS proces usnadní a učiní jej spolehlivým. V tomto tutoriálu vás provedeme vytvořením geometrie `MultiCurve` z řetězců Well‑Known Text (WKT) – ideální pro situace, kdy potřebujete **přidat řetězec úseček**, kruhové oblouky nebo složené křivky k jedné entitě. Na konci budete mít připravený shapefile, který ukazuje, jak zkombinovat více křivkových geometrií do jednoho objektu `MultiCurve`.

## Rychlé odpovědi
- **Co znamená „převod WKT na geometrie“?** Znamená to převést textovou reprezentaci WKT na konkrétní geometrický objekt, který mohou GIS knihovny manipulovat.  
- **Která třída Aspose.GIS zpracovává WKT?** `Geometry.FromText()` parsuje WKT řetězce do instancí geometrie.  
- **Mohu přidat jednoduchý řetězec úseček?** Ano – stačí zahrnout WKT `LineString` jako `"LineString (0 0, 1 0)"`.  
- **Jaký formát souboru se používá v příkladu?** Shapefile (`.shp`) vytvořený pomocí ovladače Shapefile.  
- **Potřebuji licenci pro vývoj?** Pro testování stačí bezplatná zkušební verze; pro produkční nasazení je vyžadována komerční licence.

## Co je „převod WKT na geometrie“?
Převod WKT na geometrie parsuje textový formát Well‑Known Text do objektového modelu v paměti, jako je `MultiCurve` nebo `LineString`. **`Geometry.FromText`** okamžitě vytváří tyto objekty, což vám umožní je ukládat, dotazovat a vykreslovat v jakémkoli GIS nástroji podporujícím standard OGC.

## Proč použít Aspose.GIS pro vytvoření MultiCurve?
Aspose.GIS vám umožní vytvořit **složenou křivku geometrie** jedním, samostatným voláním API. Podporuje tři pokročilé typy křivek (CircularString, CompoundCurve a CurveString) a zpracovává datové sady až do 500 MB bez načítání celého souboru do paměti, což přináší až 30 % rychlejší výkon oproti konkurenčním knihovnám ve scénářích dávkového zpracování.

## Požadavky
1. Základní znalost programovacího jazyka C#.  
2. Nainstalovaný Visual Studio (nebo jiné .NET IDE).  
3. Knihovna Aspose.GIS pro .NET – stáhněte ji z [Aspose.GIS website](https://releases.aspose.com/gis/net/).  
4. Znalost prostorových pojmů jako body, úseky a křivky.

## Importování jmenných prostorů
Pro zahájení práce s Aspose.GIS pro .NET importujte požadované jmenné prostory do svého C# projektu.

`Geometry` poskytuje statické metody pro parsování WKT do geometrických objektů.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Tyto jmenné prostory vám poskytují přístup ke třídám potřebným pro vytváření a správu geometrie `MultiCurve`.

## Postupný průvodce

### Krok 1: Definujte adresář dokumentu a název souboru
Nastavte složku, kam bude shapefile uložen. Nahraďte `"Your Document Directory"` skutečnou cestou na vašem počítači.

### Krok 2: Inicializujte `VectorLayer` s ovladačem Shapefile
`VectorLayer` představuje vektorový dataset, jako je shapefile, a umožňuje čtení i zápis geometrií.  
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block goes here
}
```
Objekt `VectorLayer` představuje vektorový dataset (v tomto případě shapefile), do kterého můžete zapisovat geometrie.

### Krok 3: Vytvořte novou entitu
Entita je kontejner, který drží geometrickou podobu a její atributové hodnoty.  
```csharp
var feature = layer.ConstructFeature();
```
Entita je kontejner pro geometrické a atributové údaje.

### Krok 4: Vytvořte instanci geometrie `MultiCurve`
`MultiCurve` je typ geometrie, který agreguje více křivkových komponent do jednoho prostorového objektu.  
```csharp
var multiCurve = new MultiCurve();
```
`MultiCurve` může obsahovat několik křivkových geometrií, což vám umožní je zkombinovat do jednoho prostorového objektu.

### Krok 5: Přidejte křivkové geometrie do `MultiCurve`
Zde **převádíme WKT na geometrie** pro tři různé typy křivek:
* jednoduchý **řetězec úseček**,  
* kruhový oblouk (`CircularString`),  
* a složená křivka, která kombinuje přímé segmenty s kruhovým obloukem.  
```csharp
multiCurve.Add(Geometry.FromText("LineString (0 0, 1 0)"));
multiCurve.Add(Geometry.FromText("CircularString (2 2, 3 3, 4 2)"));
multiCurve.Add(Geometry.FromText("CompoundCurve ((0 1, 0 0), CircularString (0 0, 3 3, 6 0))"));
```

### Krok 6: Přiřaďte `MultiCurve` k entitě
Nyní je geometrie entity kompozitní `MultiCurve`, kterou jsme právě vytvořili.  
```csharp
feature.Geometry = multiCurve;
```

### Krok 7: Přidejte entitu do `VectorLayer`
Entita je uložena do shapefile, když se ukončí blok `using`.  
```csharp
layer.Add(feature);
```

## Časté problémy a řešení
| Problém | Příčina | Řešení |
|---------|----------|--------|
| **`ArgumentException` on `Geometry.FromText`** | Neplatná syntaxe WKT | Ověřte, že řetězec WKT odpovídá specifikaci OGC (např. čárky mezi souřadnicemi, správné závorky). |
| Shapefile nebyl vytvořen | Nesprávná `path` nebo chybějící oprávnění k zápisu | Ujistěte se, že adresář existuje a aplikace má oprávnění k zápisu. |
| Křivky se v některých prohlížečích zobrazují jako přímé čáry | Prohlížeč nepodporuje kruhové/složené křivky | Použijte GIS prohlížeč, který rozumí typu geometrie `ARC` (např. QGIS). |

## Často kladené otázky

**Q: Je Aspose.GIS pro .NET kompatibilní se všemi verzemi .NET Framework?**  
A: Ano, podporuje .NET Framework, .NET Core, .NET Standard i .NET 5/6+.

**Q: Mohu pomocí Aspose.GIS pro .NET vytvořit vlastní formáty prostorových dat?**  
A: Rozhodně. API vám umožní číst, zapisovat a transformovat mnoho standardních formátů a můžete jej rozšířit i o proprietární.

**Q: Poskytuje Aspose.GIS funkce prostorové analýzy?**  
A: Ano, zahrnuje výpočty vzdáleností, detekci průniků, bufferování a další geometrické operace.

**Q: Je k dispozici zkušební verze Aspose.GIS pro .NET?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi z [Aspose.GIS website](https://releases.aspose.com/gis/net/) a vyzkoušet funkce před zakoupením.

**Q: Jak získám pomoc, pokud narazím na problémy?**  
A: Obrátit se můžete na komunitní fóra Aspose.GIS nebo konzultovat oficiální podpůrné zdroje zahrnuté ve vaší licenci.

---

**Poslední aktualizace:** 2026-09-25  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit složenou křivku geometrie](/gis/net/geometry-creation/create-compound-curve-geometry/)
- [Jak spočítat body z WKT pomocí Aspose.GIS pro .NET](/gis/net/geometry-processing/translate-geometry-from-wkt/)
- [Vytvořit MultiLineString geometrii pomocí Aspose.GIS pro .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
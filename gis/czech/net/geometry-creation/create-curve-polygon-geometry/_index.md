---
date: 2026-08-24
description: Naučte se, jak vytvořit vector layer a curve polygon geometrii pomocí
  Aspose.GIS pro .NET, včetně circular string geometry pro interior rings.
keywords:
- create vector layer
- define curved polygon
- Aspose.GIS curve polygon
- .NET GIS development
lastmod: 2026-08-24
linktitle: Vytvořte Curve Polygon Geometrii
og_description: Vytvořte vector layer a curve polygon geometrii pomocí Aspose.GIS
  pro .NET. Naučte se krok za krokem, jak během několika minut vygenerovat Shapefile
  s curved edges.
og_image_alt: Screenshot showing a curve polygon Shapefile created with Aspose.GIS
  in a GIS viewer
og_title: Vytvořte vector layer a curve polygon pomocí Aspose.GIS pro .NET
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to create vector layer and curve polygon geometry using Aspose.GIS
    for .NET, including circular string geometry for interior rings.
  headline: Create vector layer and curve polygon with Aspose.GIS
  type: TechArticle
- description: Learn how to create vector layer and curve polygon geometry using Aspose.GIS
    for .NET, including circular string geometry for interior rings.
  name: Create vector layer and curve polygon with Aspose.GIS
  steps:
  - name: define the file path
    text: First, specify where the generated Curve Polygon Shapefile will be saved.
      **Definition anchor:** `string shapefilePath = "...";` holds the absolute or
      relative path to the Shapefile that will be created on disk. Replace `"Your
      Document Directory"` with the actual folder path on your machine.
  - name: create a vector layer
    text: 'Instantiate a new vector layer using the Shapefile driver. This is the
      **create vector layer** step that prepares the container for our geometry. **Definition
      anchor:** `VectorLayer layer = new VectorLayer(shapefilePath, Drivers.Shapefile);`
      creates a writable layer tied to a Shapefile data source. '
  - name: construct a feature
    text: Create a feature object that will hold the geometry and any attribute data.
      **Definition anchor:** `Feature feature = layer.ConstructFeature();` builds
      an empty feature ready to receive geometry and attribute values.
  - name: create curve polygon geometry
    text: Now we’ll create an empty `CurvePolygon` object. **Definition anchor:**
      `CurvePolygon curvePolygon = new CurvePolygon();` represents a polygon whose
      rings may consist of straight segments or circular strings.
  - name: define the exterior ring
    text: Add a circular string that forms the outer boundary of the polygon. **Definition
      anchor:** `CircularString exterior = new CircularString();` stores a sequence
      of points that define one or more circular arcs. The coordinates above produce
      a torus‑like shape.
  - name: define an interior ring (optional)
    text: 'If you need a hole inside the polygon, define it as another circular string.
      This demonstrates how to add an **interior ring polygon** using **circular string
      geometry**. **Definition anchor:** `CircularString interior = new CircularString();`
      creates the inner ring that will be subtracted from the '
  - name: assign geometry to the feature
    text: Link the curve polygon to the feature you created earlier. **Definition
      anchor:** `feature.Geometry = curvePolygon;` attaches the fully built geometry
      to the feature, making it ready for persistence.
  - name: add the feature to the layer
    text: Finally, add the feature to the vector layer so it becomes part of the dataset.
      **Definition anchor:** `layer.Add(feature);` writes the feature into the Shapefile;
      the `using` block will flush the data to disk when it ends. When the `using`
      block ends, the Shapefile is written to disk.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS for .NET supports interoperability with many popular GIS
      formats, allowing seamless data exchange with GDAL/OGR, Proj.NET, and other
      .NET GIS toolkits.
    question: Is Aspose.GIS for .NET compatible with other GIS libraries?
  - answer: Absolutely. The Shapefile produced can be opened in QGIS, ArcGIS, or any
      GIS tool that reads the Shapefile format and supports circular strings.
    question: Can I visualize the generated curve polygon geometry in GIS software?
  - answer: Yes, it includes spatial querying, buffering, intersection, and other
      analysis functions, enabling advanced geoprocessing directly in .NET.
    question: Does Aspose.GIS for .NET provide spatial analysis capabilities?
  - answer: Join the Aspose.GIS community forum [Aspose.GIS community forum](https://forum.aspose.com/c/gis/33)
      to connect with other developers.
    question: Where can I ask for help or discuss ideas with other users?
  - answer: Of course! You can download a free trial from the [Aspose.GIS free trial
      downloads](https://releases.aspose.com/) and evaluate all features.
    question: Is a free trial available before purchasing?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create vector layer
- Aspose.GIS
- curve polygon
- .NET GIS
- C# shapefile
title: Vytvořte vector layer a curve polygon pomocí Aspose.GIS
url: /cs/net/geometry-creation/create-curve-polygon-geometry/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření vektorové vrstvy a křivkového polygonu pomocí Aspose.GIS

## Úvod
V oblasti vývoje geografických informačních systémů (GIS) **Aspose.GIS pro .NET** vyniká jako výkonná knihovna pro vytváření, úpravu a manipulaci s prostorovými daty. V tomto tutoriálu se naučíte, jak **vytvořit vektorovou vrstvu** a **vytvořit křivkový polygon** krok za krokem, takže můžete přímo do svých GIS aplikací vložit sofistikované tvary. Na konci průvodce budete mít připravený Shapefile obsahující křivkový polygon s vnější i vnitřními kruhy.

## Rychlé odpovědi
- **Jaká knihovna se používá?** Aspose.GIS pro .NET.  
- **Hlavní úkol?** Vytvořit geometrii křivkového polygonu, uložit ji jako Shapefile a **vytvořit vektorovou vrstvu** pro data.  
- **Typický čas implementace?** 5–10 minut pro základní tvar.  
- **Předpoklady?** Vývojové prostředí .NET a NuGet balíček Aspose.GIS.  
- **Mohu výsledek zobrazit?** Ano – jakýkoli GIS prohlížeč, který podporuje Shapefile (např. QGIS, ArcGIS).

## Co je křivkový polygon?
Křivkový polygon je polygon, jehož hrany mohou zahrnovat zakřivené segmenty, jako jsou kruhové oblouky, což umožňuje plynulé, realistické hranice. Tento typ geometrie je zvláště užitečný pro modelování přírodních útvarů, jako jsou jezera, ostrovy nebo zakřivené silniční koridory.

## Proč vytvářet křivkovou polygonovou geometrii pomocí Aspose.GIS?
Aspose.GIS dokáže ukládat zakřivené hrany matematicky, zachovává přesnou geometrii a zároveň zůstává kompatibilní se specifikací Shapefile. Knihovna podporuje **30+ vektorových formátů** a může zpracovávat soubory až do **2 GB** bez načítání celého datasetu do paměti, což poskytuje vysoký výkon při práci s velkými prostorovými projekty.

## Předpoklady
Předtím, než se pustíte do práce, ujistěte se, že máte následující:

1. **Aspose.GIS pro .NET** nainstalovaný. Stáhněte jej ze stránky [Aspose.GIS pro .NET releases page](https://releases.aspose.com/gis/net/).  
2. Praktické znalosti C# a ekosystému .NET.  
3. IDE, jako je Visual Studio (jakákoli recentní verze) nebo Visual Studio Code.

## Importovat jmenné prostory
Direktivy `using` níže přinášejí hlavní GIS třídy do rozsahu.

**Definiční kotva:** `using Aspose.Gis;` importuje hlavní GIS jmenný prostor, který obsahuje `VectorLayer`, `Feature` a třídy geometrie potřebné pro tento tutoriál.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Průvodce krok za krokem

### Krok 1: definujte cestu k souboru
Nejprve určete, kde bude vygenerovaný Shapefile s křivkovým polygonem uložen.

**Definiční kotva:** `string shapefilePath = "...";` obsahuje absolutní nebo relativní cestu k Shapefile, který bude vytvořen na disku.  

```csharp
string path = "Your Document Directory" + "CreateCurvePolygon_out.shp";
```

Nahraďte `"Your Document Directory"` skutečnou cestou ke složce na vašem počítači.

### Krok 2: vytvořte vektorovou vrstvu
Instanciujte novou vektorovou vrstvu pomocí ovladače Shapefile. Toto je krok **vytvořit vektorovou vrstvu**, který připraví kontejner pro naši geometrii.

**Definiční kotva:** `VectorLayer layer = new VectorLayer(shapefilePath, Drivers.Shapefile);` vytvoří zapisovatelnou vrstvu spojenou se zdrojem dat Shapefile.  

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Your code for creating the Curve Polygon Geometry will go here
}
```

Příkaz `using` zajišťuje, že prostředky jsou uvolněny správně.

### Krok 3: vytvořte prvek (feature)
Vytvořte objekt `Feature`, který bude obsahovat geometrii a případná atributová data.

**Definiční kotva:** `Feature feature = layer.ConstructFeature();` vytvoří prázdný prvek připravený přijmout geometrii a hodnoty atributů.  

```csharp
var feature = layer.ConstructFeature();
```

### Krok 4: vytvořte geometrii křivkového polygonu
Nyní vytvoříme prázdný objekt `CurvePolygon`.

**Definiční kotva:** `CurvePolygon curvePolygon = new CurvePolygon();` představuje polygon, jehož kruhy mohou sestávat z přímých segmentů nebo kruhových řetězců.  

```csharp
var curvePolygon = new CurvePolygon();
```

### Krok 5: definujte vnější kruh
Přidejte kruhový řetězec, který tvoří vnější hranici polygonu.

**Definiční kotva:** `CircularString exterior = new CircularString();` ukládá sekvenci bodů, které definují jeden nebo více kruhových oblouků.  

```csharp
var exterior = new CircularString();
exterior.AddPoint(-2, 0);
exterior.AddPoint(0, 2);
exterior.AddPoint(2, 0);
exterior.AddPoint(0, -2);
exterior.AddPoint(-2, 0);
curvePolygon.ExteriorRing = exterior;
```

Výše uvedené souřadnice vytvářejí tvar podobný torusu.

### Krok 6: definujte vnitřní kruh (volitelné)
Pokud potřebujete díru uvnitř polygonu, definujte ji jako další kruhový řetězec. Toto ukazuje, jak přidat **vnitřní kruh polygonu** pomocí **geometrie kruhového řetězce**.

**Definiční kotva:** `CircularString interior = new CircularString();` vytváří vnitřní kruh, který bude odečten od vnější oblasti.  

```csharp
var interior = new CircularString();
interior.AddPoint(-1, 0);
interior.AddPoint(0, 1);
interior.AddPoint(1, 0);
interior.AddPoint(0, -1);
interior.AddPoint(-1, 0);
curvePolygon.AddInteriorRing(interior);
```

### Krok 7: přiřaďte geometrii k prvku
Propojte křivkový polygon s prvkem, který jste vytvořili dříve.

**Definiční kotva:** `feature.Geometry = curvePolygon;` připojuje kompletně vytvořenou geometrii k prvku, čímž je připravena k uložení.  

```csharp
feature.Geometry = curvePolygon;
```

### Krok 8: přidejte prvek do vrstvy
Nakonec přidejte prvek do vektorové vrstvy, aby se stal součástí datasetu.

**Definiční kotva:** `layer.Add(feature);` zapíše prvek do Shapefile; blok `using` vyprázdní data na disk po jeho ukončení.  

```csharp
layer.Add(feature);
```

Když blok `using` skončí, Shapefile je zapsán na disk.

## Časté problémy a řešení
| Problém | Proč k tomu dochází | Řešení |
|---------|----------------------|--------|
| **Soubor nebyl vytvořen** | Nesprávná cesta nebo chybějící oprávnění k zápisu | Ověřte, že adresář existuje a aplikace má právo zapisovat. |
| **Zakřivené hrany se v některých prohlížečích zobrazují jako přímé** | Prohlížeč nepodporuje kruhové řetězce | Použijte GIS aplikaci, která plně podporuje specifikaci Shapefile (např. QGIS 3.28+). |
| **Výjimka `ArgumentException` při `AddPoint`** | Body jsou mimo platný rozsah souřadnic pro zvolený CRS | Ujistěte se, že souřadnice spadají do souřadnicového referenčního systému, který plánujete použít. |

## Často kladené otázky

**Q: Je Aspose.GIS pro .NET kompatibilní s jinými GIS knihovnami?**  
A: Ano, Aspose.GIS pro .NET podporuje interoperabilitu s mnoha populárními GIS formáty, což umožňuje bezproblémovou výměnu dat s GDAL/OGR, Proj.NET a dalšími .NET GIS nástroji.

**Q: Mohu vizualizovat vygenerovanou geometrii křivkového polygonu v GIS softwaru?**  
A: Rozhodně. Vytvořený Shapefile lze otevřít v QGIS, ArcGIS nebo jakémkoli GIS nástroji, který čte formát Shapefile a podporuje kruhové řetězce.

**Q: Poskytuje Aspose.GIS pro .NET funkce prostorové analýzy?**  
A: Ano, zahrnuje prostorové dotazování, bufferování, průnik a další analytické funkce, což umožňuje pokročilé geoprocesování přímo v .NET.

**Q: Kde mohu požádat o pomoc nebo diskutovat nápady s ostatními uživateli?**  
A: Připojte se k fóru komunity Aspose.GIS [Aspose.GIS community forum](https://forum.aspose.com/c/gis/33) a spojte se s dalšími vývojáři.

**Q: Je k dispozici bezplatná zkušební verze před zakoupením?**  
A: Samozřejmě! Můžete si stáhnout bezplatnou zkušební verzi z [Aspose.GIS free trial downloads](https://releases.aspose.com/) a vyzkoušet všechny funkce.

## Závěr
Nyní jste se naučili, jak **vytvořit vektorovou vrstvu** a **vytvořit křivkový polygon** pomocí Aspose.GIS pro .NET, uložit jej jako Shapefile a seznámit se s běžnými úskalími a častými dotazy. Nebojte se experimentovat s různými souřadnicovými sadami, přidávat atributová data nebo integrovat vrstvu do větších GIS pracovních postupů.

---

**Poslední aktualizace:** 2026-08-24  
**Testováno s:** Aspose.GIS pro .NET 24.11  
**Autor:** Aspose

## Související tutoriály

- [Create Vector Layer & Circular String in Aspose.GIS for .NET](/gis/net/geometry-creation/create-circular-string-geometry/)
- [How to Create Vector Layer with SRS using Aspose.GIS for .NET](/gis/net/layer-management/create-vector-layer-with-srs/)
- [Create Polygon with Hole Geometry using Aspose.GIS](/gis/net/geometry-creation/create-polygon-with-hole-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-02-15
description: Naučte se, jak vytvořit vektorovou vrstvu a přidat geometrii kruhového
  řetězce pomocí Aspose.GIS pro .NET – rychlý způsob, jak vytvářet GIS aplikace.
linktitle: Create Circular String Geometry
second_title: Aspose.GIS .NET API
title: Vytvořte vektorovou vrstvu a kruhový řetězec v Aspose.GIS pro .NET
url: /cs/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření vektorové vrstvy a geometrie kruhového řetězce s Aspose.GIS pro .NET

## Introduction
Pokud vytváříte GIS aplikaci na platformě .NET, prvním krokem je často **vytvořit vektorovou vrstvu** objektů, které ukládají vaše prostorové prvky. Aspose.GIS pro .NET tento proces zjednodušuje a umožňuje obohatit tyto vrstvy o pokročilé geometrie, jako jsou kruhové řetězce. V tomto tutoriálu se naučíte přesně, jak **vytvořit vektorovou vrstvu**, **přidat kruhový řetězec** geometrie a uložit výsledek jako Shapefile – vše s čistým, produkčně připraveným C# kódem.

## Quick Answers
- **Co znamená „vytvořit vektorovou vrstvu“?** Vytvoří nový kontejner (vrstvu), který může obsahovat prostorové prvky jako body, linie nebo polygony.  
- **Která třída představuje kruhový řetězec?** `CircularString` z `Aspose.Gis.Geometries`.  
- **Mohu vrstvu uložit jako Shapefile?** Ano – použijte `Drivers.Shapefile` při vytváření vrstvy.  
- **Potřebuji licenci pro vývoj?** Dočasná licence stačí pro hodnocení; plná licence je vyžadována pro produkci.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is “create vector layer”?
Vektorová vrstva je logické seskupení vektorových prvků (body, linie, polygony) uložených v jediném datovém zdroji. V Aspose.GIS vytvoříte vrstvu voláním `VectorLayer.Create`, přičemž zadáte cílovou cestu k souboru a požadovaný ovladač (např. Shapefile). Jakmile vrstva existuje, můžete do ní přidávat prvky, přiřazovat geometrie a provádět prostorové operace.

## Why add a circular string?
Kruhové řetězce jsou typ **lineární geometrie**, který aproximuje oblouky pomocí sekvence bodů. Hodí se pro reprezentaci zakřivených silnic, zatáček řek nebo jakéhokoli prvku, kde je potřeba hladká křivka bez nutnosti používat mnoho malých úseků čar.

## Prerequisites
Než začnete, ujistěte se, že máte:

- **.NET Framework nebo .NET Core** nainstalovaný na vašem počítači.  
- **Aspose.GIS for .NET** knihovnu – stáhněte ji z oficiálního webu **[zde](https://releases.aspose.com/gis/net/)**.  
- IDE, jako je **Visual Studio** nebo **JetBrains Rider**.  
- Základní znalosti programování v **C#**.

## Import Namespaces
Přidejte požadované jmenné prostory do vašeho C# souboru:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step‑by‑Step Guide

### Step 1: Define the output file path
Nastavte umístění, kam bude Shapefile zapsán.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

Nahraďte `"Your Document Directory"` skutečnou cestou ke složce ve vašem systému.

### Step 2: **Create vector layer**
Otevřete `VectorLayer` pomocí metody `Create`. Toto je jádro operace **vytvořit vektorovou vrstvu**.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### Step 3: Construct a new feature
Prvek představuje jeden prostorový záznam uvnitř vrstvy.

```csharp
    var feature = layer.ConstructFeature();
```

### Step 4: Build the circular string geometry
Přidejte body, které definují zakřivený tvar. Sekvence bodů vytvoří oblouk, který začíná a končí na stejném místě, čímž vznikne uzavřený kruhový řetězec.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### Step 5: Assign geometry and add the feature to the layer
Propojte geometrii s prvkem a uložte jej do vrstvy.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

Když se ukončí blok `using`, vrstva se automaticky zapíše do Shapefile na disku.

## Common Issues & Solutions
| Issue | Solution |
|-------|----------|
| **File path invalid** | Ujistěte se, že adresář existuje a máte oprávnění k zápisu. |
| **CircularString appears as a straight line** | Ověřte, že body jsou přidány ve správném pořadí; první a poslední bod by měly být identické pro uzavřený tvar. |
| **License exception** | Použijte dočasnou licenci během vývoje nebo zakupte plnou licenci pro produkční nasazení. |

## Frequently Asked Questions

### Is Aspose.GIS for .NET compatible with all versions of the .NET Framework?
Ano, Aspose.GIS for .NET je navržen tak, aby fungoval s širokým rozsahem verzí .NET, od Framework 4.5 až po nejnovější vydání .NET 8.

### Can I integrate Aspose.GIS for .NET with other GIS libraries?
Rozhodně! Můžete číst data pomocí jiných knihoven, manipulovat s nimi pomocí Aspose.GIS a poté je znovu zapsat, díky flexibilnímu API.

### Does Aspose.GIS for .NET support spatial data visualization?
Ano, knihovna obsahuje nástroje pro renderování, které vám umožní generovat mapy a vizuální reprezentace vašich geometrií.

### Is there a community forum where I can seek assistance with Aspose.GIS for .NET?
Ano, můžete navštívit fórum Aspose.GIS **[zde](https://forum.aspose.com/c/gis/33)**, kde můžete klást otázky a sdílet zkušenosti.

### Can I obtain a temporary license to evaluate Aspose.GIS for .NET?
Samozřejmě! Dočasná evaluační licence je k dispozici **[zde](https://purchase.aspose.com/temporary-license/)**.

### How do I add more complex geometries (e.g., MultiLineString) to the same layer?
Vytvořte příslušný geometrický objekt (např. `MultiLineString`), naplňte jej jednotlivými objekty `LineString`, přiřaďte jej k `feature.Geometry` a přidejte prvek stejně jako u kruhového řetězce.

## FAQ (Quick‑Reference)

**Q:** Jak programově **vytvořit vektorovou vrstvu**?  
**A:** Zavolejte `VectorLayer.Create(path, Drivers.Shapefile)` (nebo jiný ovladač) uvnitř bloku `using`.

**Q:** Jaká metoda přidává body do kruhového řetězce?  
**A:** Použijte `circularString.AddPoint(x, y)` pro každou souřadnici.

**Q:** Mohu v jedné vrstvě uložit více geometrií?  
**A:** Ano, vytvořte nový prvek pro každou geometrii a přidejte jej pomocí `layer.Add(feature)`.

**Q:** Co mám dělat, když se Shapefile nevytvoří?  
**A:** Ověřte, že výstupní adresář existuje, máte oprávnění k zápisu a ovladač (`Drivers.Shapefile`) je správně odkazován.

**Q:** Je licence vyžadována pro evaluační sestavení?  
**A:** Dočasná licence stačí pro vývoj a testování; plná licence je potřebná pro produkční nasazení.

## Conclusion
Po absolvování těchto kroků nyní víte, jak **vytvořit vektorovou vrstvu** a obohatit ji o **kruhový řetězec** pomocí Aspose.GIS pro .NET. Tento základ vám umožní budovat bohatší GIS řešení – ať už mapujete dopravní sítě, vizualizujete environmentální data nebo vyvíjíte vlastní nástroje pro prostorovou analytiku.

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
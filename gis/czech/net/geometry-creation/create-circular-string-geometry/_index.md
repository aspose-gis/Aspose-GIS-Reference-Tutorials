---
date: 2025-12-12
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

# Vytvoření vektorové vrstvy a geometrie kruhového řetězce pomocí Aspose.GIS pro .NET

## Úvod
Pokud vytváříte GIS aplikaci na platformě .NET, první krok je často **vytvořit vector layer** objektů, které ukládají vaše prostorové prvky. Aspose.GIS pro .NET tento proces zjednodušuje a umožňuje obohatit tyto vrstvy o pokročilé geometrie, jako jsou kruhové řetězce. V tomto tutoriálu se přesně naučíte, jak vytvořit vektorovou vrstvu, přidat geometrie circular string a uložit výsledek jako Shapefile – vše s čistým, připraveným k produkci C# kódem.

## Rychlé odpovědi
- **Co znamená “create vector layer”?** Vytváří nový kontejner (vrstvu), který může obsahovat prostorové prvky jako body, linie nebo polygony.  
- **Která třída představuje circular string?** `CircularString` z `Aspose.Gis.Geometries`.  
- **Mohu vrstvu uložit jako Shapefile?** Ano – použijte `Drivers.Shapefile` při vytváření vrstvy.  
- **Potřebuji licenci pro vývoj?** Dočasná licence stačí pro hodnocení; plná licence je vyžadována pro produkci.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co je “create vector layer”?
Vektorová vrstva je logické seskupení vektorových prvků (bodů, linií, polygonů) uložených v jednom datovém zdroji. V Aspose.GIS vytvoříte vrstvu voláním `VectorLayer.Create`, přičemž zadáte cílovou cestu k souboru a požadovaný driver (např. Shapefile). Jakmile vrstva existuje, můžete přidávat prvky, přiřazovat geometrie a provádět prostorové operace.

## Proč přidat circular string?
Circular strings jsou typ **lineární geometrie**, který aproximuje oblouky pomocí sekvence bodů. Jsou užitečné pro reprezentaci zakřivených silnic, zatáček řek nebo jakéhokoli prvku, kde je potřeba hladká křivka bez použití mnoha malých úseků linií.

## Předpoklady
- **.NET Framework nebo .NET Core** nainstalovaný na vašem počítači.  
- **Aspose.GIS pro .NET** knihovna – stáhněte ji z oficiální stránky **[zde](https://releases.aspose.com/gis/net/)**.  
- IDE, jako je **Visual Studio** nebo **JetBrains Rider**.  
- Základní znalost programování v **C#**.

## Importujte jmenné prostory
Add the required namespaces to your C# file:

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

### Krok 1: Definujte výstupní cestu k souboru
Nastavte umístění, kam bude Shapefile zapsán.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

Nahraďte `"Your Document Directory"` skutečnou cestou ke složce ve vašem systému.

### Krok 2: **Create vector layer**
Otevřete `VectorLayer` pomocí metody `Create`. Toto je jádro operace **create vector layer**.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### Krok 3: Vytvořte nový prvek
Prvek (feature) představuje jediný prostorový záznam uvnitř vrstvy.

```csharp
    var feature = layer.ConstructFeature();
```

### Krok 4: Vytvořte geometrie circular string
Přidejte body, které definují zakřivený tvar. Sekvence bodů vytváří oblouk, který začíná a končí na stejném místě, čímž vzniká uzavřený circular string.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### Krok 5: Přiřaďte geometrii a přidejte prvek do vrstvy
Propojte geometrii s prvkem a uložte ji do vrstvy.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

Když se ukončí blok `using`, vrstva se automaticky zapíše do Shapefile na disku.

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Neplatná cesta k souboru** | Ujistěte se, že adresář existuje a máte oprávnění k zápisu. |
| **CircularString se zobrazuje jako přímka** | Zkontrolujte, že jsou body přidány ve správném pořadí; první a poslední bod by měly být identické pro uzavřený tvar. |
| **Výjimka licence** | Použijte dočasnou licenci během vývoje nebo zakupte plnou licenci pro produkční použití. |

## Často kladené otázky

### Je Aspose.GIS pro .NET kompatibilní se všemi verzemi .NET Framework?
Ano, Aspose.GIS pro .NET je navržen tak, aby fungoval s širokým rozsahem verzí .NET, od Framework 4.5 až po nejnovější verze .NET 8.

### Mohu integrovat Aspose.GIS pro .NET s jinými GIS knihovnami?
Rozhodně! Můžete číst data pomocí jiných knihoven, manipulovat s nimi pomocí Aspose.GIS a poté je znovu zapsat, díky flexibilnímu API.

### Podporuje Aspose.GIS pro .NET vizualizaci prostorových dat?
Ano, knihovna obsahuje nástroje pro renderování, které vám umožní generovat mapy a vizuální reprezentace vašich geometrií.

### Existuje komunitní fórum, kde mohu získat pomoc s Aspose.GIS pro .NET?
Ano, můžete navštívit fórum Aspose.GIS **[zde](https://forum.aspose.com/c/gis/33)** a klást otázky a sdílet zkušenosti.

### Mohu získat dočasnou licenci pro vyhodnocení Aspose.GIS pro .NET?
Samozřejmě! Dočasná evaluační licence je k dispozici **[zde](https://purchase.aspose.com/temporary-license/)**.

### Jak přidám složitější geometrie (např. MultiLineString) do stejné vrstvy?
Vytvořte odpovídající geometrický objekt (např. `MultiLineString`), naplňte jej jednotlivými objekty `LineString`, přiřaďte jej k `feature.Geometry` a přidejte prvek stejně jako u circular string.

## Závěr
Po provedení těchto kroků nyní víte, jak **create vector layer** objekty a obohatit je o geometrie circular string pomocí Aspose.GIS pro .NET. Tento základ vám umožní vytvářet bohatší GIS řešení – ať už mapujete dopravní sítě, vizualizujete environmentální data nebo vyvíjíte vlastní nástroje pro prostorovou analytiku.

---

**Poslední aktualizace:** 2025-12-12  
**Testováno s:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-06-30
description: Naučte se, jak vytvořit shapefile pomocí Aspose.GIS pro .NET. Tento podrobný
  návod vám ukáže, jak definovat vector layer, přidat date attribute a efektivně spravovat
  spatial data.
keywords:
- how to create shapefile
- temporal gis shapefile
- Aspose.GIS vector layer
- GIS data automation
linktitle: Vytvořit nový shapefile
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create shapefile using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to define a vector layer, add a date attribute, and manage
    spatial data efficiently.
  headline: How to Create Shapefile with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS primarily supports .NET, but there are versions available for
      Java as well.
    question: Can I use Aspose.GIS with other programming languages?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I find support for Aspose.GIS?
  - answer: Get your temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license?
  - answer: You can buy the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Jak vytvořit shapefile pomocí Aspose.GIS pro .NET
url: /cs/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořit nový shapefile

## Úvod
Pokud se ponořujete do vývoje geografických informačních systémů (GIS) s .NET, Aspose.GIS je vaše řešení pro **jak programově vytvořit shapefile**. Tato knihovna vám poskytuje plnou kontrolu nad vektorovými vrstvami, schématy atributů a souladem s formátem souboru, takže můžete automatizovat datové kanály nebo během několika minut generovat testovací datové sady.

## Rychlé odpovědi
- **Co se v tomto tutoriálu učí?** Jak vytvořit nový shapefile, definovat vektorovou vrstvu a přidat atributy (včetně pole pro datum).  
- **Která knihovna je vyžadována?** Aspose.GIS pro .NET.  
- **Potřebuji licenci?** Bezplatná zkušební verze stačí pro učení; pro produkční nasazení je vyžadována komerční licence.  
- **Jaké IDE mám použít?** Visual Studio (jakákoli recentní verze).  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní příklad.

## Jak vytvořit shapefile pomocí Aspose.GIS pro .NET?
Načtěte knihovnu Aspose.GIS, nastavte výstupní složku, vytvořte `VectorLayer`, definujte atributy a přidejte prvky — celý tento postup lze zapsat v méně než 30 řádcích C#. Knihovna automaticky zpracovává tvorbu geometrie, typování atributů a zápis souboru, takže se nemusíte starat o nízkoúrovňové specifikace Shapefile.

## Požadavky
Než se pustíme do tutoriálu, ujistěte se, že máte následující požadavky:
- Základní znalost programovacího jazyka C#.  
- Nainstalovaný Visual Studio na vašem počítači.  
- Knihovna Aspose.GIS pro .NET. Můžete si ji stáhnout [zde](https://releases.aspose.com/gis/net/).

## Importovat jmenné prostory
Začněte importováním potřebných jmenných prostorů, abyste využili funkčnost Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Nastavte svůj projekt
Začněte vytvořením nového C# projektu ve Visual Studio a zahrňte knihovnu Aspose.GIS.

## Krok 2: Definujte adresář dokumentu
```csharp
string dataDir = "Your Document Directory";
```
Nahraďte *Your Document Directory* skutečnou cestou, kam chcete uložit nový shapefile.

## Krok 3: Vytvořte VectorLayer
`VectorLayer` třída představuje jedinou vrstvu shapefile, která ukládá geometrii a atributová data.  
V tomto kroku definujeme vektorovou vrstvu a deklarujeme tři atributy: textové pole (`name`), celočíselné pole (`age`) a pole datum‑času (`dob`). Přidání atributu pro datum je klíčové pro **časové GIS shapefile** analýzy.

```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```

## Krok 4: Přidat prvky
### Případ 1: Nastavuje hodnoty jednotlivě
Metoda `SetValues` přiřazuje hodnoty atributů k prvku v pořadí, v jakém byly definovány.  
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
Zde vytvoříme dva body, nastavíme každý atribut samostatně a přidáme prvky do vrstvy.

### Případ 2: Nastavuje nové hodnoty pro všechny atributy
Alternativně můžete poskytnout všechny hodnoty atributů najednou pomocí `SetValues` s polem objektů.  
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
V tomto přístupu naplníme všechny hodnoty atributů jedním voláním pomocí pole objektů — užitečné, když máte mnoho atributů.

## Proč je to důležité?
Programové vytvoření shapefile vám umožní automatizovat datové kanály, generovat testovací datové sady nebo vložit GIS výstup přímo do webových služeb. Aspose.GIS podporuje **30+ vektorových a rastrových formátů** a dokáže zapisovat stovky stránek shapefile bez načítání celého souboru do paměti, což poskytuje jak rychlost, tak škálovatelnost.

## Časté úskalí a tipy
- **Oddělovače cest:** Používejte `Path.Combine` pro multiplatformní kompatibilitu místo řetězcové konkatenace.  
- **Pořadí atributů:** Pořadí hodnot v `SetValues` musí odpovídat pořadí, ve kterém jste atributy přidali.  
- **Zpracování data:** Vždy používejte `DateTimeKind.Utc`, pokud budou vaše GIS data sdílena napříč časovými pásmy.

## Závěr
Gratulujeme! Úspěšně jste vytvořili nový shapefile pomocí Aspose.GIS pro .NET. Tento tutoriál pokryl základy nastavení projektu, definice vektorové vrstvy a přidání prvků — včetně atributu pro datum. Jak budete pokračovat, odkazujte se na [dokumentaci](https://reference.aspose.com/gis/net/) pro pokročilé funkce a možnosti.

## Často kladené otázky
**Q: Můžu použít Aspose.GIS s jinými programovacími jazyky?**  
A: Aspose.GIS primárně podporuje .NET, ale jsou k dispozici i verze pro Javu.

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano, bezplatnou zkušební verzi získáte [zde](https://releases.aspose.com/).

**Q: Kde mohu najít podporu pro Aspose.GIS?**  
A: Navštivte [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pro komunitní podporu a diskuse.

**Q: Jak mohu získat dočasnou licenci?**  
A: Získejte svou dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).

**Q: Kde mohu zakoupit Aspose.GIS pro .NET?**  
A: Knihovnu můžete koupit [zde](https://purchase.aspose.com/buy).

**Poslední aktualizace:** 2026-06-30  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose

## Související tutoriály

- [Získat atributy vrstvy – Získat informace o atributech vrstvy s Aspose.GIS pro .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Vytvořit vektorovou vrstvu a nastavit prostorový referenční systém vrstvy](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Vytvořit vektorovou vrstvu v souboru GDB – Aspose.GIS .NET tutoriál](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
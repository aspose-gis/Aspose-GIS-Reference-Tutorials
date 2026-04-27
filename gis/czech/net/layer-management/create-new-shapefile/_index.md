---
date: 2026-01-13
description: Naučte se, jak vytvořit nový shapefile pomocí Aspose.GIS pro .NET. Tento
  krok‑za‑krokem průvodce vám ukáže, jak definovat vektorovou vrstvu, přidat atribut
  data a spravovat prostorová data.
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
title: Vytvořit nový shapefile
url: /cs/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření nového shapefile

## Úvod
Pokud se ponořujete do vývoje geografických informačních systémů (GIS) s .NET, Aspose.GIS je vaše řešení první volby. Tato výkonná knihovna umožňuje vývojářům pracovat plynule s prostorovými daty a v tomto tutoriálu vás provedeme tím, jak **vytvořit nový shapefile** pomocí Aspose.GIS pro .NET. Ukážeme si, proč je definování vektorové vrstvy a přidání atributu data nezbytným krokem pro robustní GIS projekty.

## Rychlé odpovědi
- **Co se v tomto tutoriálu učí?** Jak vytvořit nový shapefile, definovat vektorovou vrstvu a přidat atributy (včetně pole data).  
- **Která knihovna je vyžadována?** Aspose.GIS pro .NET.  
- **Potřebuji licenci?** Bezplatná zkušební verze stačí pro učení; pro produkční nasazení je nutná komerční licence.  
- **Jaké IDE mám použít?** Visual Studio (kterákoli recentní verze).  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní příklad.

## Požadavky
Než se pustíme do tutoriálu, ujistěte se, že máte splněny následující požadavky:
- Základní znalost programovacího jazyka C#.
- Nainstalovaný Visual Studio na vašem počítači.
- Knihovna Aspose.GIS pro .NET. Můžete si ji stáhnout [zde](https://releases.aspose.com/gis/net/).

## Importování jmenných prostorů
Začněte importováním potřebných jmenných prostorů, abyste mohli využít funkčnost Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Nastavení projektu
Vytvořte nový C# projekt ve Visual Studio a zahrňte knihovnu Aspose.GIS.

## Krok 2: Definování adresáře dokumentů
```csharp
string dataDir = "Your Document Directory";
```
Nahraďte *Your Document Directory* skutečnou cestou, kam chcete uložit nový shapefile.

## Krok 3: Vytvoření VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Tento úsek kódu **definuje vektorovou vrstvu** a deklaruje tři atributy: textové pole (`name`), celočíselné pole (`age`) a pole typu datum‑času (`dob`). Přidání atributu data je klíčové pro časové GIS analýzy.

## Krok 4: Přidání prvků
### Případ 1: Nastavení hodnot jednotlivě
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
Zde vytvoříme dva body, nastavíme každý atribut zvlášť a přidáme prvky do vrstvy.

### Případ 2: Nastavení nových hodnot pro všechny atributy
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
V tomto přístupu naplníme všechny hodnoty atributů jedním voláním pomocí pole objektů — užitečné, když máte mnoho atributů.

## Proč je to důležité
Programatické vytvoření shapefile vám umožní automatizovat datové kanály, generovat testovací datové sady nebo přímo integrovat GIS výstup do webových služeb. Ovládnutím **vytvoření shapefile** s Aspose.GIS získáte plnou kontrolu nad geometrií prvků, schématem atributů a souladem s formátem souboru.

## Časté úskalí a tipy
- **Oddělovače cest:** Používejte `Path.Combine` pro multiplatformní kompatibilitu místo řetězcové konkatenace.  
- **Pořadí atributů:** Pořadí hodnot v `SetValues` musí odpovídat pořadí, ve kterém jste atributy přidali.  
- **Zpracování data:** Vždy používejte `DateTimeKind.Utc`, pokud budou vaše GIS data sdílena napříč časovými pásmy.

## Závěr
Gratulujeme! Úspěšně jste vytvořili nový shapefile pomocí Aspose.GIS pro .NET. Tento tutoriál pokryl základy nastavení projektu, definování vektorové vrstvy a přidání prvků — včetně atributu data. Jak budete pokračovat, odkazujte se na [dokumentaci](https://reference.aspose.com/gis/net/) pro pokročilé funkce a možnosti.

## Často kladené otázky
### Q: Mohu použít Aspose.GIS s jinými programovacími jazyky?
Aspose.GIS primárně podporuje .NET, ale existují také verze pro Java.

### Q: Je k dispozici bezplatná zkušební verze?
Ano, bezplatnou zkušební verzi získáte [zde](https://releases.aspose.com/).

### Q: Kde mohu najít podporu pro Aspose.GIS?
Navštivte [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pro komunitní podporu a diskuze.

### Q: Jak získat dočasnou licenci?
Získejte svou dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).

### Q: Kde mohu zakoupit Aspose.GIS pro .NET?
Knihovnu můžete zakoupit [zde](https://purchase.aspose.com/buy).

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
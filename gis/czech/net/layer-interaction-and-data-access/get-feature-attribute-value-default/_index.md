---
date: 2026-01-05
description: Naučte se, jak získávat hodnoty atributů a nastavovat výchozí hodnoty
  v Aspose.GIS pro .NET. Tento krok‑za‑krokem průvodce ukazuje vytváření vrstev GeoJSON
  a konstrukci GIS prvků.
linktitle: How to Get Attribute Value (Default)
second_title: Aspose.GIS .NET API
title: Jak získat výchozí hodnotu atributu pomocí Aspose.GIS pro .NET
url: /cs/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak získat hodnotu atributu (výchozí) s Aspise.GIS pro .NET

## Úvod
V tomto komplexním tutoriálu se dozvíte **jak získat hodnotu atributu** z GIS prvku pomocí Aspose.GIS pro .NET a jak pracovat s výchozími hodnotami, když atribut chybí. Ať už vytváříte analytický motor pro prostorová data nebo jednoduchý prohlížeč map, zvládnutí získávání atributů a jejich výchozího zpracování je nezbytné pro spolehlivé GIS aplikace.

## Rychlé odpovědi
- **Jaká je hlavní metoda?** `Feature.GetValueOrDefault<T>()`  
- **Mohu nastavit vlastní výchozí hodnotu?** Ano, pomocí přetížení, které přijímá výchozí hodnotu, nebo definováním `DefaultValue` na atributu.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Podporované formáty geometrie?** GeoJSON, Shapefile, GML a mnoho dalších prostřednictvím ovladačů Aspose.GIS.  
- **Funguje s .NET Core/.NET 6+?** Rozhodně – knihovna je multiplatformní.

## Požadavky
- Základní znalost C# a ekosystému .NET.  
- Aspose.GIS pro .NET nainstalován. Pokud jej ještě nemáte, stáhněte jej z [zde](https://releases.aspose.com/gis/net/).  
- Editor kódu, například Visual Studio nebo Visual Studio Code.

## Importujte jmenné prostory
Přidejte potřebné `using` direktivy do vašeho C# souboru, aby byly typy API k dispozici:

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Nyní projděme každý příklad krok za krokem.

## Jak získat hodnotu atributu (výchozí)
### Krok 1: Nastavte prostředí
Definujte cestu ke složce, která obsahuje vaše testovací dokumenty:

```csharp
string dataDir = "Your Document Directory";
```

### Krok 2: Vytvořte GeoJSON vrstvu
**Vytvoříme geojson vrstvu** — první místo, kde definujeme atribut, který může být null nebo nenastavený:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```

### Krok 3: Vytvořte GIS prvek
**Vytvoříme GIS prvek** — tím získáme čerstvou instanci prvku, která respektuje schéma atributů, jež jsme právě definovali:

```csharp
    Feature feature = layer.ConstructFeature();
```

### Krok 4: Získejte hodnoty
Nakonec **získáme hodnoty atributu prvku** pomocí několika scénářů, což demonstruje, jak fungují výchozí hodnoty:

```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // value == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // value == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // value == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```

## Jak nastavit výchozí hodnoty
### Krok 1: Vytvořte další GeoJSON vrstvu
Tentokrát **nastavíme výchozí hodnotu atributu** přímo ve schématu:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```

### Krok 2: Vytvořte GIS prvek (znovu)

```csharp
    Feature feature = layer.ConstructFeature();
```

### Krok 3: Získejte a nastavte hodnoty
Získáme výchozí hodnotu a poté ji změníme, abychom viděli efekt **nastavení výchozí hodnoty** za běhu:

```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // value == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // value == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // value == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```

## Časté úskalí a tipy
- **Nikdy nezapomeňte uzavřít blok `using`.** Vrstva se automaticky uvolní, čímž se uvolní souborové handle.  
- **Když je `CanBeNull` nastaveno na false, `GetValueOrDefault` vždy vrátí hodnotu** (buď uloženou, nebo definovanou výchozí).  
- **Použijte generické přetížení** (`GetValueOrDefault<T>`), abyste se vyhnuli boxování/odboxování pro hodnotové typy.  
- **Pro tip:** Pokud potřebujete zjistit, zda je atribut skutečně nastaven, použijte `feature.IsAttributeSet("attribute")` před voláním `GetValueOrDefault`.

## Často kladené otázky
### Je Aspose.GIS kompatibilní s .NET Core?
Ano, Aspose.GIS je plně kompatibilní s .NET Core a poskytuje multiplatformní podporu.

### Mohu použít Aspose.GIS pro komerční projekty?
Rozhodně! Aspose.GIS má komerční licenci, která vám umožní používat jej v komerčních aplikacích bez jakýchkoli omezení.

### Kde najdu další podporu a zdroje?
Navštivte [Aspose.GIS fórum](https://forum.aspose.com/c/gis/33) pro komunitní podporu a prozkoumejte [dokumentaci](https://reference.aspose.com/gis/net/) pro podrobné informace.

### Je k dispozici bezplatná zkušební verze?
Ano, můžete si vyzkoušet Aspose.GIS pomocí bezplatné zkušební verze. Stáhněte ji [zde](https://releases.aspose.com/).

### Jak získat dočasnou licenci pro testovací účely?
Pro dočasné licence navštivte [zde](https://purchase.aspose.com/temporary-license/).

## Další FAQ
**Q: Co se stane, když zavolám `GetValueOrDefault` na atribut, který neexistuje?**  
A: Metoda vyhodí `ArgumentException`. Vždy ověřte název atributu nebo nejprve použijte `feature.HasAttribute("name")`.

**Q: Mohu změnit výchozí hodnotu po vytvoření vrstvy?**  
A: Ano, můžete upravit `attribute.DefaultValue` a poté zavolat `layer.UpdateAttribute(attribute)`, aby se změna uložila.

**Q: Podporuje Aspose.GIS hromadné aktualizace hodnot atributů?**  
A: Můžete iterovat přes kolekci prvků a volat `SetValue` na každém prvku; pro velké datové sady zvažte použití API `FeatureCursor` pro lepší výkon.

## Závěr
V tomto průvodci jsme pokryli **jak získat hodnotu atributu**, jak definovat a přepsat výchozí hodnoty a jak **vytvořit GeoJSON vrstvu** se schématy, která vyhovují potřebám vaší aplikace. S těmito technikami můžete vytvářet robustní GIS řešení, která elegantně zvládají chybějící nebo volitelné údaje.

---

**Last Updated:** 2026-01-05  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
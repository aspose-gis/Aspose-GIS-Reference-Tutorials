---
title: Získat hodnotu atributu funkce (výchozí)
linktitle: Získat hodnotu atributu funkce (výchozí)
second_title: Aspose.GIS .NET API
description: Odemkněte sílu Aspose.GIS pro .NET! Pomocí tohoto podrobného průvodce můžete snadno získávat a manipulovat s hodnotami atributů funkcí. Stáhněte si zkušební verzi nyní!
weight: 14
url: /cs/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Získat hodnotu atributu funkce (výchozí)

## Úvod
Vítejte ve světě Aspose.GIS pro .NET! V tomto komplexním průvodci se ponoříme do složitosti získávání hodnot atributů funkcí pomocí výkonných možností Aspose.GIS. Ať už jste zkušený vývojář nebo teprve začínáte, tento tutoriál vám poskytne podrobný návod a zajistí, že využijete plný potenciál tohoto pozoruhodného nástroje.
## Předpoklady
Než se pustíme do tohoto kódovacího dobrodružství, ujistěte se, že máte splněny následující předpoklady:
- Pracovní znalost C# a .NET frameworku.
-  Aspose.GIS pro .NET nainstalován. Pokud ne, stáhněte si jej z[tady](https://releases.aspose.com/gis/net/).
- Editor kódu, jako je Visual Studio, plynule následovat.
## Importovat jmenné prostory
Ve svém projektu C# nezapomeňte zahrnout potřebné jmenné prostory:
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
Nyní si každý příklad rozdělíme do série snadno pochopitelných kroků.
## Získat hodnotu atributu funkce (výchozí)
### Krok 1: Nastavte prostředí
Začněte definováním cesty k adresáři dokumentů:
```csharp
string dataDir = "Your Document Directory";
```
### Krok 2: Vytvořte vrstvu GeoJson
Vytvořte vrstvu GeoJson a definujte atribut s výchozími hodnotami:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### Krok 3: Vytvořte prvek
Vytvořte prvek pomocí definovaného atributu:
```csharp
    Feature feature = layer.ConstructFeature();
```
### Krok 4: Načtení hodnot
Získejte hodnoty atributů pomocí různých scénářů:
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // hodnota == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // hodnota == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // hodnota == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## Nastavení výchozích hodnot
### Krok 1: Vytvořte další vrstvu GeoJson
Opakujte proces s jinou vrstvou GeoJson a dvojitým atributem:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### Krok 2: Vytvořte prvek (znovu)
```csharp
    Feature feature = layer.ConstructFeature();
```
### Krok 3: Načtení a nastavení hodnot
Načíst a nastavit hodnoty atributů, předvést výchozí hodnoty:
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // hodnota == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // hodnota == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // hodnota == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
Gratulujeme! Úspěšně jste využili sílu Aspose.GIS pro .NET při získávání a manipulaci s hodnotami atributů funkcí.
## Závěr
V tomto tutoriálu jsme prozkoumali nuance načítání hodnot atributů funkcí pomocí Aspose.GIS pro .NET. Aspose.GIS se svým intuitivním API a robustními schopnostmi otevírá svět možností pro vývoj GIS v prostředích .NET.
## Často kladené otázky
### Je Aspose.GIS kompatibilní s .NET Core?
Ano, Aspose.GIS je plně kompatibilní s .NET Core a poskytuje podporu napříč platformami.
### Mohu použít Aspose.GIS pro komerční projekty?
Absolutně! Aspose.GIS je dodáván s komerční licencí, která vám umožňuje používat jej ve vašich komerčních aplikacích bez jakýchkoli omezení.
### Kde najdu další podporu a zdroje?
 Navštivte[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) za podporu komunity a prozkoumejte[dokumentace](https://reference.aspose.com/gis/net/) pro podrobné informace.
### Je k dispozici bezplatná zkušební verze?
 Ano, můžete prozkoumat Aspose.GIS pomocí bezplatné zkušební verze. Stáhnout to[tady](https://releases.aspose.com/).
### Jak získám dočasnou licenci pro testovací účely?
 Pro dočasné licence navštivte[tady](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

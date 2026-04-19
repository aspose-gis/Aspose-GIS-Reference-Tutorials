---
date: 2026-01-10
description: Naučte se, jak pomocí Aspose.GIS pro .NET vytvářet dataset .NET pro souborovou
  geodatabázi. Průvodce krok za krokem pro snadnou správu GIS dat.
linktitle: Create New File GDB Dataset
second_title: Aspose.GIS .NET API
title: Vytvořit .NET dataset souborové geodatabáze pomocí Aspose.GIS
url: /cs/net/layer-management/create-new-file-gdb-dataset/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření .NET datasetu File Geodatabase s Aspose.GIS

## Úvod

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Vytvoření nového File Geodatabase, přidání dvou vrstev a ověření datasetu pomocí Aspose.GIS pro .NET.  
- **Jak dlouho to trvá?** Přibližně 10‑15 minut pro vývojáře, který ovládá C#.  
- **Požadavky?** .NET vývojové prostředí, knihovna Aspose.GIS pro .NET a zapisovatelná cesta ke složce.  
- **Mohu to použít v .NET Core / .NET 6+?** Ano – API je plně kompatibilní s moderními .NET runtime.  
- **Potřebuji licenci?** Pro produkční použití je vyžadována dočasná nebo trvalá licence Aspose.GIS.

## Co je File Geodatabase?
File Geodatabase (File GDB) je složkový úložiště dat, které obsahuje GIS třídy prvků, rastrové datasetu a související metadata. Nabízí rychlý výkon čtení/zápisu, podporuje velké datasetu a je široce používán v ekosystému Esri ArcGIS. Pomocí Aspose.GIS můžete tyto databáze vytvářet a manipulovat s nimi přímo z .NET kódu bez jakéhokoli externího GIS softwaru.

## Proč vytvářet File Geodatabase v .NET s Aspose.GIS?
- **Žádné externí závislosti** – knihovna zajišťuje všechny detaily formátu souboru.  
- **Cross‑platform** – funguje na Windows, Linux a macOS .NET runtime.  
- **Bohatá podpora geometrie** – body, linie, polygony a další.  
- **Plná kontrola** – vy rozhodujete o schématu, atributech a prostorovém referenčním systému.

## Požadavky
Než začnete, ujistěte se, že máte následující:

- Aspose.GIS pro .NET nainstalováno. Můžete jej stáhnout ze [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).  
- Vývojové prostředí, např. Visual Studio 2022 (nebo jakékoli IDE podporující .NET).  
- Zapisovatelná složka ve vašem počítači, kde bude vytvořen nový GDB – nahraďte `"Your Document Directory"` v kódu touto cestou.  
- Základní znalost C# a struktury .NET projektu.

## Importovat jmenné prostory
Nejprve importujte jmenné prostory, které vám poskytují přístup ke třídám Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Průvodce krok za krokem

### Krok 1: Vytvoření nového datasetu File GDB
Následující úryvek vytvoří prázdný File Geodatabase. Toto je jádro **create file geodatabase .net**.

```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Output: 0
    // Continue with subsequent steps...
}
```

**Vysvětlení:** `Dataset.Create` inicializuje GDB na zadané cestě pomocí ovladače `FileGdb`. V tomto okamžiku dataset neobsahuje žádné vrstvy, takže počet vrstev je nula.

### Krok 2: Vytvoření a naplnění `layer_1`
Nyní přidáme první vrstvu, která ukládá celočíselné atributy a geometrie bodů.

```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```

**Vysvětlení:**  
- `CreateLayer` vytvoří novou třídu prvků s názvem **layer_1**.  
- Definuje se celočíselný atribut s názvem **value**.  
- Smyčka přidá deset prvků, každý s unikátním číslem a bodem na souřadnicích *(i, i)*.

### Krok 3: Vytvoření a naplnění `layer_2`
Dále přidáme druhou vrstvu, která demonstruje práci s liniovou geometrií.

```csharp
using (var layer = dataset.CreateLayer("layer_2"))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```

**Vysvětlení:** Toto vytvoří **layer_2** a vloží jediný prvek, jehož geometrie je `LineString` spojující dva body.

### Krok 4: Ověření aktualizovaného počtu vrstev
Nakonec potvrďte, že obě vrstvy byly úspěšně přidány.

```csharp
Console.WriteLine(dataset.LayersCount); // Output: 2
```

**Vysvětlení:** Dataset nyní hlásí dvě vrstvy, což potvrzuje, že proces **create file geodatabase .net** byl úspěšně dokončen.

## Časté problémy a řešení
| Problém | Proč k tomu dochází | Řešení |
|-------|----------------|-----|
| **`UnauthorizedAccessException`** při vytváření datasetu | Cesta ke složce je jen pro čtení nebo nemáte oprávnění. | Vyberte zapisovatelný adresář nebo spusťte Visual Studio jako administrátor. |
| **`ArgumentException` pro ovladač** | Název ovladače je špatně napsán nebo verze knihovny jej nepodporuje. | Použijte `Drivers.FileGdb` přesně tak, jak je uvedeno; ujistěte se, že máte nejnovější balíček Aspose.GIS. |
| **Features not appearing in ArcGIS** | Chybí prostorová reference nebo je geometrie nekompatibilní. | Nastavte prostorovou referenci na vrstvě, pokud je potřeba, a ujistěte se, že geometrie jsou platné. |

## Často kladené otázky
### Q: Mohu použít Aspose.GIS pro .NET s jinými GIS knihovnami?
Aspose.GIS pro .NET je samostatná sada nástrojů; můžete ji však integrovat s jinými .NET knihovnami pro rozšíření funkcionality.

### Q: Existuje komunitní fórum pro podporu Aspose.GIS?
Ano, podporu a diskuze najdete na [Aspose.GIS Forum](https://forum.aspose.com/c/gis/33).

### Q: Jak mohu získat dočasnou licenci pro Aspose.GIS?
Navštivte stránku [Temporary License](https://purchase.aspose.com/temporary-license/) pro informace o získání dočasné licence.

### Q: Jsou k dispozici další příklady a dokumentace?
Prozkoumejte [Aspose.GIS documentation](https://reference.aspose.com/gis/net/) pro více příkladů a podrobné informace.

### Q: Kde mohu zakoupit Aspose.GIS pro .NET?
Aspose.GIS pro .NET můžete zakoupit na [purchase page](https://purchase.aspose.com/buy).

## Závěr
Úspěšně jste **vytvořili .NET dataset File Geodatabase**, přidali dvě odlišné vrstvy a ověřili výsledek pomocí Aspose.GIS. Tento základ vám umožní budovat bohatší GIS aplikace – přidávat další vrstvy, definovat složitá schémata nebo integrovat s webovými službami. Prozkoumejte dále API Aspose.GIS pro práci s rastrovými daty, prostorovými dotazy a pokročilými operacemi s geometrií.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.GIS for .NET 24.11 (or latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
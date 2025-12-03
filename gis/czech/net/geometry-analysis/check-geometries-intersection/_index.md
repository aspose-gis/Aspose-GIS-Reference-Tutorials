---
date: 2025-12-03
description: Naučte se, jak v C# vytvořit polygonovou geometrii a detekovat překrývající
  se polygony pomocí metody Intersects v Aspose.GIS pro .NET.
language: cs
linktitle: Create Polygon Geometry C#
second_title: Aspose.GIS .NET API
title: Vytvořte polygonovou geometrii v C# a zkontrolujte průnik pomocí Aspose.GIS
  pro .NET
url: /net/geometry-analysis/check-geometries-intersection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření polygonové geometrie v C# a kontrola průniku pomocí Aspose.GIS pro .NET

## Úvod
Pokud potřebujete **vytvořit polygonovou geometrii v C#** a rychle zjistit, zda se dva tvary překrývají, Aspose.GIS pro .NET vám poskytuje čisté, vysoce výkonné API. V tomto průvodci projdeme celý proces – od nastavení knihovny po použití metody `Intersects` k **detekci překrývajících se polygonů**. Na konci budete schopni integrovat kontrolu průniku polygonů do jakékoli .NET aplikace pomocí několika řádků kódu.

## Rychlé odpovědi
- **Co dělá metoda Intersects?** Vrací `true`, pokud dvě geometrie sdílejí jakoukoli společnou oblast.  
- **V jakém jmenném prostoru jsou třídy polygonu?** `Aspose.Gis.Geometries`.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Mohu to použít s .NET Core / .NET 6+?** Ano, Aspose.GIS podporuje všechny moderní .NET runtime.  
- **Jak dlouho trvá spuštění ukázky?** Méně než sekunda na typickém vývojovém počítači.

## Co znamená „vytvořit polygonovou geometrii v C#“?
Vytvoření polygonové geometrie v C# znamená vytvořit instanci třídy `Polygon` (nebo jiných typů geometrie) poskytované knihovnou Aspose.GIS a předat uzavřený kruh objektů `Point`, které definují vrcholy tvaru. Po vytvoření může geometrie provádět prostorové operace, jako jsou průnik, obsahování a výpočty vzdáleností.

## Proč použít Aspose.GIS k detekci překrývajících se polygonů?
- **Žádné externí závislosti** – čistá .NET knihovna, bez nativních GIS instalací.  
- **Bohaté prostorové operace** – `Intersects`, `Disjoint`, `Contains` atd., připravené k použití.  
- **Vysoká přesnost** – robustní zpracování okrajových případů, jako jsou sdílené hrany nebo vrcholy.  
- **Cross‑platform** – funguje na Windows, Linuxu i macOS s .NET Core/5/6.

## Předpoklady
Než začnete, ujistěte se, že máte:

1. **Aspose.GIS pro .NET** nainstalovaný (viz kroky níže).  
2. Vývojové prostředí .NET (Visual Studio, VS Code nebo Rider).  
3. .NET Framework 4.6+ nebo .NET Core 3.1+.

### Instalace Aspose.GIS pro .NET
1. **Přejděte na stránku ke stažení:** Navštivte [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/) a získejte nejnovější verzi toolkit‑u.  
2. **Stáhněte toolkit:** Vyberte verzi kompatibilní s vaším vývojovým prostředím a stáhněte toolkit.  
3. **Nainstalujte toolkit:** Postupujte podle poskytnutých instalačních instrukcí a nainstalujte Aspose.GIS pro .NET na svůj vývojový počítač.

## Import jmenných prostorů
Chcete‑li začít pracovat s Aspose.GIS pro .NET, musíte do svého projektu importovat potřebné jmenné prostory.

1. **Přidejte reference:** Ve svém projektu přidejte reference na sestavu Aspose.GIS.  
2. **Importujte jmenné prostory:** V souboru kódu importujte požadované jmenné prostory. Pro uvedený příklad se ujistěte, že importujete následující jmenné prostory:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Jak vytvořit polygonovou geometrii v C# pomocí Aspose.GIS?
Nyní, když je prostředí připravené, vytvoříme dva jednoduché polygonové geometrie, které později otestujeme na překrytí.

### Krok 1: Definice geometrie
V tomto kroku vytvoříte polygony představující dvě obdélníkové oblasti. Vrcholy jsou definovány ve směru hodinových ručiček a první bod je na konci zopakován, aby se uzavřel kruh.

```csharp
var geometry1 = new Polygon(new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 3),
    new Point(3, 3),
    new Point(3, 0),
    new Point(0, 0),
}));
var geometry2 = new Polygon(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 4),
    new Point(4, 4),
    new Point(4, 1),
    new Point(1, 1),
}));
```

### Krok 2: Použití metody Intersects k detekci překrývajících se polygonů
Po definování geometrie můžeme zavolat metodu `Intersects`. Tato metoda **používá algoritmus Intersects** k ověření, zda jakákoli část dvou polygonů sdílí stejný prostor.

```csharp
Console.WriteLine(geometry1.Intersects(geometry2)); // True
Console.WriteLine(geometry2.Intersects(geometry1)); // True
```

### Krok 3: Kontrola nespojených geometrie (opačný výsledek k průniku)
Pokud potřebujete potvrdit, že se dva tvary **nepřekrývají**, metoda `Disjoint` poskytuje opačný výsledek.

```csharp
// 'Disjoint' is opposite to 'Intersects'
Console.WriteLine(geometry1.Disjoint(geometry2)); // False
```

## Časté problémy a řešení
| Problém | Proč k tomu dochází | Řešení |
|---------|----------------------|--------|
| **Vždy vrací `false`** | Polygony nejsou uzavřeny (první bod ≠ poslední bod). | Ujistěte se, že je první bod zopakován na konci pole souřadnic. |
| **Neočekávané `true` u dotýkajících se hran** | `Intersects` považuje sdílené hrany za průnik. | Použijte metodu `Touches`, pokud potřebujete detekci pouze dotyku hran. |
| **Problém s výkonem při velkém počtu polygonů** | Každé volání kontroluje každý pár vrcholů. | Zpracovávejte dávky pomocí `GeometryCollection` nebo prostorového indexování (R‑tree), pokud je podporováno. |

## Často kladené otázky

**Q: Mohu použít Aspose.GIS pro .NET s jinými .NET frameworky?**  
A: Ano, Aspose.GIS pro .NET je kompatibilní s různými .NET frameworky, včetně .NET Core a .NET Framework.

**Q: Je k dispozici bezplatná zkušební verze Aspose.GIS pro .NET?**  
A: Ano, bezplatnou zkušební verzi Aspose.GIS pro .NET získáte [zde](https://releases.aspose.com/).

**Q: Kde mohu najít podporu pro Aspose.GIS pro .NET?**  
A: Pomoc a komunitní podporu můžete získat na [Aspose.GIS fóru](https://forum.aspose.com/c/gis/33).

**Q: Mohu získat dočasnou licenci pro Aspose.GIS pro .NET?**  
A: Ano, dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

**Q: Kde mohu zakoupit licencovanou verzi Aspose.GIS pro .NET?**  
A: Licencovanou verzi Aspose.GIS pro .NET můžete zakoupit [zde](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2025-12-03  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose
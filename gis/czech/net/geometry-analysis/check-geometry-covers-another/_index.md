---
date: 2026-02-08
description: Naučte se, jak vytvořit linestring v C# pomocí Aspose.GIS pro .NET, přidávat
  body do linestringu a provádět kontrolu, zda bod leží na linii, pomocí metody covers.
linktitle: Create LineString C# – Check Geometry Covers Another
second_title: Aspose.GIS .NET API
title: Vytvořit LineString v C# – Zkontrolovat, zda geometrie pokrývá jinou
url: /cs/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zkontrolujte, zda geometrie pokrývá jinou

## Úvod
V tomto tutoriálu se naučíte **jak vytvořit linestring v C#** pomocí Aspose.GIS pro .NET, přidávat body do linestringu a provádět spolehlivou **kontrolu bodu na linii** pomocí metod `Covers` a `CoveredBy`. Ať už vytváříte mapovací nástroj, provádíte prostorovou analytiku nebo jen potřebujete ověřit geometrické vztahy, zvládnutí těchto operací dodá vaší aplikaci potřebnou přesnost.

## Rychlé odpovědi
- **Co znamená “create linestring c#”?** Jedná se o vytvoření objektu geometrie `LineString` a naplnění jej souřadnicovými body.  
- **Která metoda kontroluje, zda bod leží na linii?** Použijte metodu `Covers` na objektu `LineString` nebo `CoveredBy` na objektu `Point`.  
- **Potřebuji licenci pro spuštění ukázky?** Dočasná licence stačí pro vyhodnocení; pro produkční nasazení je vyžadována plná licence.  
- **Lze to použít s .NET Core?** Ano, Aspose.GIS podporuje .NET Framework i .NET Core.  
- **Kolik bodů mohu přidat do linestringu?** Neexistuje pevný limit; můžete přidat libovolný počet bodů potřebných pro vaši prostorovou analýzu.

## Co je **create linestring c#**?
`LineString` je geometrický tvar složený z uspořádaného seznamu bodů spojených přímými úsečkami. V C# jej vytvoříte instancí třídy `LineString` z namespace `Aspose.Gis.Geometries` a následně **přidáte body do linestringu** pomocí metody `AddPoint`.

## Proč použít Aspose.GIS pro kontrolu bodu na linii?
- **Přesnost** – Správně zpracovává výpočty s plovoucí desetinnou čárkou a prostorové predikáty, což vám poskytne **přesný výsledek kontroly bodu na linii**.  
- **Cross‑platform** – Funguje s .NET Framework, .NET Core i .NET 5/6+.  
- **Bohaté API** – Nabízí kompletní sadu metod pro prostorové vztahy (`Covers`, `CoveredBy`, `Intersects` atd.).  

## Předpoklady
Než se pustíte do používání Aspose.GIS pro .NET, ujistěte se, že máte nastaveny následující předpoklady:

### 1. Instalace Visual Studio
Ujistěte se, že máte na svém systému nainstalované Visual Studio. Aspose.GIS pro .NET se bez problémů integruje s Visual Studio a poskytuje plynulý vývojový zážitek.

### 2. Získání Aspose.GIS pro .NET
Stáhněte knihovnu Aspose.GIS pro .NET z [webu](https://releases.aspose.com/gis/net/). Můžete knihovnu stáhnout přímo nebo použít správce balíčků, například NuGet, k jejímu instalování do vašeho projektu.

### 3. Základní znalost .NET Framework
Základní povědomí o .NET frameworku a programovacím jazyce C# je nezbytné pro efektivní využití Aspose.GIS pro .NET.

### 4. Přístup k dokumentaci a podpoře
Podívejte se na [dokumentaci](https://reference.aspose.com/gis/net/) pro podrobné informace o API a funkcionalitách Aspose.GIS. V případě, že narazíte na problémy nebo máte otázky, využijte [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

### 5. Volitelné: Dočasná licence
Pokud zkoušíte Aspose.GIS pro .NET, můžete získat dočasnou licenci z [této stránky](https://purchase.aspose.com/temporary-license/) pro vyhodnocení funkcí knihovny.

## Importování jmenných prostorů
Před použitím Aspose.GIS pro .NET ve vašem projektu je třeba importovat potřebné jmenné prostory:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Nyní rozdělíme ukázkový kód do několika kroků, abychom pochopili, jak **zkontrolovat, zda jedna geometrie pokrývá jinou** pomocí Aspose.GIS pro .NET.

## Jak vytvořit linestring c# – Průvodce krok za krokem

### Krok 1: Vytvoření objektu LineString
```csharp
var line = new LineString();
```
Zde vytváříme novou instanci objektu `LineString`, který představuje sekvenci spojených úseček ve dvourozměrném prostoru.

### Krok 2: **Přidání bodů do LineString**
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
**Přidáváme body do linestringu** pomocí metody `AddPoint`. V tomto příkladu přidáváme dva body: (0, 0) a (1, 1), čímž vznikne jednoduchý úhlopříčný úsek.

### Krok 3: Vytvoření objektu Point
```csharp
var point = new Point(0, 0);
```
Instanciujeme objekt `Point`, který představuje jediný bod ve dvourozměrném prostoru. Zde vytvoříme bod s souřadnicemi (0, 0).

### Krok 4: Provedení **kontroly bodu na linii** – Pokrývá linie bod?
```csharp
Console.WriteLine(line.Covers(point));    // True
```
Použijte metodu `Covers` k ověření, zda linie pokrývá bod. V tomto případě vrátí `True`, protože bod (0, 0) leží přesně na linii.

### Krok 5: Ověření opačného vztahu – Je bod pokryt linií?
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
Podobně použijte metodu `CoveredBy` k ověření, zda je bod pokryt linií. Protože bod (0, 0) leží na linii, metoda také vrátí `True`.

## Časté problémy a řešení
| Problém | Proč se vyskytuje | Řešení |
|-------|----------------|-----|
| `line.Covers(point)` vrací `False`, i když bod vypadá, že leží na linii | Souřadnice bodu nejsou přesně stejné kvůli přesnosti plovoucí desetinné čárky. | Použijte `Math.Round` na souřadnice nebo provádějte kontrolu s tolerancí pomocí `line.Distance(point) < epsilon`. |
| Chybí `using Aspose.Gis.Geometries;` | Jmenný prostor není importován, což způsobuje chyby při kompilaci. | Ujistěte se, že je importní příkaz přítomen (viz sekce **Importování jmenných prostorů**). |
| Výjimka licence za běhu | Není načtena platná licence pro produkční prostředí. | Načtěte dočasnou nebo plnou licenci pomocí `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Často kladené otázky

**Q: Mohu použít Aspose.GIS pro .NET ve svých komerčních projektech?**  
A: Ano, Aspose.GIS pro .NET můžete používat jak v komerčních, tak v nekomerčních projektech po zakoupení odpovídající licence.

**Q: Je Aspose.GIS pro .NET kompatibilní s .NET Core?**  
A: Ano, Aspose.GIS pro .NET je kompatibilní jak s .NET Framework, tak s .NET Core.

**Q: Podporuje Aspose.GIS pro .NET různé GIS formáty?**  
A: Ano, Aspose.GIS pro .NET podporuje širokou škálu GIS formátů, včetně Shapefile, GeoJSON, KML a dalších.

**Q: Mohu přispívat k vývoji Aspose.GIS pro .NET?**  
A: Aspose.GIS pro .NET je proprietární knihovna vyvíjená společností Aspose, takže externí příspěvky nejsou přijímány. Můžete však poskytovat zpětnou vazbu a návrhy na vylepšení knihovny.

**Q: Jak často jsou vydávány aktualizace pro Aspose.GIS pro .NET?**  
A: Aktualizace pro Aspose.GIS pro .NET jsou vydávány pravidelně, aby přinesly nové funkce, vylepšení a opravy chyb. Nejnovější verze najdete na [webu](https://releases.aspose.com/gis/net/).

## Závěr
Po absolvování výše uvedených kroků nyní umíte **vytvořit linestring v C#**, **přidávat body do linestringu** a provádět spolehlivou **kontrolu bodu na linii** pomocí metod `Covers` a `CoveredBy`. Tato schopnost rozšiřuje funkce prostorové analýzy vašeho softwaru a otevírá cestu k pokročilejším GIS operacím.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-02-08  
**Testováno s:** Aspose.GIS pro .NET (nejnovější verze)  
**Autor:** Aspose
---
date: 2025-12-21
description: Naučte se, jak vytvořit geometrii typu linestring a převést ji na WKB
  pomocí Aspose.GIS pro .NET s variantou ExtendedPostGis.
linktitle: Specify WKB Variant on Translation
second_title: Aspose.GIS .NET API
title: Vytvořit geometrii Linestring a variantu WKB v Aspose.GIS .NET
url: /cs/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Specifikace varianty WKB při převodu v Aspose.GIS pro .NET

## Úvod
V oblasti vývoje geografických informačních systémů (GIS) vyniká Aspose.GIS pro .NET jako výkonná sada nástrojů. Pokud potřebujete **vytvořit geometrie linestring** a následně **převést geometrie na WKB**, jste na správném místě. Jeho všestrannost a efektivita z něj činí oblíbenou volbu pro vývojáře, kteří chtějí bezproblémově integrovat GIS funkce do svých .NET aplikací. Tento článek slouží jako komplexní průvodce využitím Aspose.GIS pro .NET, zaměřením na specifikaci variant WKB (Well‑Known Binary) během procesů převodu.

## Rychlé odpovědi
- **Co znamená zkratka WKB?** Well‑Known Binary, kompaktní binární reprezentace geometrických objektů.  
- **Která varianta WKB mi umožní uložit informaci SRID?** Varianta `ExtendedPostGis` (EWKB).  
- **Potřebuji licenci pro spuštění kódu?** Pro produkční použití je vyžadována dočasná nebo plná licence.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, a .NET 5/6+.  
- **Jak dlouho trvá implementace?** Obvykle méně než 10 minut pro základní příklad.

## Co je geometrie Linestring?
Linestring je jednoduchý geometrický tvar složený ze sekvence bodů spojených přímými úsečkami. Často se používá k reprezentaci silnic, řek nebo jakéhokoli lineárního prvku v GIS datech.

## Proč specifikovat variantu WKB?
Volba správné varianty WKB zajišťuje, že důležité metadata – jako je identifikátor prostorového referenčního systému (SRID) – jsou zachována při ukládání nebo výměně geometrických dat. Varianta `ExtendedPostGis` (EWKB) je zvláště užitečná při práci s PostgreSQL/PostGIS nebo jakýmkoli systémem, který očekává SRID vložený do binárního souboru.

## Požadavky
Před tím, než se ponoříte do podrobností specifikace variant WKB v Aspose.GIS pro .NET, ujistěte se, že máte splněny následující požadavky:

### Instalace Aspose.GIS pro .NET
1. Stáhněte Aspose.GIS: Navštivte [download link](https://releases.aspose.com/gis/net/) a získejte balíček Aspose.GIS pro .NET.  
2. Instalace balíčku: Postupujte podle instalačních instrukcí uvedených v dokumentaci a bezproblémově integrujte Aspose.GIS do svého .NET prostředí.

### Znalost programování v C#
1. Základní znalost C#: Ujistěte se, že máte pevné základy syntaxe a konceptů programovacího jazyka C#.

## Importování jmenných prostorů
Abyste mohli úspěšně zahájit práci s Aspose.GIS pro .NET a využívat jeho funkce, je třeba do projektu importovat potřebné jmenné prostory. Níže je krok‑za‑krokem návod:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Tyto jmenné prostory poskytují přístup k funkcím Aspose.GIS, což vám umožní snadno pracovat s geografickými daty.

## Jak vytvořit geometrie linestring?
Rozložme poskytnutý příklad do několika kroků, abychom podrobně pochopili proces specifikace variant WKB při převodu.

### Krok 1: Vytvoření objektu geometrie
```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
V tomto kroku **vytvoříme geometrie linestring**, která představuje lineární prvek se zadanými souřadnicemi.

### Krok 2: Generování reprezentace WKB
```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Zde **převedeme geometrie na WKB** pomocí varianty `ExtendedPostGis`, která vkládá informaci SRID.

### Krok 3: Zápis do souboru
```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
Nakonec zapíšeme vygenerovaná binární data WKB do souboru s názvem `EWkbFile.ewkb` v adresáři dle vašeho výběru.

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|---------|-------|--------|
| **Prázdný soubor** | `Path.Combine` ukazuje na neexistující adresář. | Ujistěte se, že cílový adresář existuje, nebo jej vytvořte pomocí `Directory.CreateDirectory`. |
| **Nesprávný SRID** | Použití výchozí varianty `WkbVariant.Standard` ztrácí SRID. | Vždy používejte `WkbVariant.ExtendedPostGis`, pokud je vyžadováno zachování SRID. |
| **Licence výjimka** | Spouštění bez platné licence v produkci. | Aplikujte dočasnou nebo plnou licenci před spuštěním kódu v produkčním prostředí. |

## Často kladené otázky
### Je Aspose.GIS pro .NET kompatibilní se všemi verzemi .NET?
Aspose.GIS pro .NET je navržen tak, aby byl kompatibilní s různými verzemi .NET, což zajišťuje flexibilitu a přístupnost pro vývojáře.

### Mohu požádat o podporu nebo asistenci při používání Aspose.GIS pro .NET?
Ano, můžete získat podporu a asistenci prostřednictvím dedikovaného [Aspose.GIS fóra](https://forum.aspose.com/c/gis/33), kde odborníci a ostatní vývojáři odpoví na vaše dotazy.

### Nabízí Aspose.GIS pro .NET bezplatnou zkušební verzi?
Ano, funkce a možnosti Aspose.GIS pro .NET můžete vyzkoušet zdarma na [tento odkaz](https://releases.aspose.com/).

### Jak mohu získat dočasnou licenci pro Aspose.GIS pro .NET?
Dočasnou licenci získáte návštěvou [stránky dočasné licence](https://purchase.aspose.com/temporary-license/) a podle poskytnutých instrukcí.

### Kde mohu zakoupit licenci pro Aspose.GIS pro .NET?
Licenci pro Aspose.GIS pro .NET můžete zakoupit na stránce nákupu na [tento odkaz](https://purchase.aspose.com/buy).

## Často kladené otázky
**Q: Mohu použít soubor EWKB s PostGIS?**  
A: Ano, varianta `ExtendedPostGis` vytváří EWKB, který obsahuje SRID a PostGIS jej může přímo načíst.

**Q: Je možné načíst soubor WKB zpět do objektu geometrie?**  
A: Rozhodně. Použijte `Geometry.FromBinary(byteArray)` k rekonstrukci geometrie.

**Q: Podporuje knihovna i jiné typy geometrie, například polygon?**  
A: Ano, Aspose.GIS pracuje s body, linestringy, polygony, multipolygony a dalšími typy.

**Q: Jak specifikovat jiný SRID při vytváření geometrie?**  
A: Nastavte SRID na objektu geometrie před voláním `AsBinary`, např. `geometry.SRID = 4326;`.

**Q: Bude tento kód fungovat na .NET Core?**  
A: Ano, stejné API funguje napříč .NET Framework, .NET Core i .NET 5/6.

**Poslední aktualizace:** 2025-12-21  
**Testováno s:** Aspose.GIS pro .NET 23.9 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
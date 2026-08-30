---
date: 2026-08-18
description: Převod desetinných stupňů na dms pomocí Aspose.GIS for .NET. Tento podrobný
  průvodce v C# ukazuje, jak převést zeměpisnou šířku/délku, desetinné stupně na dms
  a další.
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: Převést souřadnice
og_description: Jednoduchý převod desetinných stupňů na dms pomocí Aspose.GIS for
  .NET. Naučte se převádět hodnoty zeměpisné šířky‑délky do formátu DMS v minutách.
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: Převést desetinné stupně na dms pomocí Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  headline: How to convert decimal degrees to dms with Aspose.GIS for .NET
  type: TechArticle
- description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  name: How to convert decimal degrees to dms with Aspose.GIS for .NET
  steps:
  - name: start the conversion process
    text: We print a friendly message so you know the demo has begun.
  - name: convert to decimal degrees
    text: Even though the final goal is DMS, we start by showing the original decimal
      representation. This also demonstrates the **decimal degrees to dms** path you’ll
      later follow.
  - name: convert to degree decimal minutes
    text: This format (`DD°MM.m'`) is a common intermediate step when you need to
      **convert lat long degree minutes**.
  - name: convert to degree minutes seconds (dms)
    text: Here’s the core of our tutorial—**convert coordinates to dms**.
  - name: convert to GeoRef
    text: For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing
      workflows.
  type: HowTo
- questions:
  - answer: Aspose.GIS primarily targets .NET developers, but a Java version is also
      available.
    question: Is Aspose.GIS compatible with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.GIS before purchasing?
  - answer: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  - answer: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert coordinates
- Aspose.GIS
- .NET GIS processing
title: Jak převést desetinné stupně na dms pomocí Aspose.GIS for .NET
url: /cs/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak převést desetinné stupně na dms pomocí Aspose.GIS

## Úvod
V tomto tutoriálu se naučíte **jak převést desetinné stupně na dms** pomocí výkonné knihovny Aspose.GIS pro .NET. Ať už potřebujete **c# převést lat long**, generovat lidsky čitelné řetězce umístění pro zprávy, nebo jen prozkoumat různé formáty souřadnic, tento průvodce vás provede každým krokem s jasnými vysvětleními a připravenými ukázkami C#.

## Rychlé odpovědi
- **Co znamená „convert coordinates to dms“?** Převádí číselné hodnoty zeměpisné šířky/délky do tradičního zápisu stupně‑minuty‑sekundy.  
- **Která knihovna provádí převod?** Aspose.GIS pro .NET poskytuje třídu `GeoConvert` s vestavěnou podporou formátů.  
- **Potřebuji licenci pro vyzkoušení?** K dispozici je bezplatná zkušební verze; pro produkční použití je vyžadována komerční licence.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+ a .NET 5/6+.  
- **Mohu použít stejný kód pro jiné formáty?** Ano — stačí změnit hodnotu výčtu `PointFormats` (např. `DecimalDegrees`, `GeoRef`).  

## Co je převod souřadnic na dms?
Převod souřadnic na DMS přepisuje desetinné hodnoty zeměpisné šířky a délky do formátu jako `25°30'00"N 45°30'00"E`. Proces rozdělí každý desetinný stupeň na celé stupně, minuty (jedna šedesátina stupně) a sekundy (jedna šedesátina minuty) a poté připojí odpovídající indikátor hemisféry (N, S, E, W). Tento lidsky čitelný tvar je nezbytný pro mnoho starších datových sad a pro komunikaci přesných poloh bez použití desetinného zápisu.

## Proč použít Aspose.GIS pro převod souřadnic?
Aspose.GIS podporuje **více než 50 vstupních a výstupních formátů** a dokáže zpracovat GIS soubory o stovkách stránek, aniž by načítal celý dataset do paměti. API poskytuje submilimetrovou přesnost pro okrajové případy, jako jsou záporné hodnoty a označení hemisfér, a běží konzistentně na .NET runtime na Windows, Linuxu i macOS.

## Předpoklady
Before you start, make sure you have:

1. **Základní znalost C#** – seznámení s proměnnými, voláním metod a výstupem do konzole.  
2. **Aspose.GIS nainstalováno** – stáhněte nejnovější balíček z [Aspose.GIS website](https://releases.aspose.com/gis/net/). Můžete také prozkoumat hlavní stránky vydání Aspose na [Aspose releases website](https://releases.aspose.com/).  

## Importovat jmenné prostory
First, import the namespaces required for GIS operations:

Zástupný text pro import jmenných prostorů zůstává nezměněn.

## Průvodce krok za krokem

### Co je třída GeoConvert?
Třída `GeoConvert` poskytuje statické metody pro převod mezi formáty souřadnic, jako jsou desetinné stupně, DMS a GeoRef. Obsahuje přetížení, která přijímají surové číselné hodnoty nebo objekty `Point`, a vrací formátované řetězce nebo nové instance `Point`. Díky zpracování okrajových případů, jako jsou záporné souřadnice a zaokrouhlování, třída zajišťuje, že výstup odpovídá standardním GIS specifikacím, což usnadňuje integraci do jakékoli .NET mapovací aplikace.

### Krok 1: zahájit proces převodu
Vytiskneme přátelskou zprávu, abyste věděli, že demo začalo.

```csharp
using System;
using Aspose.Gis;
```

### Krok 2: převést na desetinné stupně
I když je konečným cílem DMS, začneme zobrazením původní desetinné reprezentace. Toto také demonstruje cestu **decimal degrees to dms**, kterou později použijete.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Krok 3: převést na stupně desetinné minuty
Tento formát (`DD°MM.m'`) je běžný mezikrok, když potřebujete **convert lat long degree minutes**.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Krok 4: převést na stupně minuty sekundy (dms)
Zde je jádro našeho tutoriálu — **convert coordinates to dms**.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Krok 5: převést na GeoRef
Pro úplnost také demonstrujeme formát `GeoRef`, užitečný v pracovních postupech dálkového snímání.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## Časté problémy a řešení
- **Nesprávná písmena hemisféry** — ujistěte se, že předáváte kladné hodnoty pro sever/východ a záporné pro jih/západ; API automaticky přidá správnou příponu.  
- **Neočekávaný prázdný výstup** — ověřte, že sestavení `Aspose.Gis` je správně odkazováno a že projekt cílí na podporovanou verzi .NET.  
- **Licence nebyla nalezena** — umístěte soubor licence do kořenového adresáře aplikace nebo ji nastavte programově pomocí `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.

## Často kladené otázky

**Q: Je Aspose.GIS kompatibilní s jinými programovacími jazyky?**  
A: Aspose.GIS je primárně určen pro .NET vývojáře, ale verze pro Javu je také k dispozici.

**Q: Mohu vyzkoušet Aspose.GIS před zakoupením?**  
A: Ano, můžete získat bezplatnou zkušební verzi Aspose.GIS na [webu](https://releases.aspose.com/).

**Q: Jak mohu získat podporu pro Aspose.GIS?**  
A: Můžete požádat o pomoc na komunitním fóru Aspose.GIS [zde](https://forum.aspose.com/c/gis/33).

**Q: Jsou k dispozici dočasné licence pro Aspose.GIS?**  
A: Ano, dočasné licence lze získat na [stránce dočasných licencí](https://purchase.aspose.com/temporary-license/).

**Q: Kde mohu zakoupit Aspose.GIS?**  
A: Aspose.GIS můžete zakoupit na [stránce nákupu](https://purchase.aspose.com/buy).

## Závěr
Po provedení těchto kroků nyní víte, jak **convert decimal degrees to dms** a další běžné GIS formáty pomocí Aspose.GIS pro .NET. Tato schopnost vám umožní bez problémů integrovat lidsky čitelné řetězce umístění do mapovacích aplikací, zpráv nebo jakéhokoli pracovního postupu s prostorovými daty. Klidně experimentujte s různými hodnotami zeměpisné šířky/délky a prozkoumejte další formáty nabízené třídou `GeoConvert`.

---

**Poslední aktualizace:** 2026-08-18  
**Testováno s:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Související tutoriály

- [Jak vytvořit bodovou geometrii a získat typ geometrie pomocí Aspose.GIS pro .NET](/gis/net/geometry-analysis/get-geometry-type/)
- [Jak převést GeoJSON – Aspose.GIS pro .NET](/gis/net/geo-data-conversion/)
- [Vytvořit MultiPoint geometrii .NET s Aspose.GIS](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
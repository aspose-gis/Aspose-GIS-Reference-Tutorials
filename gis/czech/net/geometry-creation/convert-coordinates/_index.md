---
date: 2025-12-11
description: Naučte se, jak převést souřadnice na DMS pomocí Aspose.GIS pro .NET.
  Obsahuje příklady v C#, převod šířky a délky v C# a podrobný návod krok za krokem.
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: Převod souřadnic na DMS pomocí Aspose.GIS pro .NET
url: /cs/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod souřadnic na DMS pomocí Aspose.GIS

## Úvod
V tomto tutoriálu se dozvíte, jak **převést souřadnice na DMS** (stupně, minuty, sekundy) pomocí výkonné knihovny Aspose.GIS pro .NET. Ať už potřebujete c# převést zeměpisnou šířku a délku pro mapové aplikace, generovat lidsky čitelné řetězce umístění, nebo jen prozkoumat různé formáty souřadnic, tento průvodce vás provede každým krokem s jasnými vysvětleními a připraveným kódem v C#.

## Rychlé odpovědi
- **Co znamená „převést souřadnice na DMS“?** Převádí číselné hodnoty zeměpisné šířky/délky do tradičního zápisu stupně‑minuty‑sekundy.  
- **Která knihovna provádí převod?** Aspose.GIS pro .NET poskytuje třídu `GeoConvert` s vestavěnou podporou formátů.  
- **Potřebuji licenci pro vyzkoušení?** K dispozici je bezplatná zkušební verze; pro produkční použití je vyžadována komerční licence.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+ a .NET 5/6+.  
- **Mohu použít stejný kód i pro jiné formáty?** Ano – stačí změnit hodnotu výčtu `PointFormats` (např. `DecimalDegrees`, `GeoRef`).  

## Co je převod souřadnic na DMS?
Převod souřadnic na DMS přepisuje desetinné hodnoty zeměpisné šířky a délky do formátu jako `25°30'00"N 45°30'00"E`. Toto vyjádření je široce používáno v kartografii, navigaci a výměně GIS dat.

## Proč použít Aspose.GIS pro převod souřadnic?
- **All‑in‑one API** – Žádné externí knihovny ani složitá matematika; Aspose.GIS interně zpracovává parsování a formátování.  
- **Vysoká přesnost** – Precizní zpracování okrajových případů, jako jsou záporné hodnoty a označení polokoulí.  
- **Cross‑platform** – Funguje stejně na Windows, Linuxu i macOS .NET runtime.  
- **Rozšiřitelný** – Snadno přepíná mezi DMS, desetinnými stupni, stupně‑desetinné‑minuty a formáty GeoRef.  

## Předpoklady
1. **Základní znalost C#** – Znalost proměnných, volání metod a výstupu do konzole.  
2. **Aspose.GIS nainstalováno** – Stáhněte nejnovější balíček z [webu Aspose.GIS](https://releases.aspose.com/gis/net/).  

## Importování jmenných prostorů
Nejprve importujte jmenné prostory potřebné pro GIS operace:

```csharp
using System;
using Aspose.Gis;
```

## Průvodce krok za krokem

### Krok 1: Zahájení procesu převodu
Vytiskneme přátelskou zprávu, abyste věděli, že demo začalo.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Krok 2: Převod na desetinné stupně  
I když je konečným cílem DMS, nejprve zobrazíme původní desetinnou reprezentaci.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Krok 3: Převod na stupně‑desetinné‑minuty  
Tento formát (`DD°MM.m'`) je běžný mezikrok, když potřebujete *convert lat long degree minutes*.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Krok 4: Převod na stupně‑minuty‑sekundy (DMS)  
Zde je jádro našeho tutoriálu—**převést souřadnice na DMS**.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### Krok 5: Převod na GeoRef  
Pro úplnost také demonstrujeme formát `GeoRef`, užitečný v pracovních postupech dálkového snímání.

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Časté problémy a řešení
- **Nesprávná písmena polokoulí** – Ujistěte se, že předáváte kladné hodnoty pro sever/východ a záporné pro jih/západ; API automaticky přidá správnou příponu.  
- **Neočekávaný prázdný výstup** – Ověřte, že je sestavení `Aspose.Gis` správně referencováno a že projekt cílí na podporovanou verzi .NET.  
- **Licence nebyla nalezena** – Umístěte soubor licence do kořenového adresáře aplikace nebo ji nastavte programově pomocí `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.  

## Často kladené otázky

**Q: Je Aspose.GIS kompatibilní s jinými programovacími jazyky?**  
A: Aspose.GIS je primárně určen pro vývojáře .NET, ale je k dispozici i verze pro Javu.

**Q: Můžu vyzkoušet Aspose.GIS před zakoupením?**  
A: Ano, můžete získat bezplatnou zkušební verzi Aspose.GIS z [webu](https://releases.aspose.com/).

**Q: Jak mohu získat podporu pro Aspose.GIS?**  
A: Můžete požádat o pomoc na komunitním fóru Aspose.GIS [zde](https://forum.aspose.com/c/gis/33).

**Q: Jsou k dispozici dočasné licence pro Aspose.GIS?**  
A: Ano, dočasné licence lze získat na [stránce dočasných licencí](https://purchase.aspose.com/temporary-license/).

**Q: Kde mohu zakoupit Aspose.GIS?**  
A: Aspose.GIS můžete zakoupit na [stránce nákupu](https://purchase.aspose.com/buy).

## Závěr
Po provedení těchto kroků nyní víte, jak **převést souřadnice na DMS** a další běžné GIS formáty pomocí Aspose.GIS pro .NET. Tato schopnost vám umožní bez problémů integrovat lidsky čitelné řetězce umístění do mapových aplikací, reportů nebo jakéhokoli pracovního postupu se prostorovými daty. Klidně experimentujte s různými hodnotami zeměpisné šířky/délky a prozkoumejte další formáty nabízené třídou `GeoConvert`.

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
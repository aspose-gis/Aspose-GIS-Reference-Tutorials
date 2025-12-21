---
date: 2025-12-21
description: Naučte se, jak vytvořit vektorovou vrstvu, nastavit toleranci linearizace
  a přidat prvek do vrstvy pomocí Aspose.GIS pro .NET. Postupujte podle tohoto krok‑za‑krokem
  průvodce pro export souborů GeoJSON.
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: Vytvořte vektorovou vrstvu a nastavte toleranci linearizace pomocí Aspose.GIS
  pro .NET
url: /cs/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření vektorové vrstvy a nastavení tolerance linearizace pomocí Aspose.GIS pro .NET

## Úvod
Pokud potřebujete **vytvořit vektorovou vrstvu** souborů, řídit přesnost křivek a exportovat výsledek jako dokument GeoJSON, Aspose.GIS pro .NET to dělá jednoduchým. V tomto tutoriálu se naučíte, jak nakonfigurovat možnosti GeoJSON, nastavit toleranci linearizace a **přidat prvek do vrstvy** – vše při zachování čistého a produkčně připraveného kódu.

## Rychlé odpovědi
- **Co znamená „vytvořit vektorovou vrstvu“?** Vytvoří nový GIS vektorový dataset (např. soubor GeoJSON), který může ukládat geometrie a atributy.  
- **Jak nastavit toleranci?** Použijte vlastnost `LinearizationTolerance` třídy `GeoJsonOptions`.  
- **Mohu exportovat soubor GeoJSON?** Ano – jednoduše vytvořte `VectorLayer` s ovladačem `Drivers.GeoJson`.  
- **Potřebuji licenci?** Platná licence Aspose.GIS odemkne všechny funkce; dočasná licence funguje pro hodnocení.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co je „vytvořit vektorovou vrstvu“?
Vytvoření vektorové vrstvy znamená inicializaci nového GIS kontejneru (např. souboru GeoJSON), který může obsahovat geometrické prvky jako body, linie a polygony. Tato vrstva se stane cílem pro jakoukoli geometrii, kterou vytvoříte, a pro jakékoli atributy, které připojíte.

## Proč konfigurovat možnosti GeoJSON?
Konfigurace možností GeoJSON – zejména **tolerance linearizace** – zajišťuje, že zakřivené geometrie (např. `CircularString`) jsou aproximovány s přesností, která splňuje požadavky vaší aplikace. Tento krok je klíčový, když později **exportujete soubor GeoJSON** pro použití ve webových mapách nebo prostorových analýzách.

## Předpoklady
Než začneme, ujistěte se, že máte:

1. **Visual Studio** nainstalované (jakoukoli nedávnou verzi).  
2. **Licenci Aspose.GIS** (nebo dočasný evaluační klíč).  
3. **Knihovnu Aspose.GIS pro .NET** staženou a přidanou do vašeho projektu.  
4. Základní znalosti **C#**.

## Import jmenných prostorů
Nejprve importujte požadované jmenné prostory, aby kompilátor věděl, kde najít GIS třídy:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Průvodce krok za krokem

### Krok 1: Konfigurace možností GeoJSON (jak nastavit toleranci)
Vytvoříme objekt `GeoJsonOptions` a řekneme Aspose.GIS, jak blízko má být linearizovaná geometrie k původní křivce.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Krok 2: Definice výstupní cesty (jak exportovat GeoJSON)
Určete, kam bude výsledný soubor uložen. Nahraďte zástupný text skutečnou složkou.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Krok 3: **Vytvoření vektorové vrstvy** s nakonfigurovanými možnostmi
Nyní skutečně **vytvoříme vektorovou vrstvu** pomocí metody `VectorLayer.Create`. Blok `using` zajišťuje řádné uvolnění prostředků.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Krok 4: Konstrukce geometrie (např. kruhový řetězec)
Zde vytvoříme ukázkovou geometrii – `CircularString`. Můžete ji nahradit libovolným platným WKT.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Krok 5: **Přidání prvku do vrstvy** a uložení
Nakonec vytvoříme prvek, přiřadíme mu geometrii a přidáme jej do vrstvy. Toto je jádro operace **add feature to layer**.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Když blok `using` skončí, vrstva se automaticky zapíše do souboru definovaného v `path`, čímž získáte připravený soubor GeoJSON.

## Časté problémy a tipy
- **Nesprávná cesta** – Ujistěte se, že adresář existuje a máte oprávnění k zápisu.  
- **Příliš nízká tolerance** – Nastavení `LinearizationTolerance` na velmi malou hodnotu může dramaticky zvýšit velikost souboru. Přizpůsobte ji podle požadované přesnosti.  
- **Chyby licence** – Pokud vidíte varování o licenci, ověřte, že soubor licence je načten před jakýmkoli voláním Aspose.GIS.

## Často kladené otázky

**Q: Je Aspose.GIS pro .NET kompatibilní s jinými .NET frameworky?**  
A: Ano, funguje s .NET Framework, .NET Core i .NET 5/6/7.

**Q: Mohu používat Aspose.GIS v komerčních projektech?**  
A: Rozhodně. Komerční licence odstraňuje všechna omezení hodnocení.

**Q: Podporuje Aspose.GIS i jiné GIS formáty kromě GeoJSON?**  
A: Ano, podporuje Shapefile, KML, GML a mnoho dalších.

**Q: Je k dispozici zkušební verze?**  
A: Bezplatnou zkušební verzi si můžete stáhnout z webu Aspose.

**Q: Kde mohu získat podporu?**  
A: Použijte fóra Aspose nebo odkaz na podporu v sekci zdrojů.

## Závěr
Po absolvování těchto kroků nyní víte, jak **vytvořit vektorovou vrstvu**, nakonfigurovat toleranci linearizace a **přidat prvek do vrstvy** pro bezproblémové **exportování souboru GeoJSON**. Prozkoumejte další typy geometrie a práci s atributy, abyste plně využili Aspose.GIS ve svých .NET GIS projektech.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2025-12-21  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose  

---
---
date: 2026-04-09
description: Naučte se, jak převést křivky na čáry (linearizovat geometrii) pomocí
  Aspose.GIS pro .NET, což umožní efektivní zpracování a analýzu geoprostorových dat
  ve vašich .NET aplikacích.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
linktitle: Linearizovat geometrii
second_title: Aspose.GIS .NET API
title: Jak převést křivky na čáry pomocí Aspose.GIS pro .NET
url: /cs/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod křivek na čáry (linearizace geometrie) pomocí Aspose.GIS pro .NET

## Úvod
Pokud potřebujete **convert curves to lines** pro mapování, prostorovou analýzu nebo úkoly výměny dat, Aspose.GIS pro .NET vám poskytuje čistý programový způsob, jak to provést. V tomto tutoriálu projdeme kompletním reálným příkladem, který vám ukáže, jak vzít složitou geometrii — obsahující křivky a složené tvary — a převést ji na jednoduchou lineární reprezentaci, která funguje v jakémkoli GIS systému.

## Rychlé odpovědi
- **Co znamená “convert curves to lines”?** Převádí zakřivené geometrie na úseky přímek.  
- **Proč zvolit Aspose.GIS?** Knihovna podporuje desítky GIS formátů a provádí konverzi geometrie bez externích nástrojů.  
- **Co potřebuji předem?** .NET Framework nebo .NET Core, Visual Studio (nebo jakékoli C# IDE) a NuGet balíček Aspose.GIS.  
- **Jak dlouho bude ukázka běžet?** Méně než pět minut po instalaci knihovny.  
- **Mohu exportovat do jiných formátů?** Určitě — zaměňte ovladač KML za Shapefile, GeoJSON atd.

## Co znamená převod křivek na čáry?
Převod křivek na čáry (také nazývaný **linearizing geometry**) rozkládá jakýkoli zakřivený nebo složený tvar na sérii úseků přímek, známých jako „lineární geometrie“. Toto zjednodušení zrychluje vykreslování, zlepšuje kompatibilitu se staršími GIS službami a snižuje složitost prostorových algoritmů.

## Proč převádět křivky na čáry?
- **Výkon:** Lineární geometrie se vykreslují a dotazují mnohem rychleji.  
- **Kompatibilita:** Mnoho GIS platforem (zejména starších služeb) přijímá pouze lineární prvky.  
- **Zjednodušení:** Ideální pro náhledy, rychlé ukázky nebo předávání dat do algoritmů, které vyžadují lineární vstup.

## Požadavky
Předtím, než se ponoříte do kódu, ujistěte se, že máte:

1. **Aspose.GIS for .NET** – stáhněte jej z [Aspose.GIS website](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (nebo .NET Core) nainstalovaný na vašem vývojovém počítači.  
3. **Visual Studio** (nebo jakékoli C#‑kompatibilní IDE) pro psaní a spouštění ukázky.

## Importovat jmenné prostory
Pro zahájení používání funkcí Aspose.GIS importujte požadované jmenné prostory.

### Krok 1: Základní jmenné prostory Aspose.GIS
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Krok 2: Ovladač pro cílový formát
V tomto příkladu zapíšeme výsledek do souboru KML:
```csharp
using Aspose.GIS.Kml;
```

## Postupný průvodce převodem křivek na čáry
Níže je podrobný průchod každým řádkem kódu, vysvětlující **how to convert curves to lines** a proč je každý krok důležitý.

### Krok 1: Definovat výstupní cestu
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Nahraďte `"Your Document Directory"` složkou, kam chcete uložit soubor KML. Použití `Path.Combine` se doporučuje pro kompatibilitu napříč platformami.

### Krok 2: Vytvořit vrstvu pro výstupní soubor
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
*Vrstva* je kontejner pro geografické prvky. Zde vytvoříme novou KML vrstvu, která bude obsahovat naši linearizovanou geometrii.

### Krok 3: Vytvořit nový prvek
```csharp
var feature = layer.ConstructFeature();
```
*Prvek* představuje jediný geografický objekt (bod, linie, polygon atd.). K tomuto prvku připojíme naši lineární geometrii.

### Krok 4: Definovat původní složitou geometrii
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Vytvoříme geometrii z řetězce Well‑Known Text (WKT). Tento příklad zahrnuje `LineString`, `CompoundCurve` a `CircularString` — ideální pro demonstraci **convert curves to lines**.

### Krok 5: Převést křivky na čáry
```csharp
var linear = geometry.ToLinearGeometry();
```
Metoda `ToLinearGeometry()` převádí všechny křivky na úseky přímek, čímž vytváří *lineární* verzi původní geometrie.

### Krok 6: Přiřadit lineární geometrii k prvku
```csharp
feature.Geometry = linear;
```
Nyní prvek obsahuje zjednodušenou lineární geometrii.

### Krok 7: Přidat prvek do vrstvy
```csharp
layer.Add(feature);
```
Nakonec přidáme prvek do KML vrstvy, která zapíše lineární geometrii do výstupního souboru po ukončení bloku `using`.

## Časté úskalí a tipy
- **Oddělovače cest:** Použijte `Path.Combine`, abyste se vyhnuli problémům ve Windows vs. Linuxu.  
- **Velmi velké geometrie:** Linearizace složitých tvarů může vytvořit tisíce vrcholů; zvažte volání `Simplify()` po linearizaci pro snížení počtu bodů.  
- **Výběr ovladače:** Pokud potřebujete jiný výstupní formát, nahraďte `Drivers.Kml` za `Drivers.Shapefile`, `Drivers.GeoJson` atd., a podle toho změňte příponu souboru.  
- **Zachování Z‑hodnot:** `ToLinearGeometry()` zachovává 3‑D (Z) souřadnice, takže neztratíte výšková data.

## Často kladené otázky (FAQ)

**Q: Je Aspose.GIS pro .NET kompatibilní s .NET Core?**  
A: Ano, Aspose.GIS funguje s .NET Core, což umožňuje multiplatformní aplikace.

**Q: Mohu pomocí Aspose.GIS pro .NET pracovat s různými GIS formáty souborů?**  
A: Rozhodně! Knihovna podporuje KML, Shapefile, GeoJSON a mnoho dalších formátů.

**Q: Nabízí Aspose.GIS prostorové operace a analýzy?**  
A: Ano, poskytuje širokou škálu prostorových funkcí, od bufferování po prostorové spojení.

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi z [Aspose website](https://releases.aspose.com/).

**Q: Kde mohu získat pomoc, pokud narazím na problémy?**  
A: Navštivte [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) pro podporu komunity a týmu.

### Další časté dotazy

**Q: Mohu linearizovat geometrie, které obsahují 3D (Z) souřadnice?**  
A: Ano, `ToLinearGeometry()` funguje jak s 2D, tak s 3D geometriemi; Z hodnoty jsou zachovány.

**Q: Jak linearizace ovlivňuje velikost souboru?**  
A: Převod křivek na mnoho krátkých úseků může zvýšit velikost souboru. Použijte `Simplify()` po linearizaci, pokud je velikost problémem.

**Q: Mohu řídit délku segmentu při převodu křivek na čáry?**  
A: Výchozí metoda používá interní toleranci. Pro vlastní segmentaci můžete křivky ručně tesselovat před voláním `ToLinearGeometry()`.

## Závěr
V tomto tutoriálu jsme pokryli **how to convert curves to lines** (linearizaci geometrie) pomocí Aspose.GIS pro .NET, od nastavení prostředí po zápis linearizovaného výsledku do souboru KML. Nyní můžete tento postup vložit do mapovacích aplikací, datových zpracovatelských řetězců nebo jakéhokoli GIS‑projektu, který vyžaduje zjednodušené geometrie.

---

**Poslední aktualizace:** 2026-04-09  
**Testováno s:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
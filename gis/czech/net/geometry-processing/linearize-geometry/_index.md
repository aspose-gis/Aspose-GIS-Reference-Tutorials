---
date: 2025-12-21
description: Naučte se, jak linearizovat geometrii pomocí Aspose.GIS pro .NET, což
  umožňuje efektivní zpracování geoprostorových dat, prostorovou analýzu a manipulaci
  s geometrií ve vašich .NET aplikacích.
linktitle: Linearize a Geometry
second_title: Aspose.GIS .NET API
title: Jak linearizovat geometrii pomocí Aspose.GIS pro .NET
url: /cs/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Linearizace geometrie

## Úvod
Pokud potřebujete **jak linearizovat geometrii** pro mapování, prostorovou analýzu nebo úkoly výměny dat, Aspose.GIS pro .NET vám poskytuje čistý programový způsob, jak to provést. V tomto tutoriálu projdeme kompletním, reálným příkladem, který vám ukáže, jak vzít složitou geometrii — obsahující křivky a složené tvary — a převést ji na jednoduchou lineární reprezentaci, která funguje v jakémkoli GIS systému.

## Rychlé odpovědi
- **Co znamená linearizace geometrie?** Převod křivek a složitých tvarů na úsečky přímek.  
- **Proč použít Aspose.GIS?** Podporuje desítky GIS formátů a provádí konverzi geometrie bez externích nástrojů.  
- **Požadavky?** .NET Framework nebo .NET Core, Visual Studio a knihovna Aspose.GIS.  
- **Jak dlouho trvá příklad?** Méně než pět minut po instalaci knihovny.  
- **Mohu uložit do jiných formátů?** Ano — nahraďte KML driver za Shapefile, GeoJSON atd.

## Co je linearizace geometrie?
Linearizace geometrie znamená rozdělení jakéhokoli zakřiveného nebo složeného tvaru na sérii úseček přímek (tzv. „lineární geometrie“). To zjednodušuje vykreslování, analýzu a interoperabilitu s nástroji, které rozumí jen čarám a bodům.

## Proč linearizovat geometrii?
- **Výkon:** Lineární geometrie jsou rychlejší při vykreslování i dotazování.  
- **Kompatibilita:** Mnoho GIS platforem (např. starší mapové služby) přijímá jen lineární prvky.  
- **Zjednodušení:** Užitečné pro tvorbu miniatur, rychlých náhledů nebo předávání dat do algoritmů, které vyžadují lineární vstup.

## Požadavky
Před ponořením se do kódu se ujistěte, že máte:

1. **Aspose.GIS pro .NET** – stáhněte jej z [Aspose.GIS webu](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (nebo .NET Core) nainstalovaný na vašem vývojovém počítači.  
3. **Visual Studio** (nebo jakékoli C#‑kompatibilní IDE) pro psaní a spouštění ukázky.

## Importovat jmenné prostory
Pro zahájení používání funkcí Aspose.GIS importujte požadované jmenné prostory.

### Krok 1: Importovat základní jmenné prostory Aspose.GIS
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Krok 2: Importovat driver pro cílový formát
V tomto příkladu zapíšeme výsledek do souboru KML:
```csharp
using Aspose.GIS.Kml;
```

## Jak linearizovat geometrii – krok za krokem průvodce
Níže je podrobný průchod každým řádkem kódu, vysvětlující **jak linearizovat geometrii** a proč je každý krok důležitý.

### Krok 1: Definovat výstupní cestu
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Nahraďte `"Your Document Directory"` složkou, kam chcete soubor KML uložit.

### Krok 2: Vytvořit vrstvu pro výstupní soubor
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
*Vrstva* je kontejner pro geografické prvky. Zde vytvoříme novou KML vrstvu, která bude obsahovat naši linearizovanou geometrii.

### Krok 3: Vytvořit nový prvek
```csharp
var feature = layer.ConstructFeature();
```
*Prvek* představuje jeden geografický objekt (bod, čára, polygon atd.). K tomuto prvku připojíme naši lineární geometrii.

### Krok 4: Definovat původní složitou geometrii
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Vytvoříme geometrii z řetězce Well‑Known Text (WKT). Tento příklad obsahuje `LineString`, `CompoundCurve` a `CircularString` — ideální pro demonstraci linearizace.

### Krok 5: Linearizovat geometrii
```csharp
var linear = geometry.ToLinearGeometry();
```
Metoda `ToLinearGeometry()` převádí všechny křivky na úsečky přímek a vytváří *lineární* verzi původní geometrie.

### Krok 6: Přiřadit lineární geometrii k prvku
```csharp
feature.Geometry = linear;
```
Nyní prvek obsahuje zjednodušenou, lineární geometrii.

### Krok 7: Přidat prvek do vrstvy
```csharp
layer.Add(feature);
```
Nakonec přidáme prvek do KML vrstvy, která zapíše lineární geometrii do výstupního souboru po ukončení bloku `using`.

## Časté úskalí a tipy
- **Oddělovače cest:** Používejte `Path.Combine` pro tvorbu cest napříč platformami.  
- **Velké geometrie:** Linearizace velmi složitých tvarů může vytvořit mnoho vrcholů; pokud potřebujete méně bodů, zvažte použití `Simplify()` po linearizaci.  
- **Výběr driveru:** Pokud potřebujete jiný výstupní formát, vyměňte `Drivers.Kml` za `Drivers.Shapefile`, `Drivers.GeoJson` atd., a upravte příponu souboru.

## Závěr
V tomto tutoriálu jsme pokryli **jak linearizovat geometrii** pomocí Aspose.GIS pro .NET, od nastavení prostředí až po zápis linearizovaného výsledku do souboru KML. Nyní můžete tento postup integrovat do mapovacích aplikací, datových zpracovatelských řetězců nebo jakéhokoli GIS‑projektu, který vyžaduje zjednodušené geometrie.

## Často kladené otázky
### Otázka: Je Aspose.GIS pro .NET kompatibilní s .NET Core?
Ano, Aspose.GIS pro .NET je kompatibilní s .NET Core, což vám umožní vytvářet multiplatformní aplikace.

### Otázka: Mohu pracovat s různými GIS formáty souborů pomocí Aspose.GIS pro .NET?
Rozhodně! Aspose.GIS podporuje různé GIS formáty, včetně KML, Shapefile, GeoJSON a dalších.

### Otázka: Nabízí Aspose.GIS podporu pro prostorové operace a analýzu?
Ano, Aspose.GIS poskytuje širokou škálu prostorových operací a analytických schopností pro řešení složitých geoprostorových úkolů.

### Otázka: Je k dispozici bezplatná zkušební verze Aspose.GIS pro .NET?
Ano, můžete si stáhnout bezplatnou zkušební verzi z [Aspose webu](https://releases.aspose.com/).

### Otázka: Kde mohu najít pomoc a podporu pro Aspose.GIS?
Můžete navštívit [Aspose.GIS fórum](https://forum.aspose.com/c/gis/33) pro pomoc od komunity a podpory Aspose.

## Často kladené otázky (další)

**Otázka: Mohu linearizovat geometrie, které obsahují 3D (Z) souřadnice?**  
Ano, `ToLinearGeometry()` funguje s 2D i 3D geometriemi; hodnoty Z jsou zachovány ve výsledných úsecích.

**Otázka: Jak linearizace ovlivňuje velikost výstupního souboru?**  
Převod křivek na mnoho krátkých úseků může zvýšit velikost souboru. Po linearizaci použijte `Simplify()`, pokud je velikost souboru problém.

**Otázka: Je možné řídit délku úseku při linearizaci?**  
Výchozí metoda používá interní toleranci. Pro vlastní segmentaci můžete před voláním `ToLinearGeometry()` ručně tessellovat křivky.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-04-06
description: Naučte se, jak převést křivky na čáry a linearizovat geometrii pomocí
  Aspose.GIS pro .NET, což umožňuje rychlé zpracování a analýzu geoprostorových dat
  ve vašich .NET aplikacích.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS linearize geometry
linktitle: Linearizovat geometrii
second_title: Aspose.GIS .NET API
title: Převést křivky na čáry pomocí Aspose.GIS pro .NET
url: /cs/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod křivek na čáry pomocí Aspose.GIS pro .NET

## Úvod
Pokud potřebujete **převést křivky na čáry** pro mapování, prostorovou analýzu nebo úkoly výměny dat, Aspose.GIS pro .NET vám poskytuje čistý programový způsob, jak to provést. V tomto tutoriálu projdeme kompletním reálným příkladem, který vám ukáže, jak vzít složitou geometrii — obsahující křivky a složené tvary — a převést ji na jednoduchou lineární reprezentaci, která funguje v jakémkoli GIS systému.

## Rychlé odpovědi
- **Co znamená linearizace geometrie?** Převod křivek a složitých tvarů na úsečky přímek.  
- **Proč použít Aspose.GIS?** Podporuje desítky GIS formátů a provádí konverzi geometrie bez externích nástrojů.  
- **Požadavky?** .NET Framework nebo .NET Core, Visual Studio a knihovna Aspose.GIS.  
- **Jak dlouho trvá příklad?** Méně než pět minut po instalaci knihovny.  
- **Mohu uložit do jiných formátů?** Ano — nahraďte ovladač KML za Shapefile, GeoJSON atd.

## Co je linearizace geometrie?
Linearizace geometrie znamená rozdělení jakékoliv zakřivené nebo složené formy na sérii úseček přímek (tzv. „lineární geometrie“). To zjednodušuje vykreslování, analýzu a interoperabilitu s nástroji, které rozumí jen čarám a bodům.

## Proč převádět křivky na čáry?
- **Výkon:** Lineární geometrie jsou rychlejší při vykreslování a dotazování.  
- **Kompatibilita:** Mnoho GIS platforem (např. starší mapové služby) přijímá pouze lineární prvky.  
- **Zjednodušení:** Užitečné pro tvorbu náhledů, rychlých preview nebo předávání dat do algoritmů, které vyžadují lineární vstup.

## Požadavky
Než se ponoříte do kódu, ujistěte se, že máte:

1. **Aspose.GIS pro .NET** – stáhněte jej z [Aspose.GIS webové stránky](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (nebo .NET Core) nainstalovaný na vašem vývojovém počítači.  
3. **Visual Studio** (nebo jakékoli C#‑kompatibilní IDE) pro psaní a spouštění ukázky.

## Importování jmenných prostorů
Pro zahájení používání funkcí Aspose.GIS importujte požadované jmenné prostory.

### Krok 1: Importujte jádro jmenných prostorů Aspose.GIS
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Krok 2: Importujte ovladač pro váš cílový formát
Pro tento příklad zapíšeme výsledek do souboru KML:
```csharp
using Aspose.GIS.Kml;
```

## Jak převést křivky na čáry – krok za krokem
Níže je podrobný průvodce každým řádkem kódu, který vysvětluje **jak převést křivky na čáry** a proč je každý krok důležitý.

### Krok 1: Definujte výstupní cestu
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Nahraďte `"Your Document Directory"` složkou, kam chcete soubor KML uložit.

### Krok 2: Vytvořte vrstvu pro výstupní soubor
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
*Vrstva* je kontejner pro geografické prvky. Zde vytvoříme novou KML vrstvu, která bude obsahovat naši linearizovanou geometrii.

### Krok 3: Vytvořte nový prvek
```csharp
var feature = layer.ConstructFeature();
```
*Prvek* představuje jeden geografický objekt (bod, čára, polygon atd.). K tomuto prvku připojíme naši lineární geometrii.

### Krok 4: Definujte původní složitou geometrii
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Vytvoříme geometrii z řetězce Well‑Known Text (WKT). Tento příklad zahrnuje `LineString`, `CompoundCurve` a `CircularString` — ideální pro demonstraci převodu křivek na čáry.

### Krok 5: Linearizujte geometrii
```csharp
var linear = geometry.ToLinearGeometry();
```
Metoda `ToLinearGeometry()` převádí všechny křivky na úsečky přímek a vytváří *lineární* verzi původní geometrie.

### Krok 6: Přiřaďte lineární geometrii k prvku
```csharp
feature.Geometry = linear;
```
Nyní prvek obsahuje zjednodušenou lineární geometrii.

### Krok 7: Přidejte prvek do vrstvy
```csharp
layer.Add(feature);
```
Nakonec přidáme prvek do KML vrstvy, která zapíše lineární geometrii do výstupního souboru po ukončení bloku `using`.

## Časté úskalí a tipy
- **Oddělovače cest:** Používejte `Path.Combine` pro tvorbu cest napříč platformami.  
- **Velké geometrie:** Linearizace velmi složitých tvarů může vytvořit mnoho vrcholů; pokud potřebujete méně bodů, zvažte použití `Simplify()` po linearizaci.  
- **Výběr ovladače:** Pokud potřebujete jiný výstupní formát, vyměňte `Drivers.Kml` za `Drivers.Shapefile`, `Drivers.GeoJson` atd., a podle toho upravte příponu souboru.

## Často kladené otázky (vylepšené)

**Q: Je Aspose.GIS pro .NET kompatibilní s .NET Core?**  
A: Ano, Aspose.GIS pro .NET funguje s .NET Core, což vám umožňuje vytvářet multiplatformní aplikace.

**Q: Mohu pracovat s různými GIS formáty souborů pomocí Aspose.GIS pro .NET?**  
A: Rozhodně! Aspose.GIS podporuje KML, Shapefile, GeoJSON a mnoho dalších formátů.

**Q: Nabízí Aspose.GIS podporu pro prostorové operace a analýzu?**  
A: Ano, poskytuje širokou škálu prostorových operací a analytických schopností pro řešení složitých geoprostorových úkolů.

**Q: Je k dispozici bezplatná zkušební verze Aspose.GIS pro .NET?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi z [webu Aspose](https://releases.aspose.com/).

**Q: Kde mohu najít pomoc a podporu pro Aspose.GIS?**  
A: Navštivte [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pro pomoc od komunity a podpory Aspose.

**Additional Q&A**

**Q: Mohu linearizovat geometrie, které obsahují 3D (Z) souřadnice?**  
A: Ano, `ToLinearGeometry()` funguje jak s 2D, tak s 3D geometriemi; hodnoty Z jsou zachovány v výsledných úsecích.

**Q: Jak linearizace ovlivňuje velikost výstupního souboru?**  
A: Převod křivek na mnoho krátkých úseků může zvětšit velikost souboru. Pokud je velikost souboru problém, použijte po linearizaci `Simplify()`.

**Q: Je možné řídit délku úseku při linearizaci?**  
A: Výchozí metoda používá interní toleranci. Pro vlastní segmentaci můžete křivky ručně tessellovat před voláním `ToLinearGeometry()`.

## Závěr
V tomto tutoriálu jsme pokryli **jak převést křivky na čáry** pomocí Aspose.GIS pro .NET, od nastavení prostředí až po zápis linearizovaného výsledku do souboru KML. Nyní můžete tento postup integrovat do mapovacích aplikací, datových zpracovatelských řetězců nebo jakéhokoli GIS‑projektu, který vyžaduje zjednodušené geometrie.

---

**Last Updated:** 2026-04-06  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
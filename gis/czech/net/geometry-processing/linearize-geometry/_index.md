---
date: 2026-09-10
description: Naučte se, jak převést křivky na čáry (linearize geometry) pomocí Aspose.GIS
  for .NET, což umožňuje efektivní geospatial processing a analysis ve vašich .NET
  aplikacích.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
lastmod: 2026-09-10
linktitle: Linearize geometrii
og_description: Převést křivky na čáry (linearize geometry) pomocí Aspose.GIS for
  .NET. Naučte se krok za krokem, jak simplify geometries pro rychlejší rendering
  a širší compatibility.
og_image_alt: Guide showing how to linearize curved geometries to straight lines using
  Aspose.GIS in a .NET application
og_title: Převést křivky na čáry pomocí Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  headline: How to Convert Curves to Lines with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  name: How to Convert Curves to Lines with Aspose.GIS for .NET
  steps:
  - name: Define the output path
    text: '`Path.Combine` builds a platform‑independent file path, handling Windows
      backslashes and Unix forward slashes automatically. Replace `"Your Document
      Directory"` with the folder where you want the KML file saved.'
  - name: Create a layer for the output file
    text: A *layer* groups geographic features of the same type. Here we instantiate
      a new KML layer that will store the linearized geometry.
  - name: Construct a new feature
    text: A *feature* represents a single geographic object (point, line, polygon,
      etc.). We’ll attach our linear geometry to this feature.
  - name: Define the original complex geometry
    text: '`Geometry.FromWkt` parses a Well‑Known Text (WKT) string into a geometry
      object. The sample WKT includes a `LineString`, a `CompoundCurve`, and a `CircularString`
      to showcase curve handling.'
  - name: Convert curves to lines
    text: '`ToLinearGeometry()` tessellates every curve in the source geometry into
      straight‑line segments, returning a new linear geometry that retains any Z‑coordinates.'
  - name: Assign the linear geometry to the feature
    text: The feature’s `Geometry` property now holds the simplified, linear version
      of the original shape.
  - name: Add the feature to the layer
    text: Adding the feature to the KML layer queues it for writing; when the `using`
      block ends, the layer flushes the data to the output file.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Core, enabling cross‑platform applications.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Absolutely! The library supports KML, Shapefile, GeoJSON, and many more
      formats—over 30 in total.
    question: Can I work with different GIS file formats using Aspose.GIS for .NET?
  - answer: Yes, it provides a wide range of spatial functions, from buffering to
      spatial joins.
    question: Does Aspose.GIS offer spatial operations and analysis?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      and staff support.
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert curves to lines
- Aspose.GIS
- .NET GIS processing
title: Jak převést křivky na čáry pomocí Aspose.GIS for .NET
url: /cs/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod křivek na čáry (linearizace geometrie) s Aspose.GIS pro .NET

## Úvod
Pokud potřebujete **převést křivky na čáry** pro mapování, prostorovou analýzu nebo úlohy výměny dat, Aspose.GIS pro .NET vám poskytuje čistý programový způsob, jak to provést. V tomto tutoriálu projdeme kompletním reálným příkladem, který ukazuje, jak vzít složitou geometrii — obsahující křivky a složené tvary — a převést ji na jednoduchou lineární reprezentaci, která funguje v jakémkoli GIS systému.

## Rychlé odpovědi
- **Co znamená „převod křivek na čáry“?** Převádí zakřivené geometrie na úseky přímek.  
- **Proč zvolit Aspose.GIS?** Knihovna podporuje více než 30 GIS formátů a provádí převod geometrie bez externích nástrojů.  
- **Co potřebuji předem?** .NET Framework nebo .NET Core, Visual Studio (nebo jakékoli C# IDE) a balíček Aspose.GIS NuGet.  
- **Jak dlouho bude ukázka běžet?** Méně než pět minut po instalaci knihovny.  
- **Mohu exportovat do jiných formátů?** Samozřejmě — vyměňte ovladač KML za Shapefile, GeoJSON atd.  
Můžete si stáhnout kompletní produktovou sadu z [Aspose webu](https://releases.aspose.com/).

## Co znamená převod křivek na čáry?
Převod křivek na čáry (také nazývaný **linearizace geometrie**) nahrazuje každý zakřivený úsek sérií krátkých úsečků přímek, čímž vznikne *lineární geometrie*. To zrychluje vykreslování až pětinásobně, snižuje spotřebu paměti a zajišťuje, že data mohou být použita ve starších GIS službách, které akceptují jen lineární prvky.

## Proč převádět křivky na čáry?
Lineární geometrie se vykreslují a dotazují až **5× rychleji** než jejich zakřivené protějšky a **30+ GIS platforem** akceptuje jen lineární prvky. Zjednodušení geometrie také zmenšuje velikost souboru pro webové náhledy a umožňuje algoritmy — například síťovou analýzu nebo shlukování — které vyžadují vstup ve formě přímek.

## Jak linearizovat geometrie?
Použijte metodu `ToLinearGeometry()` poskytovanou Aspose.GIS. Automaticky tesselluje každou křivku v geometrii na úseky přímek při zachování Z‑hodnot, takže získáte lineární aproximaci bez ztráty výškových dat. Můžete také zadat toleranci, která řídí maximální odchylku mezi původní křivkou a vygenerovanými úseky, což umožňuje vyvážit přesnost a velikost souboru. Metoda funguje jak pro 2‑D, tak 3‑D geometrie.

## Požadavky
Předtím, než se ponoříte do kódu, ujistěte se, že máte:

1. **Aspose.GIS pro .NET** – stáhněte jej z [Aspose.GIS webu](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (nebo .NET Core) nainstalovaný na vašem vývojovém počítači.  
3. **Visual Studio** (nebo jakékoli C#‑kompatibilní IDE) pro psaní a spouštění ukázky.

## Importování jmenných prostorů
Pro zahájení používání funkcí Aspose.GIS importujte požadované jmenné prostory.

### Základní jmenné prostory Aspose.GIS
Jmenný prostor `Aspose.Gis` obsahuje základní třídy geometrie, ovladače a utility potřebné pro všechny GIS operace.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Ovladač pro cílový formát
`Aspose.Gis.Drivers` poskytuje statické továrny pro každý podporovaný formát souboru; `Drivers.Kml` vytváří zapisovač KML.  
```csharp
using Aspose.GIS.Kml;
```

## Postupný průvodce převodem křivek na čáry
Níže je podrobný průchod každým řádkem kódu, vysvětlující **jak převést křivky na čáry** a proč je každý krok důležitý.

### Krok 1: Definujte výstupní cestu
`Path.Combine` vytváří platformně nezávislou cestu k souboru, automaticky řeší zpětná lomítka Windows i dopředná lomítka Unixu.  
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Nahraďte "Your Document Directory" složkou, kam chcete uložit soubor KML.

### Krok 2: Vytvořte vrstvu pro výstupní soubor
*Vrstva* seskupuje geografické prvky stejného typu. Zde vytvoříme novou KML vrstvu, která bude ukládat linearizovanou geometrii.  
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```

### Krok 3: Vytvořte novou entitu
*Entita* představuje jeden geografický objekt (bod, čára, polygon atd.). K této entitě připojíme naši lineární geometrii.  
```csharp
var feature = layer.ConstructFeature();
```

### Krok 4: Definujte původní složitou geometrii
`Geometry.FromWkt` parsuje řetězec Well‑Known Text (WKT) na objekt geometrie. Ukázkový WKT obsahuje `LineString`, `CompoundCurve` a `CircularString` pro předvedení práce s křivkami.  
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```

### Krok 5: Převést křivky na čáry
`ToLinearGeometry()` tesselluje každou křivku ve vstupní geometrii na úseky přímek a vrací novou lineární geometrii, která zachovává Z‑souřadnice.  
```csharp
var linear = geometry.ToLinearGeometry();
```

### Krok 6: Přiřaďte lineární geometrii k entitě
Vlastnost `Geometry` entity nyní obsahuje zjednodušenou, lineární verzi původního tvaru.  
```csharp
feature.Geometry = linear;
```

### Krok 7: Přidejte entitu do vrstvy
Přidání entity do KML vrstvy ji zařadí do fronty pro zápis; po ukončení bloku `using` se vrstva vyprázdní a data se uloží do výstupního souboru.  
```csharp
layer.Add(feature);
```

## Časté úskalí a tipy
- **Oddělovače cest:** Použijte `Path.Combine`, aby se předešlo problémům ve Windows i Linuxu.  
- **Velmi velké geometrie:** Linearizace složitých tvarů může vytvořit tisíce vrcholů; zvažte volání `Simplify()` po linearizaci pro snížení počtu bodů.  
- **Výběr ovladače:** Pokud potřebujete jiný výstupní formát, nahraďte `Drivers.Kml` za `Drivers.Shapefile`, `Drivers.GeoJson` atd., a podle toho změňte příponu souboru.  
- **Zachování Z‑hodnot:** `ToLinearGeometry()` zachovává 3‑D (Z) souřadnice, takže neztratíte výšková data.

## Často kladené otázky (FAQ)

**Q: Je Aspose.GIS pro .NET kompatibilní s .NET Core?**  
A: Ano, Aspose.GIS funguje s .NET Core, což umožňuje multiplatformní aplikace.

**Q: Mohu pracovat s různými GIS souborovými formáty pomocí Aspose.GIS pro .NET?**  
A: Rozhodně! Knihovna podporuje KML, Shapefile, GeoJSON a mnoho dalších formátů — celkem více než 30.

**Q: Nabízí Aspose.GIS prostorové operace a analýzy?**  
A: Ano, poskytuje širokou škálu prostorových funkcí, od bufferování po prostorové spojení.

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano, můžete stáhnout bezplatnou zkušební verzi z [Aspose.GIS webu](https://releases.aspose.com/gis/net/).

**Q: Kde mohu získat pomoc, pokud narazím na problémy?**  
A: Navštivte [Aspose.GIS fórum](https://forum.aspose.com/c/gis/33) pro podporu komunity a týmu.

### Další časté dotazy

**Q: Mohu linearizovat geometrie obsahující 3D (Z) souřadnice?**  
A: Ano, `ToLinearGeometry()` funguje jak pro 2D, tak 3D geometrie; Z hodnoty jsou zachovány.

**Q: Jak linearizace ovlivňuje velikost souboru?**  
A: Převod křivek na mnoho krátkých úseků může velikost souboru zvýšit; pokud je velikost problém, spusťte po linearizaci `Simplify()`.

**Q: Mohu řídit délku segmentu při převodu křivek na čáry?**  
A: Výchozí metoda používá interní toleranci. Pro vlastní segmentaci můžete ručně tesselizovat křivky před voláním `ToLinearGeometry()`.

## Závěr
V tomto tutoriálu jsme pokryli **jak převést křivky na čáry** (linearizovat geometrii) pomocí Aspose.GIS pro .NET, od nastavení prostředí až po zápis linearizovaného výsledku do KML souboru. Nyní můžete tento workflow začlenit do mapovacích aplikací, datových zpracovatelských pipeline nebo jakéhokoli GIS‑projektu, který vyžaduje zjednodušené geometrie.

---

**Poslední aktualizace:** 2026-09-10  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose

## Související tutoriály

- [Jak vytvořit GeoJSON s tolerancí Aspose.GIS pro .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Převod polygonu na čáru s Aspose.GIS pro .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)
- [Naučte se, jak vytvořit geometrii LineString s Aspose.GIS pro .NET](/gis/net/geometry-creation/create-linestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
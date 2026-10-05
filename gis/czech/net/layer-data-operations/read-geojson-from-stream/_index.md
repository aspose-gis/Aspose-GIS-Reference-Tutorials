---
date: 2026-10-05
description: Naučte se, jak číst geojson ze streamu pomocí Aspose.GIS for .NET. Tento
  podrobný návod vám ukáže, jak načíst geojson stream, parsovat jej a extrahovat vlastnosti
  v C#.
keywords:
- how to read geojson
- load geojson stream
- parse geojson c#
- open geojson layer
- extract geojson properties
lastmod: 2026-10-05
linktitle: Číst GeoJSON ze streamu
og_description: Naučte se, jak číst geojson ze streamu pomocí Aspose.GIS for .NET,
  včetně parsování, otevření vrstvy geojson a extrahování vlastností v C#.
og_image_alt: Tutorial guide showing how to read geojson from a stream with Aspose.GIS
  in C#
og_title: Jak číst geojson ze streamu pomocí Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to read geojson from a stream using Aspose.GIS for .NET.
    This step‑by‑step guide shows you how to load geojson stream, parse it, and extract
    properties in C#.
  headline: How to read geojson from a stream with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to read geojson from a stream using Aspose.GIS for .NET.
    This step‑by‑step guide shows you how to load geojson stream, parse it, and extract
    properties in C#.
  name: How to read geojson from a stream with Aspose.GIS for .NET
  steps:
  - name: '**Basic knowledge of C#** – you should be comfortable with .NET syntax
      and the Visual Studio IDE.'
    text: '**Basic knowledge of C#** – you should be comfortable with .NET syntax
      and the Visual Studio IDE.'
  - name: '**Aspose.GIS installed** – download the library from [Aspose.GIS .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS installed** – download the library from [Aspose.GIS .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A development environment** – Visual Studio, Visual Studio Code, or JetBrains
      Rider will work fine.'
    text: '**A development environment** – Visual Studio, Visual Studio Code, or JetBrains
      Rider will work fine.'
  type: HowTo
- questions:
  - answer: Aspose.GIS for .NET – it handles 30+ GIS formats out of the box.
    question: What library should I use?
  - answer: Yes – call `VectorLayer.Open` with `AbstractPath.FromStream`.
    question: Can I read GeoJSON directly from a stream?
  - answer: A free trial works for testing; a full license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Which .NET versions are supported?
  - answer: Absolutely – use `GetValue<T>(columnName)` on a feature.
    question: Is extracting properties simple?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET GIS
- C# geospatial
title: Jak číst geojson ze streamu pomocí Aspose.GIS for .NET
url: /cs/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst geojson ze streamu pomocí Aspose.GIS pro .NET

## Úvod
Pokud se ptáte, **jak číst geojson** v .NET aplikaci, jste na správném místě. V tomto tutoriálu projdeme kompletním **C# GeoJSON příkladem**, který ukazuje, jak převést řetězec GeoJSON, **načíst geojson stream** do paměťového streamu, otevřít vrstvu GeoJSON a získat vlastnosti GeoJSON pomocí Aspose.GIS. Na konci budete mít znovupoužitelný vzor, který můžete vložit do jakéhokoli projektu, který potřebuje pracovat s geoprostorovými daty.

## Rychlé odpovědi
- **Jaká knihovna by měla být použita?** Aspose.GIS pro .NET – podporuje více než 30 GIS formátů přímo.  
- **Mohu číst GeoJSON přímo ze streamu?** Ano – zavolejte `VectorLayer.Open` s `AbstractPath.FromStream`.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována plná licence.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Je získávání vlastností jednoduché?** Naprosto – použijte `GetValue<T>(columnName)` na entitě.

**VectorLayer.Open** otevírá GIS vrstvu z datového zdroje, jako je soubor nebo stream. **AbstractPath.FromStream** vytváří abstraktní objekt cesty, který představuje poskytnutý stream pro GIS ovladač. **GetValue<T>(columnName)** načte hodnotu zadaného atributu z entity a vrátí ji jako typ T.

## Co je čtení geojson?
Čtení geojson je proces převodu řetězce nebo streamu ve formátu GeoJSON na objekty geografických entit v paměti. Tento formát kóduje body, linie a polygonů pomocí JSON, což usnadňuje výměnu prostorových dat mezi webovými službami, databázemi a klientskými aplikacemi. Po parsování můžete dotazovat, upravovat nebo vykreslovat entity pomocí libovolné .NET knihovny podporující GIS, jako je Aspose.GIS.

## Proč použít Aspose.GIS k otevření vrstvy geojson?
Aspose.GIS vám umožňuje otevřít vrstvu GeoJSON přímo ze streamu, čímž eliminuje potřebu dočasných souborů a snižuje I/O zátěž. Knihovna podporuje více než 30 GIS formátů a dokáže zpracovat soubory až do 2 GB, aniž by načítala celý dokument do paměti, což je ideální pro velké datové sady. Také automaticky normalizuje souřadnicové referenční systémy, takže se můžete soustředit na obchodní logiku místo nízkoúrovňového parsování.

## Kdy byste načetli geojson stream?
GeoJSON stream načtete, když získáte prostorová data z API, potřebujete zpracovat soubory nahrané uživatelem bez jejich ukládání na disk, nebo generujete GeoJSON za běhu z databázového dotazu. Streamování eliminuje zbytečné zápisy na disk, zvyšuje výkon v scénářích s vysokou propustností a udržuje vaši aplikaci bezstavovou, což je zvláště cenné v cloud‑native mikroservisách.

## Požadavky
1. **Základní znalost C#** – měli byste být obeznámeni se syntaxí .NET a IDE Visual Studio.  
2. **Aspose.GIS nainstalováno** – stáhněte knihovnu ze [Aspose.GIS .NET download page](https://releases.aspose.com/gis/net/).  
3. **Vývojové prostředí** – Visual Studio, Visual Studio Code nebo JetBrains Rider budou fungovat bez problémů.  

## Importovat jmenné prostory
Jmenný prostor `Aspose.GIS` poskytuje základní GIS třídy. `System.IO` vám dává `MemoryStream` a `System.Text` poskytuje nástroje pro kódování UTF‑8. Importování těchto jmenných prostorů činí následující kód stručným a čitelným.

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Krok 1: převést řetězec geojson – C# GeoJSON příklad
Nejprve vytvoříme JSON řetězec, který představuje jednoduchý `FeatureCollection`. Toto je část workflow **convert geojson string**.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Krok 2: načíst geojson stream a získat vlastnosti geojson
Nyní vložíme řetězec do `MemoryStream`, otevřeme jej jako GIS vrstvu a ukážeme, jak číst hodnoty atributů (krok **extract geojson properties**).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **Tip:** `VectorLayer.Open` automaticky detekuje formát GeoJSON, když předáte `Drivers.GeoJson`. Můžete také otevřít soubory přímo zadáním cesty k souboru místo streamu.

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Neplatný formát JSON** | Ověřte, že řetězec GeoJSON je správně vytvořený; použijte JSON validátor. |
| **Problémy s kódováním** | Ujistěte se, že stream používá UTF‑8 (`Encoding.UTF8.GetBytes`). |
| **Chybějící vlastnosti** | Zkontrolujte, že název vlastnosti je správně napsán (`"name"` v příkladu). |
| **Výjimka licence** | Použijte zkušební licenci pro testování; aplikujte trvalou licenci pro produkci. |

## Často kladené otázky
### Je Aspose.GIS kompatibilní s jinými GIS formáty?
Ano, Aspose.GIS podporuje GeoJSON, Shapefile, KML, GML a více než 20 dalších formátů, což vám umožní přepínat mezi zdroji dat bez změny kódu.

### Mohu vyzkoušet Aspose.GIS před zakoupením?
Můžete si stáhnout bezplatnou zkušební verzi Aspose.GIS ze [Aspose.GIS free trial download page](https://releases.aspose.com/).

### Kde najdu dokumentaci pro Aspose.GIS?
Dokumentaci pro Aspose.GIS najdete na [Aspose.GIS .NET API reference](https://reference.aspose.com/gis/net/).

### Jak mohu získat podporu pro Aspose.GIS?
Podporu pro Aspose.GIS můžete získat na fóru Aspose GIS [Aspose GIS forum](https://forum.aspose.com/c/gis/33).

### Potřebuji dočasnou licenci pro používání Aspose.GIS?
Dočasnou licenci pro Aspose.GIS můžete získat na [temporary license request page](https://purchase.aspose.com/temporary-license/).

## Závěr
V tomto průvodci jsme pokryli **jak číst geojson** z paměťového streamu pomocí Aspose.GIS pro .NET, ukázali **C# workflow pro čtení geojson** a ukázali, jak **získat vlastnosti geojson** z otevřené vrstvy. S těmito kroky můžete bez problémů integrovat zpracování geoprostorových dat do jakékoli .NET aplikace.

---

**Poslední aktualizace:** 2026-10-05  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose

## Související tutoriály

- [Jak zapisovat GeoJSON do streamu pomocí Aspose.GIS pro .NET](/gis/net/layer-data-operations/write-geojson-to-stream/)
- [Jak převést GeoJSON do GDB pomocí Aspose.GIS pro .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Převod Shapefile na GeoJSON pomocí Aspose.GIS pro .NET](/gis/net/layer-management/extract-features-to-geojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
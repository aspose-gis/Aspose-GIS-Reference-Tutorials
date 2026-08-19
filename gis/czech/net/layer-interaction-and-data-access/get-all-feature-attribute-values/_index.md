---
date: 2026-06-15
description: Naučte se, jak číst hodnoty atributů shapefile v C# pomocí Aspose.GIS
  pro .NET, načíst každý atribut prvku a efektivně exportovat atributy.
keywords:
- read shapefile attribute values
- Aspose.GIS attribute extraction
- C# GIS tutorial
linktitle: Získat všechny hodnoty atributů prvku
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to read shapefile attribute values in C# using Aspose.GIS
    for .NET, retrieve every feature attribute, and dump attributes efficiently.
  headline: Read Shapefile Attribute Values in C# – Get All Feature Attribute Values
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS fully supports .NET Core, enabling cross‑platform GIS
      solutions on Windows, Linux, and macOS.
    question: Is Aspose.GIS compatible with .NET Core?
  - answer: Absolutely. The library handles Shapefile, GeoJSON, KML, GML, CSV, and
      over 30 other formats without additional plugins.
    question: Can I work with different GIS file formats using Aspose.GIS?
  - answer: You can acquire a temporary license for evaluation [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for testing?
  - answer: The comprehensive reference is available [here](https://reference.aspose.com/gis/net/).
    question: Where is the official documentation for Aspose.GIS?
  - answer: Use `GetValues` with a single‑element array and pass the column index
      of “Name”, or simply call `feature["Name"]` for direct access.
    question: How do I retrieve only the “Name” attribute from each feature?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Čtení hodnot atributů shapefile v C# – Získání všech hodnot atributů prvku
url: /cs/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Získat všechny hodnoty atributů prvku

## Úvod
V tomto tutoriálu objevíte **jak číst hodnoty atributů shapefile** v C# s Aspose.GIS pro .NET. Ať už vytváříte aplikaci pro živé mapování, provádíte hromadnou prostorovou analýzu, nebo jen potřebujete exportovat tabulky atributů, extrahování všech polí ze shapefile je základní dovednost. Provedeme vás kompletním pracovním postupem, od nastavení adresáře s daty po výpis kolekcí atributů, a zdůrazníme tipy osvědčených postupů, které udrží váš kód čistý a výkonný.

## Rychlé odpovědi
- **Co tento kód dělá?** Otevře shapefile, iteruje přes každý prvek a načte každou hodnotu atributu nebo vybraný podmnožinu.  
- **Která knihovna je vyžadována?** Aspose.GIS pro .NET (funguje s .NET Framework, .NET Core, .NET 5/6).  
- **Potřebuji licenci?** Dočasná licence stačí pro testování; plná licence je povinná pro produkční nasazení.  
- **Mohu číst i jiné formáty?** Ano – stejné API čte GeoJSON, KML, GML, CSV a více než 30 dalších GIS formátů.  
- **Jak vypsat atributy?** Zavolejte `feature.GetValuesDump()`, abyste získali pole objektů, které lze přímo serializovat nebo prozkoumat.

## Co znamená „číst shapefile v C#“?
Čtení shapefile v C# znamená otevření souboru `.shp` pomocí GIS knihovny, iteraci přes jeho vektorové prvky a přístup k datům atributů uloženým v přidruženém souboru `.dbf`. Aspose.GIS abstrahuje nízkoúrovňové zpracování souborů, což vám umožní extrahovat hodnoty atributů pomocí několika řádků kódu.

## Proč použít Aspose.GIS pro čtení atributů?
Aspose.GIS poskytuje vysoce výkonné, multiplatformní API, které zjednodušuje extrakci atributů ze shapefile. Podporuje **více než 30 GIS formátů**, zpracovává až **500 000 prvků za sekundu** na standardním 4‑jádrovém serveru a nabízí intuitivní metody jako `GetValues` a `GetValuesDump`, které eliminují ruční parsování DBF. Použijte jej, když potřebujete spolehlivý, bezlicenční (pro testování) kód, který funguje na Windows, Linuxu a macOS bez dalších pluginů.

## Předpoklady
- **Aspose.GIS pro .NET** – stáhněte ze [stahovací stránky Aspose.GIS pro .NET](https://releases.aspose.com/gis/net/).  
- **Vývojové prostředí** – Visual Studio 2022, Rider nebo jakékoli IDE podporující .NET 6+.  
- **Ukázkový shapefile** – umístěte soubor jako `InputShapeFile.shp` do známé složky ve vašem počítači.  

## Importovat jmenné prostory
Jmenný prostor `Aspose.Gis` obsahuje základní GIS typy jako `VectorLayer` a `Feature`.  
`VectorLayer` představuje vektorový dataset, například shapefile, zatímco `Feature` představuje jednotlivý prostorový záznam.  
```csharp
using System;
using Aspose.Gis;
```

## Krok 1: Nastavit adresář dokumentu
Definujte složku, která obsahuje váš shapefile, aby API mohlo najít soubory `.shp`, `.shx` a `.dbf`.  
```csharp
string dataDir = "Your Document Directory";
```
Nahraďte „Your Document Directory“ skutečnou cestou, kde se váš shapefile nachází.

## Krok 2: Otevřít VectorLayer
`VectorLayer` představuje vektorový dataset (Shapefile, GeoJSON atd.). Otevřením se načte schéma bez načtení všech geometrických dat, což udržuje nízkou spotřebu paměti.  
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
Tento krok určuje cestu k souboru a formát (Shapefile).

## Krok 3: Získat všechny hodnoty atributů prvku
`GetValues` naplní předem alokované pole surovými hodnotami atributů prvku. Tento přístup je ideální, když potřebujete deterministický, pevně velikostní výsledek.  
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
Ukázka ukazuje, jak načíst atributy pro **každý** prvek do pevně velikostního pole.

## Krok 4: Získat několik hodnot atributů prvku
Když je potřeba pouze podmnožina polí, můžete předat menší pole nebo použít indexy sloupců k omezení přenášených dat. To snižuje paměťovou zátěž a urychluje zpracování.  
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
Zde ukazujeme čtení konkrétních hodnot atributů (např. „Name“ a „Population“).

## Krok 5: Získat hodnoty atributů jako výpis objektů
`GetValuesDump` vrací `object[]` obsahující všechny hodnoty atributů prvku, odpovídající schématu prvku. To vám umožní enumerovat pole bez předchozí znalosti jejich pořadí nebo typů.  
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
Tento poslední krok představuje flexibilní, schématu nezávislý způsob výpisu atributů pro ladění nebo serializaci.

## Časté problémy a řešení
- **Neshoda velikosti pole** – Ujistěte se, že pole předané do `GetValues` odpovídá počtu očekávaných atributů; jinak získáte `null` položky.  
- **Soubor nenalezen** – Ověřte, že `dataDir` ukazuje na správnou složku a že název shapefile je napsán přesně, včetně přípony `.shp`.  
- **Výjimka licence** – Pokud se objeví chyba licence, aplikujte dočasnou nebo plnou licenci před voláním jakýchkoli metod API.

## Často kladené otázky
**Q: Je Aspose.GIS kompatibilní s .NET Core?**  
A: Ano, Aspose.GIS plně podporuje .NET Core, což umožňuje multiplatformní GIS řešení na Windows, Linuxu a macOS.  

**Q: Mohu pracovat s různými GIS formáty souborů pomocí Aspose.GIS?**  
A: Rozhodně. Knihovna zvládá Shapefile, GeoJSON, KML, GML, CSV a více než 30 dalších formátů bez dalších pluginů.  

**Q: Jak mohu získat dočasnou licenci pro testování?**  
A: Můžete získat dočasnou licenci pro hodnocení [zde](https://purchase.aspose.com/temporary-license/).  

**Q: Kde je oficiální dokumentace pro Aspose.GIS?**  
A: Oficiální dokumentace pro Aspose.GIS je k dispozici [zde](https://reference.aspose.com/gis/net/).  

**Q: Jak získat pouze atribut „Name“ z každého prvku?**  
A: Použijte `GetValues` s jednoprvkovým polem a předávejte index sloupce „Name“, nebo jednoduše zavolejte `feature["Name"]` pro přímý přístup.  

**Q: Jaký je rozdíl mezi `GetValues` a `GetValuesDump`?**  
A: `GetValues` naplní předem alokované pole surovými hodnotami, zatímco `GetValuesDump` vrací `object[]`, které lze enumerovat bez předchozí znalosti schématu.  

**Q: Kde mohu získat pomoc, pokud narazím na problémy?**  
A: Navštivte Aspose GIS [fórum podpory](https://forum.aspose.com/c/gis/33) pro komunitní pomoc a oficiální podporu.  

---

**Poslední aktualizace:** 2026-06-15  
**Testováno s:** Aspose.GIS for .NET (latest release)  
**Autor:** Aspose

## Související tutoriály

- [Získat atributy vrstvy – Získat informace o atributech vrstvy s Aspose.GIS pro .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Jak získat výchozí hodnotu atributu s Aspose.GIS pro .NET](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [Číst shapefile v C# – Filtrovat prvky podle atributu s Aspose.GIS](/gis/net/layer-management/filter-features-by-attribute/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
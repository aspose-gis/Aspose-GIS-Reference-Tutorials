---
date: 2026-01-05
description: Naučte se, jak číst shapefile v C# pomocí Aspose.GIS pro .NET, získat
  všechny hodnoty atributů prvků a efektivně vypisovat atributy.
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
title: Čtení shapefile v C# – Získání všech hodnot atributů prvků
url: /cs/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Získat všechny hodnoty atributů prvků

## Úvod
Vítejte ve světě geoprostorového vývoje s Aspose.GIS pro .NET! V tomto tutoriálu se naučíte **jak číst shapefile v C#** a získat každou hodnotu atributu z jeho prvků. Ať už vytváříte mapovou aplikaci nebo zpracováváte prostorová data dávkově, zvládnutí extrakce atributů je nezbytné. Ponořme se do toho a podívejme se na kód v akci.

## Rychlé odpovědi
- **Co tento kód dělá?** Otevře Shapefile a načte všechny, některé nebo vypsané hodnoty atributů z každého prvku.  
- **Která knihovna je vyžadována?** Aspose.GIS pro .NET (kompatibilní s .NET Framework a .NET Core).  
- **Potřebuji licenci?** Dočasná licence stačí pro testování; pro produkci je vyžadována plná licence.  
- **Mohu číst i jiné formáty?** Ano – stejná API podporuje GeoJSON, KML a mnoho dalších.  
- **Jak vypsat atributy?** Použijte `feature.GetValuesDump()` k získání flexibilního pole objektů.

## Co znamená „read shapefile C#“?
Čtení Shapefile v C# znamená otevření souboru .shp pomocí GIS knihovny, iteraci přes jeho vektorové prvky a přístup k datům atributů uloženým v přidruženém souboru .dbf. Aspose.GIS abstrahuje nízkoúrovňové zpracování souborů, takže se můžete soustředit na hodnoty atributů, které potřebujete.

## Proč použít Aspose.GIS pro čtení atributů?
- **Jednoduché API** – intuitivní metody jako `GetValues` a `GetValuesDump`.  
- **Cross‑platform** – funguje na Windows, Linuxu i macOS s .NET Core.  
- **Bohatá podpora formátů** – pracujte se Shapefile, GeoJSON, GML a dalšími bez dalších pluginů.  
- **Optimalizovaný výkon** – rychlá iterace nad velkými datovými sadami.

## Předpoklady
Než se vydáte na tuto vzrušující cestu, ujistěte se, že máte připravené následující:
- Aspose.GIS pro .NET: Stáhněte a nainstalujte knihovnu ze [stahovací stránky Aspose.GIS pro .NET](https://releases.aspose.com/gis/net/).
- Vývojové prostředí: Nastavte .NET vývojové prostředí, například Visual Studio.
- Shapefile: Mějte připravený ukázkový Shapefile (např. „InputShapeFile.shp“) ve vašem adresáři dokumentů.

## Import jmenných prostorů
Ve svém C# kódu začněte importováním potřebných jmenných prostorů pro využití funkcí Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

## Krok 1: Nastavte adresář dokumentů
```csharp
string dataDir = "Your Document Directory";
```
Nahraďte „Your Document Directory“ skutečnou cestou, kde se váš Shapefile nachází.

## Krok 2: Otevřete VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
Tento krok zahrnuje otevření Shapefile pomocí Aspose.GIS, zadání cesty k souboru a formátu (v tomto případě Shapefile).

## Krok 3: Získejte všechny hodnoty atributů prvků
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
Ukázka ukazuje **jak číst atributy** pro každý prvek načtením do pole pevné velikosti.

## Krok 4: Získejte několik hodnot atributů prvků
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
Zde demonstrujeme **jak číst konkrétní hodnoty atributů**, když potřebujete jen podmnožinu polí.

## Krok 5: Získejte hodnoty atributů jako výpis objektů
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
Tento poslední krok ukazuje **jak vypsat atributy** pomocí `GetValuesDump()`, který vrací flexibilní kolekci, kterou můžete prozkoumat nebo serializovat.

## Časté problémy a řešení
- **Neshoda velikosti pole** – Ujistěte se, že pole předané do `GetValues` odpovídá počtu očekávaných atributů; jinak získáte položky `null`.  
- **Soubor nenalezen** – Ověřte, že `dataDir` ukazuje na správnou složku a že název Shapefile je napsán přesně.  
- **Výjimka licence** – Pokud se objeví chyba licence, aplikujte dočasnou nebo plnou licenci před voláním jakýchkoli metod API.

## Často kladené otázky
### Je Aspose.GIS kompatibilní s .NET Core?
Ano, Aspose.GIS je plně kompatibilní s .NET Core, což vám umožní vytvářet cross‑platform aplikace.

### Mohu pracovat s různými GIS formáty pomocí Aspose.GIS?
Rozhodně! Aspose.GIS podporuje různé formáty, včetně Shapefile, GeoJSON a dalších.

### Existuje komunitní fórum pro podporu Aspose.GIS?
Ano, můžete získat pomoc a zapojit se do komunity Aspose.GIS na [fóru podpory](https://forum.aspose.com/c/gis/33).

### Jak získat dočasnou licenci pro Aspose.GIS?
Dočasnou licenci pro testovací účely můžete získat [zde](https://purchase.aspose.com/temporary-license/).

### Kde najdu podrobnou dokumentaci pro Aspose.GIS?
Komplexní dokumentace je dostupná [zde](https://reference.aspose.com/gis/net/).

### Jak získat pouze atribut „Name“ z každého prvku?
Použijte `GetValues` s polem velikosti jeden prvek a předávejte index pole „Name“, nebo přímo zavolejte `feature["Name"]`.

### Jaký je rozdíl mezi `GetValues` a `GetValuesDump`?
`GetValues` naplní předalokované pole surovými hodnotami, zatímco `GetValuesDump` vrací pole objektů, které lze enumerovat bez předchozího znalosti schématu.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-01-05  
**Testováno s:** Aspose.GIS pro .NET (nejnovější verze)  
**Autor:** Aspose  

---
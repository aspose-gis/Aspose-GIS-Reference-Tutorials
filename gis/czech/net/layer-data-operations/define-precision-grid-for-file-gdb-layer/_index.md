---
date: 2025-12-28
description: Naučte se, jak nastavit mřížku pro vrstvu File GDB pomocí Aspose.GIS
  pro .NET, včetně přidání prvků do vrstvy a ověření rozsahu souřadnic.
linktitle: Define Precision Grid for File GDB Layer
second_title: Aspose.GIS .NET API
title: Jak nastavit mřížku pro vrstvu File GDB v Aspose.GIS
url: /cs/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit mřížku pro vrstvu File GDB v Aspose.GIS

## Úvod
V tomto tutoriálu se naučíte **jak nastavit mřížku** pro vrstvu File Geodatabase (GDB) pomocí Aspose.GIS pro .NET. Nastavení přesné mřížky vám pomáhá **validovat rozsah souřadnic**, zabraňuje chybám mimo rozsah a zajišťuje, že data, která **přidáváte do vrstvy**, zůstávají přesná a spolehlivá. Provedeme vás každým krokem, vysvětlíme, proč jsou nastavení důležitá, a ukážeme, jak zvládat běžné úskalí.

## Rychlé odpovědi
- **Co znamená „nastavit mřížku“?** Definuje přesnost souřadnic a platný rozsah pro GIS vrstvu.  
- **Proč používat přesnou mřížku?** Chrání vaše data před neplatnými souřadnicemi a zlepšuje efektivitu úložiště.  
- **Která knihovna tuto funkci poskytuje?** Aspose.GIS pro .NET.  
- **Potřebuji licenci?** K dispozici je zkušební verze; pro produkci je vyžadována komerční licence.  
- **Mohu to použít s .NET Core?** Ano, Aspose.GIS podporuje .NET Framework i .NET Core.

## Co je přesná mřížka a proč ji nastavit?
Přesná mřížka je sada parametrů (počátek, měřítko atd.), která říká GIS enginu, jak zaokrouhlovat a ukládat hodnoty souřadnic. Definováním mřížky **automaticky validujete rozsah souřadnic** a jakýkoli pokus vložit bod mimo mřížku vyvolá výjimku — pomáhá vám **zvládat situace mimo rozsah** již v raném vývoji.

## Předpoklady
Předtím, než začneme, ujistěte se, že máte nainstalováno následující:

1. **Visual Studio** – jakákoli recentní verze (Community, Professional nebo Enterprise).  
2. **Aspose.GIS pro .NET** – stáhněte jej z [webu](https://releases.aspose.com/gis/net/).  
3. **Základní znalost C#** – měli byste být schopni vytvářet .NET konzolové projekty.

## Importování jmenných prostorů
Nejprve importujte jmenné prostory potřebné pro práci s Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## Jak nastavit mřížku ve vrstvě File GDB
Níže je krok‑za‑krokem průvodce, který přesně ukazuje, jak nakonfigurovat mřížku, vytvořit vrstvu a bezpečně **přidávat prvky do vrstvy**.

### Krok 1: Vytvoření datasetu
Začneme vytvořením nového datasetu File Geodatabase. Toto je místo, kde bude vrstva umístěna.

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### Krok 2: Definování možností přesné mřížky
Zde specifikujeme parametry mřížky. Přizpůsobte počátky a měřítka tak, aby odpovídaly souřadnicovému systému vašeho projektu.

```csharp
var options = new FileGdbOptions
{
    CoordinatePrecisionGrid = new FileGdbCoordinatePrecisionGrid
    {
        XOrigin = -400,
        YOrigin = -400,
        XYScale = 1e10,
        MOrigin = 0,
        MScale = 1e4,
    },
    EnsureValidCoordinatesRange = true,
};
```

*Příznak `EnsureValidCoordinatesRange = true` říká Aspose.GIS, aby **validoval rozsah souřadnic** pro každý prvek, který přidáte.*

### Krok 3: Vytvoření vrstvy s mřížkou
Nyní vytvoříme novou vrstvu uvnitř datasetu, aplikujeme právě definované možnosti mřížky. Použijeme prostorový referenční systém WGS84.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### Krok 4: Přidání prvků do vrstvy
Vytvoříme dva bodové prvky. První bod leží uvnitř mřížky, zatímco druhý úmyslně spadá mimo, aby demonstroval **jak zvládat chyby mimo rozsah**.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### Krok 5: Zpracování výjimek při přidávání prvků mimo rozsah
Pokus o přidání druhého prvku vyvolá výjimku, protože jeho X souřadnice (`-410`) je mimo definovanou mřížku. Zachytíme výjimku a vypíšeme jasnou zprávu.

```csharp
try
{
    layer.Add(feature);
}
catch (GisException e)
{
    Console.WriteLine(e.Message); // X value -410 is out of valid range.
}
```

### Krok 6: Vyčištění
Příkazy `using` automaticky uzavřou a uvolní dataset a vrstvu, čímž zajistí uvolnění všech zdrojů.

## Časté problémy a řešení
| Problém | Proč se to děje | Řešení |
|-------|----------------|-----|
| **Výjimka: „X hodnota … je mimo platný rozsah.“** | Souřadnice spadají mimo přesnou mřížku. | Upravte `XOrigin`, `YOrigin` nebo `XYScale`, aby zahrnovaly vaše data, nebo zajistěte, že vstupní data jsou v definovaném rozsahu. |
| **Prvky se nezobrazují v GIS prohlížeči** | Vrstva není uložena nebo je špatný prostorový referenční systém. | Ověřte, že `SpatialReferenceSystem.Wgs84` odpovídá CRS prohlížeče, a že `Dataset.Create` byl úspěšný. |
| **M hodnoty jsou ignorovány** | `MScale` nastaven na 0 nebo příliš nízký. | Nastavte rozumný `MScale` (např. `1e4`) pro ukládání měrných hodnot. |

## Často kladené otázky

**Q: Mohu použít Aspose.GIS pro .NET s jinými GIS formáty souborů?**  
A: Ano, Aspose.GIS podporuje Shapefile, GeoJSON, KML a mnoho dalších formátů.

**Q: Je Aspose.GIS pro .NET kompatibilní s .NET Core?**  
A: Rozhodně. Knihovna funguje s .NET Framework, .NET Core i .NET 5/6+.

**Q: Mohu provádět prostorové operace jako bufferování nebo průnik?**  
A: Ano, API obsahuje metody pro bufferování, průnik a výpočet vzdáleností.

**Q: Poskytuje Aspose.GIS možnosti transformace souřadnic?**  
A: Ano, můžete transformovat geometrie mezi různými prostorovými referenčními systémy pomocí vestavěných nástrojů pro reprojekci.

**Q: Je k dispozici zkušební verze?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi z [webu](https://releases.aspose.com/gis/net/).

---

**Poslední aktualizace:** 2025-12-28  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2025-12-06
description: Naučte se, jak převést GeoJSON na TopoJSON se seskupováním, nastavit
  atribut názvu objektu a seskupit funkce GeoJSON pomocí Aspose.GIS pro .NET.
language: cs
linktitle: How to Convert GeoJSON to TopoJSON with Grouping using Aspose.GIS
second_title: Aspose.GIS .NET API
title: Jak převést GeoJSON na TopoJSON se seskupením pomocí Aspose.GIS
url: /net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak převést GeoJSON na TopoJSON se seskupením pomocí Aspose.GIS

## Úvod

V tomto krok‑za‑krokem tutoriálu se naučíte **jak převést GeoJSON** soubory na TopoJSON při seskupování prvků podle zvoleného atributu. Použití Aspose.GIS .NET API umožňuje rychlou, spolehlivou a plně kontrolovatelnou konverzi z vašeho C# kódu. Ať už vytváříte ASP.NET službu pro konverzi GeoJSON nebo desktopový GIS nástroj, tento průvodce vám ukáže přesně, co je potřeba udělat.

## Rychlé odpovědi
- **Která knihovna provádí konverzi?** Aspose.GIS for .NET  
- **Jak dlouho trvá implementace?** Obvykle 5‑10 minut pro základní nastavení  
- **Potřebuji licenci pro produkci?** Ano, je vyžadována komerční licence (k dispozici bezplatná zkušební verze)  
- **Mohu seskupovat prvky podle libovolného atributu?** Ano – nastavte `ObjectNameAttribute` na pole, podle kterého chcete seskupovat  
- **Je podporovNET Core?** Rozhodně – API funguje s .NET Core, .NET 5/6 a klasickým .NET Framework  

## Co je GeoJSON a TopoJSON?

GeoJSON je široce používaný formát JSON pro kódování geografických prvků, jako jsou body, čáry a polygony. TopoJSON rozšiřuje GeoJSON ukládáním topologie (sdílených úseků čar), což snižuje velikost souboru a zlepšuje výkon vykreslování u složitých map. Převod mezi nimi je běžný krok, když potřebujete kompaktní mapová data pro webové vizualizace.

## Proč seskupovat GeoJSON prvky?

Grouping (`group geojson features`) vám umožní uspořádat související geometrie pod jedním pojmenovaným objektem ve výsledném TopoJSON. To je zvláště užitečné, když:
- Chcete vytvořit samostatné vrstvy pro různé administrativní oblasti.  
- Vaše front‑endová mapová knihovna očekává pojmenované objekty pro stylování nebo interakci.  
- Potřebujete snížit duplikaci sdílením hranic mezi sousedními prvky.

## Požadavky

Než začneme, ujistěte se, že máte následující požadavky:

1. **Aspose.GIS for .NET** – stáhněte a nainstalujte z oficiální stránky [here](https://releases.aspose.com/gis/net/).  
2. **Vývojové prostředí** – Visual Studio, Visual Studio Code nebo jakékoli IDE podporující C#.  
3. **Ukázkový GeoJSON soubor** – soubor obsahující prvky, které chcete převést.  

## Importujte jmenné prostory

Nejprve zahrňte potřebné jmenné prostory do vašeho projektu:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```

## Průvodce krok za krokem

### Krok 1: Definujte cesty k souborům

Určete, kde se nachází zdrojový GeoJSON a kam má být zapsán TopoJSON:

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

> **Tip:** Použijte `Path.Combine` pro tvorbu cest napříami, pokud cílíte na .NET Core.

### Krok 2: Nakonfigurujte možnosti konverze (nastavte atribut názvu objektu)

Vytvořte instanci `ConversionOptions` a sdělte Aspose.GIS, jak seskupit prvky:

```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // Specify the attribute in GeoJSON layer by which we are going to group into objects
        ObjectNameAttribute = "group",
        // Specify the default object name for features with unknown attribute values
        DefaultObjectName = "unnamed",
    }
};
```

Nahraďte `"group"` skutečným názvem vlastnosti ve vašem GeoJSON, kterou chcete použít pro **seskupování geojson prvků**. `DefaultObjectName` zajišťuje, že každý prvek skončí v objektu TopoJSON, i když atribut chybí.

### Krok 3: Proveďte konverzi (převod GeoJSON na TopoJSON)

Spusťte konverzi jedním voláním API:

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

Po provedení bude `convertedSampleWithGrouping_out.topojson` obsahovat TopoJSON reprezentaci s prvky seskupenými podle vámi zadaného atributu.

## Časté problémy a řešení

| **Všechny prvky končí v „unnamed“** | `ObjectNameAttribute` neodpovídá žádné vlastnosti v GeoJSON | Ověřte přesný název vlastnosti (rozlišuje velká a malá písmena) a aktualizujte volbu |
| **Výstupní soubor je prázdný** | Nesprávná cesta k souboru nebo chybějící oprávnění ke čtení | Použijte absolutní cesty nebo zajistěte, aby aplikace měla přístup k souborovému systému |
| **Konverze vyvolá `NotSupportedException`** | Pokus o konverzi GeoJSON s nepodporovanými typy geometrie (např. GeometryCollection) | Zjednodušte zdrojová data nebo aktualizujte na nejnovější verzi Aspose.GIS |

## Často kladené otázky

**Q: Mohu seskupovat prvky na základě více atributů?**  
A: Ano, můžete spojit několik polí do jednoho virtuálního atributu nebo provést více konverzních průchodů s různými hodnotami `ObjectNameAttribute`.

**Q: Je Aspose.GIS kompatibilní s ASP.NET Core?**  
A: Rozhodně – knihovna funguje s ASP.NET Core, .NET 5, .NET 6 a klasickým .NET Framework.

**Q: Mohu převést i jiné geografické formáty než GeoJSON?**  
A: Ano, Aspose.GIS podporuje Shapefile, KML, GML, CSV a mnoho dalších formátů pro import i export.

**Q: Nabízí Aspose.GIS bezplatnou zkušební verzi?**  
A: Ano, můžete získat bezplatnou zkušební verzi Aspose.GIS [zde](https://releases.aspose.com/).

**Q: Kde mohu získat podporu pro Aspose.GIS?**  
A: Podporu můžete získat na komunitním fóru Aspose.GIS [zde](https://forum.aspose.com/c/gis/33).

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Poslední aktualizace:** 2025-12-06  
**Testováno s:** Aspose.GIS for .NET (nejnovější verze)  
**Autor:** Aspose  

---
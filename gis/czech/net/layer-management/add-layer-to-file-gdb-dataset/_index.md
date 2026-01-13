---
date: 2026-01-13
description: Naučte se, jak přidat vrstvu do datasetu File GDB pomocí Aspose.GIS s
  podporou prostorového referenčního systému WGS84. Postupujte podle tohoto krok‑za‑krokem
  průvodce a přidejte vrstvu do GDB v .NET.
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: prostorová reference WGS84 – Přidat vrstvu do GDB pomocí Aspose.GIS
url: /cs/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# spatial reference wgs84 – Přidání vrstvy do GDB pomocí Aspose.GIS

## Úvod
Jste připraveni zrychlit svůj GIS workflow pomocí Aspose.GIS pro .NET? V tomto tutoriálu se naučíte **jak přidat vrstvu do datasetu File GDB** při práci se souřadnicovým systémem **spatial reference wgs84**. Provedeme vás každým krokem, od přípravy složky s daty až po ověření nově vytvořené vrstvy, abyste mohli sebejistě manipulovat s geografickými daty.

## Rychlé odpovědi
- **Jaký je primární souřadnicový systém?** spatial reference wgs84 (WGS 84)  
- **Která knihovna poskytuje API?** Aspose.GIS for .NET  
- **Potřebuji licenci pro testování?** Yes – a temporary Aspose license is available.  
- **Mohu přidat atributy do nové vrstvy?** Absolutely, you can define any number of feature attributes.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## Co je spatial reference wgs84?
Spatial reference wgs84 (World Geodetic System 1984) je nejrozšířenějším geografickým souřadnicovým systémem. Definuje zeměpisnou šířku a délku ve stupních a slouží jako výchozí CRS pro mnoho GIS datasetů, včetně toho, který v tomto průvodci vytvoříme.

## Proč použít Aspose.GIS pro přidání vrstvy?
- **Žádné externí závislosti:** Works out‑of‑the‑box with pure .NET code.  
- **Plná kontrola nad schématem:** You can define custom attributes and geometry types.  
- **Cross‑platform:** Compatible with Windows, Linux, and macOS runtimes.  
- **Robustní licencování:** Temporary licenses let you evaluate quickly before committing.

## Požadavky
Před zahájením se ujistěte, že máte:

- Aspose.GIS for .NET Library: Stáhněte a nainstalujte knihovnu z [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Document Directory: Vytvořte vyhrazenou složku ve svém počítači pro ukládání GIS souborů.

## Importování jmenných prostorů
Přidejte požadované `using` příkazy do svého C# projektu, abyste mohli přistupovat ke třídám Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Zkopírování adresáře
Nejprve duplikujte složku, která obsahuje původní dataset GDB. Uchování kopie chrání zdrojová data během experimentování.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Krok 2: Otevření datasetu a ověření možnosti vytváření
Otevřete nově zkopírovaný dataset a potvrďte, že může vytvářet nové vrstvy. Vlastnost `CanCreateLayers` by měla vracet **True**.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Krok 3: Vytvoření a naplnění nové vrstvy se spatial reference wgs84
Nyní vytvoříme vrstvu pojmenovanou **data** a explicitně nastavíme její spatial reference na **Wgs84**. Také přidáme jednoduchý atribut nazvaný **Name** a vložíme jeden bodový prvek.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## Krok 4: Otevření a ověření přidané vrstvy
Nakonec otevřete vrstvu, kterou jste právě vytvořili, a ověřte její obsah. Konzole zobrazí, že vrstva obsahuje jeden prvek a že atribut **Name** odpovídá nastavené hodnotě.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Časté problémy a tipy
- **Incorrect path:** Ujistěte se, že `dataDir` končí oddělovačem cesty (`/` nebo `\`), aby spojené řetězce tvořily platné cesty k souborům.  
- **License errors:** Pokud vidíte varování o licencích, aplikujte dočasnou licenci z portálu Aspose před spuštěním kódu.  
- **CRS mismatch:** Při otevírání vrstvy později v jiném GIS nástroji ověřte, že nástroj rozpozná WGS 84 (EPSG:4326) jako souřadnicový systém.

## Často kladené otázky
### Q: Mohu používat Aspose.GIS pro .NET s jinými GIS knihovnami?
Aspose.GIS pro .NET je navržen tak, aby fungoval samostatně, ale může být integrován s jinými knihovnami pro rozšířenou funkčnost.

### Q: Je k dispozici dočasná licence pro testovací účely?
Ano, můžete získat dočasnou licenci z [here](https://purchase.aspose.com/temporary-license/) pro testování a hodnocení.

### Q: Jaké souřadnicové systémy podporuje Aspose.GIS pro .NET?
Aspose.GIS pro .NET podporuje širokou škálu souřadnicových systémů, což poskytuje flexibilitu při práci s geografickými daty.

### Q: Mohu přispívat do komunity Aspose.GIS?
Určitě! Připojte se k diskusím a sdílejte své zkušenosti na [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### Q: Kde najdu podrobnou dokumentaci pro Aspose.GIS pro .NET?
Prozkoumejte komplexní dokumentaci [here](https://reference.aspose.com/gis/net/) pro podrobné informace o Aspose.GIS pro .NET.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-01-13  
**Testováno s:** Aspose.GIS for .NET (nejnovější stabilní verze)  
**Autor:** Aspose
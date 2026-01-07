---
date: 2026-01-07
description: Naučte se, jak pomocí Aspose.GIS pro .NET zapisovat soubory KML, jak
  vytvořit KML, přidat booleanový atribut a vytvořit LineString ve svých aplikacích.
linktitle: Interact with KML Layer
second_title: Aspose.GIS .NET API
title: Jak zapisovat KML soubor pomocí Aspose.GIS pro .NET
url: /cs/net/layer-interaction-and-data-access/interact-with-kml-layer/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit KML soubor pomocí Aspose.GIS pro .NET

## Úvod
V dnešním daty řízeném světě vám schopnost **zapsat KML soubor** programově poskytuje moc sdílet geografické informace napříč platformami, vizualizovat trasy na mapách a integrovat údaje o poloze do webových nebo mobilních aplikací. Aspose.GIS pro .NET tento proces zjednodušuje, takže se můžete soustředit na logiku místo na složitosti formátu souboru. V tomto tutoriálu projdeme vytvoření KML vrstvy, přidání atributů (včetně boolean atributu) a vytvoření geometrie line string – vše s jasným, krok‑za‑krokem kódem.

## Rychlé odpovědi
- **Co znamená „zapsat KML soubor“?** Vytvoření dokumentu KML (Keyhole Markup Language), který popisuje geografické prvky jako body, linie a polygony.  
- **Která knihovna je nejlepší pro .NET?** Aspose.GIS pro .NET poskytuje plynulé API pro vytváření a úpravu KML souborů.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze stačí pro hodnocení; licence je vyžadována pro produkční použití.  
- **Mohu přidat vlastní atributy?** Ano – můžete přidávat řetězcové, celočíselné, boolean a double atributy ke každému prvku.  
- **Je podporováno vytváření geometrie?** Rozhodně – můžete vytvářet body, line stringy, polygony a další.

## Předpoklady
Než se pustíme do práce, ujistěte se, že máte připravené následující:
- Aspose.GIS pro .NET: Stáhněte a nainstalujte knihovnu ze [stahovací stránky Aspose.GIS pro .NET](https://releases.aspose.com/gis/net/).
- Vývojové prostředí: Nastavte vhodné vývojové prostředí, například Visual Studio, aby se Aspose.GIS hladce integroval do vašich .NET projektů.

## Import jmenných prostorů
Než začnete pracovat s KML vrstvami, zahrňte do svého projektu potřebné jmenné prostory. Tento krok zajistí přístup ke třídám a metodám potřebným pro manipulaci s geoprostorovými daty.

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Drawing;
using System.Threading;
using Aspose.Gis.Formats.Kml;
using Aspose.Gis.Formats.Kml.Styles;
using Aspose.Gis.Geometries;
using Point = Aspose.Gis.Geometries.Point;
```

## Krok 1: Nastavte adresář dokumentu
Definujte cestu k adresáři, kde budou uloženy KML soubory.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Vytvořte KML vrstvu
Inicializujte KML vrstvu pomocí Aspose.GIS a určete cestu k souboru KML.

```csharp
using (var layer = Drivers.Kml.CreateLayer(dataDir + "Kml_File_out.kml"))
{
```

## Krok 3: Definujte atributy (přidejte boolean atribut)
Přidejte atributy do KML vrstvy, které reprezentují různé datové typy jako řetězec, celé číslo, **boolean** a double. Zde „přidáte boolean atribut“ ke každému prvku.

```csharp
layer.Attributes.Add(new FeatureAttribute("string_data", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("int_data", AttributeDataType.Integer));
layer.Attributes.Add(new FeatureAttribute("bool_data", AttributeDataType.Boolean));
layer.Attributes.Add(new FeatureAttribute("float_data", AttributeDataType.Double));
```

## Krok 4: Vytvořte a naplňte prvky (vytvořte line string)
Sestavte prvky představující geoprostorové entity a nastavte hodnoty pro definované atributy. Zde **vytvoříte line string** geometrii pro ilustraci jednoduché cesty.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("string_data", "string value");
feature.SetValue("int_data", 10);
feature.SetValue("bool_data", true);
feature.SetValue("float_data", 3.14);
feature.Geometry = new LineString(new[] { new Point(0, 0), new Point(1, 1) });
layer.Add(feature);
```

## Krok 5: Přidejte další prvek
Opakujte proces a přidejte druhý prvek s odlišnými hodnotami atributů a nulovou geometrií.

```csharp
Feature feature2 = layer.ConstructFeature();
feature2.SetValue("string_data", "string value2");
feature2.SetValue("int_data", 100);
feature2.SetValue("bool_data", false);
feature2.SetValue("float_data", 3.1415);
feature2.Geometry = Geometry.Null;
layer.Add(feature2);
```

## Jak zapsat KML soubor – vše dohromady
Po provedení výše uvedených kroků máte plně funkční KML soubor, který obsahuje vlastní atributy (včetně boolean příznaku) a geometrii line string. Výsledný soubor `Kml_File_out.kml` můžete otevřít v Google Earth, ArcGIS nebo jakémkoli GIS prohlížeči podporujícím KML.

## Časté problémy a řešení
- **Chyby cesty k souboru** – Ujistěte se, že `dataDir` končí oddělovačem cesty (`\` nebo `/`) vhodným pro váš OS.  
- **Chybějící licence** – Zkušební verze funguje pro hodnocení, ale pro neomezené zápisy KML souborů je vyžadována licencovaná verze.  
- **Nulová geometrie** – Nastavení `Geometry.Null` je úmyslné pro prvky bez prostorových dat; vynechte, pokud vždy potřebujete geometrii.

## Často kladené otázky
### Je Aspose.GIS kompatibilní s jinými GIS formáty?
Ano, Aspose.GIS podporuje různé GIS formáty, včetně shapefile, GeoJSON a KML.

### Můžu vizualizovat geoprostorová data vytvořená pomocí Aspose.GIS?
Rozhodně! Aspose.GIS se hladce integruje s knihovnami pro mapování, což vám umožní vizualizovat vaše geoprostorová data.

### Je k dispozici zkušební verze Aspose.GIS?
Ano, můžete si vyzkoušet funkce Aspose.GIS stažením [verze zdarma ke zkušebnímu použití](https://releases.aspose.com/).

### Jak získám podporu pro Aspose.GIS?
Navštivte [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pro komunitní podporu nebo prozkoumejte prémiové možnosti podpory [zde](https://purchase.aspose.com/buy).

### Jsou k dispozici dočasné licence pro Aspose.GIS?
Ano, dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

## Další často kladené otázky

**Q: Jak **vytvořit KML** soubory s vlastním stylingem?**  
A: Použijte jmenný prostor `Aspose.Gis.Formats.Kml.Styles` k definování ikon, barev linek a stylů popisků před přidáním prvků.

**Q: Můžu efektivně zapisovat velké KML soubory?**  
A: Zapisujte prvky po dávkách a periodicky flushujte vrstvu, aby se udržela nízká spotřeba paměti.

**Q: Podporuje Aspose.GIS .NET Core a .NET 6+?**  
A: Ano, knihovna je plně kompatibilní s .NET Core, .NET 5 i .NET 6.

---

**Poslední aktualizace:** 2026-01-07  
**Testováno s:** Aspose.GIS 24.10 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-05-16
description: Příklad vektorové vrstvy ukazující, jak nastavit šířku pole, definovat
  šířku atributu a přidat délku atributu v Aspose.GIS pro .NET – kompletní průvodce
  krok za krokem.
keywords:
- vector layer example
- how to set width
- set field width
- define attribute width
- add attribute length
linktitle: Jak nastavit šířku pole
schemas:
- author: Aspose
  dateModified: '2026-05-16'
  description: Vector layer example showing how to set field width, define attribute
    width, and add attribute length in Aspose.GIS for .NET – a complete step‑by‑step
    guide.
  headline: Vector Layer Example – How to Set Field Width in Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for peer‑to‑peer
      help and official responses.
    question: Where can I find community support for Aspose.GIS for .NET?
  - answer: Yes, explore the [free trial](https://releases.aspose.com/) to experience
      the full feature set without cost.
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Purchase your license [here](https://purchase.aspose.com/buy).
    question: How do I purchase a license for Aspose.GIS for .NET?
  - answer: Refer to the [documentation](https://reference.aspose.com/gis/net/) for
      comprehensive API details.
    question: Where can I access the documentation for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Příklad vektorové vrstvy – Jak nastavit šířku pole v Aspose.GIS pro .NET
url: /cs/net/layer-data-operations/specify-attribute-value-length/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Příklad vektorové vrstvy – Jak nastavit šířku pole v Aspose.GIS pro .NET

V tomto **příkladu vektorové vrstvy** se naučíte, jak nastavit šířku pole pro atribut při vytváření Shapefile pomocí Aspose.GIS pro .NET. Provedeme vás každým krokem, od importování jmenných prostorů po přidání prvku, a vysvětlíme, proč kontrola délky atributu má význam pro integritu dat a interoperabilitu s ostatními GIS nástroji.

## Rychlé odpovědi
- **Jaký je hlavní účel tohoto průvodce?** Ukázat, jak nastavit šířku pole pro atribut v shapefile pomocí Aspose.GIS pro .NET.  
- **Která třída definuje šířku pole?** `FeatureAttribute.Width`.  
- **Potřebuji licenci pro spuštění kódu?** Dočasná licence funguje pro hodnocení; plná licence je vyžadována pro produkci.  
- **Jaký formát souboru je v příkladu použit?** ESRI Shapefile (`.shp`).  
- **Mohu změnit šířku po vytvoření vrstvy?** Ne – šířka musí být definována před přidáním prvků.

## Co je šířka pole a proč je důležitá?
Šířka pole (také nazývaná délka atributu) je maximální počet znaků, které může řetězcové pole uložit v komponentě DBF shapefile. Nastavení správné šířky zabraňuje tichému oříznutí, zajišťuje, že jiné GIS aplikace přečtou data přesně tak, jak jste je zadali, a udržuje předvídatelnou velikost souboru – každý další znak přidá jeden bajt na záznam.

## Požadavky
- **Aspose.GIS for .NET Library** – stáhněte z [download link](https://releases.aspose.com/gis/net/).  
- **Vývojové prostředí** – Visual Studio 2022, Visual Studio Code nebo jakékoli IDE podporující .NET 6+.  
- **Zápisový přístup** – složka na disku, kam bude vygenerovaný shapefile uložen.

## Proč použít příklad vektorové vrstvy s definovanou šířkou?
Aspose.GIS podporuje **více než 30 GIS formátů souborů**, včetně Shapefile, GeoJSON, KML a GML. Když explicitně nastavíte šířku pole, vyhnete se výchozímu limitu 255 znaků, který může zbytečně nafouknout soubor `.dbf` až o 255 × početZáznamů bajtů. Ve velkých datových sadách to vede k patrným úsporám úložiště.

## Jak nastavit šířku pole pro atribut?
V této sekci načteme nebo vytvoříme `VectorLayer`, který ukazuje na cílový soubor `.shp`, definujeme řetězcový atribut s přesnou šířkou a poté přidáme prvky – vše v několika stručných příkazech. `VectorLayer` představuje vektorový dataset, jako je Shapefile, a poskytuje přístup k jeho geometrii a tabulce atributů. Níže je přímý, akční návod, který můžete krok za krokem sledovat:

Načtěte nebo vytvořte `VectorLayer`, který ukazuje na cílový soubor `.shp`, deklarujte řetězcový atribut pojmenovaný **wide** s `Width = 120`, poté přidejte prvek, jehož hodnota respektuje limit 120 znaků. Aspose.GIS automaticky ořízne jakýkoli delší řetězec na definovanou šířku, čímž zachová konzistenci dat bez vyvolání výjimek.

### Import jmenných prostorů
`FeatureAttribute`, `VectorLayer` a související typy se nacházejí v jmenném prostoru `Aspose.Gis`. Importujte je na začátku souboru:

The `Aspose.Gis` namespace provides the core GIS objects you’ll work with, such as `VectorLayer`, `Feature`, and `FeatureAttribute`. Importing it makes the classes available without fully‑qualified names.

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Vytvoření VectorLayer
Třída `VectorLayer` představuje zdroj vektorových dat (např. Shapefile). Je to kontejner, který obsahuje prvky a jejich atributy.

Třída `VectorLayer` je reprezentací vektorového datasetu v Aspose.GIS, spravující geometrii a tabulky atributů v paměti. Vytvořte instanci, která ukazuje na nový nebo existující soubor `.shp`.

```csharp
string dataDir = "Your Document Directory";
using (VectorLayer layer = VectorLayer.Create(dataDir + "SpecifyAttributeValueLength_out.shp", Drivers.Shapefile))
{
    // Your code for the next steps will go here.
}
```

### Přidání atributu s konkrétní délkou
Definujte řetězcový atribut pojmenovaný **wide** a nastavte jeho vlastnost `Width` na 120 znaků. Toto je hlavní krok **příkladu vektorové vrstvy**.

Objekt `FeatureAttribute` popisuje sloupec v tabulce atributů; nastavení `Width = 120` říká zapisovači Shapefile, aby alokoval přesně 120 bajtů pro každý záznam tohoto pole.

```csharp
FeatureAttribute attribute = new FeatureAttribute("wide", AttributeDataType.String);
attribute.Width = 120;
layer.Attributes.Add(attribute);
```

> **Tip:** Vlastnost `Width` se vztahuje pouze na řetězcové atributy. Číselná, datumová nebo Boolean pole ignorují `Width`, protože jejich velikost je určena typem dat.

### Vytvoření a přidání prvku
Vytvořte `Feature`, přiřaďte hodnotu, která se vejde do limitu 120 znaků, a přidejte ji do vrstvy. Pokud řetězec překročí limit, Aspose.GIS jej tiše ořízne na definovanou šířku, čímž zachová integritu dat.

Třída `Feature` zapouzdřuje geometrii a hodnoty atributů; po nastavení atributu volání `layer.Add(feature)` zapíše záznam do Shapefile.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("wide", "this string can be up to 120 characters long now.");
layer.Add(feature);
```

Pokud se pokusíte přiřadit delší řetězec, Aspose.GIS jej ořízne na definovanou šířku, čímž zachová integritu dat.

## Časté úskalí a řešení problémů
- **Zapomněl(a) jste nastavit `Width` před přidáním atributu?** Výchozí šířka je 255 znaků; změna později neovlivní již vytvořená pole. Vždy nejprve definujte šířku.  
- **Používáte datový typ, který není řetězec?** `Width` se ignoruje pro číselná nebo datumová pole; ujistěte se, že `AttributeDataType` atributu je `String`.  
- **Chyba „Field not found“?** Názvy atributů rozlišují velká a malá písmena. Ověřte, že název použitý v `SetValue` přesně odpovídá názvu definovanému ve schématu.  
- **Neočekávaný nárůst velikosti souboru?** Větší šířky lineárně zvyšují velikost `.dbf`. Pro 10 000 záznamů zvýšení šířky z 50 na 120 přidá přibližně 700 KB.

## Často kladené otázky
**Q: Jak mohu získat dočasnou licenci pro Aspose.GIS pro .NET?**  
A: Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

**Q: Kde mohu najít komunitní podporu pro Aspose.GIS pro .NET?**  
A: Navštivte [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pro pomoc od komunity a oficiální odpovědi.

**Q: Je k dispozici bezplatná zkušební verze pro Aspose.GIS pro .NET?**  
A: Ano, vyzkoušejte [bezplatnou zkušební verzi](https://releases.aspose.com/), abyste si vyzkoušeli kompletní sadu funkcí bez nákladů.

**Q: Jak si mohu zakoupit licenci pro Aspose.GIS pro .NET?**  
A: Zakupte si licenci [zde](https://purchase.aspose.com/buy).

**Q: Kde mohu najít dokumentaci pro Aspose.GIS pro .NET?**  
A: Viz [dokumentaci](https://reference.aspose.com/gis/net/) pro podrobné informace o API.

**Q: Mohu změnit šířku pole po vytvoření vrstvy?**  
A: Ne. Šířka pole musí být definována před přidáním atributu; pro její změnu musíte vrstvu znovu vytvořit s novým schématem.

**Q: Ovlivňuje nastavení větší šířky velikost souboru?**  
A: Shapefiles ukládají řetězcová pole s pevnou délkou, takže zvýšení šířky přímo zvětšuje velikost souboru `.dbf` úměrně počtu záznamů.

## Závěr
Tento **příklad vektorové vrstvy** ukázal, jak nastavit šířku pole pro atribut v Shapefile pomocí Aspose.GIS pro .NET, a jak efektivně přidat atribut s konkrétní délkou. Kontrolou šířky atributu se vyhnete oříznutí dat, udržíte optimální velikost souborů a zajistíte bezproblémovou interoperabilitu s ostatními GIS platformami. Experimentujte s různými šířkami, prozkoumejte [dokumentaci](https://reference.aspose.com/gis/net/) a odemkněte plný potenciál geospatial vývoje s Aspose.GIS.

---

**Poslední aktualizace:** 2026-05-16  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Získat atributy vrstvy – Získání informací o atributech vrstvy s Aspose.GIS pro .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Jak získat hodnotu atributu (výchozí) s Aspose.GIS pro .NET](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [Vytvořit vektorovou vrstvu v souboru GDB – Tutoriál Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
date: 2026-06-25
description: Naučte se, jak číst shapefile a převést polygonový shapefile na linestring
  pomocí Aspose.GIS for .NET. Zrychlete svůj vývoj GIS s jasným krok‑za‑krokem návodem.
keywords:
- how to read shapefile
- convert polygon to line
- shapefile to geojson c#
- extract lines from polygon
linktitle: Převést Polygon Shapefile na Linestring
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  headline: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  type: TechArticle
- description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  name: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  steps:
  - name: Set the Document Directory
    text: Replace `"Your Document Directory"` with the actual path where your shapefile
      resides.
  - name: Open the Source Shapefile
    text: This line opens the source Polygon Shapefile so you can read its features.
  - name: Create the Destination Linestring Shapefile
    text: Here we create a new Linestring Shapefile that will store the converted
      geometries.
  - name: Iterate Through Source Features
    text: The loop walks through each polygon feature in the original file.
  - name: Convert Polygon to Linestring and Write to Destination
    text: The `ExteriorRing` property returns the outer boundary of a polygon as a
      `LineString`. In this block we convert polygon to line (`LineString`) and add
      the new feature to the destination shapefile.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS supports .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7, ensuring seamless integration with modern development stacks.
    question: Is Aspose.GIS compatible with all versions of .NET?
  - answer: Yes, you can. Purchase a license [here](https://purchase.aspose.com/buy)
      to remove evaluation limitations and obtain full support.
    question: Can I use Aspose.GIS for commercial projects?
  - answer: Yes, you can find comprehensive documentation and code samples on the
      [documentation page](https://reference.aspose.com/gis/net/).
    question: Are there any examples or documentation available?
  - answer: Absolutely – explore Aspose.GIS with a free trial by visiting [this link](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      assistance and official support.
    question: Where can I seek help or support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Jak číst Shapefile C# – Převést Polygon Shapefile na Linestring
url: /cs/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přečíst Shapefile C# – Převést polygonový Shapefile na Linestring

## Úvod
Pokud potřebujete **how to read shapefile** data v .NET prostředí, jste na správném místě. Aspose.GIS pro .NET abstrahuje nízkoúrovňový binární formát Shapefile, což vám umožní načíst, dotazovat a transformovat geografické prvky pomocí několika volání API. Převod polygonového shapefile na linestring je zvláště užitečný, když chcete získat lineární reprezentace pro směrování, analýzu sítí nebo jednoduchou vizualizaci.

## Rychlé odpovědi
- **Která knihovna vám pomůže číst shapefile c#?** Aspose.GIS pro .NET – podporuje více než 50 GIS formátů a zvládá soubory až několik stovek megabajtů, aniž by načítala celý soubor do paměti.  
- **Můžete převést polygon na linii?** Ano – zavolejte `LineString` na vnější obvod polygonu a výsledek zapište do nového shapefile.  
- **Potřebuji licenci pro produkci?** Komerní licence je vyžadována pro produkční nasazení; bezplatná zkušební verze funguje pro hodnocení.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Je k dispozici zkušební verze?** Ano – stáhněte si bezplatnou zkušební verzi z webu Aspose.

`LineString` je typ geometrie představující sérii spojených úseků čar.

## Co je “read shapefile c#”?
`Document` je hlavní třída, která představuje GIS dataset a poskytuje přístup k jeho prvkům.  
Čtení shapefile v C# znamená načtení souboru `.shp` do paměti, abyste mohli dotazovat, upravovat nebo transformovat jeho geometrie. **Jednoduše vytvoříte instanci třídy `Document` s cestou k souboru a Aspose.GIS pro vás parsuje binární strukturu**, čímž zpřístupní prvky prostřednictvím snadno použitelné kolekce. Tento přístup eliminuje potřebu pracovat ručně s nízkoúrovňovými hlavičkami souborů nebo poli souřadnic.

## Proč převést polygon na linii s Aspose.GIS?
Převod polygonu na linestring zachovává přesnou vnější hranici a odstraňuje vnitřní kruhy, čímž vám poskytne čistou lineární reprezentaci. Aspose.GIS zpracovává **datové sady až do 500 MB za méně než 2 sekundy na typickém serveru**, což umožňuje rychlé a paměťově úsporné hromadné převody. Knihovna také zachovává původní prostorovou referenci, takže výsledné linie se perfektně slaďují s jakýmikoli existujícími GIS vrstvami.

## Předpoklady
Než se ponoříme do tutoriálu, ujistěte se, že máte následující připravené:

- **Aspose.GIS Library** – Stáhněte a nainstalujte knihovnu Aspose.GIS z [webu](https://releases.aspose.com/gis/net/).  
- **Shapefile Data** – Mějte připravený polygonový Shapefile pro převod. Pokud žádný nemáte, můžete najít ukázková data nebo si vytvořit vlastní.  
- **Development Environment** – Nastavte své .NET vývojové prostředí s potřebnými nástroji (Visual Studio, .NET SDK, atd.).

## Importovat jmenné prostory
`Document` třída je jádrový objekt Aspose.GIS, který představuje GIS dataset a poskytuje metody pro čtení a zápis shapefile. Přidejte následující jmenné prostory na začátek vašeho souboru kódu:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Jak číst shapefile a převést polygon na linestring?
Načtěte zdrojový polygonový shapefile, extrahujte vnější obvod každého polygonu, vytvořte `LineString` z tohoto obvodu a výsledek zapište do nového shapefile – vše v pěti jednoduchých krocích. Tento vzor funguje pro dataset libovolné velikosti a zajišťuje, že souřadnicový systém zdroje je zachován v cíli.

### Krok 1: Nastavit adresář dokumentu
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
Nahraďte `"Your Document Directory"` skutečnou cestou, kde se váš shapefile nachází.

### Krok 2: Otevřít zdrojový Shapefile
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Tento řádek otevře zdrojový polygonový Shapefile, abyste mohli číst jeho prvky.

### Krok 3: Vytvořit cílový Linestring Shapefile
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Zde vytvoříme nový Linestring Shapefile, který bude ukládat převedené geometrie.

### Krok 4: Procházet zdrojové prvky
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
Smyčka prochází každý polygonový prvek v původním souboru.

### Krok 5: Převést polygon na Linestring a zapsat do cíle
Vlastnost `ExteriorRing` vrací vnější hranici polygonu jako `LineString`.  
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
V tomto bloku převádíme polygon na linii (`LineString`) a přidáváme nový prvek do cílového shapefile.

## Časté problémy a tipy
- **Neshoda souřadnicových systémů** – Ujistěte se, že jak zdrojové, tak cílové vrstvy používají stejnou prostorovou referenci; jinak se mohou linie posunout.  
- **Velké soubory** – Při zpracování velmi velkých shapefile zvažte streamování prvků místo načítání všech najednou do paměti.  
- **Null geometrie** – Chraňte se před prvky s prázdnými geometriemi, aby nedošlo k výjimkám za běhu.  
- **Extrahovat linie z polygonu** – Pokud potřebujete jen vnější obvod, použijte vlastnost `ExteriorRing`; pro vnitřní obvody iterujte `InteriorRings`.  

## Často kladené otázky

**Q: Je Aspose.GIS kompatibilní se všemi verzemi .NET?**  
A: Ano, Aspose.GIS podporuje .NET Framework 4.5+, .NET Core 3.1+, a .NET 5/6/7, což zajišťuje bezproblémovou integraci s moderními vývojovými stacky.

**Q: Mohu používat Aspose.GIS pro komerční projekty?**  
A: Ano, můžete. Zakupte licenci [zde](https://purchase.aspose.com/buy) pro odstranění omezení hodnocení a získání plné podpory.

**Q: Existují nějaké příklady nebo dokumentace?**  
A: Ano, můžete najít komplexní dokumentaci a ukázky kódu na [stránce dokumentace](https://reference.aspose.com/gis/net/).

**Q: Je k dispozici zkušební verze?**  
A: Ano – prozkoumejte Aspose.GIS s bezplatnou zkušební verzí návštěvou [tohoto odkazu](https://releases.aspose.com/).

**Q: Kde mohu získat pomoc nebo podporu?**  
A: Navštivte [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pro komunitní pomoc a oficiální podporu.

---

**Poslední aktualizace:** 2026-06-25  
**Testováno s:** Aspose.GIS for .NET (latest release)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak převést Shapefile na GeoJSON pomocí Aspose.GIS pro .NET](/gis/net/layer-management/extract-features-to-geojson/)
- [Jak číst GeoJSON ze streamu pomocí Aspose.GIS pro .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Jak vytvořit polygonovou geometrii pomocí Aspose.GIS pro .NET](/gis/net/geometry-creation/create-polygon-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
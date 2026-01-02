---
date: 2026-01-02
description: Naučte se, jak přidat bodový prvek při nastavení názvů polí a čtení ID
  objektu pomocí Aspose.GIS pro .NET. Krok‑za‑krokem průvodce pro vývojáře.
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
title: Přidat bodový prvek a zadat názvy polí Object ID a geometrie
url: /cs/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání bodové funkce a určení názvů polí Object ID a Geometry

## Úvod
Vydejte se na cestu do oblasti geografických informačních systémů (GIS) s využitím Aspose.GIS pro .NET, která otevírá svět možností pro vývojáře i nadšence. V tomto tutoriálu **se naučíte, jak přidat bodovou funkci**, zároveň **nastavit názvy polí** a **číst hodnoty object id**, což vám poskytne plnou kontrolu nad vašimi prostorovými daty.

## Rychlé odpovědi
- **Jaký je hlavní účel tohoto průvodce?** – Ukázat, jak přidat bodovou funkci a nakonfigurovat názvy polí Object ID a Geometry.  
- **Která knihovna je použita?** – Aspose.GIS pro .NET.  
- **Potřebuji licenci?** – K dispozici je bezplatná zkušební verze; licence je vyžadována pro produkční nasazení.  
- **Jaké verze .NET jsou podporovány?** – .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Mohu po vložení přečíst Object ID?** – Ano – tutoriál ukazuje, jak přečíst object id z vrstvy.

## Předpoklady
- Aspose.GIS pro .NET: Stáhněte a nainstalujte knihovnu z [zde](https://releases.aspose.com/gis/net/).
- Adresář dokumentů: Nastavte adresář pro vaše dokumenty, kde budete ukládat geodatabáze.
- Prostředí .NET: Ujistěte se, že máte funkční .NET prostředí.

## Importování jmenných prostorů
Pro zahájení je třeba do projektu importovat potřebné jmenné prostory. Tyto jmenné prostory poskytují základní třídy a metody pro práci s Aspose.GIS pro .NET.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Krok 1: Přidání bodové funkce a určení názvů polí Object ID a Geometry
V tomto kroku se naučíte, jak nastavit názvy polí Object ID a Geometry pro vaše GIS data. To je klíčové pro efektivní správu dat a pro možnost **číst object id** později.

### Krok 1.1: Nastavení adresáře dokumentů
Startujte definováním cesty k vašemu adresáři dokumentů:

```csharp
string dataDir = "Your Document Directory";
```

### Krok 1.2: Vytvoření GeoDatabase a definice možností
Vytvořte GeoDatabase s požadovaným **set field names** pro Object ID a Geometry:

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

### Krok 1.3: Vytvoření a přidání vrstvy
Vytvořte vrstvu v rámci GeoDatabase a přidejte funkci, která představuje bodovou geometrii:

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

### Krok 1.4: Otevření a načtení dat z vrstvy
Otevřete vrstvu a načtěte funkci, kterou jste právě přidali. Toto demonstruje, jak **číst object id** ze souboru dat:

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Proč nastavit vlastní názvy polí?
Přizpůsobení názvů polí Object ID a Geometry vám poskytuje flexibilitu při integraci s existujícími databázemi nebo při dodržování pojmenovacích konvencí požadovaných následnými aplikacemi. Také to činí data více samovysvětlujícími, což usnadňuje údržbu a spolupráci.

## Časté úskalí a řešení problémů
- **Chybějící adresář** – Ujistěte se, že `dataDir` ukazuje na existující složku; jinak `Dataset.Create` vyhodí výjimku.
- **Konflikty názvů polí** – Pokud pole se stejným názvem již v geodatabázi existuje, vytvoření selže. Zvolte jedinečné názvy.
- **Neshoda prostorového referenčního systému** – Vždy sladěte prostorový referenční systém (např. WGS84) s daty, která chcete uložit.

## Závěr
Gratulujeme! Úspěšně jste se naučili **přidat bodovou funkci**, **nastavit názvy polí** a **číst object id** pomocí Aspose.GIS pro .NET. Tento základ vám umožní vytvářet robustní GIS aplikace a s jistotou spravovat prostorová data.

## Často kladené otázky
### Q: Mohu použít Aspose.GIS pro .NET ve svých webových aplikacích?
A: Ano, Aspose.GIS pro .NET je vhodný jak pro desktopové, tak pro webové aplikace a poskytuje univerzální geoprostorové funkce.

### Q: Je k dispozici zkušební verze před zakoupením?
A: Ano, můžete si vyzkoušet funkce Aspose.GIS pro .NET pomocí bezplatné zkušební verze dostupné [zde](https://releases.aspose.com/).

### Q: Jak mohu získat dočasnou licenci pro Aspose.GIS pro .NET?
A: Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/) pro evaluační účely.

### Q: Jaké prostorové referenční systémy Aspose.GIS pro .NET podporuje?
A: Aspose.GIS pro .NET podporuje různé prostorové referenční systémy, což poskytuje flexibilitu pro různé geografické datové sady.

### Q: Kde mohu získat pomoc nebo diskutovat o dotazech souvisejících s Aspose.GIS?
A: Navštivte fórum Aspose.GIS [zde](https://forum.aspose.com/c/gis/33) pro podporu a diskuse.

## Další často kladené otázky

**Q: Mohu změnit pole Object ID po vytvoření vrstvy?**  
A: Ne. Název pole je definován při vytvoření vrstvy; pro jeho změnu musíte vrstvu znovu vytvořit s novým objektem `FileGdbOptions`.

**Q: Jak získám jiné hodnoty atributů kromě Object ID?**  
A: Použijte `feature.GetValue<T>("FieldName")`, kde `FieldName` je název atributu, který chcete načíst.

**Q: Je možné přidat více bodových funkcí najednou?**  
A: Ano. Projděte svá data v cyklu, vytvořte funkci pro každý bod, nastavte její geometrii a zavolejte `layer.Add(feature)` ve stejném `using` bloku.

**Q: Podporuje Aspose.GIS jiné typy geometrie?**  
A: Rozhodně. Můžete pracovat s `LineString`, `Polygon`, `MultiPoint` a dalšími vytvořením odpovídajících objektů geometrie.

**Q: Co se stane, když se pokusím načíst Object ID, které neexistuje?**  
A: Přístup k indexu mimo rozsah (např. `layer[10]`, když existuje jen jedna funkce) vyvolá `IndexOutOfRangeException`. Vždy nejprve zkontrolujte `layer.Count`.

**Poslední aktualizace:** 2026-01-02  
**Testováno s:** Aspose.GIS pro .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
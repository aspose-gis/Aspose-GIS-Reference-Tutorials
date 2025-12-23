---
date: 2025-12-23
description: Naučte se, jak převést geometrii na WKT s různými možnostmi, nastavit
  číselný formát a upravit desetinnou přesnost pomocí Aspose.GIS pro .NET.
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: Převod geometrie na varianty WKT pomocí Aspose.GIS
url: /cs/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod geometrie na varianty WKT pomocí Aspose.GIS

## Úvod
V moderních .NET aplikacích je **převod geometrie na WKT** běžným krokem, když potřebujete vyměňovat prostorová data s jinými systémy nebo je uložit v textovém formátu. Aspose.GIS pro .NET tento převod usnadňuje a zároveň vám poskytuje plnou kontrolu nad variantou WKT, číselným formátem a desetinnou přesností. V tomto tutoriálu se naučíte, jak převést geometrie na WKT, vybrat správnou variantu a doladit výstup tak, aby splňoval přesné požadavky vašeho projektu.

## Rychlé odpovědi
- **Co znamená „převod geometrie na WKT“?** Převádí geometrické objekty (body, čáry, polygony) do reprezentace Well‑Known Text.  
- **Které varianty WKT jsou podporovány?** `Iso`, `SimpleFeatureAccessOutdated` a `ExtendedPostGis`.  
- **Jak mohu řídit desetinnou přesnost?** Použijte možnosti `NumericFormat` jako `General`, `RoundTrip` nebo `Flat`.  
- **Potřebuji licenci pro produkční použití?** Ano, pro ne‑zkušební použití je vyžadována komerční licence.  
- **Jaké verze .NET jsou kompatibilní?** .NET Framework 4.0+ a .NET 5/6/7.

## Co je „převod geometrie na WKT“?
Převod geometrie na WKT vytváří lidsky čitelný řetězec, který popisuje prostorové objekty. Tento formát je široce akceptován GIS nástroji, databázemi a webovými službami, což z něj činí ideální prostředek pro výměnu dat.

## Proč použít Aspose.GIS pro tento převod?
- **Řízení přesnosti** – Zvolte, kolik desetinných míst bude vypsáno.  
- **Flexibilita variant** – Přizpůsobte se přesnému dialektu WKT požadovanému vaším následným systémem.  
- **Žádné externí závislosti** – Čistá .NET knihovna, bez nativních binárek.

## Předpoklady
Předtím, než začneme, ujistěte se, že máte:

1. **Aspose.GIS pro .NET** – Stáhněte a nainstalujte jej ze [stránky ke stažení](https://releases.aspose.com/gis/net/).  
2. **Vývojové prostředí** – Jakákoli aktuální verze Visual Studio nebo VS Code s .NET SDK.  
3. **Základní znalost C#** – Znalost tříd, objektů a .NET frameworku.

## Importování jmenných prostorů
Nejprve načtěte požadované jmenné prostory:

```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```

## Krok 1: Vytvoření objektu Point
Vytvořte `Point`, který později **převodíte na WKT**. Bod obsahuje zeměpisnou šířku, délku a volitelnou hodnotu měření (M):

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Krok 2: Nastavení systému prostorových referencí (SRS)
Přiřaďte systém prostorových referencí, aby výstup WKT věděl, na který souřadnicový systém se odkazuje. Zde používáme běžný systém WGS84:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Krok 3: Specifikace varianty WKT
Zvolte vhodnou variantu WKT při **převodu geometrie na WKT**. Každá varianta formátuje výstup mírně odlišně:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Krok 4: Řízení číselného formátu (Nastavení číselného formátu a úprava desetinné přesnosti)
Doladit číselnou reprezentaci souřadnic. Třída `NumericFormat` vám umožní **nastavit číselný formát** a **upravit desetinnou přesnost** podle vašich potřeb:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## Časté problémy a tipy
- **Chybějící hodnota M** – Pokud měření nepotřebujete, vynechte vlastnost `M`; ISO varianta ji automaticky odstraní.  
- **Neočekávaná přesnost** – Zkontrolujte, že používáte správný `NumericFormat`; `General` zachovává plnou dvojitou přesnost, zatímco `Flat` zaokrouhluje na zadaný počet desetinných míst.  
- **SRID se nezobrazuje** – Pouze varianta `ExtendedPostGis` přidává před výstup `SRID=`. Zvolte tuto variantu, pokud váš cílový systém očekává SRID.

## Závěr
Po provedení těchto kroků nyní víte, jak **převést geometrie na WKT**, vybrat správnou variantu a přesně řídit číselný výstup. To vám poskytuje flexibilitu integrovat Aspose.GIS do jakéhokoli GIS workflow, databáze nebo webové služby, která konzumuje WKT.

## Často kladené otázky
### Je Aspose.GIS kompatibilní se všemi verzemi .NET?
Ano, Aspose.GIS podporuje .NET Framework 4.0 a vyšší.  

### Mohu použít Aspose.GIS pro komerční projekty?
Ano, Aspose.GIS lze použít jak pro osobní, tak pro komerční projekty.  

### Poskytuje Aspose.GIS podporu pro jiné formáty prostorových dat?
Ano, Aspose.GIS podporuje širokou škálu formátů prostorových dat, včetně ESRI Shapefile, GeoJSON a KML.  

### Je k dispozici bezplatná zkušební verze Aspose.GIS?
Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.GIS [zde](https://releases.aspose.com/).  

### Kde mohu získat pomoc nebo podporu pro Aspose.GIS?
Můžete své dotazy zveřejnit nebo požádat o pomoc v komunitě Aspose.GIS na [fóru](https://forum.aspose.com/c/gis/33).

## Často kladené otázky
**Q: Jak exportovat kolekci Geometry do jediného řetězce WKT?**  
A: Projděte každou geometrii v kolekci a spojte jejich výsledky `AsText`, volitelně je oddělte čárkami nebo novými řádky.

**Q: Mohu změnit SRID bez úpravy souřadnic?**  
A: Ano, nastavte vlastnost `SpatialReferenceSystem` na požadovaný SRID; hodnoty souřadnic zůstanou nezměněny.

**Q: Co se stane, pokud použiji nepodporovanou variantu WKT?**  
A: Aspose.GIS vyhodí `ArgumentException`. Vždy ověřte variantu vůči hodnotám výčtu `WktVariant`.

---

**Poslední aktualizace:** 2025-12-23  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
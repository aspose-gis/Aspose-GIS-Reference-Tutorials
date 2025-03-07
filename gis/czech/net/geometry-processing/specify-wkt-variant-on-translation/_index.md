---
title: Určete variantu WKT při překladu pomocí Aspose.GIS
linktitle: Při překladu zadejte variantu WKT
second_title: Aspose.GIS .NET API
description: Naučte se, jak specifikovat varianty WKT v Aspose.GIS pro .NET, abyste mohli efektivně řídit formát a přesnost reprezentace prostorových dat.
weight: 19
url: /cs/net/geometry-processing/specify-wkt-variant-on-translation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Určete variantu WKT při překladu pomocí Aspose.GIS

## Úvod
Aspose.GIS for .NET je výkonná knihovna, která umožňuje vývojářům bez námahy pracovat s daty geografického informačního systému (GIS) v jejich aplikacích .NET. Jednou ze základních funkcí poskytovaných Aspose.GIS je schopnost specifikovat variantu dobře známého textu (WKT) během překladu, což uživatelům umožňuje řídit formát a přesnost reprezentací prostorových dat. V tomto tutoriálu prozkoumáme, jak specifikovat varianty WKT krok za krokem pomocí Aspose.GIS pro .NET.
## Předpoklady
Než začneme, ujistěte se, že máte splněny následující předpoklady:
1. Aspose.GIS pro .NET: Stáhněte a nainstalujte Aspose.GIS pro .NET z[stránka ke stažení](https://releases.aspose.com/gis/net/).
2. Vývojové prostředí: Ujistěte se, že máte nastavené vývojové prostředí .NET.
3. Základní znalosti: Znalost programovacího jazyka C# a .NET frameworku.

## Importovat jmenné prostory
Před použitím funkce Aspose.GIS ve svém kódu importujte potřebné jmenné prostory:
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
## Krok 1: Vytvořte bodový objekt
 Nejprve vytvořte a`Point` objekt s hodnotami zeměpisné šířky, zeměpisné délky a volitelných rozměrů (M):
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## Krok 2: Nastavení prostorového referenčního systému (SRS)
Bodovému objektu přiřaďte prostorový referenční systém (SRS). V tomto příkladu používáme prostorový referenční systém WGS84:
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## Krok 3: Zadejte variantu WKT
 Nyní zadejte variantu WKT pro překlad. Aspose.GIS podporuje různé varianty WKT, včetně`Iso`, `SimpleFeatureAccessOutdated` , a`ExtendedPostGis`. Vyberte si vhodnou variantu na základě vašich požadavků:
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // BOD M (23,5732, 25,3421, 40,3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // BOD (23,5732, 25,3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23,5732, 25,3421, 40,3)
```
## Krok 4: Kontrola číselného formátu
Můžete ovládat číselný formát souřadnic v reprezentaci WKT. Aspose.GIS poskytuje možnosti pro určení desetinné přesnosti:
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // BOD M (23,5732 25,342099999999999 40,299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // BOD M (23,5732 25,3421 40,3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // BOD M (23,6 25,3 40,3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // BOD M (23,573 25,342 40,3)
```

## Závěr
tomto tutoriálu jsme se naučili, jak specifikovat varianty WKT při překladu pomocí Aspose.GIS pro .NET. Dodržením výše uvedených kroků mohou vývojáři efektivně řídit formát a přesnost reprezentací prostorových dat ve svých aplikacích .NET, čímž se zvýší flexibilita a použitelnost geografických informačních systémů.
## FAQ
### Je Aspose.GIS kompatibilní se všemi verzemi .NET?
Ano, Aspose.GIS podporuje .NET Framework 4.0 a vyšší.
### Mohu použít Aspose.GIS pro komerční projekty?
Ano, Aspose.GIS lze použít pro osobní i komerční projekty.
### Poskytuje Aspose.GIS podporu pro jiné formáty prostorových dat?
Ano, Aspose.GIS podporuje širokou škálu formátů prostorových dat, včetně ESRI Shapefile, GeoJSON a KML.
### Je k dispozici bezplatná zkušební verze pro Aspose.GIS?
 Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.GIS z[tady](https://releases.aspose.com/).
### Kde mohu získat pomoc nebo podporu pro Aspose.GIS?
 Své dotazy můžete zveřejnit nebo požádat o pomoc komunitu Aspose.GIS na adrese[Fórum](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Zvládnutí překrytí geometrie pomocí Aspose.GIS pro .NET
linktitle: Najděte překrytí geometrie
second_title: Aspose.GIS .NET API
description: Naučte se provádět operace geometrického překrývání pomocí Aspose.GIS pro .NET. Operace hlavního průniku, sjednocení, rozdílu a symetrického rozdílu.
weight: 16
url: /cs/net/geometry-analysis/find-geometry-overlays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zvládnutí překrytí geometrie pomocí Aspose.GIS pro .NET

## Úvod
oblasti geografických informačních systémů (GIS) jsou operace překrytí zásadní pro prostorovou analýzu. Umožňují porovnávání a kombinování různých souborů prostorových dat za účelem získání cenných poznatků. Aspose.GIS for .NET poskytuje robustní funkce pro efektivní provádění geometrických překryvů. V tomto tutoriálu se ponoříme do různých překryvných operací, jako je Intersection, Union, Difference a Symmetric Difference pomocí Aspose.GIS pro .NET.
## Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:
### 1. Vývojové prostředí .NET
Ujistěte se, že máte na svém počítači nastavené vývojové prostředí .NET. .NET SDK si můžete stáhnout a nainstalovat z webu .NET.
### 2. Aspose.GIS pro knihovnu .NET
 Stáhněte a nainstalujte knihovnu Aspose.GIS for .NET z[webová stránka](https://releases.aspose.com/gis/net/).
## Importovat jmenné prostory
Než budete moci začít používat Aspose.GIS pro .NET, musíte do svého projektu importovat potřebné jmenné prostory.
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Vytvořte polygonové objekty
Nejprve definujeme dva polygonové objekty reprezentující prostorové oblasti.
```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```
## Krok 2: Proveďte operaci křižovatky
Dále najdeme průsečík dvou polygonů.
```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Polygon
```
## Krok 3: Tisk průsečíků
Vytiskneme body polygonu průsečíku.
```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```
## Krok 4: Proveďte Union Operation
Nyní najdeme spojení dvou polygonů.
```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Polygon
```
## Krok 5: Vytiskněte unijní body
Vytiskněte body sjednocovacího mnohoúhelníku.
```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```
## Krok 6: Proveďte rozdílovou operaci
Dále najdeme rozdíl mezi těmito dvěma polygony.
```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Polygon
```
## Krok 7: Vytiskněte rozdílové body
Vytiskněte body rozdílového mnohoúhelníku.
```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```
## Krok 8: Proveďte operaci symetrického rozdílu
Nakonec najdeme symetrický rozdíl mezi těmito dvěma polygony.
```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // Multipolygon
```
## Krok 9: Tisk symetrických rozdílových polygonů
Vytiskněte body každého mnohoúhelníku v symetrickém rozdílu.
```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```
## Závěr
Zvládnutí překryvů geometrie je v prostorové analýze zásadní a Aspose.GIS pro .NET poskytuje komplexní sadu nástrojů pro efektivní provádění těchto operací. Podle tohoto tutoriálu jste se naučili, jak používat Aspose.GIS pro .NET k provádění operací průniku, sjednocení, rozdílu a symetrického rozdílu na geometrických tvarech.
## FAQ
### Otázka: Mohu použít Aspose.GIS pro .NET ve svých komerčních projektech?
Ano, Aspose.GIS for .NET lze použít v komerčních i nekomerčních projektech.
### Otázka: Je k dispozici zkušební verze pro Aspose.GIS pro .NET?
 Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).
### Otázka: Jak mohu získat podporu pro Aspose.GIS pro .NET?
 Podporu můžete získat na fóru komunity Aspose.GIS[tady](https://forum.aspose.com/c/gis/33).
### Otázka: Jsou k dispozici nějaké dočasné licence pro Aspose.GIS pro .NET?
 Ano, dočasné licence jsou k dispozici pro účely testování a hodnocení. Můžete je získat z[tady](https://purchase.aspose.com/temporary-license/).
### Otázka: Mohu koupit Aspose.GIS pro .NET přímo?
 Ano, Aspose.GIS pro .NET si můžete zakoupit z webu[tady](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

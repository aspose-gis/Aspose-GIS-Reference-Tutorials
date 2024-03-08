---
title: Počítání geometrií v geometrii s Aspose.GIS
linktitle: Počítání geometrií v geometrii
second_title: Aspose.GIS .NET API
description: Naučte se počítat geometrie v geometrii pomocí Aspose.GIS pro .NET. Výukový program krok za krokem s příklady kódu pro vývojáře.
type: docs
weight: 23
url: /cs/net/geometry-creation/count-geometries-in-geometry/
---
## Úvod
Aspose.GIS for .NET je výkonný nástroj pro vývojáře, kteří chtějí začlenit geoprostorové funkce do svých aplikací .NET. Ať už vytváříte mapový software, služby založené na poloze nebo nástroje pro prostorovou analýzu, Aspose.GIS poskytuje komplexní sadu funkcí, které splní vaše potřeby. V tomto tutoriálu prozkoumáme, jak počítat geometrie v geometrii pomocí Aspose.GIS pro .NET.
## Předpoklady
Než se pustíte do tohoto tutoriálu, ujistěte se, že máte následující předpoklady:
1. Visual Studio: Ujistěte se, že máte v systému nainstalované Visual Studio.
2. Aspose.GIS pro .NET: Stáhněte a nainstalujte Aspose.GIS pro .NET z[stránka ke stažení](https://releases.aspose.com/gis/net/).
3. Základní znalost C#: Seznamte se se základy programovacího jazyka C#.

## Importovat jmenné prostory
Než začnete kódovat, musíte importovat potřebné jmenné prostory pro přístup k funkcím Aspose.GIS.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 2: Vytvořte geometrii bodů
```csharp
Point point = new Point(40.7128, -74.006);
```
 Zde vytvoříme a`Point` geometrie se zeměpisnou šířkou 40,7128 a délkou -74,006.
## Krok 3: Vytvořte geometrii LineString
```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```
 Tento krok vytvoří a`LineString` geometrii a přidá k ní dva body.
## Krok 4: Vytvořte kolekci geometrie
```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```
 Poté vytvoříme a`GeometryCollection` a přidejte k němu dříve vytvořené geometrie bodů a čar.
## Krok 5: Počítejte geometrie
```csharp
int geometriesCount = geometryCollection.Count;
```
 Tento krok počítá počet geometrií v rámci`GeometryCollection`.
## Krok 6: Zobrazte počet
```csharp
Console.WriteLine(geometriesCount); // 2
```
 Nakonec vytiskneme počet geometrií, což v tomto případě je`2`.

## Závěr
tomto tutoriálu jsme se naučili, jak počítat geometrie v geometrii pomocí Aspose.GIS pro .NET. Pomocí těchto kroků můžete snadno začlenit geoprostorové funkce do svých aplikací .NET.
## FAQ
### Je Aspose.GIS for .NET vhodný pro desktopové i webové aplikace?
Ano, Aspose.GIS for .NET lze bezproblémově používat v desktopových i webových aplikacích.
### Mohu provádět prostorové dotazy pomocí Aspose.GIS pro .NET?
Aspose.GIS pro .NET samozřejmě poskytuje robustní podporu pro provádění prostorových dotazů na geometrie.
### Podporuje Aspose.GIS for .NET různé formáty souborů GIS?
Ano, Aspose.GIS for .NET podporuje širokou škálu formátů souborů GIS včetně SHP, KML a GeoJSON.
### Je k dispozici bezplatná zkušební verze pro Aspose.GIS pro .NET?
 Ano, můžete si stáhnout bezplatnou zkušební verzi z[webová stránka](https://releases.aspose.com/).
### Kde najdu podporu pro Aspose.GIS pro .NET?
 Podporu najdete na[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33).
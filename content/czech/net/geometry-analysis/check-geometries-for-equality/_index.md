---
title: Zkontrolujte geometrie pro rovnost
linktitle: Zkontrolujte geometrie pro rovnost
second_title: Aspose.GIS .NET API
description: Naučte se, jak používat Aspose.GIS pro .NET ke kontrole rovnosti geometrií ve vašich aplikacích .NET pomocí tohoto komplexního kurzu.
type: docs
weight: 10
url: /cs/net/geometry-analysis/check-geometries-for-equality/
---
## Úvod
Aspose.GIS for .NET je výkonná knihovna, která umožňuje vývojářům efektivně pracovat s geoprostorovými daty v jejich aplikacích .NET. Ať už vytváříte mapové aplikace, nástroje pro prostorovou analýzu nebo integrujete geoprostorové funkce do stávajícího softwaru, Aspose.GIS poskytuje nástroje, které potřebujete k dokončení své práce.
## Předpoklady
Než se pustíte do používání Aspose.GIS pro .NET, ujistěte se, že máte splněny následující předpoklady:
### .NET Framework nainstalováno
Ujistěte se, že máte v systému nainstalované rozhraní .NET Framework. Můžete si jej stáhnout z webu společnosti Microsoft.
### Aspose.GIS pro knihovnu .NET
 Stáhněte a nainstalujte knihovnu Aspose.GIS for .NET z[stránka ke stažení](https://releases.aspose.com/gis/net/). Postupujte podle pokynů k instalaci uvedených v dokumentaci.
### Vývojové prostředí
Nastavte své preferované vývojové prostředí, jako je Visual Studio, pro vývoj .NET.

## Importovat jmenné prostory
Do své aplikace .NET importujte potřebné obory názvů, abyste mohli používat funkci Aspose.GIS:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Definujte geometrie
Nejprve definujte geometrie, které chcete porovnat. V tomto příkladu máme dvě geometrie:`geometry1` a`geometry2`.
```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```
## Krok 2: Zkontrolujte rovnost geometrií
 Nyní zkontrolujte, zda jsou geometrie prostorově stejné pomocí`SpatiallyEquals` metoda poskytovaná Aspose.GIS.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // Skutečný
```
 Toto se vytiskne`True` do konzole od té doby`geometry1` a`geometry2` jsou prostorově stejné.
## Krok 3: Upravte geometrii
 Dále upravíme`geometry2` přidáním nového bodu.
```csharp
geometry2.AddPoint(3, 3);
```
## Krok 4: Znovu zkontrolujte rovnost
Nyní znovu zkontrolujte rovnost geometrií po úpravě.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // Nepravdivé
```
 Tentokrát bude výstup`False` protože geometrie již nejsou prostorově stejné kvůli provedené úpravě`geometry2`.

## Závěr
Závěrem lze říci, že Aspose.GIS for .NET poskytuje výkonné nástroje pro práci s geoprostorovými daty v aplikacích .NET. Podle tohoto podrobného průvodce můžete snadno zkontrolovat rovnost geometrií pomocí metod Aspose.GIS.
## FAQ
### Mohu použít Aspose.GIS pro .NET s jinými frameworky .NET?
Ano, Aspose.GIS for .NET je kompatibilní s různými .NET frameworky, včetně .NET Core a .NET Standard.
### Je k dispozici bezplatná zkušební verze pro Aspose.GIS pro .NET?
 Ano, můžete si stáhnout bezplatnou zkušební verzi z[stránka vydání](https://releases.aspose.com/).
### Kde najdu dokumentaci k Aspose.GIS pro .NET?
 Podrobnou dokumentaci najdete na[Dokumentační stránka Aspose.GIS](https://reference.aspose.com/gis/net/).
### Jak mohu získat podporu pro Aspose.GIS pro .NET?
 Podporu můžete získat na fóru komunity Aspose.GIS[tady](https://forum.aspose.com/c/gis/33).
### Mohu si zakoupit dočasnou licenci pro Aspose.GIS pro .NET?
 Ano, můžete si zakoupit dočasnou licenci od[nákupní stránku](https://purchase.aspose.com/temporary-license/).
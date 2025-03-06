---
title: Zkontrolujte dotykové geometrie
linktitle: Zkontrolujte dotykové geometrie
second_title: Aspose.GIS .NET API
description: Odemkněte výkon práce s prostorovými daty s Aspose.GIS pro .NET. Bezproblémově integrujte prostorové funkce do svých aplikací s touto všestrannou sadou nástrojů.
weight: 13
url: /cs/net/geometry-analysis/check-geometries-touching/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zkontrolujte dotykové geometrie

## Úvod
V oblasti geografických informačních systémů (GIS) vyniká Aspose.GIS for .NET jako výkonný nástroj pro vývojáře, kteří chtějí bezproblémově začlenit prostorové funkce do svých aplikací. Díky svým robustním funkcím a uživatelsky přívětivému rozhraní umožňuje Aspose.GIS vývojářům pracovat s prostorovými daty bez námahy, ať už jde o analýzu, vizualizaci nebo manipulaci s geometriemi.
## Předpoklady
Než se ponoříte do složitosti Aspose.GIS pro .NET, musíte splnit několik předpokladů:
### Nastavení vašeho prostředí
1. Nainstalujte Visual Studio: Ujistěte se, že máte v systému nainstalované Visual Studio. Můžete si jej stáhnout z webu.
   
2.  Stáhnout Aspose.GIS pro .NET: Přejděte na[odkaz ke stažení](https://releases.aspose.com/gis/net/) získejte nejnovější verzi Aspose.GIS pro .NET.
3.  Získejte licenci: Abyste mohli využít plný potenciál Aspose.GIS, potřebujete platnou licenci. Můžete si jej buď zakoupit, nebo se rozhodnout pro bezplatnou zkušební verzi[tady](https://releases.aspose.com/).

## Importovat jmenné prostory
Chcete-li začít využívat sílu Aspose.GIS pro .NET, musíte do svého projektu importovat potřebné jmenné prostory. Můžete to udělat takto:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Nyní, když jste nastavili své prostředí a importovali požadované jmenné prostory, pojďme se ponořit do praktického příkladu kontroly geometrií dotýkajících se pomocí Aspose.GIS pro .NET.
## Krok 1: Vytvořte geometrie
```csharp
var geometry1 = new LineString();
geometry1.AddPoint(0, 0);
geometry1.AddPoint(2, 2);
var geometry2 = new LineString();
geometry2.AddPoint(2, 2);
geometry2.AddPoint(3, 3);
var geometry3 = new Point(2, 2);
var geometry4 = new LineString();
geometry4.AddPoint(1, 1);
geometry4.AddPoint(4, 4);
```
## Krok 2: Zkontrolujte Dotyk
```csharp
Console.WriteLine(geometry1.Touches(geometry2)); // Skutečný
Console.WriteLine(geometry2.Touches(geometry1)); // Skutečný
Console.WriteLine(geometry1.Touches(geometry3)); // Skutečný
Console.WriteLine(geometry1.Touches(geometry4)); // Nepravdivé
```

## Závěr
Závěrem, Aspose.GIS for .NET je všestranná sada nástrojů, která zjednodušuje práci s prostorovými daty a analýzu pro vývojáře .NET. Podle tohoto výukového programu můžete bezproblémově integrovat prostorové funkce do svých aplikací a vylepšit tak jejich možnosti a uživatelskou zkušenost.
## FAQ
### Je Aspose.GIS kompatibilní se všemi .NET frameworky?
Aspose.GIS podporuje různé .NET frameworky, včetně .NET Framework, .NET Core a .NET Standard, což zajišťuje kompatibilitu v celé řadě vývojových prostředí.
### Mohu si Aspose.GIS vyzkoušet před zakoupením licence?
 Ano, můžete využít bezplatnou zkušební verzi z webu Aspose[tady](https://purchase.aspose.com/temporary-license/) prozkoumat jeho vlastnosti a funkce před rozhodnutím o koupi.
### Kde najdu podporu pro dotazy související s Aspose.GIS?
 Můžete navštívit[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) požádat o pomoc komunitu nebo vznést jakékoli dotazy, které byste mohli mít.
### Jak často jsou vydávány aktualizace pro Aspose.GIS?
Aspose.GIS pravidelně dostává aktualizace a vylepšení, aby byla zajištěna kompatibilita s nejnovějšími technologiemi a vyřešeny všechny hlášené problémy.
### Mohu získat dočasnou licenci pro Aspose.GIS?
 Ano, můžete získat dočasnou licenci od[tady](https://purchase.aspose.com/temporary-license/) k vyhodnocení schopností Aspose.GIS ve vašem vývojovém prostředí.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Převod souřadnic pomocí Aspose.GIS
linktitle: Převést souřadnice
second_title: Aspose.GIS .NET API
description: Naučte se převádět souřadnice pomocí Aspose.GIS pro .NET. K dispozici je podrobný průvodce, předpoklady a často kladené otázky.
type: docs
weight: 25
url: /cs/net/geometry-creation/convert-coordinates/
---
## Úvod
V tomto tutoriálu se ponoříme do světa geografických informačních systémů (GIS) pomocí výkonné knihovny Aspose.GIS pro .NET. Aspose.GIS je komplexní sada nástrojů, která umožňuje vývojářům pracovat s prostorovými daty bez námahy. Ať už jste zkušený vývojář nebo teprve začínáte, tento tutoriál vás provede procesem využití Aspose.GIS k efektivnímu převodu souřadnic.
## Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:
1. Základní znalost C#: Pro pochopení a implementaci uvedených příkladů kódu je nezbytná znalost programovacího jazyka C#.
  
2.  Instalace Aspose.GIS: Ujistěte se, že jste si stáhli a nainstalovali knihovnu Aspose.GIS pro .NET. Můžete si jej stáhnout z[Web Aspose.GIS](https://releases.aspose.com/gis/net/).

## Importovat jmenné prostory
Než začneme, importujme potřebné jmenné prostory pro přístup k funkcím Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

Pojďme si uvedený příklad rozdělit do několika kroků, abychom lépe porozuměli:
## Krok 1: Spusťte proces převodu
```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```
Tento řádek jednoduše zobrazí zprávu indikující začátek procesu převodu souřadnic.
## Krok 2: Převeďte na desetinné stupně
```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```
 Zde převedeme souřadnice (25,5, 45,5) na desetinný formát stupňů pomocí`AsPointText` metoda s`PointFormats.DecimalDegrees` parametr. Výsledek je poté vytištěn na konzole.
## Krok 3: Převod na stupně desetinných minut
```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```
Tento krok převede souřadnice na formát stupně desetinných minut a vytiskne výsledek.
## Krok 4: Převeďte na stupně Minuty sekund
```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```
Podobně převedeme souřadnice na formát stupně minut a sekund a zobrazíme výstup.
## Krok 5: Převeďte na GeoRef
```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```
Nakonec souřadnice převedeme do formátu GeoRef a výsledek vytiskneme.

## Závěr
tomto tutoriálu jsme prozkoumali proces převodu souřadnic pomocí Aspose.GIS pro .NET. Dodržováním tohoto podrobného průvodce a používáním knihovny Aspose.GIS můžete efektivně manipulovat s prostorovými daty ve svých aplikacích .NET.
## FAQ
### Je Aspose.GIS kompatibilní s jinými programovacími jazyky?
Aspose.GIS se primárně zaměřuje na vývojáře .NET, ale nabízí interoperabilitu s Javou prostřednictvím Aspose.GIS for Java.
### Mohu vyzkoušet Aspose.GIS před nákupem?
 Ano, máte přístup k bezplatné zkušební verzi Aspose.GIS z[webová stránka](https://releases.aspose.com/).
### Jak mohu získat podporu pro Aspose.GIS?
 Pomoc můžete vyhledat na fóru komunity Aspose.GIS[tady](https://forum.aspose.com/c/gis/33).
### Jsou pro Aspose.GIS dostupné dočasné licence?
 Ano, dočasné licence lze získat z[dočasná licenční stránka](https://purchase.aspose.com/temporary-license/).
### Kde mohu zakoupit Aspose.GIS?
 Aspose.GIS můžete zakoupit od[nákupní stránku](https://purchase.aspose.com/buy).
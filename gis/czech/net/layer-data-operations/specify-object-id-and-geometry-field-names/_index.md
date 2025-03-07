---
title: Zadejte ID objektu a názvy geometrických polí
linktitle: Zadejte ID objektu a názvy geometrických polí
second_title: Aspose.GIS .NET API
description: Prozkoumejte kouzlo GIS s Aspose.GIS pro .NET! Spravujte geoprostorová data bez námahy. Stáhněte si nyní a uvolněte sílu prostorové inteligence.
weight: 20
url: /cs/net/layer-data-operations/specify-object-id-and-geometry-field-names/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zadejte ID objektu a názvy geometrických polí

## Úvod
Vydání se na cestu do říše geografických informačních systémů (GIS) pomocí Aspose.GIS for .NET otevírá svět možností pro vývojáře i nadšence. Tato výkonná knihovna vám umožňuje bez námahy zpracovávat geoprostorová data. V tomto tutoriálu vás provedeme procesem zadávání názvů polí ID objektu a geometrie, čímž položíme základ pro vaše úsilí v oblasti GIS.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
-  Aspose.GIS pro .NET: Stáhněte a nainstalujte knihovnu z[tady](https://releases.aspose.com/gis/net/).
- Adresář dokumentů: Nastavte adresář pro vaše dokumenty pro ukládání geodatabází.
- Prostředí .NET: Ujistěte se, že máte funkční prostředí .NET.
## Importovat jmenné prostory
Chcete-li to nastartovat, musíte do projektu importovat potřebné jmenné prostory. Tyto jmenné prostory poskytují základní třídy a metody pro interakci s Aspose.GIS pro .NET.
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```
## Krok 1: Zadejte ID objektu a názvy geometrických polí
V tomto kroku se naučíte, jak nastavit ID objektu a názvy polí Geometry pro vaše data GIS. To je zásadní pro efektivní správu dat.
## Krok 1.1: Nastavte adresář dokumentů
Začněte definováním cesty k adresáři dokumentů:
```csharp
string dataDir = "Your Document Directory";
```
## Krok 1.2: Vytvořte geodatabázi a definujte možnosti
Vytvořte geodatabázi se zadaným ID objektu a názvy polí geometrie:
```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Zadejte název pole ID objektu
        GeometryFieldName = "POINT",       // Zadejte název pole Geometry
    };
```
## Krok 1.3: Vytvořte a přidejte vrstvu
Vytvořte vrstvu v GeoDatabázi a přidejte prvek s konkrétní geometrií:
```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  //Určete geometrii (v tomto případě bod)
    layer.Add(feature);
}
```
## Krok 1.4: Otevřete a načtěte data z vrstvy
Otevřete vrstvu a načtěte z ní data na základě zadaného ID objektu:
```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Výstup: 1
}
```
## Závěr
Gratulujeme! Úspěšně jste prošli procesem zadávání názvů objektů ID a geometrie pomocí Aspose.GIS for .NET. To pokládá pevný základ pro vaše projekty GIS a umožňuje vám snadno spravovat geoprostorová data.
## Často kladené otázky
### Otázka: Mohu použít Aspose.GIS pro .NET ve svých webových aplikacích?
Odpověď: Ano, Aspose.GIS for .NET je vhodný pro desktopové i webové aplikace a poskytuje všestranné geoprostorové možnosti.
### Otázka: Je před zakoupením k dispozici zkušební verze?
 Odpověď: Ano, můžete prozkoumat funkce Aspose.GIS pro .NET pomocí bezplatné zkušební verze[tady](https://releases.aspose.com/).
### Otázka: Jak mohu získat dočasnou licenci pro Aspose.GIS pro .NET?
 Odpověď: Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/) pro účely hodnocení.
### Otázka: Jaké prostorové referenční systémy Aspose.GIS pro .NET podporuje?
Odpověď: Aspose.GIS for .NET podporuje různé prostorové referenční systémy a poskytuje flexibilitu pro různé geografické datové sady.
### Otázka: Kde mohu vyhledat pomoc nebo prodiskutovat dotazy týkající se Aspose.GIS?
 Odpověď: Navštivte fórum Aspose.GIS[tady](https://forum.aspose.com/c/gis/33) za podporu a diskuze.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Vytvořte nový soubor GDB Dataset
linktitle: Vytvořte nový soubor GDB Dataset
second_title: Aspose.GIS .NET API
description: Prozkoumejte Aspose.GIS for .NET, abyste mohli snadno vytvářet a spravovat datové sady GIS. Stáhněte si nyní pro bezproblémový geoprostorový rozvoj. #State #GIS
type: docs
weight: 10
url: /cs/net/layer-management/create-new-file-gdb-dataset/
---
## Úvod
oblasti geoprostorového vývoje vyniká Aspose.GIS for .NET jako výkonná sada nástrojů pro správu a manipulaci s daty geografického informačního systému (GIS). Ať už jste zkušený vývojář nebo teprve začínáte svou cestu do GIS, tento tutoriál vás provede procesem vytváření nové datové sady File Geodatabase (GDB) pomocí Aspose.GIS for .NET.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
-  Aspose.GIS for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.GIS for .NET. Můžete si jej stáhnout z[Stránka pro stahování Aspose.GIS pro .NET](https://releases.aspose.com/gis/net/).
- Vývojové prostředí: Nastavte si vývojové prostředí s kompatibilním IDE, jako je Visual Studio, a mějte základní znalosti o programování .NET.
- Adresář dokumentů: Nahraďte "Your Document Directory" ve fragmentu kódu příslušnou cestou, kam chcete uložit svou datovou sadu GDB.
- Znalost C#: Tento tutoriál předpokládá, že znáte programovací jazyk C#.
## Importovat jmenné prostory
úvodních krocích naimportujte potřebné jmenné prostory, abyste mohli využít funkce Aspose.GIS ve vaší aplikaci .NET:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Krok 1: Vytvořte nový soubor GDB Dataset
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Výstup: 0
    // Pokračujte následujícími kroky...
}
```
 Vysvětlení: V tomto kroku vytvoříme novou datovou sadu GDB pomocí`Dataset.Create` metoda. Určíme cestu a ovladač (FileGdb) pro vytvoření Geodatabáze souborů. Výstup konzoly zobrazuje počáteční počet vrstev, který je v tomto okamžiku nulový.
## Krok 2: Vytvořte a naplňte vrstvu_1
```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```
Vysvětlení: Tento krok zahrnuje vytvoření vrstvy s názvem "vrstva_1" v rámci datové sady. Definuje atribut s názvem „hodnota“ celočíselného typu a naplní vrstvu deseti prvky, z nichž každý má bodovou geometrii.
## Krok 3: Vytvořte a vyplňte vrstvu_2
```csharp
using (var layer = dataset.CreateLayer("layer_2"))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Vysvětlení: Zde vytvoříme druhou vrstvu s názvem "vrstva_2" a přidáme jeden prvek s geometrií čárového řetězce.
## Krok 4: Zkontrolujte počet aktualizovaných vrstev
```csharp
Console.WriteLine(dataset.LayersCount); // Výstup: 2
```
Vysvětlení: Nakonec zkontrolujeme počet aktualizovaných vrstev po přidání dvou vrstev. V tomto případě by měl být výstup 2.
## Závěr
Gratulujeme! Úspěšně jste vytvořili novou datovou sadu File GDB a naplnili ji vrstvami pomocí Aspose.GIS pro .NET. Tento kurz poskytuje základní pochopení práce s geoprostorovými daty v prostředí .NET.
## Často kladené otázky
### Otázka: Mohu používat Aspose.GIS pro .NET s jinými knihovnami GIS?
Aspose.GIS for .NET je samostatná sada nástrojů; můžete jej však integrovat s jinými knihovnami .NET a rozšířit tak funkčnost.
### Otázka: Existuje komunitní fórum pro podporu Aspose.GIS?
 Ano, podporu a diskuze najdete na[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33).
### Otázka: Jak mohu získat dočasnou licenci pro Aspose.GIS?
 Navštivte[Dočasná licence](https://purchase.aspose.com/temporary-license/) stránku s informacemi o získání dočasné licence.
### Otázka: Jsou k dispozici další příklady a dokumentace?
 Prozkoumat[Dokumentace Aspose.GIS](https://reference.aspose.com/gis/net/) pro další příklady a podrobné informace.
### Otázka: Kde mohu zakoupit Aspose.GIS pro .NET?
 Aspose.GIS pro .NET můžete zakoupit na[nákupní stránku](https://purchase.aspose.com/buy).
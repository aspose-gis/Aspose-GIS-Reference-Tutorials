---
title: Vytvořte soubor GDB s jednou vrstvou
linktitle: Vytvořte soubor GDB s jednou vrstvou
second_title: Aspose.GIS .NET API
description: Odemkněte potenciál správy geoprostorových dat v .NET s Aspose.GIS. Naučte se krok za krokem vytvářet souborové geodatabáze a vrstvy. Stáhnout teď!
type: docs
weight: 11
url: /cs/net/layer-management/create-file-gdb-with-single-layer/
---
## Úvod
Jste připraveni pozvednout své geoprostorové aplikace pomocí robustních souborových geodatabází a vrstev? Nehledejte nic jiného než Aspose.GIS pro .NET. V tomto tutoriálu vás provedeme procesem vytváření geodatabáze souborů (GDB) s jednou vrstvou pomocí Aspose.GIS pro .NET. Využijte možnosti správy a vizualizace prostorových dat ve svých aplikacích .NET bez námahy.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
1.  Aspose.GIS pro .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.GIS. Můžete si jej stáhnout z[Stránka pro stahování Aspose.GIS pro .NET](https://releases.aspose.com/gis/net/).
2. Vývojové prostředí: Nastavte na svém počítači funkční vývojové prostředí .NET.
3. Adresář dokumentů: Vyberte nebo vytvořte adresář ve vašem systému, kam budete ukládat soubory geoprostorových dat.
## Importovat jmenné prostory
Chcete-li začít, musíte do svého projektu .NET importovat potřebné jmenné prostory. Tyto jmenné prostory budou poskytovat přístup k funkcím Aspose.GIS. Na začátek souboru kódu přidejte následující řádky:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```
## Krok 1: Nastavte adresář dokumentů
```csharp
string dataDir = "Your Document Directory";
```
Nahraďte "Your Document Directory" cestou k adresáři, kam chcete uložit soubory geoprostorových dat.
## Krok 2: Vytvořte souborovou geodatabázi s jednou vrstvou
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
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
Tento fragment kódu vytvoří souborovou geodatabázi s jednou vrstvou a přidá do ní rys čáry.
## Krok 3: Otevřete Geodatabázi souborů a načtěte informace o vrstvě
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Výstup: Počet funkcí: 1
}
```
V tomto kroku otevřeme vytvořenou Geodatabázi souborů, načteme vrstvu s názvem „vrstva“ a vytiskneme počet prvků ve vrstvě.
## Závěr
Gratulujeme! Úspěšně jste vytvořili souborovou geodatabázi s jednou vrstvou pomocí Aspose.GIS pro .NET. Snadno prozkoumejte rozsáhlé možnosti správy prostorových dat ve svých aplikacích.
## Často kladené otázky
### Mohu použít Aspose.GIS pro .NET ve svých stávajících projektech .NET?
Ano, Aspose.GIS for .NET lze bez problémů integrovat do vašich stávajících projektů .NET.
### Je k dispozici zkušební verze pro Aspose.GIS pro .NET?
 Ano, funkce Aspose.GIS pro .NET můžete prozkoumat stažením souboru[zkušební verze zdarma](https://releases.aspose.com/).
### Kde najdu podrobnou dokumentaci k Aspose.GIS pro .NET?
 Odkazovat na[dokumentace](https://reference.aspose.com/gis/net/) pro komplexní informace o Aspose.GIS pro .NET.
### Jak mohu získat podporu pro Aspose.GIS pro .NET?
 Navštivte[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) za podporu a pomoc komunity.
### Jsou k dispozici dočasné licence pro Aspose.GIS pro .NET?
 Ano, můžete získat a[dočasná licence](https://purchase.aspose.com/temporary-license/) pro Aspose.GIS pro .NET.
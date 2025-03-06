---
title: Konverze GeoJSON na soubor GDB demystifikována
linktitle: Převeďte vrstvu GeoJSON na soubor GDB
second_title: Aspose.GIS .NET API
description: Odemkněte geoprostorové zázraky s Aspose.GIS pro .NET! Bez námahy převádějte vrstvy GeoJSON do souborových geodatabází. Vyzkoušej to teď! #State #GIS
weight: 17
url: /cs/net/layer-management/convert-geojson-layer-to-file-gdb/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konverze GeoJSON na soubor GDB demystifikována

## Úvod
V dynamické oblasti geografických informačních systémů (GIS) je schopnost plynule převádět data mezi různými formáty klíčová. Aspose.GIS for .NET se ukazuje jako mocný spojenec, který nabízí komplexní sadu nástrojů pro snadnou manipulaci s geoprostorovými daty. V tomto tutoriálu se ponoříme do procesu převodu vrstvy GeoJSON na souborovou geodatabázi (File GDB) pomocí Aspose.GIS pro .NET.
## Předpoklady
Než se vydáte na tuto geoprostorovou cestu, ujistěte se, že máte splněny následující předpoklady:
- Pracovní znalost programování .NET.
-  Aspose.GIS pro .NET nainstalován. Pokud ne, stáhněte si jej z[tady](https://releases.aspose.com/gis/net/) a postupujte podle pokynů k instalaci.
## Importovat jmenné prostory
Chcete-li zahájit proces převodu, začněte importem potřebných jmenných prostorů:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Nyní si tento proces rozebereme do průvodce krok za krokem:
## Krok 1: Nastavte vrstvu GeoJSON
Začněte vytvořením vrstvy GeoJSON s relevantními atributy a funkcemi. Zde je úryvek, který vás provede:
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Přidejte atributy
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //Vytvářejte a přidávejte funkce
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```
## Krok 2: Zkopírujte testovací datovou sadu
Chcete-li zachovat integritu testovacích dat, vytvořte kopii datové sady. Použijte následující fragment kódu:
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## Krok 3: Převeďte GeoJSON na soubor GDB
Nyní je čas provést konverzi. Použijte následující kód:
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Zkopírujte atributy
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Přidejte funkce
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## Závěr
V tomto tutoriálu jsme prošli zajímavým terénem převodu vrstvy GeoJSON na geodatabázi souborů pomocí Aspose.GIS pro .NET. Vyzbrojeni těmito znalostmi jste nyní vybaveni k bezproblémové manipulaci s geoprostorovými daty ve vašich aplikacích .NET.
## Nejčastější dotazy
### Je Aspose.GIS kompatibilní s nejnovějším rámcem .NET?
Ano, Aspose.GIS je kompatibilní s nejnovějšími verzemi .NET frameworku.
### Mohu pomocí Aspose.GIS převést jiné geoprostorové formáty?
Absolutně! Aspose.GIS podporuje širokou škálu geoprostorových formátů pro všestrannou manipulaci s daty.
### Je k dispozici zkušební verze pro Aspose.GIS?
 Ano, funkce Aspose.GIS můžete prozkoumat stažením zkušební verze[tady](https://releases.aspose.com/).
### Jak mohu získat podporu pro dotazy související s Aspose.GIS?
 Přejděte na Aspose.GIS[Fórum](https://forum.aspose.com/c/gis/33) za specializovanou podporu.
### Mohu získat dočasnou licenci pro Aspose.GIS?
 Ano, můžete si zajistit dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

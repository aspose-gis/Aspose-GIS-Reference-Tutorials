---
title: Převést Polygon Shapefile na Linestring
linktitle: Převést Polygon Shapefile na Linestring
second_title: Aspose.GIS .NET API
description: Prozkoumejte sílu Aspose.GIS pro .NET a bez námahy převádějte polygonové tvarové soubory na Linestrings. Podpořte svůj vývoj GIS ještě dnes!
type: docs
weight: 18
url: /cs/net/layer-management/convert-polygon-shapefile-to-linestring/
---
## Úvod
Pokud pracujete s geografickými informačními systémy (GIS) v .NET, Aspose.GIS je výkonná knihovna, která může zjednodušit vaše úkoly. V tomto tutoriálu vás provedeme procesem převodu Polygon Shapefile na Linestring pomocí Aspose.GIS. To může být zvláště užitečné, když potřebujete extrahovat lineární prvky z polygonálních dat pro různé aplikace, jako je plánování trasy nebo analýza sítě.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte na svém místě následující:
-  Knihovna Aspose.GIS: Stáhněte a nainstalujte knihovnu Aspose.GIS z[webová stránka](https://releases.aspose.com/gis/net/).
- Data Shapefile: Mějte připravený Polygon Shapefile pro konverzi. Pokud žádné nemáte, můžete najít ukázková data nebo si vytvořit vlastní.
- Vývojové prostředí: Nastavte své vývojové prostředí .NET pomocí nezbytných nástrojů.
## Importovat jmenné prostory
Do vašeho C# kódu musíte importovat jmenné prostory Aspose.GIS, abyste získali přístup k požadovaným třídám a metodám. Na začátek souboru kódu přidejte následující jmenné prostory:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Krok 1: Nastavte adresář dokumentů
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";
```
Nahraďte "Your Document Directory" cestou k adresáři, kde je umístěn váš Shapefile.
## Krok 2: Otevřete zdrojový soubor Shapefile
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Zbytek kódu půjde sem
}
```
Tento krok otevře zdrojový Polygon Shapefile pro čtení.
## Krok 3: Vytvořte soubor tvaru cílového čárového řetězce
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Zbytek kódu půjde sem
}
```
Zde vytvoříme nový Linestring Shapefile pro zápis převedených dat.
## Krok 4: Iterace přes funkce zdroje
```csharp
foreach (Feature sourceFeature in source)
{
    // Zbytek kódu půjde sem
}
```
Tato smyčka prochází každým prvkem ve zdrojovém polygonovém Shapefile.
## Krok 5: Převeďte mnohoúhelník na čárový řetězec a zapište do cíle
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
tomto kroku je každý prvek Polygon převeden na Linestring a výsledný prvek Linestring je zapsán do cílového Shapefile.
## Závěr
Pomocí následujících kroků můžete snadno převést Polygon Shapefile na Linestring pomocí Aspose.GIS for .NET. Tento proces otevírá nové možnosti pro analýzu a vizualizaci dat v aplikacích GIS.

## Nejčastější dotazy
### Je Aspose.GIS kompatibilní se všemi verzemi .NET?
Ano, Aspose.GIS podporuje různé verze .NET a zajišťuje kompatibilitu s vaším vývojovým prostředím.
### Mohu použít Aspose.GIS pro komerční projekty?
 Ano můžeš. Chcete-li používat Aspose.GIS v komerčních projektech, zvažte zakoupení licence[tady](https://purchase.aspose.com/buy).
### Jsou k dispozici nějaké příklady nebo dokumentace?
 Ano, komplexní dokumentaci a příklady naleznete na[dokumentační stránku](https://reference.aspose.com/gis/net/).
### Je k dispozici zkušební verze?
 Ano, můžete prozkoumat Aspose.GIS s bezplatnou zkušební verzí na návštěvě[tento odkaz](https://releases.aspose.com/).
### Kde mohu hledat pomoc nebo podporu?
 Navštivte[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) pro jakoukoli pomoc nebo dotazy týkající se podpory.
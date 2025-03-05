---
title: Extrahujte funkce do GeoJSON
linktitle: Extrahujte funkce do GeoJSON
second_title: Aspose.GIS .NET API
description: Prozkoumejte podrobného průvodce používáním Aspose.GIS pro .NET k extrahování funkcí do GeoJSON. Využijte sílu GIS snadno! #State #GIS
type: docs
weight: 23
url: /cs/net/layer-management/extract-features-to-geojson/
---
## Úvod
Vítejte v našem podrobném návodu na extrahování funkcí do GeoJSON pomocí Aspose.GIS pro .NET! Ať už jste zkušený vývojář nebo teprve začínáte svou cestu v programování GIS, tento průvodce vás provede celým procesem a zajistí, že využijete plný výkon Aspose.GIS pro .NET.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte následující předpoklady:
-  Aspose.GIS for .NET: Ujistěte se, že máte nainstalovanou knihovnu. Pokud ne, můžete si jej stáhnout z[Aspose.GIS pro stránku .NET](https://releases.aspose.com/gis/net/).
-  Data souboru Shapefile: Připravte si soubor Shapefile pro vstup. Pokud potřebujete ukázková data, najdete je v[Dokumentace Aspose.GIS](https://reference.aspose.com/gis/net/).
- Prostředí .NET: Nastavte prostředí .NET pro spouštění poskytnutého kódu.
- Adresář dokumentů: Ve fragmentu kódu definujte cestu k adresáři vašeho dokumentu.
Nyní, když máte vše na svém místě, začněme extrahovat funkce do GeoJSON!
## Importovat jmenné prostory
Nejprve do kódu zahrňte potřebné jmenné prostory:
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Tyto jmenné prostory jsou nezbytné pro práci s funkcemi Aspose.GIS.
## Krok 1: Otevřete Input Shapefile
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Váš kód pro zpracování vstupního shapefile je zde
}
```
 Otevřete vstupní Shapefile pomocí`VectorLayer.Open` metoda.
## Krok 2: Vytvořte výstupní GeoJSON
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Zde je váš kód pro vytvoření výstupu GeoJSON
}
```
 Vytvořte výstupní GeoJSON pomocí`VectorLayer.Create` metoda.
## Krok 3: Zkopírujte atributy
```csharp
outputLayer.CopyAttributes(inputLayer);
```
 Zkopírujte atributy ze vstupní vrstvy do výstupní vrstvy pomocí`CopyAttributes` metoda.
## Krok 4: Funkce procesu
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Zde je váš kód pro zpracování každé vstupní funkce
}
```
Iterujte každý prvek ve vstupní vrstvě a zpracujte je jednotlivě.
## Krok 5: Filtrování funkcí podle data
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
Filtrujte funkce na základě podmínky data. V tomto příkladu přeskočí objekty s datem narození před rokem 1982.
## Krok 6: Vytvořte nový prvek
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Vytvořte nový prvek pro výstupní vrstvu zkopírováním geometrie a hodnot ze vstupního prvku.
Gratulujeme! Úspěšně jste extrahovali funkce do GeoJSON pomocí Aspose.GIS pro .NET.
## Závěr
V tomto tutoriálu jsme prozkoumali proces extrahování funkcí do GeoJSON pomocí Aspose.GIS pro .NET. Tato výkonná knihovna otevírá svět možností pro vývoj GIS. Experimentujte s různými datovými sadami a funkcemi, abyste odemkli plný potenciál Aspose.GIS.
## Nejčastější dotazy
### Otázka: Kde najdu další dokumentaci?
 Navštivte[Dokumentace Aspose.GIS](https://reference.aspose.com/gis/net/) pro podrobné informace.
### Otázka: Jak mohu získat dočasnou licenci?
 Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Otázka: Kde mohu hledat podporu?
 Připojte se k[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) za podporu komunity a diskuze.
### Otázka: Je k dispozici bezplatná zkušební verze?
 Ano, bezplatnou zkušební verzi najdete[tady](https://releases.aspose.com/).
### Otázka: Kde mohu zakoupit Aspose.GIS pro .NET?
 Produkt si můžete zakoupit[tady](https://purchase.aspose.com/buy).
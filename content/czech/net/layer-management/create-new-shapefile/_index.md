---
title: Vytvořit nový soubor Shapefile
linktitle: Vytvořit nový soubor Shapefile
second_title: Aspose.GIS .NET API
description: Naučte se, jak vytvořit nový shapefile pomocí Aspose.GIS pro .NET. Postupujte podle našeho podrobného průvodce a odemkněte sílu manipulace s prostorovými daty.
type: docs
weight: 12
url: /cs/net/layer-management/create-new-shapefile/
---
## Úvod
Pokud se ponoříte do vývoje geografických informačních systémů (GIS) s .NET, Aspose.GIS je vaším řešením. Tato výkonná knihovna umožňuje vývojářům bezproblémově pracovat s prostorovými daty a v tomto tutoriálu vás provedeme procesem vytváření nového souboru shapefile pomocí Aspose.GIS for .NET.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Základní znalost programovacího jazyka C#.
- Visual Studio nainstalované na vašem počítači.
-  Aspose.GIS pro knihovnu .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/gis/net/).
## Importovat jmenné prostory
Začněte importem potřebných jmenných prostorů, abyste mohli využít funkčnost Aspose.GIS:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Krok 1: Nastavte svůj projekt
Začněte vytvořením nového projektu C# v sadě Visual Studio a zahrňte knihovnu Aspose.GIS.
## Krok 2: Definujte adresář dokumentů
```csharp
string dataDir = "Your Document Directory";
```
Nahraďte "Your Document Directory" skutečnou cestou, kam chcete uložit nový soubor shapefile.
## Krok 3: Vytvořte VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //přidat atributy před přidáním funkcí
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Tento segment kódu nastavuje vektorovou vrstvu a definuje atributy pro vaše funkce.
## Krok 4: Přidejte funkce
### Případ 1: Nastavuje hodnoty individuálně
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
### Případ 2: Nastaví nové hodnoty pro všechny atributy
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## Závěr
 Gratulujeme! Úspěšně jste vytvořili nový shapefile pomocí Aspose.GIS pro .NET. Tento výukový program pokryl základy nastavení vašeho projektu, definování atributů a přidávání funkcí. Při dalším zkoumání se podívejte na[dokumentace](https://reference.aspose.com/gis/net/) pro pokročilé vlastnosti a funkce.
## Často kladené otázky
### Otázka: Mohu používat Aspose.GIS s jinými programovacími jazyky?
Aspose.GIS primárně podporuje .NET, ale existují verze dostupné i pro Javu.
### Otázka: Je k dispozici bezplatná zkušební verze?
 Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).
### Otázka: Kde najdu podporu pro Aspose.GIS?
 Navštivte[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) za podporu komunity a diskuze.
### Otázka: Jak mohu získat dočasnou licenci?
 Získejte dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Otázka: Kde mohu zakoupit Aspose.GIS pro .NET?
 Knihovnu si můžete koupit[tady](https://purchase.aspose.com/buy).
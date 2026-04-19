---
date: 2026-01-10
description: Naučte se, jak číst shapefile v C# a převést polygonový shapefile na
  linestring pomocí Aspose.GIS pro .NET. Zvyšte svůj vývoj GIS s jasným krok‑za‑krokem
  návodem.
linktitle: Convert Polygon Shapefile to Linestring
second_title: Aspose.GIS .NET API
title: Načtení shapefile v C# – Převod polygonového shapefile na linestring
url: /cs/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Čtení Shapefile C# – Převod polygonového shapefile na Linestring

## Úvod
Pokud pracujete se systémy geografických informací (GIS) v .NET, **read shapefile c#** je běžný první krok, než můžete data upravovat. Aspose.GIS tento proces zjednodušuje a umožňuje vám převést polygonový shapefile na Linestring pomocí několika řádků kódu. Tato funkce je zvláště užitečná, když potřebujete z polygonových dat získat lineární prvky pro úkoly jako plánování tras, analýza sítí nebo vizualizace dat.

## Rychlé odpovědi
- **Která knihovna vám pomůže číst shapefile c#?** Aspose.GIS pro .NET  
- **Lze převést polygon na čáru?** Ano – použijte `LineString` s vnějším okrajem polygonu.  
- **Potřebuji licenci pro produkční nasazení?** Pro produkční použití je vyžadována komerční licence.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Je k dispozici zkušební verze?** Rozhodně – stáhněte si bezplatnou zkušební verzi ze stránek Aspose.

## Co je “read shapefile c#”?
Čtení shapefile v C# znamená načtení souboru `.shp` do paměti, abyste mohli dotazovat, upravovat nebo transformovat jeho geometrie. Aspose.GIS poskytuje jednoduché API, které abstrahuje nízkoúrovňové detaily a umožňuje vám soustředit se na GIS logiku.

## Proč převádět polygon na čáru pomocí Aspose.GIS?
- **Zachování topologie** – převod zachovává přesnou vnější hranici každého polygonu.  
- **Výkonnost** – knihovna je optimalizována pro velké datové sady, takže hromadné převody jsou rychlé.  
- **Flexibilita** – později můžete linestringy zapsat do jiného shapefile, GeoJSON nebo jakéhokoli podporovaného formátu.

## Předpoklady
Než se pustíme do tutoriálu, ujistěte se, že máte připraveno následující:

- **Aspose.GIS Library** – Stáhněte a nainstalujte knihovnu Aspose.GIS z [webu](https://releases.aspose.com/gis/net/).  
- **Shapefile Data** – Mějte připravený polygonový shapefile k převodu. Pokud žádný nemáte, můžete najít ukázková data nebo si vytvořit vlastní.  
- **Vývojové prostředí** – Nastavte své .NET vývojové prostředí s potřebnými nástroji (Visual Studio, .NET SDK, atd.).

## Import Namespaces
Ve vašem C# kódu musíte importovat jmenné prostory Aspose.GIS, abyste získali přístup k požadovaným třídám a metodám. Přidejte následující jmenné prostory na začátek souboru s kódem:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Jak převést shapefile z polygonu na čáru?
Níže je krok‑za‑krokem průvodce, který ukazuje **jak převést shapefile** data z polygonu na čáru pomocí Aspose.GIS.

### Krok 1: Nastavte adresář dokumentu
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
Nahraďte `"Your Document Directory"` skutečnou cestou, kde se váš shapefile nachází.

### Krok 2: Otevřete zdrojový shapefile
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Tento řádek **otevírá zdrojový polygonový shapefile**, abyste mohli číst jeho prvky.

### Krok 3: Vytvořte cílový Linestring shapefile
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Zde **vytvoříme nový Linestring shapefile**, který bude ukládat převedené geometrie.

### Krok 4: Procházejte zdrojové prvky
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
Smyčka prochází každý polygonový prvek v původním souboru.

### Krok 5: Převod polygonu na Linestring a zápis do cíle
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
V tomto bloku **převádíme polygon na čáru** (`LineString`) a přidáváme nový prvek do cílového shapefile.

## Časté problémy a tipy
- **Neshoda souřadnicových systémů** – Ujistěte se, že vrstvy zdroje i cíle používají stejný prostorový referenční systém; jinak se čáry mohou zobrazit posunuté.  
- **Velké soubory** – Při zpracování velmi velkých shapefile zvažte streamování prvků místo načítání všeho najednou do paměti.  
- **Null geometrie** – Ošetřete prvky s prázdnými geometriemi, aby nedošlo k výjimkám během běhu.

## Často kladené otázky

**Q: Je Aspose.GIS kompatibilní se všemi verzemi .NET?**  
A: Ano, Aspose.GIS podporuje různé verze .NET, což zajišťuje kompatibilitu s vaším vývojovým prostředím.

**Q: Mohu používat Aspose.GIS v komerčních projektech?**  
A: Ano. Pro komerční projekty zvažte zakoupení licence [zde](https://purchase.aspose.com/buy).

**Q: Existují příklady nebo dokumentace?**  
A: Ano, komplexní dokumentaci a příklady najdete na [stránce dokumentace](https://reference.aspose.com/gis/net/).

**Q: Je k dispozici zkušební verze?**  
A: Ano, můžete si vyzkoušet Aspose.GIS zdarma na [tomto odkazu](https://releases.aspose.com/).

**Q: Kde mohu získat pomoc nebo podporu?**  
A: Navštivte [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pro jakékoli dotazy související s podporou.

---

**Poslední aktualizace:** 2026-01-10  
**Testováno s:** Aspose.GIS pro .NET (nejnovější vydání)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
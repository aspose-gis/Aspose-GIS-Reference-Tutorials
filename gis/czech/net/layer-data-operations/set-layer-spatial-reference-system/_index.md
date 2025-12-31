---
date: 2025-12-31
description: Naučte se, jak vytvořit vektorovou vrstvu a nastavit prostorový referenční
  systém vrstvy pomocí Aspose.GIS pro .NET. Ovládněte definování prostorové reference,
  přidání bodové funkce a získání kódu EPSG.
linktitle: Set Layer Spatial Reference System
second_title: Aspose.GIS .NET API
title: Vytvořit vektorovou vrstvu a nastavit prostorový referenční systém vrstvy
url: /cs/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření vektorové vrstvy a nastavení souřadnicového systému vrstvy

## Úvod
V rozsáhlém světě geografických informačních systémů (GIS) **Aspose.GIS for .NET** vyniká jako robustní a univerzální nástroj pro vývojáře. V tomto tutoriálu **vytvoříte vektorovou vrstvu**, definujete její souřadnicový referenční systém, přidáte bodový prvek a získáte kód EPSG — vše s jasným, krok‑za‑krokem návodem. Ať už jste zkušený GIS inženýr nebo teprve začínáte, tyto techniky vám pomohou správně nastavit souřadnicový systém shapefile a zvýšit spolehlivost vašich pracovních postupů se prostorovými daty.

## Rychlé odpovědi
- **Co znamená „vytvořit vektorovou vrstvu“?** Vytvoří novou GIS vrstvu (např. Shapefile), která může ukládat geometrie jako body, linie nebo polygony.  
- **Jaký kód EPSG se v příkladu používá?** EPSG 26918 (NAD83 / UTM zóna 18N).  
- **Mohu po vytvoření vrstvy přidat bodový prvek?** Ano — použijte `ConstructFeature()` a přiřaďte geometrii `Point`.  
- **Jak získám CRS vrstvy?** Přečtěte `layer.SpatialReferenceSystem.EpsgCode` nebo `.Name`.  
- **Potřebuji licenci pro Aspose.GIS?** K dispozici je bezplatná zkušební verze; licence je vyžadována pro produkční použití.

## Předpoklady
Předtím, než se pustíte do tutoriálu, ujistěte se, že máte připravené následující:
- Praktické znalosti programování v .NET.  
- Nainstalované Visual Studio.  
- Knihovnu Aspose.GIS for .NET, kterou si můžete stáhnout [zde](https://releases.aspose.com/gis/net/).  
- Základní pochopení souřadnicových referenčních systémů v GIS.

## Import jmenných prostorů
Ve svém .NET projektu začněte importováním potřebných jmenných prostorů, abyste získali přístup k funkcím poskytovaným Aspose.GIS. Použijte následující úryvek kódu:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Krok 1: Zadejte adresář dokumentů
Nejprve určete cestu k adresáři, ve kterém budou uloženy soubory prostorových dat.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Definujte souřadnicový referenční systém a nastavte souřadnicový systém shapefile
Určete cestu ke shapefile a **definujte souřadnicový referenční systém** pomocí kódu EPSG (v tomto příkladu 26918). Tento krok **nastaví souřadnicový systém shapefile** pro vrstvu.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Krok 3: Vytvořte vektorovou vrstvu
Nyní **vytvořte vektorovou vrstvu** s určenou cestou ke shapefile, typem ovladače (Shapefile) a souřadnicovým referenčním systémem, který jste právě definovali.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

## Krok 4: Přidejte bodový prvek do vrstvy
Vytvořte nový prvek a **přidejte bodový prvek** nastavením jeho geometrie (`Point` s souřadnicemi 60, 24). Poté přidejte prvek do vektorové vrstvy.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

## Krok 5: Získejte informace o souřadnicovém referenčním systému (získání kódu EPSG)
Otevřete vektorovou vrstvu a získejte informace o souřadnicovém referenčním systému, jako je kód EPSG a čitelný název. Tím se ukáže, jak **získat kód EPSG** a **nastavit CRS vrstvy**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

Opakujte tyto kroky podle vašeho konkrétního scénáře a budete na dobré cestě k ovládnutí techniky **vytvořit vektorovou vrstvu** a správy souřadnicových referencí s Aspose.GIS for .NET.

## Časté problémy a řešení
| Problém | Proč k tomu dochází | Řešení |
|---------|----------------------|--------|
| **Vrstva se nepodaří otevřít** | Nesprávný ovladač nebo poškozená cesta k souboru | Ověřte `Drivers.Shapefile` a ujistěte se, že `path` ukazuje na existující soubor `.shp`. |
| **Zobrazuje se nesprávný CRS** | Použit nesprávný kód EPSG | Zkontrolujte kód EPSG u autoritativního zdroje (např. EPSG.io). |
| **Prvek se neuloží** | Nevolá se `layer.Add(feature)` uvnitř bloku `using` | Ujistěte se, že metoda `Add` je vykonána před uvolněním vrstvy. |

## Často kladené otázky
### Je Aspose.GIS kompatibilní s jinými GIS knihovnami?
Ano, Aspose.GIS se dobře integruje s dalšími GIS knihovnami a lze jej používat společně s nimi.

### Lze Aspose.GIS použít jak pro desktopové, tak pro webové aplikace?
Rozhodně! Aspose.GIS je univerzální a může být nasazen jak v desktopových, tak ve webových aplikacích.

### Jaké licenční možnosti jsou pro Aspose.GIS k dispozici?
Ano, můžete prozkoumat licenční možnosti a provést nákup [zde](https://purchase.aspose.com/buy).

### Je k dispozici bezplatná zkušební verze Aspose.GIS?
Samozřejmě! Bezplatnou zkušební verzi si můžete stáhnout [zde](https://releases.aspose.com/).

### Kde mohu získat podporu pro dotazy související s Aspose.GIS?
Pro jakoukoli podporu nebo dotazy navštivte [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

## Další často kladené otázky
**Q: Jak změním CRS existujícího shapefile?**  
A: Otevřete vrstvu, vytvořte nový `SpatialReferenceSystem` s požadovaným kódem EPSG a přiřaďte jej `layer.SpatialReferenceSystem` před uložením.

**Q: Mohu pomocí stejného přístupu přidat i jiné typy geometrie (např. polygony)?**  
A: Ano — nahraďte `new Point(x, y)` za `new Polygon(...)` nebo `new LineString(...)` podle potřeby.

**Q: Je možné efektivně pracovat s velkými datovými sadami?**  
A: Používejte streamingové API (`VectorLayer.Create` s `FeatureCollection`) a vrstvu uvolňujte co nejdříve, aby se uvolnily zdroje.

**Q: Podporuje Aspose.GIS transformaci souřadnic?**  
A: Ano — použijte `Geometry.Transform(targetSrs)` k reprojekci geometrie mezi různými souřadnicovými referencemi.

**Q: Jaké verze .NET jsou podporovány?**  
A: Aspose.GIS funguje s .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

## Závěr
V tomto tutoriálu jsme si ukázali, jak **vytvořit vektorovou vrstvu**, definovat její souřadnicový referenční systém, **přidat bodový prvek** a **získat kód EPSG** pomocí Aspose.GIS for .NET. Ovládnutím těchto kroků můžete sebejistě nastavit souřadnicový systém shapefile, spravovat CRS vrstvy a vytvářet spolehlivé GIS aplikace.

---

**Poslední aktualizace:** 2025-12-31  
**Testováno s:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
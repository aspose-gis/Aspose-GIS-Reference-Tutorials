---
date: 2025-12-20
description: Naučte se, jak vytvořit polygon s otvorem pomocí Aspose.GIS pro .NET.
  Tento průvodce vám ukáže, jak vytvořit otvor v polygonu a pracovat s geoprostorovými
  daty.
linktitle: Create Polygon with Hole Geometry
second_title: Aspose.GIS .NET API
title: Vytvořte polygon s otvorem pomocí Aspose.GIS
url: /cs/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření polygonu s otvorem pomocí Aspose.GIS

## Úvod
V tomto tutoriálu **vytvoříte polygon s otvorem** pomocí Aspose.GIS pro .NET. Ať už budujete mapovou aplikaci, provádíte prostorovou analýzu nebo připravujete data pro GIS služby, znalost vložení otvoru do polygonu je nezbytná. Provedeme vás celým procesem krok za krokem, od nastavení prostředí až po vytvoření finálního objektu polygonu.

## Rychlé odpovědi
- **Co znamená „vytvořit polygon s otvorem“?** Znamená to vytvořit polygon, který obsahuje jeden nebo více vnitřních kruhů (otvorů), které jsou z oblasti vyloučeny.
- **Která knihovna to řeší?** Aspose.GIS pro .NET poskytuje plnou podporu pro vnější a vnitřní kruhy.
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Jak dlouho to trvá?** Obvykle méně než 10 minut na implementaci a testování.

## Co je „vytvoření polygonu s otvorem“?
Vytvoření polygonu s otvorem zahrnuje definování **vnějšího kruhu**, který vymezuje vnější hranici, a jednoho nebo více **vnitřních kruhů**, které vyřezávají prázdné prostory. Vnitřní kruhy se často nazývají *otvory*, protože představují oblasti, které nejsou součástí povrchu polygonu.

## Proč vytvořit otvor v polygonu pomocí Aspose.GIS?
- **Přesné prostorové modelování:** Reálné prvky jako jezera uvnitř pozemků nebo dvory v budovách vyžadují otvory.
- **Interoperabilita:** Formáty jako Shapefile, GeoJSON a GML nativně podporují vnitřní kruhy; Aspose.GIS je zachovává.
- **Výkon:** Knihovna spravuje platnost geometrie, takže nemusíte psát vlastní validační kód.

## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Aspose.GIS pro .NET Library: Můžete si ji stáhnout [zde](https://releases.aspose.com/gis/net/).
2. Vývojové prostředí: Zajistěte, aby bylo nastavené vývojové prostředí s Visual Studio nebo jiným .NET IDE.

## Import jmenných prostorů
Nejprve je potřeba importovat potřebné jmenné prostory pro práci s funkcemi Aspose.GIS. Zde je postup:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Nyní přejděme k vytvoření geometrie polygonu s otvorem pomocí Aspose.GIS pro .NET.

## Krok 1: Vytvoření objektu Polygon
Začneme vytvořením prázdného objektu `Polygon`, který později bude obsahovat jak vnější, tak vnitřní kruhy.

```csharp
Polygon polygon = new Polygon();
```

## Krok 2: Definování vnějšího kruhu
Vnější kruh vymezuje vnější hranici polygonu. Přidejte body ve směru hodinových ručiček, aby vznikl uzavřený tvar.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Krok 3: Definování vnitřního kruhu (otvoru)
Dále vytvoříme vnitřní kruh — to je **otvor**, který bude z oblasti polygonu vyloučen. Body se obvykle přidávají v protisměru hodinových ručiček, ale Aspose.GIS orientaci zpracuje automaticky.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Krok 4: Přiřazení vnějšího kruhu a přidání vnitřního kruhu do polygonu
Nakonec přiřaďte vnější kruh k polygonu a poté přidejte vnitřní kruh (otvor). Metodu `AddInteriorRing` můžete volat vícekrát, pokud potřebujete několik otvorů.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|---------|-------|--------|
| Otevř není vidět v GIS prohlížeči | Orientace vnitřního kruhu je obrácená | Ujistěte se, že body jsou přidány v opačném směru než vnější kruh (proti směru hodinových ručiček). |
| Chyba „Polygon invalid“ | Kruhy nejsou uzavřeny (první ≠ poslední bod) | Opakujte první bod jako poslední bod v každém kruhu (jak je ukázáno výše). |
| Neočekávaná prázdná geometrie | Zapomněli jste přiřadit `ExteriorRing` před přidáním vnitřních kruhů | Nejprve nastavte `polygon.ExteriorRing`, pak zavolejte `AddInteriorRing`. |

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak **vytvořit polygon s otvorem** pomocí Aspose.GIS pro .NET. Tato technika je základní pro mnoho geoprostorových scénářů, kde potřebujete reprezentovat složité tvary s vnitřními dutinami.

## Často kladené otázky
### 1. Co je Aspose.GIS?
Aspose.GIS je .NET knihovna, která umožňuje vývojářům pracovat s geoprostorovými daty, vytvářet, číst a manipulovat s různými geoprostorovými formáty souborů.

### 2. Mohu používat Aspose.GIS pro komerční projekty?
Ano, Aspose.GIS můžete používat jak pro osobní, tak pro komerční projekty zakoupením licence. Více informací najdete [zde](https://purchase.aspose.com/buy).

### 3. Je k dispozici bezplatná zkušební verze Aspose.GIS?
Ano, bezplatnou zkušební verzi Aspose.GIS získáte [zde](https://releases.aspose.com/).

### 4. Kde mohu najít podporu pro Aspose.GIS?
Podporu pro Aspose.GIS najdete na [fóru Aspose.GIS](https://forum.aspose.com/c/gis/33).

### 5. Jak mohu získat dočasnou licenci pro Aspose.GIS?
Dočasnou licenci pro Aspose.GIS můžete získat [zde](https://purchase.aspose.com/temporary-license/).

---

**Poslední aktualizace:** 2025-12-20  
**Testováno s:** Aspose.GIS 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
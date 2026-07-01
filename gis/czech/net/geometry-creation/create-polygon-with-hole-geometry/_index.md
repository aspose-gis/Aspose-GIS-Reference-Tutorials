---
date: 2026-04-03
description: Naučte se, jak vytvořit polygon s otvorem pomocí Aspose.GIS pro .NET.
  Tento průvodce vám ukáže, jak vytvořit otvor v polygonu a pracovat s geoprostorovými
  daty.
keywords:
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
linktitle: Vytvořit polygon s otvorem
second_title: Aspose.GIS .NET API
title: Vytvořte polygon s otvorem pomocí Aspose.GIS
url: /cs/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření polygonu s dírou pomocí Aspose.GIS

## Úvod
V tomto tutoriálu **vytvoříte polygon s dírou** pomocí Aspose.GIS pro .NET. Ať už budujete mapovou aplikaci, provádíte prostorovou analýzu nebo připravujete data pro GIS služby, znalost vložení díry do polygonu je nezbytná. Provedeme vás celým procesem krok za krokem, od nastavení prostředí až po vytvoření finálního objektu polygonu.

## Rychlé odpovědi
- **Co znamená „vytvořit polygon s dírou“?** Znamená to vytvořit polygon, který obsahuje jeden nebo více vnitřních okruhů (děr), jež jsou vyloučeny z plochy.  
- **Která knihovna to řeší?** Aspose.GIS pro .NET poskytuje plnou podporu pro vnější i vnitřní okruhy.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Jak dlouho to trvá?** Obvykle méně než 10 minut na implementaci a testování.

## Jak přidat díru do polygonu pomocí Aspose.GIS
Přidání díry je jen otázkou definování **vnitřního okruhu** a jeho připojení k polygonu. Knihovna se postará o orientaci a platnost, takže se můžete soustředit na souřadnice představující požadovanou prázdnotu.

## Co znamená „vytvořit polygon s dírou“?
Vytvoření polygonu s dírou zahrnuje definování **vnějšího okruhu**, který vymezuje vnější hranici, a jednoho nebo více **vnitřních okruhů**, které vyřezávají prázdné prostory. Vnitřní okruhy se často nazývají *díry*, protože představují oblasti, které nejsou součástí povrchu polygonu.

## Proč vytvářet díru v polygonu pomocí Aspose.GIS?
- **Přesné prostorové modelování:** Reálné prvky jako jezera uvnitř pozemků nebo dvory v budovách vyžadují díry.  
- **Interoperabilita:** Formáty jako Shapefile, GeoJSON a GML nativně podporují vnitřní okruhy; Aspose.GIS je zachovává.  
- **Výkon:** Knihovna spravuje platnost geometrie, takže nemusíte psát vlastní validační kód.

## Scénáře ze skutečného světa pro polygony s dírami
1. **Pozemek s vnitřním jezerem** – jezero je modelováno jako díra, takže se nepočítá do plochy pozemku.  
2. **Obrysy budov s dvorci** – dvůr je vyloučen z obrysu budovy.  
3. **Chráněné zóny uvnitř většího chráněného území** – můžete vyloučit omezené sekce, aniž byste vytvářeli samostatné vrstvy.

## Požadavky
Než začneme, ujistěte se, že máte následující předpoklady:
1. Aspose.GIS pro .NET knihovna: můžete ji stáhnout [zde](https://releases.aspose.com/gis/net/).  
2. Vývojové prostředí: zajistěte, aby bylo nastavené vývojové prostředí s Visual Studio nebo jiným .NET IDE.

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

Nyní přistoupíme k vytvoření polygonu s dírou pomocí Aspose.GIS pro .NET.

## Krok 1: Vytvořit objekt Polygon
Začneme vytvořením prázdného objektu `Polygon`, který později bude obsahovat jak vnější, tak vnitřní okruhy.

```csharp
Polygon polygon = new Polygon();
```

## Krok 2: Definovat vnější obrys
Vnější obrys vymezuje vnější hranici polygonu. Přidejte body ve směru hodinových ručiček, aby vznikl uzavřený tvar.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Krok 3: Definovat vnitřní obrys (díru)
Dále vytvoříme vnitřní obrys — toto je **díra**, která bude z polygonu vyloučena. Body se obvykle přidávají v protisměru hodinových ručiček, ale Aspose.GIS automaticky řeší orientaci.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Krok 4: Přiřadit vnější obrys a přidat vnitřní obrys do polygonu
Nakonec připojíme vnější obrys k polygonu a poté přidáme vnitřní obrys (díru). Metodu `AddInteriorRing` můžete volat vícekrát, pokud potřebujete několik děr.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Tipy a osvědčené postupy
- **Orientace má význam pro čitelnost** – i když Aspose.GIS automaticky opravuje orientaci, udržování vnějších okruhů ve směru hodinových ručiček a vnitřních okruhů v protisměru usnadňuje kontrolu geometrie v GIS prohlížečích.  
- **Uzavřete každý okruh** – vždy opakujte první souřadnici jako poslední bod; tím zajistíte platný uzavřený tvar.  
- **Validujte po vytvoření** – můžete zavolat `polygon.IsValid`, abyste se ujistili, že geometrie splňuje OGC standardy před uložením.

## Časté problémy a řešení
| Problém | Příčina | Řešení |
|-------|--------|-----|
| Díra se nezobrazuje v GIS prohlížeči | Orientace vnitřního okruhu je obrácená | Zajistěte, aby body byly přidány v opačném směru než vnější okruh (protisměr hodinových ručiček). |
| Chyba „Polygon invalid“ | Okruhy nejsou uzavřeny (první ≠ poslední bod) | Opakujte první bod jako poslední bod v každém okruhu (jak je ukázáno výše). |
| Neočekávaná prázdná geometrie | Zapomněli jste přiřadit `ExteriorRing` před přidáním vnitřních okruhů | Nejprve nastavte `polygon.ExteriorRing`, pak volejte `AddInteriorRing`. |

## Často kladené otázky
### 1. Co je Aspose.GIS?
Aspose.GIS je .NET knihovna, která umožňuje vývojářům pracovat s geoprostorovými daty, vytvářet, číst a manipulovat s různými geoprostorovými formáty souborů.

### 2. Mohu používat Aspose.GIS pro komerční projekty?
Ano, Aspose.GIS můžete používat jak pro osobní, tak pro komerční projekty zakoupením licence. Více informací najdete [zde](https://purchase.aspose.com/buy).

### 3. Je k dispozici bezplatná zkušební verze Aspose.GIS?
Ano, bezplatnou zkušební verzi Aspose.GIS získáte [zde](https://releases.aspose.com/).

### 4. Kde mohu najít podporu pro Aspose.GIS?
Podporu pro Aspose.GIS najdete na [fóru Aspose.GIS](https://forum.aspose.com/c/gis/33).

### 5. Jak získat dočasnou licenci pro Aspose.GIS?
Dočasnou licenci pro Aspose.GIS můžete získat [zde](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
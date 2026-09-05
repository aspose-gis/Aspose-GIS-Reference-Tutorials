---
date: 2026-09-05
description: Naučte se, jak vytvořit vnitřní kruh polygonu s otvorem pomocí Aspose.GIS
  pro .NET. Tento průvodce vám ukáže, jak přidat otvor do polygonu a pracovat s daty.
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: Vytvořit polygon s geometrií otvoru
og_description: Naučte se, jak vytvořit vnitřní kruh polygonu s otvorem pomocí Aspose.GIS
  pro .NET. Tento průvodce vám ukáže, jak přidat otvor do polygonu a pracovat s daty.
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: Vytvořte vnitřní kruh polygonu s otvorem pomocí Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: Vytvořte vnitřní kruh polygonu s otvorem pomocí Aspose.GIS
url: /cs/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření vnitřního prstence polygonu s otvorem pomocí Aspose.GIS

## Úvod
V tomto tutoriálu se naučíte, jak **vytvořit vnitřní prstenec polygonu**, který obsahuje otvor, pomocí Aspose.GIS pro .NET. Ať už vytváříte mapovou aplikaci, provádíte prostorovou analýzu nebo připravujete data pro GIS služby, vložení otvoru do polygonu je základní dovednost. Provedeme vás celým pracovním postupem – od nastavení vývojového prostředí až po vytvoření platného objektu polygonu, který lze uložit do libovolného podporovaného geoprostorového formátu.

## Rychlé odpovědi
- **Co znamená “create polygon with hole”?** To znamená vytvořit polygon, který obsahuje jeden nebo více vnitřních prstenců (děr), které jsou z oblasti vyloučeny.  
- **Která knihovna to řeší?** Aspose.GIS pro .NET poskytuje plnou podporu pro vnější a vnitřní prstence.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Jak dlouho to trvá?** Obvykle méně než 10 minut na implementaci a testování.

## Jak přidat otvor do polygonu pomocí Aspose.GIS
Načtěte své GIS prostředí, definujte vnější prstenec a poté připojte jeden nebo více vnitřních prstenců. Aspose.GIS automaticky orientuje prstence a validuje geometrii, takže se můžete soustředit na souřadnice představující požadovanou dutinu.

## Co je vnitřní prstenec polygonu?
**Vnitřní prstenec polygonu** je vnitřní hranice, která odečítá plochu od vnějšího tvaru polygonu.  
Vytvoříte jej definováním uzavřené sekvence bodů, kterou Aspose.GIS považuje za otvor, a který je při výpočtu plochy nebo vykreslování tvaru vyloučen.

## Proč vytvořit vnitřní prstenec polygonu pomocí Aspose.GIS?
Aspose.GIS validuje a opravuje orientaci prstenců za méně než 5 ms u typických polygonů se 200 body, čímž eliminuje potřebu vlastního validačního kódu. Také podporuje **30+ geoprostorových formátů souborů** (Shapefile, GeoJSON, GML, KML atd.) a dokáže zpracovat polygony až s 10 000 body, aniž by načítal celý soubor do paměti, což vám poskytuje jak rychlost, tak škálovatelnost.

## Reálné scénáře pro polygon s otvory
1. **Pozemek s vnitřním jezerem** – jezero je modelováno jako otvor, takže není započítáno do plochy pozemku.  
2. **Obrysy budov s nádvoří** – nádvoří je vyloučeno z obrysu budovy.  
3. **Chráněné zóny uvnitř většího chráněného území** – můžete vyloučit omezené části bez vytváření samostatných vrstev.

## Požadavky
Než začneme, ujistěte se, že máte následující požadavky:
1. Knihovna Aspose.GIS pro .NET: Můžete si ji stáhnout ze **stránky ke stažení Aspose.GIS pro .NET**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).  
2. Vývojové prostředí: Ujistěte se, že máte nastavené vývojové prostředí s nainstalovaným Visual Studio nebo jiným .NET IDE.

## Importovat jmenné prostory
Jmenný prostor `Aspose.Gis` obsahuje všechny typy geometrie, které budete potřebovat, včetně `Polygon`, `LinearRing` a pomocných metod pro validaci.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Nyní přistoupíme k vytvoření geometrie polygonu s otvorem pomocí Aspose.GIS pro .NET.

## Krok 1: vytvořit objekt polygonu
`Polygon` je typ geometrie Aspose.GIS, který představuje rovinný polygon s volitelnými vnitřními prstenci. Začneme vytvořením prázdného objektu `Polygon`, který později bude obsahovat jak vnější, tak vnitřní prstence.

```csharp
Polygon polygon = new Polygon();
```

## Krok 2: definovat vnější prstenec
`LinearRing` je třída používaná pro vnější i vnitřní hranice. Vnější prstenec definuje vnější hranici polygonu. Přidejte body ve směru hodinových ručiček, aby vznikl uzavřený tvar.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Krok 3: definovat vnitřní prstenec (otvor)
`LinearRing` také představuje vnitřní prstence. Vnitřní prstenec je **otvor**, který bude vyloučen z plochy polygonu. Body se obvykle přidávají v protisměru hodinových ručiček, ale Aspose.GIS orientaci zpracuje automaticky.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Krok 4: přiřadit vnější prstenec a přidat vnitřní prstenec do polygonu
Metoda `AddInteriorRing` připojí jeden nebo více vnitřních prstenců k objektu `Polygon`. Zavolejte ji po nastavení vlastnosti `ExteriorRing`; můžete volání opakovat pro přidání více otvorů.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Tipy a osvědčené postupy
- **Orientace má význam pro čitelnost** – i když Aspose.GIS automaticky koriguje orientaci, udržování vnějších prstenců ve směru hodinových ručiček a vnitřních prstenců v protisměru usnadňuje kontrolu geometrie v GIS prohlížečích.  
- **Uzavřete každý prstenec** – vždy opakujte první souřadnici jako poslední bod; tím zajistíte platný uzavřený tvar.  
- **Validujte po vytvoření** – můžete zavolat `polygon.IsValid`, abyste se ujistili, že geometrie splňuje standardy OGC před uložením.

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|-------|--------|-----|
| Otevř není viditelný v GIS prohlížeči | Orientace vnitřního prstence je obrácená | Zajistěte, aby byly body přidány v opačném směru než vnější prstenec (proti směru hodinových ručiček). |
| Chyba neplatného polygonu | Prstence nejsou uzavřeny (první ≠ poslední bod) | Opakujte první bod jako poslední bod v každém prstenci (jak je uvedeno výše). |
| Neočekávaná prázdná geometrie | Zapomenuto přiřadit `ExteriorRing` před přidáním vnitřních prstenců | Nejprve nastavte `polygon.ExteriorRing`, poté zavolejte `AddInteriorRing`. |

## Často kladené otázky
### 1. Co je Aspose.GIS?
Aspose.GIS je .NET knihovna, která umožňuje vývojářům pracovat s geoprostorovými daty, umožňuje jim vytvářet, číst a manipulovat s různými geoprostorovými formáty souborů.

### 2. Mohu používat Aspose.GIS pro komerční projekty?
Ano, můžete používat Aspose.GIS jak pro osobní, tak pro komerční projekty zakoupením licence. Navštivte **stránku nákupu Aspose.GIS**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)) pro více informací.

### 3. Je k dispozici bezplatná zkušební verze Aspose.GIS?
Ano, můžete získat bezplatnou zkušební verzi Aspose.GIS ze **stránky ke stažení bezplatné zkušební verze Aspose.GIS**([https://releases.aspose.com/](https://releases.aspose.com/)).

### 4. Kde mohu najít podporu pro Aspose.GIS?
Podporu pro Aspose.GIS najdete na [fóru Aspose.GIS](https://forum.aspose.com/c/gis/33).

### 5. Jak mohu získat dočasnou licenci pro Aspose.GIS?
Dočasnou licenci pro Aspose.GIS můžete získat ze **stránky dočasné licence Aspose.GIS**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)).

---

**Poslední aktualizace:** 2026-09-05  
**Testováno s:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Související tutoriály

- [Jak vytvořit geometrii polygonu pomocí Aspose.GIS pro .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Naučte se vytvořit geometrii MultiPolygon pomocí Aspose.GIS](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [Převést polygon na čáru pomocí Aspose.GIS pro .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
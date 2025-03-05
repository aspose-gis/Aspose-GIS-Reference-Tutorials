---
title: Vytvořte mnohoúhelník s geometrií díry pomocí Aspose.GIS
linktitle: Vytvořte mnohoúhelník s geometrií díry
second_title: Aspose.GIS .NET API
description: Naučte se, jak vytvořit polygon s geometrií díry pomocí Aspose.GIS pro .NET. Výukový program krok za krokem s příklady kódu.
type: docs
weight: 13
url: /cs/net/geometry-creation/create-polygon-with-hole-geometry/
---
## Úvod
V tomto tutoriálu si projdeme procesem vytváření mnohoúhelníku s geometrií díry pomocí Aspose.GIS pro .NET. Aspose.GIS je výkonná knihovna, která umožňuje vývojářům pracovat s geoprostorovými daty v jejich aplikacích .NET. 
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Aspose.GIS for .NET Library: Můžete si ji stáhnout z[tady](https://releases.aspose.com/gis/net/).
2. Vývojové prostředí: Ujistěte se, že máte nastavené vývojové prostředí se sadou Visual Studio nebo jiným nainstalovaným .NET IDE.
## Importovat jmenné prostory
Nejprve musíte importovat potřebné jmenné prostory pro práci s funkcemi Aspose.GIS. Jak na to:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Nyní přistoupíme k vytvoření mnohoúhelníku s geometrií díry pomocí Aspose.GIS pro .NET.
## Krok 1: Vytvořte polygonový objekt
```csharp
Polygon polygon = new Polygon();
```
## Krok 2: Definujte vnější prstenec
```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```
## Krok 3: Definujte vnitřní prstenec (otvor)
```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```
## Krok 4: Přiřaďte vnější prstenec a přidejte vnitřní prstenec k mnohoúhelníku
```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak vytvořit polygon s geometrií díry pomocí Aspose.GIS pro .NET. Tyto znalosti budou přínosné pro různé geoprostorové aplikace, kde jsou takové geometrie nezbytné.
## FAQ
### 1. Co je Aspose.GIS?
Aspose.GIS je knihovna .NET, která umožňuje vývojářům pracovat s geoprostorovými daty a umožňuje jim vytvářet, číst a manipulovat s různými formáty geoprostorových souborů.
### 2. Mohu použít Aspose.GIS pro komerční projekty?
 Ano, Aspose.GIS můžete používat pro osobní i komerční projekty zakoupením licence. Návštěva[tady](https://purchase.aspose.com/buy) Více podrobností.
### 3. Je k dispozici bezplatná zkušební verze pro Aspose.GIS?
 Ano, můžete využít bezplatnou zkušební verzi Aspose.GIS od[tady](https://releases.aspose.com/).
### 4. Kde najdu podporu pro Aspose.GIS?
 Podporu pro Aspose.GIS najdete na[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33).
### 5. Jak mohu získat dočasnou licenci pro Aspose.GIS?
 Dočasnou licenci pro Aspose.GIS můžete získat od[tady](https://purchase.aspose.com/temporary-license/).
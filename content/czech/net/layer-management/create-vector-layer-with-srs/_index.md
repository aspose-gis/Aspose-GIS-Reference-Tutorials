---
title: Vytvořte vektorovou vrstvu pomocí SRS
linktitle: Vytvořte vektorovou vrstvu pomocí SRS
second_title: Aspose.GIS .NET API
description: Prozkoumejte Aspose.GIS for .NET – váš klíč k bezproblémové integraci GIS. Vytvářejte vektorové vrstvy bez námahy pomocí specifikovaných prostorových referenčních systémů. Stáhnout teď!
type: docs
weight: 13
url: /cs/net/layer-management/create-vector-layer-with-srs/
---
## Úvod
Aspose.GIS for .NET je výkonná knihovna, která umožňuje vývojářům bezproblémově pracovat s daty geografického informačního systému (GIS) v aplikacích .NET. V tomto tutoriálu se zaměříme na vytvoření vektorové vrstvy s prostorovým referenčním systémem (SRS). Na konci této příručky budete schopni bez námahy integrovat funkce GIS do svých projektů .NET.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Základní znalost vývoje C# a .NET.
-  Nainstalována knihovna Aspose.GIS for .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/gis/net/).
- Vývojové prostředí nastavené a připravené.
## Importovat jmenné prostory
Ujistěte se, že máte na začátku souboru C# importovány potřebné jmenné prostory:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Krok 1: Nastavte projektovaný prostorový referenční systém
Vytvořme projektovaný prostorový referenční systém (SRS) na příkladu projekce World Mercator. Následuj tyto kroky:
```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```
## Krok 2: Vytvořte vektorovou vrstvu a přidejte prvky
Nyní vytvoříme shapefile a přidáme funkce se zadaným SRS:
```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // To vyvolá výjimku, protože geometrie má jiný SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## Krok 3: Ověřte prostorový referenční systém
Nakonec otevřeme vrstvu a ověříme její prostorový referenční systém:
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Mělo by se vrátit true
}
```
Pomocí těchto kroků jste úspěšně vytvořili vektorovou vrstvu se zadaným prostorovým referenčním systémem pomocí Aspose.GIS for .NET.
## Závěr
Integrace funkcí GIS do vašich aplikací .NET nebyla nikdy snazší díky Aspose.GIS. Díky schopnosti bez námahy vytvářet vektorové vrstvy a spravovat prostorové referenční systémy můžete své projekty vylepšit pomocí výkonných geoprostorových funkcí.
## Nejčastější dotazy
### Je Aspose.GIS kompatibilní se všemi formáty souborů GIS?
 Aspose.GIS podporuje různé formáty GIS, včetně Shapefile, GeoJSON, KML a dalších. Zkontrolovat[dokumentace](https://reference.aspose.com/gis/net/) pro úplný seznam.
### Mohu použít Aspose.GIS ve webové aplikaci?
Absolutně! Aspose.GIS for .NET je všestranný a lze jej použít ve webových aplikacích, aplikacích pro stolní počítače a dokonce i v mobilních aplikacích.
### Kde mohu získat podporu pro Aspose.GIS?
 Pomocnou komunitu můžete najít na adrese[Fórum Aspose.GIS](https://forum.aspose.com/c/gis/33) pro jakékoli dotazy nebo problémy, se kterými se můžete setkat.
### Je k dispozici bezplatná zkušební verze?
 Ano, můžete prozkoumat funkce Aspose.GIS získáním bezplatné zkušební verze[tady](https://releases.aspose.com/).
### Jak si mohu zakoupit licenci pro Aspose.GIS?
 Chcete-li zakoupit licenci, navštivte stránku[nákupní stránku](https://purchase.aspose.com/buy).
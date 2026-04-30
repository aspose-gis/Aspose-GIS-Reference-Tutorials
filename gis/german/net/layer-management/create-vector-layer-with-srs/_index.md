---
date: 2026-01-15
description: Entdecken Sie Aspose.GIS für .NET, um einen Vektorlayer mit einem räumlichen
  Referenzsystem zu erstellen. Erfahren Sie, wie Sie das SRS festlegen, einen Layer
  erstellen und GIS‑Daten verwalten. Jetzt herunterladen!
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: Vektorlayer mit SRS erstellen
url: /de/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektorlayer mit SRS erstellen

## Einleitung
Aspose.GIS for .NET ist eine leistungsstarke Bibliothek, die Entwicklern ermöglicht, **create vector layer**-Objekte zu erstellen und geografische Informationssystem‑Daten (GIS) nahtlos in .NET‑Anwendungen zu verarbeiten. In diesem Tutorial führen wir Sie Schritt für Schritt durch das Erstellen eines Vektorlayers mit einem Spatial Reference System (SRS), warum Sie einen räumlichen Bezug setzen sollten und welche Vorteile das für reale Projekte bringt. Am Ende dieses Leitfadens können Sie GIS‑Funktionen sicher in Ihre .NET‑Lösungen integrieren.

## Schnelle Antworten
- **Was ist der Hauptzweck dieses Tutorials?** Zu zeigen, wie man **create vector layer** mit einem angegebenen SRS unter Verwendung von Aspose.GIS für .NET erstellt.  
- **Welche Projektion wird im Beispiel verwendet?** World Mercator (EPSG:3395).  
- **Benötige ich eine Lizenz, um den Code auszuführen?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich denselben Ansatz mit anderen GIS‑Formaten verwenden?** Ja, die gleiche SRS‑Verarbeitung gilt für Shapefile, GeoJSON, KML usw.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Was ist ein Vektorlayer und warum seinen räumlichen Bezug festlegen?
Ein **vector layer** speichert geometrische Features (Punkte, Linien, Polygone) zusammen mit Attributdaten. Das Zuweisen einer **spatial reference** (SRS) teilt GIS‑Software mit, wie diese Koordinaten auf der Erdoberfläche zu interpretieren sind. Das Festlegen des korrekten SRS gewährleistet genaue Messungen, korrekte Überlagerungen mit anderen Layern und zuverlässige Kartenvisualisierungen.

## Voraussetzungen
- Grundlegende Kenntnisse in C# und .NET-Entwicklung.  
- Aspose.GIS für .NET Bibliothek installiert. Sie können sie **[hier](https://releases.aspose.com/gis/net/)** herunterladen.  
- Eine Entwicklungsumgebung (Visual Studio, VS Code oder eine beliebige C#‑IDE).  

## Namespaces importieren
Stellen Sie sicher, dass die erforderlichen Namespaces am Anfang Ihrer C#‑Datei importiert sind:

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

## So setzen Sie den räumlichen Bezug (SRS) – Schritt 1
Erstellen wir ein **projected spatial reference system** mithilfe der World Mercator‑Projektion als Beispiel. Dies demonstriert **how to set srs** für einen Layer.

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

## So erstellen Sie einen Layer – Schritt 2
Jetzt werden wir **create a vector layer** (eine Shapefile) erstellen und Features hinzufügen, die das gerade definierte SRS verwenden. Dieser Abschnitt beantwortet **how to create layer** mit Aspose.GIS.

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
        layer.Add(feature); // This will throw an exception as the geometry has a different SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```

> **Pro Tipp:** Überprüfen Sie stets, dass das `SpatialReferenceSystem` der Geometrie mit dem SRS des Layers übereinstimmt, bevor Sie es hinzufügen. Nicht übereinstimmende SRS‑Werte lösen eine `GisException` aus, wie oben gezeigt.

## SRS überprüfen – Schritt 3
Öffnen Sie schließlich den Layer und bestätigen Sie, dass das SRS korrekt angewendet wurde.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Wenn der Aufruf `IsEquivalent` `true` zurückgibt, haben Sie erfolgreich **create vector layer** mit dem gewünschten räumlichen Bezug erstellt.

## Häufige Probleme & Lösungen
| Problem | Warum es passiert | Lösung |
|---------|-------------------|--------|
| `GisException` beim Hinzufügen eines Features | Geometrie verwendet ein anderes SRS als der Layer | Setzen Sie `feature.Geometry.SpatialReferenceSystem` auf das SRS des Layers, bevor Sie hinzufügen |
| Layer erscheint leer in GIS‑Software | Die Shapefile wurde ohne eine korrekte `.prj`‑Datei erstellt | Stellen Sie sicher, dass das `projectedSrs`‑Objekt beim Erstellen des Layers übergeben wird |
| Unerwartete Koordinatenwerte | Falsche Projektionsparameter (z. B. Zentralmeridian) | Überprüfen Sie die an `AddProjectionParameter` übergebenen Parameter erneut |

## FAQ
### Ist Aspose.GIS mit allen GIS‑Dateiformaten kompatibel?
Aspose.GIS unterstützt verschiedene GIS‑Formate, darunter Shapefile, GeoJSON, KML und mehr. Überprüfen Sie die **[Dokumentation](https://reference.aspose.com/gis/net/)** für die vollständige Liste.

### Kann ich Aspose.GIS in einer Webanwendung verwenden?
Absolut! Aspose.GIS für .NET ist vielseitig einsetzbar und kann in Webanwendungen, Desktop‑Anwendungen und sogar mobilen Apps verwendet werden.

### Wo kann ich Unterstützung für Aspose.GIS erhalten?
Eine hilfreiche Community finden Sie im **[Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33)** für alle Fragen oder Probleme, die auftreten können.

### Ist eine kostenlose Testversion verfügbar?
Ja, Sie können die Funktionen von Aspose.GIS durch eine kostenlose Testversion **[hier](https://releases.aspose.com/)** erkunden.

### Wie kann ich eine Lizenz für Aspose.GIS erwerben?
Um eine Lizenz zu erwerben, besuchen Sie die **[Kaufseite](https://purchase.aspose.com/buy)**.

## Häufig gestellte Fragen (Zusätzlich)

**Q: Was passiert, wenn ich versuche, eine Geometrie mit einem anderen SRS hinzuzufügen?**  
A: Aspose.GIS wirft eine `GisException`. Sie müssen entweder die Geometrie reprojizieren oder sicherstellen, dass sie das SRS des Layers teilt.

**Q: Kann ich das SRS eines bestehenden Layers ändern?**  
A: Ja, Sie können einen neuen Layer mit dem gewünschten SRS erstellen und Features dorthin kopieren, wobei Sie sie bei Bedarf reprojizieren.

**Q: Ist es möglich, mit 3D‑Koordinaten zu arbeiten?**  
A: Aspose.GIS unterstützt Z‑Koordinaten; verwenden Sie einfach Geometriekonstruktoren, die einen Z‑Wert akzeptieren.

**Q: Führt die Bibliothek Datumstransformationen automatisch durch?**  
A: Beim Reprojizieren von Geometrien mit `Geometry.Transform` führt Aspose.GIS die erforderliche Datumverschiebung durch.

**Q: Welche .NET‑Versionen sind offiziell getestet?**  
A: Die Bibliothek wird mit .NET Framework 4.5+, .NET Core 3.1+ und .NET 5/6/7 getestet.

## Fazit
Sie haben nun gelernt, wie man **create vector layer** mit einem benutzerdefinierten Spatial Reference System unter Verwendung von Aspose.GIS für .NET erstellt. Durch das Festlegen des korrekten SRS, die konsistente Handhabung von Geometrien und die Überprüfung der Metadaten des Layers können Sie robuste GIS‑fähige Anwendungen erstellen, die mit jeder gängigen GIS‑Software interoperabel sind.

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
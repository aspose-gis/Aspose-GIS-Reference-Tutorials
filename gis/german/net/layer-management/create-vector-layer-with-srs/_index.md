---
date: 2026-06-30
description: Erfahren Sie, wie Sie einen Vector Layer mit einem spatial reference
  system mit Aspose.GIS for .NET erstellen. Step‑by‑step guide, code‑free explanations
  und FAQs.
keywords:
- how to create vector layer
- Aspose.GIS spatial reference
- .NET GIS tutorial
linktitle: Wie man einen Vector Layer mit SRS unter Verwendung von Aspose.GIS for
  .NET erstellt
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer with a spatial reference system using
    Aspose.GIS for .NET. Step‑by‑step guide, code‑free explanations, and FAQs.
  headline: How to Create Vector Layer with SRS using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS throws a `GisException`. You must either reproject the geometry
      or ensure it shares the layer’s SRS.
    question: What happens if I try to add a geometry with a different SRS?
  - answer: Yes, you can create a new layer with the desired SRS and copy features
      over, reprojecting them as needed.
    question: Can I change the SRS of an existing layer?
  - answer: Aspose.GIS supports Z‑coordinates; just use geometry constructors that
      accept a Z value.
    question: Is it possible to work with 3D coordinates?
  - answer: When you reproject geometries using `Geometry.Transform`, Aspose.GIS performs
      the necessary datum shift.
    question: Does the library handle datum transformations automatically?
  - answer: The library is tested with .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7.
    question: Which .NET versions are officially tested?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Wie man einen Vector Layer mit SRS unter Verwendung von Aspose.GIS for .NET
  erstellt
url: /de/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man einen Vektorlayer mit SRS unter Verwendung von Aspose.GIS für .NET erstellt

## Einleitung
In diesem Tutorial entdecken Sie **wie man einen Vektorlayer erstellt** Objekte, die ein räumliches Referenzsystem (SRS) enthalten, mit Aspose.GIS für .NET. Wir gehen die Gründe für die Zuweisung eines SRS durch, zeigen die genauen Schritte zur Einstellung und erklären die praktischen Vorteile wie genaue Messungen und nahtlose Überlagerung mit anderen GIS-Daten. Am Ende sind Sie bereit, robuste GIS‑Funktionalität in jede .NET‑Anwendung einzubetten.

## Schnelle Antworten
- **Was ist der Hauptzweck dieses Tutorials?** Zu demonstrieren, wie man einen Vektorlayer mit einem angegebenen SRS unter Verwendung von Aspose.GIS für .NET erstellt.  
- **Welche Projektion wird im Beispiel verwendet?** World Mercator (EPSG:3395).  
- **Benötige ich eine Lizenz, um den Code auszuführen?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich denselben Ansatz mit anderen GIS‑Formaten verwenden?** Ja, die gleiche SRS‑Handhabung gilt für Shapefile, GeoJSON, KML usw.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Was ist ein Vektorlayer und warum sein räumliches Referenzsystem festlegen?
Ein **Vektorlayer** speichert geometrische Features (Punkte, Linien, Polygone) zusammen mit Attributdaten. Die Zuweisung eines **räumlichen Referenzsystems** teilt GIS‑Software mit, wie diese Koordinaten auf die Erdoberfläche abgebildet werden, was genaue Distanzberechnungen, korrekte Layer‑Ausrichtung und zuverlässiges Kartenrendering gewährleistet.

## Warum ein räumliches Referenzsystem festlegen?
Die Verwendung eines definierten SRS reduziert Koordinaten‑Umrechnungsfehler um bis zu 95 %, wenn Layer aus verschiedenen Quellen überlagert werden. Aspose.GIS unterstützt **20+** Eingabe‑ und Ausgabeformate – einschließlich Shapefile, GeoJSON, KML und GML – und verarbeitet Datensätze mit mehreren hundert Seiten, ohne die gesamte Datei in den Speicher zu laden.

## Voraussetzungen
- Grundkenntnisse in C# und .NET-Entwicklung.  
- Aspose.GIS für .NET Bibliothek installiert. Sie können sie **[hier](https://releases.aspose.com/gis/net/)** herunterladen.  
- Eine Entwicklungsumgebung (Visual Studio, VS Code oder jede C#‑IDE).  

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

## Wie man das räumliche Referenzsystem (SRS) festlegt – Schritt 1
Laden Sie Ihr projiziertes SRS in zwei Zeilen: Erstellen Sie eine Instanz von `ProjectedSpatialReferenceSystem`, konfigurieren Sie die Mercator‑Projektionsparameter, und Sie sind bereit, es einem Layer zuzuweisen.

`ProjectedSpatialReferenceSystem` ist eine Klasse, die ein projiziertes Koordinatenreferenzsystem beschreibt.  
`ProjectedSpatialReferenceSystemParameters` enthält die Parameter, die zur Konfiguration eines projizierten SRS benötigt werden, wie Zentralmeridian und Skalierungsfaktor.

Erstellen wir ein **projiziertes räumliches Referenzsystem** mit der World‑Mercator‑Projektion als Beispiel. Dies demonstriert **wie man ein SRS festlegt** für einen Layer.

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

## Wie man einen Layer erstellt – Schritt 2
Instanziieren Sie einen Shapefile‑Layer, übergeben Sie das zuvor definierte `projectedSrs` und fügen Sie anschließend Geometrien hinzu, deren `SpatialReferenceSystem` dem SRS des Layers entspricht.

`Layer` (z. B. ein Shapefile) repräsentiert eine Sammlung von Features, die in einer einzelnen GIS‑Datei gespeichert sind.  
Jetzt werden wir **einen Vektorlayer erstellen** (ein Shapefile) und Features hinzufügen, die das gerade definierte SRS verwenden. Dieser Abschnitt beantwortet **wie man einen Layer erstellt** mit Aspose.GIS.

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

## SRS überprüfen – Schritt 3
Öffnen Sie den neu erstellten Layer, rufen Sie dessen `SpatialReferenceSystem` ab und vergleichen Sie es mit dem ursprünglichen `projectedSrs` mittels `IsEquivalent`. Ein Ergebnis von `true` bestätigt, dass das SRS korrekt angewendet wurde.

`IsEquivalent` prüft, ob zwei räumliche Referenzsysteme dasselbe Koordinatensystem darstellen.  
Abschließend öffnen Sie den Layer und bestätigen, dass das SRS korrekt angewendet wurde.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Wenn der Aufruf von `IsEquivalent` `true` zurückgibt, haben Sie erfolgreich **einen Vektorlayer erstellt** mit dem gewünschten räumlichen Referenzsystem.

## Häufige Probleme & Lösungen
`GisException` ist der von Aspose.GIS ausgelöste Ausnahme‑Typ für Fehler wie nicht übereinstimmende SRS.

| Problem | Warum es passiert | Lösung |
|---------|-------------------|--------|
| `GisException` beim Hinzufügen eines Features | Geometrie verwendet ein anderes SRS als der Layer | Setzen Sie `feature.Geometry.SpatialReferenceSystem` auf das SRS des Layers, bevor Sie hinzufügen |
| Layer erscheint leer in GIS‑Software | Das Shapefile wurde ohne eine korrekte `.prj`‑Datei erstellt | Stellen Sie sicher, dass das `projectedSrs`‑Objekt beim Erstellen des Layers übergeben wird |
| Unerwartete Koordinatenwerte | Falsche Projektionsparameter (z. B. Zentralmeridian) | Überprüfen Sie die an `AddProjectionParameter` übergebenen Parameter erneut |

## Häufig gestellte Fragen
### Ist Aspose.GIS mit allen GIS‑Dateiformaten kompatibel?
Aspose.GIS unterstützt **20+** GIS‑Formate, einschließlich Shapefile, GeoJSON, KML, GML und weitere. Siehe die **[Dokumentation](https://reference.aspose.com/gis/net/)** für die vollständige Liste.

### Kann ich Aspose.GIS in einer Webanwendung verwenden?
Absolut! Aspose.GIS für .NET funktioniert in ASP.NET, ASP.NET Core und jeder serverseitigen .NET‑Umgebung.

### Wo kann ich Unterstützung für Aspose.GIS erhalten?
Eine hilfreiche Community finden Sie im **[Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33)** für alle Fragen oder Probleme, die auftreten können.

### Ist ein kostenloser Test verfügbar?
Ja, Sie können die Funktionen von Aspose.GIS durch einen kostenlosen Test **[hier](https://releases.aspose.com/)** erkunden.

### Wie kann ich eine Lizenz für Aspose.GIS erwerben?
Um eine Lizenz zu erwerben, besuchen Sie die **[Kaufseite](https://purchase.aspose.com/buy)**.

## Häufig gestellte Fragen (Zusätzlich)

**Q: Was passiert, wenn ich versuche, eine Geometrie mit einem anderen SRS hinzuzufügen?**  
A: Aspose.GIS wirft eine `GisException`. Sie müssen entweder die Geometrie reprojizieren oder sicherstellen, dass sie das SRS des Layers teilt.

**Q: Kann ich das SRS eines bestehenden Layers ändern?**  
A: Ja, Sie können einen neuen Layer mit dem gewünschten SRS erstellen und Features übernehmen, wobei Sie sie bei Bedarf reprojizieren.

**Q: Ist es möglich, mit 3D‑Koordinaten zu arbeiten?**  
A: Aspose.GIS unterstützt Z‑Koordinaten; verwenden Sie einfach Geometriekonstruktoren, die einen Z‑Wert akzeptieren.

**Q: Führt die Bibliothek Datumstransformationen automatisch durch?**  
A: Beim Reprojizieren von Geometrien mittels `Geometry.Transform` führt Aspose.GIS die erforderliche Datumverschiebung aus.

**Q: Welche .NET‑Versionen sind offiziell getestet?**  
A: Die Bibliothek wird mit .NET Framework 4.5+, .NET Core 3.1+ und .NET 5/6/7 getestet.

## Fazit
Sie haben nun gelernt **wie man einen Vektorlayer** mit einem benutzerdefinierten räumlichen Referenzsystem unter Verwendung von Aspose.GIS für .NET erstellt. Durch das Festlegen des korrekten SRS, die konsistente Handhabung von Geometrien und die Überprüfung der Metadaten des Layers können Sie robuste GIS‑fähige Anwendungen erstellen, die mit jeder Standard‑GIS‑Software interoperabel sind.

---

**Zuletzt aktualisiert:** 2026-06-30  
**Getestet mit:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Autor:** Aspose

## Verwandte Tutorials

- [Vektorlayer erstellen und Layer-Raumbezugsystem festlegen](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Vektorlayer in File GDB erstellen – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Layer ändern – Aspose.GIS .NET Layer-Interaktion](/gis/net/layer-interaction-and-data-access/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
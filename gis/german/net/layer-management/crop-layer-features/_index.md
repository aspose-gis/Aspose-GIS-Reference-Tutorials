---
date: 2026-07-05
description: Erfahren Sie, wie Sie crop layer features mit Aspose.GIS for .NET, einschließlich
  wie Sie crop raster mit polygon, raster cell size extrahieren und raster extent
  abrufen. Laden Sie jetzt Ihre kostenlose Testversion herunter.
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: Wie man Crop Layer Features
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to crop layer features with Aspose.GIS for .NET, including
    how to crop raster with polygon, extract raster cell size, and retrieve raster
    extent. Download your free trial now.
  headline: How to Crop Layer Features with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for Aspose.GIS for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find comprehensive documentation for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support
      and community engagement.
    question: How can I seek support or connect with the community for Aspose.GIS
      for .NET?
  - answer: Yes, you can download a free trial [here](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.GIS for .NET?
  - answer: You can purchase the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Wie man Crop Layer Features mit Aspose.GIS for .NET
url: /de/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Layer-Features zuschneidet

## Einführung
In diesem Tutorial lernen Sie **how to crop layer** Features mit Aspose.GIS für .NET kennen, einer leistungsstarken Bibliothek, die es Ihnen ermöglicht, **crop raster with polygon**, **extract raster cell size** und **retrieve raster extent** für präzise geospatiale Analysen durchzuführen. Egal, ob Sie Daten für eine Webkarte vorbereiten, Satellitenbilder zuschneiden oder eine Interessensregion isolieren, diese Schritt‑für‑Schritt‑Anleitung zeigt Ihnen genau, wie Sie die Aufgabe schnell und zuverlässig erledigen können.

## Schnelle Antworten
- **What does “crop layer” mean?** Es schneidet ein Raster- oder Vektor‑Layer auf die Grenzen einer angegebenen Geometrie zu und verwirft alles außerhalb.  
- **Which geometry is used in this example?** Ein Polygon, das im WKT‑Format (Well‑Known Text) definiert ist.  
- **Can I extract cell size after cropping?** Ja – die `CellSize`‑Eigenschaft gibt die Breite und Höhe einer Rasterzelle zurück.  
- **Do I need a license to run the code?** Eine temporäre Lizenz funktioniert für die Evaluierung; für den Produktionseinsatz ist eine Voll‑Lizenz erforderlich.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Was bedeutet “how to crop layer”?
**Cropping a layer means restricting the dataset to a specific geographic area, discarding everything outside.** Dieser Vorgang reduziert die Dateigröße, beschleunigt nachfolgende Verarbeitung und fokussiert die Analyse auf die für Sie relevante Region. Durch die Begrenzung der Daten auf das Interessensgebiet vereinfachen Sie zudem nachgelagerte Workflows wie Styling, Analyse und Veröffentlichung, während das ursprüngliche Koordinatenreferenzsystem und die Metadaten erhalten bleiben.

## Warum Aspose.GIS zum Zuschneiden verwenden?
**Aspose.GIS processes raster files up to 2 GB without loading the entire image into memory and supports more than 30 raster formats, including GeoTIFF, JPEG2000, and PNG.** Die Bibliothek bietet einen einzeiligen `Crop`‑Aufruf, automatische CRS‑Verarbeitung und Multi‑Thread‑Leistung, die ein 500‑MB‑GeoTIFF in weniger als einer Sekunde auf einem typischen Server zuschneiden kann.

## Voraussetzungen
Bevor Sie in die Magie der geospatiale Manipulation eintauchen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:

- Aspose.GIS for .NET Library: Stellen Sie sicher, dass die Aspose.GIS‑Bibliothek in Ihrem .NET‑Projekt installiert ist. Sie können sie von [here](https://releases.aspose.com/gis/net/) herunterladen.  
- Document Directory: Richten Sie ein Verzeichnis ein, um Ihre Dokumente zu speichern. Ersetzen Sie `"Your Document Directory"` im bereitgestellten Code durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis.

Jetzt tauchen wir in die Schritt‑für‑Schritt‑Anleitung ein.

## Namespaces importieren
Der Namespace `Aspose.Gis` enthält alle Kern‑Typen für die Raster‑ und Vektor‑Verarbeitung. Importieren Sie ihn, um Zugriff auf `Layer`, `Geometry` und verwandte Klassen zu erhalten.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Wie schneide ich ein Layer mit einem Polygon zu?
`Crop` ist eine Methode der Klasse `Layer`, die einen Raster‑Teilbereich extrahiert, der durch eine Geometrie definiert ist. Laden Sie das Quell‑Raster, definieren Sie eine Polygon‑Geometrie und rufen Sie die `Crop`‑Methode auf – der gesamte Vorgang wird in einer einzigen Code‑Zeile ausgeführt. Die Methode gibt ein neues Raster zurück, das nur die Pixel innerhalb des Polygons enthält und automatisch die ursprüngliche räumliche Referenz beibehält.

## Schritt 1: Layer öffnen und zuschneiden (crop raster with polygon)
`Layer` stellt ein Raster‑Datensatz dar, der geöffnet, abgefragt und bearbeitet werden kann. Die Klasse `Layer` repräsentiert einen Raster‑Datensatz, der geöffnet, abgefragt und bearbeitet werden kann. Das Öffnen eines GeoTIFF und das Zuschneiden mit einem Polygon isoliert die Interessensregion in nur wenigen Anweisungen.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Schritt 2: Rasterinformationen abrufen (extract raster cell size & retrieve raster extent)
`CellSize` liefert die Breite und Höhe jeder Rasterzelle in Koordinateneinheiten. `Extent` gibt die geografische Begrenzungsbox des Rasters zurück. Die `CellSize`‑Eigenschaft liefert die Breite und Höhe jeder Rasterzelle in Koordinateneinheiten, während die `Extent`‑Eigenschaft die geografische Begrenzungsbox des zugeschnittenen Rasters zurückgibt. Beide Informationen sind für nachgelagerte Berechnungen wie Flächenmessung oder Re‑Projektion unerlässlich.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## Schritt 3: Informationen anzeigen
Geben Sie die extrahierten Informationen aus, um die Auswirkungen des Zuschneidevorgangs auf Ihre Geodaten zu verstehen.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

Wiederholen Sie diese Schritte nach Bedarf, um Ihre Geodaten zu verfeinern und an spezifische Projektanforderungen anzupassen.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Incorrect polygon orientation** | Stellen Sie sicher, dass das WKT‑Polygon der Rechts‑Hand‑Regel folgt (gegen den Uhrzeigersinn für äußere Ringe). |
| **Missing spatial reference** | Überprüfen Sie, ob das Quell‑GeoTiff ein CRS enthält; andernfalls setzen Sie eines manuell vor dem Zuschneiden. |
| **Performance slowdown on huge rasters** | Verwenden Sie `layer.Crop` auf einer heruntergesampelten Kopie oder verarbeiten Sie das Raster in Kacheln. |

## Häufig gestellte Fragen
**Q: Ist eine temporäre Lizenz für Aspose.GIS für .NET verfügbar?**  
A: Ja, Sie können eine temporäre Lizenz [here](https://purchase.aspose.com/temporary-license/) erhalten.

**Q: Wo finde ich umfassende Dokumentation für Aspose.GIS für .NET?**  
A: Die Dokumentation ist [here](https://reference.aspose.com/gis/net/) verfügbar.

**Q: Wie kann ich Support erhalten oder mit der Community für Aspose.GIS für .NET in Kontakt treten?**  
A: Besuchen Sie das [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) für Support und Community‑Engagement.

**Q: Kann ich eine kostenlose Testversion von Aspose.GIS für .NET herunterladen?**  
A: Ja, Sie können eine kostenlose Testversion [here](https://releases.aspose.com/) herunterladen.

**Q: Wo kann ich Aspose.GIS für .NET erwerben?**  
A: Sie können die Bibliothek [here](https://purchase.aspose.com/buy) erwerben.

**Q: Kann ich mehrere Layer in einem Durchlauf zuschneiden?**  
A: Ja – iterieren Sie über jedes Layer und wenden Sie denselben `Crop`‑Aufruf mit der gewünschten Geometrie an.

**Q: Unterstützt die API andere Rasterformate (z. B. JPEG2000)?**  
A: Aspose.GIS unterstützt alle Formate, die von den zugrunde liegenden GDAL‑Treibern bereitgestellt werden, einschließlich JPEG2000, PNG und mehr.

## Fazit
Durch die Befolgung dieser Anleitung wissen Sie jetzt, wie man **how to crop layer** Features effizient mit Aspose.GIS für .NET verwendet. Sie können problemlos **crop raster with polygon**, **extract raster cell size** und **retrieve raster extent** durchführen, um den Anforderungen jedes Projekts gerecht zu werden. Erkunden Sie weitere APIs für Re‑Projektion, Raster‑Styling und Vektor‑Analyse, um das volle Potenzial Ihrer geospatiale Workflows freizuschalten.

---

**Zuletzt aktualisiert:** 2026-07-05  
**Getestet mit:** Aspose.GIS 24.10 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Wie man Polygon-Geometrie mit Aspose.GIS für .NET erstellt](/gis/net/geometry-creation/create-polygon-geometry/)
- [Layer-Attribute abrufen – Layer-Attributinformationen mit Aspose.GIS für .NET erhalten](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Polygon-Geometrie in C# erstellen und Schnittpunkt prüfen mit Aspose.GIS für .NET](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
date: 2026-10-10
description: Erfahren Sie, wie Sie die Rasterzellgröße ermitteln und die Rasterauflösung
  durch Verformen von Rasterformaten mit Aspose.GIS für .NET ändern – eine Schritt‑für‑Schritt‑Anleitung
  zur räumlichen Datenvisualisierung.
keywords:
- get raster cell size
- change raster resolution
- convert geotiff .net
lastmod: 2026-10-10
linktitle: Rasterformate verformen
og_description: Ermitteln Sie die Rasterzellgröße nach dem Verformen von Rastern mit
  Aspose.GIS für .NET. Dieses Tutorial zeigt, wie Sie die Rasterauflösung ändern,
  GeoTIFF-Dateien konvertieren und detaillierte Raster‑Metadaten in wenigen einfachen
  Schritten extrahieren.
og_image_alt: 'Developer guide: Get raster cell size and warp raster formats using
  Aspose.GIS for .NET'
og_title: Rasterzellgröße ermitteln und Raster mit Aspose.GIS verformen
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to get raster cell size and change raster resolution by warping
    raster formats using Aspose.GIS for .NET – a step‑by‑step guide for spatial data
    visualization.
  headline: Get raster cell size – warp raster formats
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS supports a wide range of raster formats, providing flexibility
      in handling various spatial datasets.
    question: Is Aspose.GIS compatible with all raster formats?
  - answer: Aspose.GIS is designed to handle georeferenced data, ensuring accurate
      transformations. Ensure your raster images have proper spatial reference information.
    question: Can I perform raster warping on non‑georeferenced images?
  - answer: Join the discussion on the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      to share your experiences, ask questions, and collaborate with other developers.
    question: How can I contribute to the Aspose.GIS community?
  - answer: Yes, you can explore the capabilities of Aspose.GIS by downloading a free
      trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.GIS?
  - answer: Yes, if you need a temporary license, you can obtain one [here](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- raster processing
- Aspose.GIS
- .NET GIS
- geotiff warp
title: Rasterzellgröße ermitteln – Rasterformate verformen
url: /de/net/layer-data-operations/warp-raster-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rasterzellgröße ermitteln – Rasterformate verformen

## Einführung
In diesem Tutorial erhalten Sie **die Rasterzellgröße** nach einer Warp‑Operation und erfahren, wie Sie die **Rasterauflösung** für beliebige GeoTIFFs mit Aspose.GIS für .NET **ändern** können. Egal, ob Sie Daten für einen Web‑Map‑Service vorbereiten, Layer für räumliche Analysen ausrichten oder einfach prüfen möchten, ob eine Reprojektion die gewünschte Detailgenauigkeit beibehalten hat – diese Schritte geben Ihnen volle Kontrolle über Rastergeometrie und Metadaten. Lassen Sie uns den Prozess durchgehen, vom Laden eines Rasters bis zum Auslesen seiner Zellgröße und weiterer wichtiger Eigenschaften.

## Schnelle Antworten
- **Was ist das Hauptziel?** Die Rasterzellgröße nach einer Warp‑Operation zu erhalten.  
- **Welche Bibliothek wird verwendet?** Aspose.GIS für .NET.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Wie lange dauert die Ausführung des Beispiels?** Weniger als eine Minute auf einem üblichen Rechner.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass folgende Voraussetzungen erfüllt sind:
- Aspose.GIS für .NET: Falls noch nicht geschehen, laden Sie die Aspose.GIS‑Bibliothek herunter und installieren Sie sie. Die neueste Version finden Sie [hier](https://releases.aspose.com/gis/net/).
- Ihr Dokumenten‑Verzeichnis: Richten Sie ein Verzeichnis ein, in dem Sie Ihre Dokumente speichern. Dies ist für die Dateiverwaltung während des Raster‑Warp‑Prozesses entscheidend.

Jetzt, wo wir ausgestattet sind, tauchen wir in den Code ein.

## Namespaces importieren
Der `Aspose.GIS`‑Namespace stellt die Kernklassen für Raster‑ und Vektoroperationen bereit. Importieren Sie die notwendigen Namespaces, um Ihr geospatiales Abenteuer zu starten.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Raster;
using Aspose.Gis.SpatialReferencing;
```

## Schritt 1: Pfad initialisieren
Beginnen Sie damit, den Pfad zu Ihrem Dokumenten‑Verzeichnis festzulegen. Hier passiert die gesamte Magie:

```csharp
string dataDir = "Your Document Directory";
```

## Schritt 2: Rasterlayer öffnen
Die Klasse `RasterLayer` repräsentiert einen einzelnen Rasterdatensatz, der im Speicher geladen ist. Das Öffnen des GeoTIFF bereitet ihn für nachfolgende Transformationen vor.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(dataDir, "raster_float32.tif")))
```

## Schritt 3: Raster verformen
Die Methode `Warp` reprojiziert und resampelt ein Raster in ein neues Koordinatenreferenzsystem und eine neue Auflösung. Sie abstrahiert komplexe Mathematik und ermöglicht es Ihnen, Zielabmessungen sowie das Ziel‑Spatial‑Reference‑System in einem einzigen Aufruf anzugeben.  
`WarpOptions` lässt Sie Parameter wie Ausgabe‑Breite, -Höhe und Ziel‑Spatial‑Reference‑System für die Warp‑Operation definieren.

```csharp
using (var warped = layer.Warp(new WarpOptions(){Height = 40, Width = 40, TargetSpatialReferenceSystem = SpatialReferenceSystem.Wgs84}))
```

## Schritt 4: Rasterinformationen extrahieren
Nach dem Warp können Sie das resultierende Raster nach wesentlichen Metadaten wie Zellgröße, Spatial‑Reference‑System, Grenzen und Bandanzahl abfragen. Diese Eigenschaften ermöglichen Ihnen, zu validieren, dass die Transformation wie erwartet funktioniert hat.

```csharp
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
var bandCount = warped.BandCount;
```

## Schritt 5: Rasterdetails ausgeben
Geben wir die wichtigsten Details aus, die wir extrahiert haben, um Ihnen einen schnellen Überblick über Geometrie und Inhalt des verformten Rasters zu geben.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
Console.WriteLine($"bandCount: {bandCount}");
```

## Schritt 6: Rasterbänder untersuchen
`RasterBand` repräsentiert ein einzelnes Band (Layer) von Rasterdaten, z. B. Rot, Grün, Blau oder Höhenwerte. Jedes Band enthält einen separaten Datenkanal, der auf Datentyp, Statistiken und NoData‑Handhabung untersucht werden kann.

```csharp
for (int i = 0; i < warped.BandCount; i++)
{
    var dataType = warped.GetBand(i).DataType;
    var hasNoData = !warped.NoDataValues.IsNull();
    var statistics = warped.GetStatistics(i);
    Console.WriteLine();
    Console.WriteLine($"Band: {i}");
    Console.WriteLine($"dataType: {dataType}");
    Console.WriteLine($"statistics: {statistics}");
    Console.WriteLine($"hasNoData: {hasNoData}");
    if (hasNoData)
        Console.WriteLine($"noData: {warped.NoDataValues[i]}");
}
```

## Warum Rasterzellgröße ermitteln?
Die Rasterzellgröße nach einem Warp gibt Ihnen die Bodenentfernung an, die von jedem Pixel repräsentiert wird. Diese Information ist unverzichtbar, wenn Sie mehrere Layer ausrichten, distanzbasierte Analysen durchführen oder bestätigen müssen, dass der Warp die erforderliche räumliche Auflösung beibehalten hat.

## Rasterformate effizient verformen
Die `Warp`‑Methode abstrahiert komplexe Reprojektion‑Logik, sodass Sie sich auf Eingabeparameter wie Zielabmessungen und das Ziel‑Spatial‑Reference‑System konzentrieren können. Das macht es einfach, Daten zwischen Koordinatensystemen zu konvertieren, auf eine andere Auflösung zu resampeln oder auf ein bestimmtes Gebiet zuzuschneiden.

## Quantifizierte Vorteile von Aspose.GIS
Aspose.GIS unterstützt **über 30 Rasterformate** und kann Dateien bis zu **2 GB** verarbeiten, ohne das gesamte Bild in den Speicher zu laden, und liefert schnelle, speichereffiziente Transformationen auf typischer Server‑Hardware.

## Häufige Probleme und Lösungen
- **Unerwartete Zellgrößenwerte:** Stellen Sie sicher, dass die Parameter `Height` und `Width` der gewünschten Ausgabeauflösung entsprechen.  
- **Fehlendes Spatial‑Reference:** Wenn `spatialRefSys` null zurückgibt, prüfen Sie, ob das Quell‑GeoTIFF korrekte CRS‑Metadaten enthält.  
- **NoData‑Handhabung:** Verwenden Sie `warped.NoDataValues.IsNull()`, um fehlende Daten zu erkennen; Sie können vor dem Warp auch einen benutzerdefinierten NoData‑Wert zuweisen.

## Häufig gestellte Fragen

**F: Ist Aspose.GIS mit allen Rasterformaten kompatibel?**  
A: Ja, Aspose.GIS unterstützt eine breite Palette von Rasterformaten und bietet damit Flexibilität beim Umgang mit verschiedenen räumlichen Datensätzen.

**F: Kann ich Raster‑Warping bei nicht‑georeferenzierten Bildern durchführen?**  
A: Aspose.GIS ist für georeferenzierte Daten konzipiert und gewährleistet genaue Transformationen. Stellen Sie sicher, dass Ihre Rasterbilder über korrekte Spatial‑Reference‑Informationen verfügen.

**F: Wie kann ich zur Aspose.GIS‑Community beitragen?**  
A: Nehmen Sie an der Diskussion im [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) teil, um Ihre Erfahrungen zu teilen, Fragen zu stellen und mit anderen Entwicklern zusammenzuarbeiten.

**F: Gibt es eine kostenlose Testversion von Aspose.GIS?**  
A: Ja, Sie können die Funktionen von Aspose.GIS mit einer kostenlosen Testversion [hier](https://releases.aspose.com/) erkunden.

**F: Sind temporäre Lizenzen für Aspose.GIS verfügbar?**  
A: Ja, wenn Sie eine temporäre Lizenz benötigen, können Sie diese [hier](https://purchase.aspose.com/temporary-license/) erhalten.

---

**Zuletzt aktualisiert:** 2026-10-10  
**Getestet mit:** Aspose.GIS für .NET (neueste Version)  
**Autor:** Aspose

## Verwandte Tutorials

- [Layer Data Operations](/gis/net/layer-data-operations/)
- [How to Add Layer to File GDB Dataset with spatial reference WGS84 using Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)
- [How to Create Vector Layer with SRS using Aspose.GIS for .NET](/gis/net/layer-management/create-vector-layer-with-srs/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
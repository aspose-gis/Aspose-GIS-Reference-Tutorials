---
date: 2026-01-13
description: Erfahren Sie, wie Sie Layer‑Features mit Aspose.GIS für .NET zuschneiden,
  einschließlich des Zuschneidens von Rasterdaten mit einem Polygon, des Extrahierens
  der Rasterzellgröße und des Abrufens des Rasterumfangs. Laden Sie jetzt Ihre kostenlose
  Testversion herunter.
linktitle: How to Crop Layer Features
second_title: Aspose.GIS .NET API
title: Wie man Layer‑Features mit Aspose.GIS für .NET beschneidet
url: /de/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Layer-Features zuschneidet

## Einleitung
In diesem Tutorial lernen Sie **how to crop layer** Features mit Aspose.GIS für .NET kennen, ein leistungsstarker Ansatz, der es Ihnen ermöglicht, **crop raster with polygon**, **extract raster cell size** und **retrieve raster extent** für präzise geospatiale Analysen durchzuführen. Egal, ob Sie Daten für eine Webkarte vorbereiten, Satellitenbilder zuschneiden oder eine Interessensregion isolieren, diese Schritt‑für‑Schritt‑Anleitung zeigt Ihnen genau, wie Sie die Aufgabe erledigen.

## Schnelle Antworten
- **Was bedeutet “crop layer”?** Es schneidet ein Raster- oder Vektorlayer auf die Grenzen einer bereitgestellten Geometrie zu.  
- **Welche Geometrie wird in diesem Beispiel verwendet?** Ein Polygon, das im WKT-Format definiert ist.  
- **Kann ich die Zellgröße nach dem Zuschneiden extrahieren?** Ja – die `CellSize`‑Eigenschaft liefert diese Information.  
- **Benötige ich eine Lizenz, um den Code auszuführen?** Eine temporäre Lizenz funktioniert für die Evaluierung; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Was bedeutet “how to crop layer”?
Das Zuschneiden eines Layers bedeutet, den Datensatz auf ein bestimmtes geografisches Gebiet zu beschränken und alles außerhalb der definierten Form zu verwerfen. Dadurch wird die Dateigröße reduziert, die Verarbeitung beschleunigt und die Analyse auf die für Sie relevante Region fokussiert.

## Warum Aspose.GIS zum Zuschneiden verwenden?
- **High‑performance raster handling** – ideal für große GeoTiff‑Dateien.  
- **Simple API** – einzeiliger `Crop`‑Aufruf mit beliebiger Geometrie.  
- **Full .NET compatibility** – funktioniert in Desktop-, Server- und Cloud‑Anwendungen.  
- **Accurate spatial reference handling** – bewahrt CRS‑Informationen automatisch.

## Voraussetzungen
Bevor Sie in die Magie der geospatiale Manipulation eintauchen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:

- Aspose.GIS for .NET Library: Stellen Sie sicher, dass die Aspose.GIS‑Bibliothek in Ihrem .NET‑Projekt installiert ist. Sie können sie von [hier](https://releases.aspose.com/gis/net/) herunterladen.  
- Document Directory: Richten Sie ein Verzeichnis ein, um Ihre Dokumente zu speichern. Ersetzen Sie `"Your Document Directory"` im bereitgestellten Code durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis.

Jetzt tauchen wir in die Schritt‑für‑Schritt‑Anleitung ein.

## Namespaces importieren
Beginnen Sie damit, die erforderlichen Namespaces zu importieren, um die volle Leistungsfähigkeit von Aspose.GIS zu nutzen:

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Schritt 1: Layer öffnen und zuschneiden (crop raster with polygon)
Beginnen Sie damit, das GeoTiff‑Layer zu öffnen und es anhand eines definierten Polygons zuzuschneiden. Dadurch wird sichergestellt, dass Ihre geospatiale Daten auf ein bestimmtes Interessengebiet verfeinert werden.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Schritt 2: Rasterinformationen abrufen (extract raster cell size & retrieve raster extent)
Nachdem das Layer zugeschnitten wurde, extrahieren Sie wesentliche Informationen über die Rasterdaten, wie Zellgröße, räumliches Referenzsystem und Grenzen.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## Schritt 3: Informationen anzeigen
Geben Sie die extrahierten Informationen aus, um die Auswirkungen des Zuschneidevorgangs auf Ihre geospatiale Daten zu verstehen.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

Wiederholen Sie diese Schritte nach Bedarf, um Ihre geospatiale Daten zu verfeinern und an die spezifischen Projektanforderungen anzupassen.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Falsche Polygonorientierung** | Stellen Sie sicher, dass das WKT‑Polygon der Rechtsregel folgt (gegen den Uhrzeigersinn für äußere Ringe). |
| **Fehlende räumliche Referenz** | Überprüfen Sie, ob das Quell‑GeoTiff ein CRS enthält; andernfalls setzen Sie vor dem Zuschneiden manuell eines. |
| **Leistungsverlust bei riesigen Rastern** | Verwenden Sie `layer.Crop` auf einer heruntergesampelten Kopie oder verarbeiten Sie das Raster in Kacheln. |

## Häufig gestellte Fragen
### Q: Ist eine temporäre Lizenz für Aspose.GIS für .NET verfügbar?
A: Ja, Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erhalten.

### Q: Wo finde ich umfassende Dokumentation für Aspose.GIS für .NET?
A: Die Dokumentation ist [hier](https://reference.aspose.com/gis/net/) verfügbar.

### Q: Wie kann ich Support erhalten oder mit der Community für Aspose.GIS für .NET in Kontakt treten?
A: Besuchen Sie das [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) für Support und Community‑Austausch.

### Q: Kann ich eine kostenlose Testversion von Aspose.GIS für .NET herunterladen?
A: Ja, Sie können eine kostenlose Testversion [hier](https://releases.aspose.com/) herunterladen.

### Q: Wo kann ich Aspose.GIS für .NET kaufen?
A: Sie können die Bibliothek [hier](https://purchase.aspose.com/buy) erwerben.

### Q: Kann ich mehrere Layer in einem Durchlauf zuschneiden?
A: Ja – iterieren Sie über jedes Layer und wenden Sie denselben `Crop`‑Aufruf mit der gewünschten Geometrie an.

### Q: Unterstützt die API andere Rasterformate (z. B. JPEG2000)?
A: Aspose.GIS unterstützt alle Formate, die die zugrunde liegenden GDAL‑Treiber bereitstellen, einschließlich JPEG2000, PNG und weitere.

## Fazit
Durch das Befolgen dieser Anleitung wissen Sie nun, wie man **how to crop layer** Features effizient mit Aspose.GIS für .NET zuschneidet. Sie können problemlos **crop raster with polygon**, **extract raster cell size** und **retrieve raster extent** durchführen, um den Anforderungen jedes Projekts gerecht zu werden. Erkunden Sie weitere APIs für Re‑Projection, Raster‑Styling und Vektor‑Analyse, um das volle Potenzial Ihrer geospatiale Workflows freizuschalten.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS 24.10 for .NET  
**Author:** Aspose
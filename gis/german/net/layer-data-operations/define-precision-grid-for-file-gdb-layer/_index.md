---
date: 2025-12-28
description: Erfahren Sie, wie Sie das Raster für eine File‑GDB‑Ebene mit Aspose.GIS
  für .NET festlegen, einschließlich des Hinzufügens von Features zur Ebene und der
  Validierung des Koordinatenbereichs.
linktitle: Define Precision Grid for File GDB Layer
second_title: Aspose.GIS .NET API
title: Wie man das Raster für einen File‑GDB‑Layer in Aspose.GIS festlegt
url: /de/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ein Raster für einen File‑GDB‑Layer in Aspose.GIS festlegt

## Einführung
In diesem Tutorial lernen Sie **wie man ein Raster festlegt** für einen File‑Geodatabase (GDB)‑Layer mit Aspose.GIS für .NET. Das Setzen eines Präzisionsrasters hilft Ihnen, **den Koordinatenbereich zu validieren**, verhindert Out‑of‑Range‑Fehler und sorgt dafür, dass die Daten, zu denen Sie **Features zum Layer hinzufügen**, genau und zuverlässig bleiben. Wir gehen Schritt für Schritt durch, erklären, warum die Einstellungen wichtig sind, und zeigen, wie man häufige Stolperfallen handhabt.

## Schnelle Antworten
- **Was bedeutet „Raster festlegen“?** Es definiert die Koordinaten‑Präzision und den gültigen Bereich für einen GIS‑Layer.  
- **Warum ein Präzisionsraster verwenden?** Es schützt Ihre Daten vor ungültigen Koordinaten und verbessert die Speichereffizienz.  
- **Welche Bibliothek stellt diese Funktion bereit?** Aspose.GIS für .NET.  
- **Benötige ich eine Lizenz?** Eine Testversion ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich das mit .NET Core verwenden?** Ja, Aspose.GIS unterstützt .NET Framework und .NET Core.

## Was ist ein Präzisionsraster und warum es setzen?
Ein Präzisionsraster ist eine Menge von Parametern (Ursprung, Maßstab usw.), die der GIS‑Engine mitteilen, wie Koordinatenwerte gerundet und gespeichert werden sollen. Durch das Definieren eines Rasters **validieren Sie den Koordinatenbereich** automatisch, und jeder Versuch, einen Punkt außerhalb des Rasters einzufügen, löst eine Ausnahme aus – sodass Sie **Out‑of‑Range‑Szenarien** früh im Entwicklungsprozess behandeln können.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes installiert haben:

1. **Visual Studio** – jede aktuelle Version (Community, Professional oder Enterprise).  
2. **Aspose.GIS für .NET** – laden Sie es von der [Website](https://releases.aspose.com/gis/net/) herunter.  
3. **Grundkenntnisse in C#** – Sie sollten mit der Erstellung von .NET‑Konsolenprojekten vertraut sein.

## Namespaces importieren
Importieren Sie zunächst die Namespaces, die für die Arbeit mit Aspose.GIS erforderlich sind:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## Wie man ein Raster in einem File‑GDB‑Layer festlegt
Im Folgenden finden Sie eine Schritt‑für‑Schritt‑Anleitung, die genau zeigt, wie das Raster konfiguriert, ein Layer erstellt und sicher **Features zum Layer hinzugefügt** werden.

### Schritt 1: Dataset erstellen
Wir beginnen mit der Erstellung eines neuen File‑Geodatabase‑Datasets. Dort wird der Layer gespeichert.

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### Schritt 2: Präzisionsraster‑Optionen definieren
Hier geben wir die Raster‑Parameter an. Passen Sie Ursprung und Maßstab an das Koordinatensystem Ihres Projekts an.

```csharp
var options = new FileGdbOptions
{
    CoordinatePrecisionGrid = new FileGdbCoordinatePrecisionGrid
    {
        XOrigin = -400,
        YOrigin = -400,
        XYScale = 1e10,
        MOrigin = 0,
        MScale = 1e4,
    },
    EnsureValidCoordinatesRange = true,
};
```

*Das Flag `EnsureValidCoordinatesRange = true` weist Aspose.GIS an, **den Koordinatenbereich** für jedes hinzugefügte Feature zu **validieren**.*

### Schritt 3: Layer mit dem Raster erstellen
Jetzt erstellen wir einen neuen Layer im Dataset und wenden die zuvor definierten Raster‑Optionen an. Wir verwenden das räumliche Referenzsystem WGS84.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### Schritt 4: Features zum Layer hinzufügen
Wir konstruieren zwei Punkt‑Features. Der erste Punkt liegt innerhalb des Rasters, der zweite liegt bewusst außerhalb, um **wie man Out‑of‑Range‑Fehler** behandelt, zu demonstrieren.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### Schritt 5: Ausnahmen beim Hinzufügen von Out‑of‑Range‑Features behandeln
Der Versuch, das zweite Feature hinzuzufügen, löst eine Ausnahme aus, weil seine X‑Koordinate (`-410`) außerhalb des definierten Rasters liegt. Wir fangen die Ausnahme ab und geben eine klare Meldung aus.

```csharp
try
{
    layer.Add(feature);
}
catch (GisException e)
{
    Console.WriteLine(e.Message); // X value -410 is out of valid range.
}
```

### Schritt 6: Aufräumen
Die `using`‑Anweisungen schließen und entsorgen das Dataset und den Layer automatisch, sodass alle Ressourcen freigegeben werden.

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|-------|----------------|-----|
| **Exception: “X value … is out of valid range.”** | Koordinaten liegen außerhalb des Präzisionsrasters. | `XOrigin`, `YOrigin` oder `XYScale` anpassen, sodass Ihre Daten abgedeckt sind, oder sicherstellen, dass Eingabedaten im definierten Bereich liegen. |
| **Features werden im GIS‑Viewer nicht angezeigt** | Layer wurde nicht gespeichert oder falsches räumliches Referenzsystem. | Prüfen Sie, ob `SpatialReferenceSystem.Wgs84` mit dem CRS des Viewers übereinstimmt und ob `Dataset.Create` erfolgreich war. |
| **M‑Werte werden ignoriert** | `MScale` ist auf 0 oder zu klein gesetzt. | Einen sinnvollen `MScale` festlegen (z. B. `1e4`), um Maß‑Werte zu speichern. |

## Häufig gestellte Fragen

**F: Kann ich Aspose.GIS für .NET mit anderen GIS‑Dateiformaten verwenden?**  
A: Ja, Aspose.GIS unterstützt Shapefile, GeoJSON, KML und viele weitere Formate.

**F: Ist Aspose.GIS für .NET mit .NET Core kompatibel?**  
A: Absolut. Die Bibliothek funktioniert mit .NET Framework, .NET Core und .NET 5/6+.  

**F: Kann ich räumliche Operationen wie Buffering oder Intersection durchführen?**  
A: Ja, die API enthält Methoden zum Puffer‑Erzeugen, Schneiden und Berechnen von Distanzen.  

**F: Bietet Aspose.GIS Koordinatentransformations‑Funktionen?**  
A: Ja, Sie können Geometrien zwischen verschiedenen räumlichen Referenzsystemen mit den integrierten Reprojektionstools transformieren.  

**F: Gibt es eine Testversion?**  
A: Ja, Sie können eine kostenlose Testversion von der [Website](https://releases.aspose.com/gis/net/) herunterladen.  

---

**Zuletzt aktualisiert:** 2025-12-28  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
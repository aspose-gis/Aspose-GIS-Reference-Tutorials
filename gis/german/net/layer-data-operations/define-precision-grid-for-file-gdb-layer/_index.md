---
date: 2026-04-24
description: Erfahren Sie, wie Sie eine Dateigeodatenbank erstellen und ein Präzisionsraster
  für einen File‑GDB‑Layer mit Aspose.GIS für .NET festlegen, einschließlich des Hinzufügens
  von Features zum Layer und der Validierung des Koordinatenbereichs.
keywords:
- create file geodatabase
- handle out of range
- add features layer
- configure coordinate grid
- validate coordinate range
linktitle: Präzisionsraster für File‑GDB‑Layer definieren
second_title: Aspose.GIS .NET API
title: Dateigeodatenbank erstellen & Raster für GDB‑Ebene festlegen (Aspose.GIS)
url: /de/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ein Raster für File GDB Layer in Aspose.GIS festlegt

## Einleitung
In diesem Tutorial werden Sie **create file geodatabase**‑Objekte erstellen und lernen, wie man **set grid** für einen File Geodatabase (GDB)‑Layer mit Aspose.GIS für .NET festlegt. Das Definieren eines Präzisionsrasters ermöglicht es Ihnen, **validate coordinate range** automatisch, verhindert **out‑of‑range**‑Fehler und garantiert, dass jede **add features layer**‑Operation Daten genau speichert. Wir gehen jeden Schritt durch, erklären, warum jede Einstellung wichtig ist, und zeigen Ihnen, wie man **handle out of range**‑Szenarien elegant handhabt.

## Schnelle Antworten
- **Was bedeutet „set grid“?** Es definiert die Koordinatenpräzision und den gültigen Bereich für einen GIS‑Layer.  
- **Warum ein Präzisionsraster verwenden?** Es schützt Ihre Daten vor ungültigen Koordinaten und verbessert die Speichereffizienz.  
- **Welche Bibliothek stellt diese Funktion bereit?** Aspose.GIS für .NET.  
- **Benötige ich eine Lizenz?** Eine Testversion ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich das mit .NET Core verwenden?** Ja, Aspose.GIS unterstützt .NET Framework und .NET Core.

## Was ist ein Präzisionsraster und warum es festlegen?
Ein Präzisionsraster ist ein Satz von Parametern (Ursprung, Maßstab usw.), der der GIS‑Engine mitteilt, wie Koordinatenwerte gerundet und gespeichert werden sollen. Durch die Konfiguration eines Rasters **validate coordinate range** automatisch, und jeder Versuch, einen Punkt außerhalb des Rasters einzufügen, löst eine Ausnahme aus – was Ihnen hilft, **handle out of range**‑Szenarien frühzeitig in der Entwicklung zu bewältigen.

## Warum eine File Geodatabase mit einem Präzisionsraster erstellen?
Das Erstellen einer File Geodatabase bietet Ihnen einen portablen, leistungsstarken Container für Vektordaten. Das Hinzufügen eines Präzisionsrasters zum Zeitpunkt der Erstellung stellt sicher:

- **Konsistente Datenqualität** – jedes Feature respektiert dieselbe numerische Präzision.  
- **Schnelleres Indexieren** – die Engine kann Koordinaten effizienter speichern.  
- **Frühe Fehlererkennung** – **out‑of‑range**‑Koordinaten werden abgefangen, bevor sie den Datensatz beschädigen.

## Voraussetzungen
Stellen Sie vor Beginn sicher, dass Sie Folgendes installiert haben:

1. **Visual Studio** – jede aktuelle Version (Community, Professional oder Enterprise).  
2. **Aspose.GIS für .NET** – laden Sie es von der [Website](https://releases.aspose.com/gis/net/) herunter.  
3. **Grundkenntnisse in C#** – Sie sollten mit dem Erstellen von .NET‑Konsolenprojekten vertraut sein.

## Häufige Anwendungsfälle
- **Erfassung von Felddaten** bei der GPS‑Geräte Koordinaten erzeugen können, die leicht außerhalb des vorgesehenen Ausdehnungsbereichs liegen.  
- **Datenmigration** von Altsystemen, die unterschiedliche Koordinatenpräzisionen verwendeten.  
- **Automatisierte ETL‑Pipelines**, die räumliche Integrität durchsetzen müssen, bevor Daten in eine GIS‑Datenbank geladen werden.

## Namespaces importieren
Zuerst importieren Sie die Namespaces, die für die Arbeit mit Aspose.GIS erforderlich sind:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## Wie man das Koordinatenraster in einem File GDB‑Layer konfiguriert
Im Folgenden finden Sie eine Schritt‑für‑Schritt‑Anleitung, die genau zeigt, wie man das Raster konfiguriert, einen Layer erstellt und sicher **add features to layer**.

### Schritt 1: Datensatz erstellen
Wir beginnen mit dem Erstellen eines neuen File‑Geodatabase‑Datensatzes. Dort wird der Layer gespeichert.

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### Schritt 2: Präzisionsraster‑Optionen definieren
Hier geben wir die Rasterparameter an. Passen Sie die Ursprünge und Maßstäbe an das Koordinatensystem Ihres Projekts an.

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

*Das Flag `EnsureValidCoordinatesRange = true` weist Aspose.GIS an, **validate coordinate range** für jedes Feature, das Sie hinzufügen, zu überprüfen.*

### Schritt 3: Layer mit dem Raster erstellen
Jetzt erstellen wir einen neuen Layer im Datensatz und wenden die gerade definierten Rasteroptionen an. Wir verwenden das räumliche Referenzsystem WGS84.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### Schritt 4: Features zum Layer hinzufügen
Wir erstellen zwei Punkt‑Features. Der erste Punkt liegt innerhalb des Rasters, während der zweite bewusst außerhalb liegt, um **how to handle out of range**‑Fehler zu demonstrieren.

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
Die `using`‑Anweisungen schließen und entsorgen den Datensatz und den Layer automatisch, sodass alle Ressourcen freigegeben werden.

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|-------|----------------|-----|
| **Ausnahme: „X‑Wert … ist außerhalb des gültigen Bereichs.“** | Koordinaten liegen außerhalb des Präzisionsrasters. | Passen Sie `XOrigin`, `YOrigin` oder `XYScale` an, um Ihre Daten zu umfassen, oder stellen Sie sicher, dass die Eingabedaten innerhalb des definierten Bereichs liegen. |
| **Features werden im GIS‑Viewer nicht angezeigt** | Layer nicht gespeichert oder falsches räumliches Referenzsystem. | Überprüfen Sie, ob `SpatialReferenceSystem.Wgs84` mit dem CRS des Viewers übereinstimmt und ob `Dataset.Create` erfolgreich war. |
| **M‑Werte ignoriert** | `MScale` ist auf 0 oder zu niedrig gesetzt. | Setzen Sie einen angemessenen `MScale` (z. B. `1e4`), um Messwerte zu speichern. |

## Tipps zur Fehlersuche
- **Überprüfen Sie die Rasterausdehnungen** erneut, bevor Sie große Datenmengen laden; ein kleiner Tippfehler in `XOrigin` kann dazu führen, dass viele Zeilen abgelehnt werden.  
- **Protokollieren Sie die Ausnahme­meldung** (wie im try‑catch‑Block gezeigt) in einer Datei, wenn Sie automatisierte Importe verarbeiten; das erleichtert das Erkennen von Mustern in **out‑of‑range**‑Daten.  
- **Verwenden Sie `EnsureValidCoordinatesRange = false` nur für vertrauenswürdige Datenquellen** – das Deaktivieren überspringt die Validierung und kann zu beschädigten Geometrien führen.

## Häufig gestellte Fragen

**Q: Kann ich Aspose.GIS für .NET mit anderen GIS‑Dateiformaten verwenden?**  
A: Ja, Aspose.GIS unterstützt Shapefile, GeoJSON, KML und viele weitere Formate.

**Q: Ist Aspose.GIS für .NET mit .NET Core kompatibel?**  
A: Absolut. Die Bibliothek funktioniert mit .NET Framework, .NET Core und .NET 5/6+.

**Q: Kann ich räumliche Operationen wie Buffering oder Schnittmengen durchführen?**  
A: Ja, die API enthält Methoden für Buffering, Schnittmengen und Distanzberechnungen.

**Q: Bietet Aspose.GIS Möglichkeiten zur Koordinatentransformation?**  
A: Ja, Sie können Geometrien zwischen verschiedenen räumlichen Referenzsystemen mit den integrierten Reprojektionstools transformieren.

**Q: Gibt es eine Testversion?**  
A: Ja, Sie können eine kostenlose Testversion von der [Website](https://releases.aspose.com/gis/net/) herunterladen.

---

**Zuletzt aktualisiert:** 2026-04-24  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
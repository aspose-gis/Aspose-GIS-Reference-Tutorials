---
date: 2026-02-15
description: Erfahren Sie, wie Sie mit Aspose.GIS für .NET Vektorlayer und gekrümmte
  Polygongeometrie erstellen, einschließlich CircularString‑Geometrie für Innenringe.
linktitle: Create Curve Polygon Geometry
second_title: Aspose.GIS .NET API
title: Vektorlayer und Kurvenpolygon mit Aspose.GIS erstellen
url: /de/net/geometry-creation/create-curve-polygon-geometry/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektor‑Layer erstellen und gekrümmtes Polygon mit Aspose.GIS

## Einführung
Im Bereich der Entwicklung von Geographic Information Systems (GIS) hebt sich **Aspose.GIS for .NET** als leistungsstarke Bibliothek zum Erstellen, Bearbeiten und Manipulieren von räumlichen Daten hervor. In diesem Tutorial lernen Sie, wie Sie **create vector layer** und **create curve polygon** Geometrie Schritt für Schritt erstellen, sodass Sie anspruchsvolle Formen direkt in Ihre GIS‑Anwendungen einbetten können. Am Ende der Anleitung verfügen Sie über eine einsatzbereite Shapefile, die ein gekrümmtes Polygon mit äußeren und inneren Ringen enthält.

## Schnelle Antworten
- **Welche Bibliothek wird verwendet?** Aspose.GIS for .NET  
- **Primäre Aufgabe?** Eine Curve‑Polygon‑Geometrie erstellen, als Shapefile speichern und **create vector layer** für die Daten erzeugen.  
- **Typische Implementierungszeit?** 5–10 Minuten für eine einfache Form  
- **Voraussetzungen?** .NET‑Entwicklungsumgebung und Aspose.GIS NuGet‑Paket  
- **Kann ich das Ergebnis ansehen?** Ja – jeder GIS‑Viewer, der Shapefile unterstützt (z. B. QGIS, ArcGIS)

## Was ist ein Curve Polygon?
Ein *curve polygon* ist ein Polygon, dessen Kanten aus gekrümmten Segmenten (wie Kreisbögen) anstelle ausschließlich gerader Linien bestehen können. Dies ermöglicht eine realistischere Modellierung natürlicher Merkmale wie Seen, Inseln oder jeder Form, die von glatten Grenzen profitiert.

## Warum Curve‑Polygon‑Geometrie mit Aspose.GIS erstellen?
- **Precision** – Gekrümmte Kanten werden mathematisch gespeichert und erhalten die exakte Geometrie.  
- **Interoperability** – Die erzeugte Shapefile funktioniert mit allen gängigen GIS‑Plattformen.  
- **Productivity** – Es wird nur minimaler Code benötigt, um komplexe Formen zu definieren, was Entwicklungszyklen beschleunigt.  
- **Flexibility** – Sie können **create vector layer**‑Objekte zur Laufzeit erzeugen und jede benötigte Geometrie anhängen.

## Voraussetzungen
1. **Aspose.GIS for .NET** installiert. Laden Sie es von der [Aspose.GIS for .NET releases page](https://releases.aspose.com/gis/net/) herunter.  
2. Fundierte Kenntnisse in C# und dem .NET‑Ökosystem.  
3. Eine IDE wie Visual Studio (beliebige aktuelle Version) oder Visual Studio Code.

## Namespaces importieren
In diesem Schritt importieren wir die erforderlichen Namespaces, um die Aspose.GIS‑Funktionen in unserem Code zu nutzen.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Dateipfad festlegen
Zuerst geben Sie an, wo die erzeugte Curve‑Polygon‑Shapefile gespeichert werden soll.

```csharp
string path = "Your Document Directory" + "CreateCurvePolygon_out.shp";
```

Ersetzen Sie `"Your Document Directory"` durch den tatsächlichen Ordnerpfad auf Ihrem Rechner.

### Schritt 2: Vektor‑Layer erstellen
Instanziieren Sie einen neuen Vektor‑Layer mithilfe des Shapefile‑Treibers. Dies ist der **create vector layer**‑Schritt, der den Container für unsere Geometrie vorbereitet.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Your code for creating the Curve Polygon Geometry will go here
}
```

Die `using`‑Anweisung stellt sicher, dass Ressourcen korrekt freigegeben werden.

### Schritt 3: Feature erstellen
Erzeugen Sie ein Feature‑Objekt, das die Geometrie und etwaige Attributdaten enthält.

```csharp
var feature = layer.ConstructFeature();
```

### Schritt 4: Curve‑Polygon‑Geometrie erstellen
Jetzt erstellen wir ein leeres `CurvePolygon`‑Objekt.

```csharp
var curvePolygon = new CurvePolygon();
```

### Schritt 5: Äußeren Ring definieren
Fügen Sie einen CircularString hinzu, der die äußere Grenze des Polygons bildet.

```csharp
var exterior = new CircularString();
exterior.AddPoint(-2, 0);
exterior.AddPoint(0, 2);
exterior.AddPoint(2, 0);
exterior.AddPoint(0, -2);
exterior.AddPoint(-2, 0);
curvePolygon.ExteriorRing = exterior;
```

Die obigen Koordinaten erzeugen eine torus‑ähnliche Form.

### Schritt 6: Inneren Ring definieren (optional)
Falls Sie ein Loch im Polygon benötigen, definieren Sie es als einen weiteren CircularString. Dies zeigt, wie man ein **interior ring polygon** mithilfe von **circular string geometry** hinzufügt.

```csharp
var interior = new CircularString();
interior.AddPoint(-1, 0);
interior.AddPoint(0, 1);
interior.AddPoint(1, 0);
interior.AddPoint(0, -1);
interior.AddPoint(-1, 0);
curvePolygon.AddInteriorRing(interior);
```

### Schritt 7: Geometrie dem Feature zuweisen
Verknüpfen Sie das CurvePolygon mit dem zuvor erstellten Feature.

```csharp
feature.Geometry = curvePolygon;
```

### Schritt 8: Feature zum Layer hinzufügen
Fügen Sie schließlich das Feature dem Vektor‑Layer hinzu, damit es Teil des Datensatzes wird.

```csharp
layer.Add(feature);
```

Wenn der `using`‑Block endet, wird die Shapefile auf die Festplatte geschrieben.

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|---------|-------------------|--------|
| **Datei nicht erstellt** | Falscher Pfad oder fehlende Schreibberechtigungen | Stellen Sie sicher, dass das Verzeichnis existiert und die Anwendung Schreibzugriff hat. |
| **Gekrümmte Kanten werden in einigen Betrachtern als gerade Linien angezeigt** | Der Viewer unterstützt keine CircularStrings | Verwenden Sie eine GIS‑Anwendung, die die Shapefile‑Spezifikation vollständig unterstützt (z. B. QGIS 3.28+). |
| **Ausnahme `ArgumentException` bei `AddPoint`** | Punkte liegen außerhalb des gültigen Koordinatenbereichs für das gewählte CRS | Stellen Sie sicher, dass die Koordinaten innerhalb des geplanten Koordinatenreferenzsystems liegen. |

## Häufig gestellte Fragen

**F: Ist Aspose.GIS for .NET mit anderen GIS‑Bibliotheken kompatibel?**  
A: Ja, Aspose.GIS for .NET unterstützt die Interoperabilität mit vielen gängigen GIS‑Formaten, sodass Sie Daten mit Bibliotheken wie GDAL/OGR oder Proj.NET austauschen können.

**F: Kann ich die erzeugte Curve‑Polygon‑Geometrie in GIS‑Software visualisieren?**  
A: Natürlich! Die erzeugte Shapefile kann in QGIS, ArcGIS oder jedem GIS‑Tool, das das Shapefile‑Format liest, geöffnet werden.

**F: Bietet Aspose.GIS for .NET räumliche Analysefunktionen?**  
A: Ja, es enthält Funktionen für räumliche Abfragen, Pufferbildung, Schnittmengen und mehr, wodurch fortgeschrittene Analysen direkt in .NET möglich sind.

**F: Wo kann ich Hilfe erhalten oder Ideen mit anderen Nutzern diskutieren?**  
A: Treten Sie dem Aspose.GIS‑Community‑Forum [hier](https://forum.aspose.com/c/gis/33) bei, um sich mit anderen Entwicklern zu vernetzen.

**F: Gibt es eine kostenlose Testversion vor dem Kauf?**  
A: Natürlich! Sie können eine kostenlose Testversion von der [releases page](https://releases.aspose.com/) herunterladen und alle Funktionen evaluieren.

## Fazit
Sie haben nun gelernt, wie Sie mit Aspose.GIS for .NET **create vector layer** und **create curve polygon** Geometrie erstellen, sie als Shapefile speichern und häufige Stolperfallen sowie FAQs kennenlernen. Experimentieren Sie gern mit verschiedenen Koordinatensätzen, fügen Sie Attributdaten hinzu oder integrieren Sie den Layer in umfangreichere GIS‑Workflows.

---

**Zuletzt aktualisiert:** 2026-02-15  
**Getestet mit:** Aspose.GIS for .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
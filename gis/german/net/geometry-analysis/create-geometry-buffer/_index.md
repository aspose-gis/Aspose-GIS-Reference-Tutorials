---
date: 2026-02-08
description: Erfahren Sie, wie Sie Geometrien mit Aspose.GIS für .NET puffern und
  räumliche Analyse‑Puffer durchführen, einschließlich Installation, Namespace‑Importen
  und Enthaltenheitsprüfungen.
linktitle: How to Create Buffer Using Aspose.GIS for .NET
second_title: Aspose.GIS .NET API
title: Wie man Geometrien mit Aspose.GIS für .NET puffert
url: /de/net/geometry-analysis/create-geometry-buffer/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Geometrien mit Aspose.GIS für .NET puffert

## Einführung
Wenn Sie in einer .NET‑Umgebung mit Geodaten arbeiten, ist das **Puffern von Geometrien** essenziell für Nähe‑Analysen, Zonierung und Feature‑Generalisierung. In diesem Tutorial führen wir Sie durch den gesamten Prozess mit Aspose.GIS für .NET – von der Installation über das Einbinden der erforderlichen Namespaces, das Erzeugen von Puffern für Linien‑ und Polygongeometrien bis hin zur Prüfung räumlicher Einschlussbedingungen. Am Ende können Sie **räumliche Analyse‑Puffer** sicher in Ihren eigenen Anwendungen einsetzen.

## Schnellantworten
- **Was ist ein Geometriepuffer?** Ein Polygon, das alle Punkte innerhalb einer angegebenen Entfernung von einer Ausgangsgeometrie umschließt.  
- **Warum Aspose.GIS zum Puffer‑Erzeugen verwenden?** Es bietet eine einfache, hoch‑performante API, die auf .NET Framework, .NET Core und .NET 5/6+ funktioniert.  
- **Wie installiere ich Aspose.GIS?** Laden Sie die Bibliothek von der offiziellen Website herunter und fügen Sie sie als Referenz in Visual Studio hinzu.  
- **Wie prüfe ich den Einschluss?** Verwenden Sie die Methode `SpatiallyContains`, um zu testen, ob ein Punkt innerhalb des erzeugten Puffers liegt.  
- **Kann ich über das Puffer‑Erzeugen hinaus räumliche Analysen durchführen?** Ja – Operationen wie Schnitt, Vereinigung und Distanzberechnungen werden ebenfalls unterstützt.

## Was ist ein Geometriepuffer?
Ein Geometriepuffer erzeugt eine Zone um ein Feature (Punkt, Linie oder Polygon) in einem benutzerdefinierten Abstand. Diese Zone ist nützlich, um nahegelegene Features zu identifizieren, Wirkungsbereiche zu erstellen oder komplexe Formen zu vereinfachen.

## Wie man Geometrien mit Aspose.GIS puffert
### Warum Aspose.GIS für räumliche Analyse‑Puffer verwenden?
- **Plattformübergreifende Unterstützung:** Läuft unter Windows, Linux und macOS.  
- **Keine externen Abhängigkeiten:** Keine nativen GIS‑Bibliotheken nötig.  
- **Umfangreiche API:** Enthält Puffer‑Funktionen, räumliche Prädikate und Koordinatensystem‑Transformationen.  
- **Performance‑optimiert:** Verarbeitet große Datensätze effizient und eignet sich daher ideal für anspruchsvolle räumliche Analyse‑Puffer.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- **Visual Studio 2019 oder neuer** (oder ein kompatibles .NET‑IDE).  
- **.NET 6 SDK** (oder .NET Core 3.1+).  
- **Aspose.GIS für .NET‑Bibliothek** – siehe die Installationsschritte unten.  

### Wie man Aspose.GIS für .NET installiert
1. Laden Sie die Aspose.GIS für .NET‑Bibliothek von dem [Download‑Link](https://releases.aspose.com/gis/net/) herunter.  
2. In Visual Studio klicken Sie mit der rechten Maustaste auf Ihr Projekt → **Add** → **Reference…** → navigieren Sie zur heruntergeladenen DLL und fügen Sie sie hinzu.  
3. Besorgen Sie sich eine Lizenz von [Aspose](https://purchase.aspose.com/buy) oder verwenden Sie eine [temporäre Lizenz](https://purchase.aspose.com/temporary-license/) für Evaluierungszwecke.

## Namespaces importieren
Um die API zu nutzen, importieren Sie die erforderlichen Namespaces in Ihre C#‑Datei.

### Wie man Aspose.GIS importiert
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Jetzt zerlegen wir den Puffer‑Erstellungsprozess Schritt für Schritt.

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Einen Geometriepuffer erstellen
Zuerst definieren wir eine einfache `LineString`‑Geometrie, die als Quelle für unseren Puffer dient.

```csharp
// Define a LineString geometry
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(3, 3);
```

In diesem Snippet erzeugen wir einen `LineString` und fügen zwei Punkte hinzu, die eine diagonale Linie von (0,0) nach (3,3) bilden.

### Schritt 2: Puffer für LineString erzeugen
Als Nächstes erzeugen wir einen Puffer um die Linie mit einem **positiven Abstand** von 1 Einheit.

```csharp
// Generate a buffer for the LineString with a positive distance
var lineBuffer = line.GetBuffer(distance: 1);
```

Die Methode `GetBuffer` liefert ein Polygon, das jeden Punkt innerhalb von 1 Einheit zur ursprünglichen Linie enthält.

### Schritt 3: Räumlichen Einschluss prüfen
Jetzt zeigen wir **wie man den Einschluss prüft**, indem wir testen, ob bestimmte Punkte innerhalb des Puffers liegen.

```csharp
// Check spatial containment of points within the buffer
Console.WriteLine(lineBuffer.SpatiallyContains(new Point(1, 2)));     // True
Console.WriteLine(lineBuffer.SpatiallyContains(new Point(3.1, 3.1))); // True
```

Das Prädikat `SpatiallyContains` gibt `true` zurück, wenn der Punkt im Puffer‑Polygon liegt.

### Schritt 4: Eine Polygongeometrie definieren
Wir erstellen außerdem eine `Polygon`‑Geometrie, um das Puffer‑Erzeugen mit einem **negativen Abstand** zu demonstrieren, wodurch die Form verkleinert wird.

```csharp
// Define a Polygon geometry
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 3),
    new Point(3, 3),
    new Point(3, 0),
    new Point(0, 0),
});
```

Das Polygon stellt ein Quadrat mit den Eckpunkten (0,0), (0,3), (3,3) und (3,0) dar.

### Schritt 5: Puffer für Polygon erzeugen
Durch Anwenden eines negativen Abstands von –1 Einheit wird das Polygon nach innen kontrahiert.

```csharp
// Generate a buffer for the Polygon with a negative distance
var polygonBuffer = (IPolygon)polygon.GetBuffer(distance: -1);
```

Das resultierende `polygonBuffer` ist ein kleineres Quadrat, das sich gut für innere Zonen eignet.

### Schritt 6: Punkte des äußeren Rings des Puffers auslesen
Abschließend holen wir die Koordinaten des äußeren Rings des Puffers und geben sie aus.

```csharp
// Access points of the exterior ring of the buffer Polygon
var ring = polygonBuffer.ExteriorRing;
for (int i = 0; i < ring.Count; ++i)
{
    Console.WriteLine("[{0}] = ({1} {2})", i, ring[i].X, ring[i].Y);
}
```

Diese Schleife gibt jeden Scheitelpunkt des kontrahierten Polygons aus und bestätigt die Puffergeometrie.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Puffer liefert `null`** | Stellen Sie sicher, dass der Abstandswert für das Koordinatensystem der Geometrie geeignet ist. |
| **`SpatiallyContains` gibt immer `false` zurück** | Prüfen Sie, ob beide Geometrien dieselbe räumliche Referenz (CRS) verwenden. |
| **Leistungsabfall bei großen Datensätzen** | Verarbeiten Sie Geometrien in Batches und verwenden Sie dieselbe `GeometryFactory`‑Instanz wieder. |

## Häufig gestellte Fragen

**F: Ist Aspose.GIS für .NET mit anderen .NET‑Frameworks kompatibel?**  
A: Ja, es funktioniert mit .NET Framework, .NET Core, .NET 5 und .NET 6.

**F: Kann ich räumliche Analysen mit Aspose.GIS für .NET durchführen?**  
A: Absolut. Die Bibliothek unterstützt Puffer, Schnitte, Distanzberechnungen und mehr.

**F: Gibt es Beschränkungen bei der Datensatzgröße?**  
A: Die API ist für große Datensätze optimiert, jedoch hängt der Speicherverbrauch von der Größe der geladenen Geometrien ab.

**F: Unterstützt Aspose.GIS verschiedene räumliche Referenzsysteme?**  
A: Ja, es verarbeitet ein breites Spektrum an Koordinatensystemen und ermöglicht Transformationen „on‑the‑fly“.

**F: Wo bekomme ich technischen Support?**  
A: Besuchen Sie das Aspose.GIS‑Community‑Forum unter [https://forum.aspose.com/c/gis/33](https://forum.aspose.com/c/gis/33) für Unterstützung.

---

**Zuletzt aktualisiert:** 2026‑02‑08  
**Getestet mit:** Aspose.GIS für .NET (neueste Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
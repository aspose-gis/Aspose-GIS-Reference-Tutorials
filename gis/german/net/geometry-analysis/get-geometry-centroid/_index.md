---
date: 2026-02-10
description: Erfahren Sie, wie Sie den Schwerpunkt einer Geometrie mit Aspose.GIS
  für .NET berechnen, den Mittelpunkt eines Polygons ermitteln und den Schwerpunkt
  eines Multipolygons für die räumliche Analyse berechnen.
linktitle: Get Geometry Centroid
second_title: Aspose.GIS .NET API
title: Wie man den Schwerpunkt einer Geometrie mit Aspose.GIS für .NET berechnet
url: /de/net/geometry-analysis/get-geometry-centroid/
weight: 19
---

Now produce final translated content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Berechnung des Schwerpunkts einer Geometrie mit Aspose.GIS für .NET

## Einführung
Wenn Sie an **C# Spatial Analysis** arbeiten und wissen müssen **wie man den Schwerpunkt** einer beliebigen Form berechnet, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie durch die Verwendung von Aspose.GIS für .NET, um **den Polygon‑Schwerpunkt zu berechnen**, diesen Schwerpunkt abzurufen und zu sehen, wie dieses kleine Geometrie‑Stück leistungsstarke **integrierte räumliche Analysen** ermöglichen kann, wie z. B. Beschriftungsplatzierung, Clustering und Distanzberechnungen.

## Schnelle Antworten
- **Was ist die primäre Methode?** `GetCentroid()` auf einem `IGeometry`‑Objekt.  
- **Welche Bibliothek stellt sie bereit?** Aspose.GIS für .NET.  
- **Wie viele Code‑Zeilen?** Weniger als 15 Zeilen insgesamt (ohne using‑Anweisungen).  
- **Benötige ich eine Lizenz?** Eine temporäre Lizenz funktioniert für Tests; eine Voll‑Lizenz ist für die Produktion erforderlich.  
- **Läuft es auf .NET 6+?** Ja – die API ist vollständig kompatibel mit .NET Core und .NET 5/6.  

## Was ist ein Schwerpunkt und warum ist er wichtig?
Ein Schwerpunkt ist das geometrische Zentrum einer Form – man kann ihn sich als den „Balancierungspunkt“ vorstellen. Für Polygone wird der Schwerpunkt (oder **center point of polygon**) häufig verwendet, um Beschriftungen zu platzieren, durchschnittliche Positionen zu berechnen oder als Referenzpunkt in räumlichen Abfragen zu dienen. Das schnelle **Berechnen des Schwerpunkts** ermöglicht es Ihnen, Funktionen der räumlichen Analyse zu integrieren, ohne selbst komplexe Mathematik zu implementieren.

## Warum den Schwerpunkt eines Multipolygons berechnen?
Wenn Sie mit Sammlungen von Polygonen arbeiten (z. B. Ländergrenzen, die aus Inseln bestehen), müssen Sie möglicherweise **den Schwerpunkt von Multipolygon‑Objekten** berechnen. Aspose.GIS ermöglicht es Ihnen, `GetCentroid()` auf einem `MultiPolygon` aufzurufen und gibt den Schwerpunkt der kombinierten Form zurück, was die Stapelverarbeitung und Kartenvisualisierung vereinfacht.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

### 1. Installation von Aspose.GIS für .NET
Laden Sie die Bibliothek von der [Aspose.GIS für .NET-Website](https://releases.aspose.com/gis/net/) herunter. Befolgen Sie die Installationsanweisungen, um das NuGet‑Paket zu Ihrem Projekt hinzuzufügen.

### 2. Vertrautheit mit C#‑Programmierung
Sie sollten sich mit dem Schreiben von einfachem C#‑Code wohlfühlen. Wenn Sie neu sind, sollten Sie eine kurze Auffrischung zu Variablen, Klassen und Konsolenausgabe in Betracht ziehen.

### 3. Grundlegendes Verständnis geografischer Konzepte
Obwohl nicht zwingend erforderlich, hilft Ihnen das Wissen um den Unterschied zwischen Punkten, Linien und Polygonen, den Beispielen leichter zu folgen.

## Namespaces importieren
Wir müssen die Aspose.GIS‑Klassen in den Gültigkeitsbereich holen. Fügen Sie die folgenden `using`‑Direktiven am Anfang Ihrer C#‑Datei hinzu:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Diese Namespaces geben Ihnen Zugriff auf Geometrietypen, die Methode `GetCentroid()` und Standard‑.NET‑Hilfsprogramme.

## Wie man den Schwerpunkt einer Geometrie berechnet
Im Folgenden finden Sie eine Schritt‑für‑Schritt‑Anleitung, die zeigt, wie man **Polygongeometrie erstellt**, deren Schwerpunkt berechnet und das Ergebnis anzeigt.

### Schritt 1: Polygon definieren
Zuerst **erstellen wir Polygongeometrie**, indem wir die Eckpunkte angeben. Dieses Beispiel erstellt ein einfaches, nicht‑selbst‑überschneidendes Polygon:

```csharp
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(1, 0),
    new Point(2, 2),
    new Point(0, 4),
    new Point(5, 5),
    new Point(6, 1),
    new Point(1, 0),
});
```

### Schritt 2: Polygon‑Schwerpunkt abrufen (center point of polygon)
Nachdem das Polygon definiert ist, rufen Sie `GetCentroid()` auf, um **den Polygon‑Schwerpunkt abzurufen**:

```csharp
IPoint centroid = polygon.GetCentroid();
```

### Schritt 3: Schwerpunktkoordinaten anzeigen
Zum Schluss geben Sie die X‑ und Y‑Koordinaten des Schwerpunkts aus. Der Format‑String rundet die Werte auf zwei Dezimalstellen:

```csharp
Console.WriteLine("{0:F} {1:F}", centroid.X, centroid.Y); // Output: 3.33 2.58
```

Das Ausführen des Programms gibt die Schwerpunktkoordinaten in der Konsole aus und bestätigt, dass die Geometrie korrekt verarbeitet wurde.

## Häufige Fallstricke & Pro‑Tipps
- **Fallstrick:** Das Bereitstellen eines selbst‑überschneidenden Polygons kann einen unerwarteten Schwerpunkt erzeugen.  
  **Tipp:** Validieren Sie Ihr Polygon (z. B. mit `IsValid`, falls verfügbar) bevor Sie `GetCentroid()` aufrufen.
- **Fallstrick:** Das Schließen des Rings zu vergessen (der erste und letzte Punkt müssen identisch sein).  
  **Tipp:** Wiederholen Sie immer den ersten Punkt als letzten Punkt beim Erstellen eines `LinearRing`.
- **Pro‑Tipp:** Für große Datensätze berechnen Sie Schwerpunkte parallel mit `Parallel.ForEach`, um die Stapelverarbeitung zu beschleunigen.
- **Pro‑Tipp:** Beim Arbeiten mit einem `MultiPolygon` rufen Sie `GetCentroid()` direkt auf der Sammlung auf, um **den Schwerpunkt eines Multipolygons** in einem einzigen Aufruf zu **berechnen**.

## FAQ
### Q: Ist Aspose.GIS für .NET mit allen Versionen des .NET Framework kompatibel?
A: Aspose.GIS für .NET ist kompatibel mit .NET Framework 4.6 und höher, was eine breite Kompatibilität über verschiedene Versionen hinweg sicherstellt.

### Q: Kann ich temporäre Lizenzen für Aspose.GIS für .NET erhalten?
A: Ja, temporäre Lizenzen für Aspose.GIS für .NET stehen für Testzwecke zur Verfügung. Sie können sie von der [temporären Lizenzseite](https://purchase.aspose.com/temporary-license/) beziehen.

### Q: Ist Aspose.GIS für .NET sowohl für Desktop‑ als auch für Web‑Anwendungen geeignet?
A: Absolut! Aspose.GIS für .NET lässt sich nahtlos in sowohl Desktop‑ als auch Web‑Anwendungen integrieren und bietet Flexibilität bei der Entwicklung.

### Q: Bietet Aspose.GIS für .NET umfangreiche Dokumentation?
A: Ja, umfassende Dokumentation für Aspose.GIS für .NET ist auf der [Dokumentationsseite](https://reference.aspose.com/gis/net/) verfügbar und bietet detaillierte Einblicke in Nutzung und Funktionen.

### Q: Wie kann ich Unterstützung erhalten oder mit der Community zu Aspose.GIS für .NET interagieren?
A: Für Anfragen, Support oder Community‑Austausch können Sie das dedizierte Aspose.GIS‑Forum [hier](https://forum.aspose.com/c/gis/33) besuchen.

## Häufig gestellte Fragen

**Q: Kann ich den Schwerpunkt eines MultiPolygons berechnen?**  
A: Ja. Rufen Sie `GetCentroid()` für jedes einzelne Polygon oder für das `MultiPolygon`‑Objekt auf; die API gibt den Schwerpunkt der kombinierten Form zurück.

**Q: Berücksichtigt die Schwerpunktberechnung die Krümmung der Erde?**  
A: Das eingebaute `GetCentroid()` arbeitet im Koordinatenraum der Geometrie (planar). Für geodätische Daten sollten Sie vor der Berechnung des Schwerpunkts in ein geeignetes planare CRS reprojizieren.

**Q: Gibt es eine Möglichkeit, den Schwerpunkt einer Geometriesammlung in einem Aufruf zu erhalten?**  
A: Sie können über die Sammlung iterieren und Schwerpunkte einzeln berechnen, oder die `GeometryFactory` verwenden, um Geometrien zu verschmelzen und anschließend `GetCentroid()` auf dem zusammengeführten Ergebnis aufzurufen.

**Q: Wie genau ist der Schwerpunkt bei sehr großen Polygonen?**  
A: Die Genauigkeit hängt von der Koordinatenpräzision und der Projektion ab. Bei extrem großen oder komplexen Polygonen sollten Sie die Geometrie zunächst vereinfachen, um die Leistung zu verbessern.

**Q: Kann ich die Schwerpunktausgabe als GeoJSON formatieren?**  
A: Ja. Nachdem Sie das `IPoint` erhalten haben, können Sie es mit Aspose.GIS' `GeoJsonWriter` oder einem beliebigen JSON‑Serializer Ihrer Wahl serialisieren.

---

**Zuletzt aktualisiert:** 2026-02-10  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
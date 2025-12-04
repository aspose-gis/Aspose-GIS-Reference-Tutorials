---
date: 2025-12-04
description: Lernen Sie, wie Sie mit C# bestimmen, ob ein Punkt innerhalb eines Polygons
  liegt. Dieses Aspose.GIS .NET‑Tutorial behandelt Prüfungen, ob Geometrien einen
  Punkt enthalten, Techniken der geospatialen Analyse in .NET und bewährte Methoden
  mit Aspose.GIS .NET.
language: de
linktitle: point inside polygon c# – Check Geometry Contains Another
second_title: Aspose.GIS .NET API
title: Punkt im Polygon C# – Prüfen, ob Geometrie eine andere enthält
url: /net/geometry-analysis/check-geometry-contains-another/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Punkt innerhalb Polygon c# – Geometrie enthält ein anderes

## Einführung
Wenn Sie an **geospatial analysis .net**‑Projekten arbeiten, ist eine der häufigsten Aufgaben, zu bestimmen, ob sich ein bestimmter Ort (ein Punkt) innerhalb eines definierten Bereichs (eines Polygons) befindet. In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie eine **point inside polygon c#**‑Prüfung mit der **Aspose.GIS .NET**‑Bibliothek durchführen. Egal, ob Sie eine Kartenanwendung, einen standortbasierten Service oder irgendeine Lösung entwickeln, die räumliche Einschlusslogik benötigt – die untenstehenden Code‑Snippets bringen Sie in wenigen Minuten zum Laufen.

## Schnelle Antworten
- **Was bedeutet “point inside polygon c#”?** Es ist eine räumliche Abfrage, die **true** zurückgibt, wenn eine Punktgeometrie vollständig innerhalb einer Polygongeometrie liegt.  
- **Welche Bibliothek erledigt das in .NET?** Aspose.GIS für .NET stellt die Methoden `SpatiallyContains` und `Within` bereit.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Ist es kompatibel mit .NET Core / .NET 6+?** Ja – Aspose.GIS unterstützt moderne .NET‑Laufzeiten vollständig.  
- **Wie lange dauert die Implementierung?** Etwa 10 Minuten, um den Code zu kopieren und das Beispiel auszuführen.

## Was ist point inside polygon c#?
Ein *point inside polygon*‑Test prüft, ob die Koordinaten eines `Point`‑Objekts innerhalb der Grenzen eines `Polygon`‑Objekts liegen. In C# wird dies typischerweise über Geometriebibliotheken realisiert, die die **Ray Casting**‑ oder **Winding Number**‑Algorithmen implementieren. Aspose.GIS abstrahiert diese Details und bietet eine einfache API: `polygon.SpatiallyContains(point)`.

## Warum Aspose.GIS .NET für Geometrie‑Enthält‑Punkt‑Prüfungen verwenden?
- **Umfangreiches Geometriemodell** – Unterstützt Polygone, Multipolygone, lineare Ringe und mehr.  
- **Hochleistungs‑Räumliche Operationen** – Optimiert für große Datensätze.  
- **Plattformübergreifend** – Funktioniert unter .NET Framework, .NET Core und .NET 5/6+.  
- **Umfassende Dokumentation** – Viele Beispiele für **geospatial analysis .net**‑Szenarien.  

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **.NET‑Entwicklungsumgebung** – .NET 6 SDK (oder neuer) installiert.  
2. **Aspose.GIS für .NET** – Laden Sie die Bibliothek von der offiziellen Release‑Seite herunter und fügen Sie das NuGet‑Paket zu Ihrem Projekt hinzu.  
3. **Grundlegendes C#‑Wissen** – Vertrautheit mit Klassen, Objekten und Konsolenanwendungen.

### 1. .NET-Entwicklungsumgebung einrichten
Stellen Sie sicher, dass Sie eine funktionierende .NET‑Entwicklungsumgebung auf Ihrem Rechner eingerichtet haben. Dazu gehört, dass das .NET‑SDK installiert und korrekt konfiguriert ist.

### 2. Aspose.GIS-Installation
Installieren Sie Aspose.GIS für .NET, indem Sie die Bibliothek von der Release‑Seite [hier](https://releases.aspose.com/gis/net/) herunterladen. Folgen Sie den Installationsanweisungen in der Dokumentation [hier](https://reference.aspose.com/gis/net/), um Aspose.GIS in Ihr Projekt zu integrieren.

### 3. Grundlegendes Verständnis von C#
Machen Sie sich mit der Programmiersprache C# vertraut, da Aspose.GIS für .NET hauptsächlich mit C# verwendet wird.

## Namespaces importieren
In Ihrem C#‑Projekt importieren Sie die erforderlichen Namespaces, um die Aspose.GIS‑Funktionen zu nutzen:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt 1: Geometrieobjekte definieren
Definieren Sie zunächst die Geometrieobjekte mithilfe der Aspose.GIS‑Klassen. Hier erstellen wir ein Polygon mit einem äußeren Ring und einem inneren Ring (einem Loch) sowie einen Punkt, den wir auf Einschluss prüfen wollen.
```csharp
var geometry1 = new Polygon();
geometry1.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 4),
    new Point(4, 4),
    new Point(4, 0),
    new Point(0, 0),
});
geometry1.AddInteriorRing(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 3),
    new Point(3, 3),
    new Point(3, 1),
    new Point(1, 1),
}));
var geometry2 = new Point(2, 2);
```

## Schritt 2: Räumliche Einschließung prüfen
Prüfen Sie nun, ob das Polygon **geometry1** den Punkt **geometry2** enthält. Die Methode `SpatiallyContains` liefert `false`, weil der Punkt innerhalb des inneren Rings (des Lochs) liegt.
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry2)); // False
```

## Schritt 3: Weitere Geometrie definieren
Jetzt definieren wir einen zweiten Punkt, der im äußeren Ring, aber außerhalb des inneren Rings liegt.
```csharp
var geometry3 = new Point(0.5, 0.5);
```

## Schritt 4: Räumliche Einschließung erneut prüfen
Die gleiche Einschlussprüfung mit dem neuen Punkt liefert `true` und bestätigt, dass der Punkt tatsächlich innerhalb der äußeren Grenze des Polygons liegt.
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry3)); // True
```

## Schritt 5: Äquivalente Funktionalität
Aspose.GIS bietet zudem die inverse Methode `Within`. Die folgende Zeile zeigt, dass `geometry3.Within(geometry1)` dasselbe Ergebnis liefert wie `geometry1.SpatiallyContains(geometry3)`.
```csharp
Console.WriteLine(geometry3.Within(geometry1)); // True
```

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|---------|-------------------|--------|
| **Unerwartetes `false`‑Ergebnis** | Der Punkt liegt innerhalb eines Lochs (innerer Ring) des Polygons. | Stellen Sie sicher, dass Sie das richtige Polygon testen oder verwenden Sie `geometry1.ExteriorRing` für einfache Polygone ohne Löcher. |
| **NullReferenceException** | Geometrieobjekte wurden nicht initialisiert, bevor `SpatiallyContains` aufgerufen wurde. | Instanziieren Sie sowohl Polygon‑ als auch Punktobjekte, bevor Sie räumliche Methoden aufrufen. |
| **Leistungsabfall bei großen Datensätzen** | Wiederholtes Erzeugen von Geometrieobjekten innerhalb von Schleifen. | Wiederverwenden Sie Geometrieinstanzen oder verarbeiten Sie stapelweise mit `GeometryCollection`. |

## Häufig gestellte Fragen

**Q: Ist Aspose.GIS mit .NET Core kompatibel?**  
A: Ja, Aspose.GIS unterstützt .NET Core vollständig, sodass Sie geospatiale Anwendungen plattformübergreifend entwickeln können.

**Q: Kann ich mit Aspose.GIS geospatiale Analysen durchführen?**  
A: Absolut, Aspose.GIS bietet zahlreiche Funktionen für geospatiale Analysen, einschließlich räumlicher Abfragen, Distanzberechnungen und Geometrie‑Manipulationen.

**Q: Wie häufig werden Updates für Aspose.GIS veröffentlicht?**  
A: Aspose.GIS veröffentlicht regelmäßig Updates, um die Leistung zu verbessern, neue Funktionen hinzuzufügen und gemeldete Probleme zu beheben. Sie bleiben auf dem Laufenden, indem Sie die Release‑Seite besuchen.

**Q: Gibt es ein Community‑Forum für Aspose.GIS‑Nutzer?**  
A: Ja, Sie können dem Aspose.GIS‑Community‑Forum [hier](https://forum.aspose.com/c/gis/33) beitreten, um sich mit anderen Nutzern auszutauschen, Fragen zu stellen und Erfahrungen zu teilen.

**Q: Kann ich Aspose.GIS vor dem Kauf testen?**  
A: Natürlich, Sie können Aspose.GIS über die kostenlose Testversion [hier](https://releases.aspose.com/) herunterladen und ausprobieren.

## Fazit
In diesem Leitfaden haben wir eine praktische **point inside polygon c#**‑Lösung mit Aspose.GIS für .NET demonstriert. Durch das Definieren Ihrer Geometrien und die Nutzung der Methode `SpatiallyContains` (oder `Within`) können Sie räumliche Einschlussfragen schnell beantworten – ein wesentlicher Bestandteil jedes **geospatial analysis .net**‑Workflows. Experimentieren Sie gern mit größeren Datensätzen, verschiedenen Geometrietypen und kombinieren Sie diese Prüfungen mit weiteren Aspose.GIS‑Funktionen wie Distanzberechnungen oder räumlichen Indizes.

---

**Zuletzt aktualisiert:** 2025-12-04  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
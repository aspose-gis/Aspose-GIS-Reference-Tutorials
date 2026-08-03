---
date: 2026-08-03
description: Erfahren Sie, wie Sie in C# mit Aspose.GIS .NET prüfen, ob ein Punkt
  innerhalb eines Polygons liegt. Dieser Leitfaden behandelt geometry contains checks,
  geospatial analysis techniques und best practices.
keywords:
- check point inside polygon
- c# point in polygon
- geometry contains point
- aspose.gis .net
lastmod: 2026-08-03
linktitle: Punkt innerhalb eines Polygons in C# mit der Aspose.GIS-Bibliothek prüfen
og_description: Erfahren Sie, wie Sie in C# mit Aspose.GIS .NET prüfen, ob ein Punkt
  innerhalb eines Polygons liegt. Dieser Leitfaden behandelt geometry contains checks,
  geospatial analysis techniques und best practices.
og_image_alt: Guide showing how to check point inside polygon in C# using Aspose.GIS
og_title: Punkt innerhalb eines Polygons in C# mit der Aspose.GIS-Bibliothek prüfen
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to check point inside polygon in C# using Aspose.GIS .NET.
    This guide covers geometry contains checks, geospatial analysis techniques, and
    best practices.
  headline: Check point inside polygon in C# with Aspose.GIS library
  type: TechArticle
- description: Learn how to check point inside polygon in C# using Aspose.GIS .NET.
    This guide covers geometry contains checks, geospatial analysis techniques, and
    best practices.
  name: Check point inside polygon in C# with Aspose.GIS library
  steps:
  - name: '**.NET development environment** – .NET 6 SDK (or later) installed.'
    text: '**.NET development environment** – .NET 6 SDK (or later) installed.'
  - name: '**Aspose.GIS for .NET** – Download the NuGet package from the official
      release page **[Aspose.GIS .NET release page](https://releases.aspose.com/gis/net/)**
      and add it to your project.'
    text: '**Aspose.GIS for .NET** – Download the NuGet package from the official
      release page **[Aspose.GIS .NET release page](https://releases.aspose.com/gis/net/)**
      and add it to your project.'
  - name: '**Basic C# knowledge** – Familiarity with classes, objects, and console
      applications.'
    text: '**Basic C# knowledge** – Familiarity with classes, objects, and console
      applications.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS fully supports .NET Core, allowing you to develop cross‑platform
      geospatial applications.
    question: Is Aspose.GIS compatible with .NET Core?
  - answer: Absolutely. The library includes spatial queries, distance calculations,
      geometry transformations, and spatial indexing.
    question: Can I perform advanced geospatial analysis with Aspose.GIS?
  - answer: Aspose.GIS receives regular updates—typically every 4‑6 weeks—to improve
      performance, add new formats, and fix bugs.
    question: How often are updates released for Aspose.GIS?
  - answer: Yes, you can join the Aspose GIS community forum **[Aspose GIS community
      forum](https://forum.aspose.com/c/gis/33)** to ask questions and share experiences.
    question: Is there a community forum for Aspose.GIS users?
  - answer: Certainly, you can explore Aspose.GIS by downloading the free trial **[Aspose
      releases page](https://releases.aspose.com/)**.
    question: Can I try Aspose.GIS before purchasing?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- point inside polygon
- aspose.gis
- c# geospatial
- geometry contains
title: Punkt innerhalb eines Polygons in C# mit der Aspose.GIS-Bibliothek prüfen
url: /de/net/geometry-analysis/check-geometry-contains-another/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Punkt in Polygon prüfen c# – Geometrie enthält prüfen

## Einführung
Wenn Sie **geospatial analysis .NET**‑Lösungen erstellen, ist eine der ersten Fragen, ob ein bestimmter Ort (ein Punkt) innerhalb eines definierten Bereichs (eines Polygons) liegt. In diesem Tutorial führen wir Sie durch eine vollständige **check point inside polygon**‑Implementierung mit der **Aspose.GIS .NET**‑Bibliothek. Egal, ob Sie einen Geofencing‑Dienst, eine Karten‑UI oder eine räumliche Analyse‑Pipeline erstellen, die folgenden Schritte bringen Sie in wenigen Minuten zum Laufen.

## Schnelle Antworten
- **Was bedeutet „check point inside polygon c#“?** Es ist eine räumliche Abfrage, die true zurückgibt, wenn eine Punktgeometrie vollständig innerhalb einer Polygongeometrie liegt.  
- **Welche .NET‑Bibliothek führt diese Prüfung durch?** Aspose.GIS für .NET bietet die Methoden `SpatiallyContains` und `Within` für schnelle Einschluss‑Tests.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Ist sie kompatibel mit .NET 6+ und .NET Core?** Ja – Aspose.GIS unterstützt moderne .NET‑Laufzeiten vollständig.  
- **Wie lange dauert die Implementierung?** Etwa 10 Minuten, um den Code zu kopieren und das Beispiel auszuführen.

## Was ist check point inside polygon c#?
Ein **check point inside polygon**‑Test bestimmt, ob die Koordinaten eines `Point`‑Objekts innerhalb der Grenzen eines `Polygon`‑Objekts liegen. In C# wird dies typischerweise von Geometriebibliotheken durchgeführt, die Ray‑Casting‑ oder Winding‑Number‑Algorithmen implementieren. Aspose.GIS abstrahiert diese Details und stellt eine einzeilige API bereit: `polygon.SpatiallyContains(point)`.

## Warum Aspose.GIS .NET für Prüfungen, ob Geometrie einen Punkt enthält, verwenden?
Aspose.GIS liefert ein umfangreiches, leistungsstarkes Geometriemodell. Es unterstützt **50+** Eingabe‑ und Ausgabeformate, verarbeitet bis zu **10 Millionen Scheitelpunkte pro Sekunde** auf einer Standard‑CPU mit 2,5 GHz und läuft auf **.NET Framework 4.6+, .NET Core 2.0+, .NET 5/6+**, wodurch 95 % der .NET‑Installationen abgedeckt werden. Die Bibliothek enthält zudem umfangreiche Dokumentation und Beispielcode, was die Integration von räumlicher Einschlusslogik in jedes .NET‑Projekt erleichtert.

## Häufige Anwendungsfälle für check point inside polygon c#
- **Geofencing:** Aktionen auslösen, wenn ein Gerät einen vordefinierten Servicebereich betritt oder verlässt.  
- **Kartenvisualisierung:** Regionen hervorheben, die einen vom Benutzer ausgewählten Punkt auf einer interaktiven Karte enthalten.  
- **Räumliche Analyse:** Große Datensätze filtern, um nur Datensätze zu behalten, die innerhalb eines Untersuchungsgebiets liegen.  
- **Lieferrouting:** Überprüfen, ob eine Lieferadresse innerhalb der Servicezone eines Kurierdienstes liegt.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie folgendes haben:

1. **.NET‑Entwicklungsumgebung** – .NET 6 SDK (oder neuer) installiert.  
2. **Aspose.GIS für .NET** – Laden Sie das NuGet‑Paket von der offiziellen Release‑Seite **[Aspose.GIS .NET release page](https://releases.aspose.com/gis/net/)** herunter und fügen Sie es Ihrem Projekt hinzu.  
3. **Grundkenntnisse in C#** – Vertrautheit mit Klassen, Objekten und Konsolenanwendungen.

### 1. .NET‑Entwicklungsumgebung einrichten
Stellen Sie sicher, dass das .NET‑SDK korrekt installiert ist und der Befehl `dotnet` in Ihrem Terminal verfügbar ist. Sie können die Installation überprüfen mit:

```
dotnet --version
```

Wenn der Befehl eine Versionsnummer zurückgibt (z. B. 6.0.300), sind Sie bereit, fortzufahren.

### 2. Aspose.GIS‑Installation
Installieren Sie Aspose.GIS für .NET, indem Sie die Bibliothek von der Release‑Seite **[Aspose.GIS .NET release page](https://releases.aspose.com/gis/net/)** herunterladen. Befolgen Sie die Installationsanweisungen in der Dokumentation **[Aspose.GIS .NET documentation](https://reference.aspose.com/gis/net/)**, um Aspose.GIS in Ihr Projekt zu integrieren.

### 3. Grundlegendes Verständnis von C#
Wenn Sie neu in C# sind, sollten Sie vor dem Eintauchen in die Code‑Beispiele den offiziellen Microsoft C#‑Leitfaden oder ein Schnellstart‑Tutorial durchgehen.

## Namespaces importieren
Die folgenden Namespaces bieten Zugriff auf Aspose.GIS‑Geometrietypen und räumliche Operationen.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt 1: Geometrieobjekte definieren
Ein `Polygon` definiert einen geschlossenen Bereich, während ein `Point` einen einzelnen Koordinatenort darstellt.

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

## Schritt 2: räumliche Einschließung prüfen
`SpatiallyContains` prüft, ob eine Geometrie eine andere Geometrie vollständig umschließt.

```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry2)); // False
```

## Schritt 3: weitere Geometrie definieren
Hier erstellen wir einen zweiten `Point`, der sich im äußeren Ring des Polygons befindet.

```csharp
var geometry3 = new Point(0.5, 0.5);
```

## Schritt 4: räumliche Einschließung erneut prüfen
Die Ausführung derselben Einschlussprüfung mit dem neuen Punkt gibt `true` zurück und bestätigt, dass der Punkt tatsächlich innerhalb der äußeren Grenze des Polygons liegt.

```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry3)); // True
```

## Schritt 5: äquivalente Funktionalität
`Within` gibt true zurück, wenn die Geometrie vollständig innerhalb einer anderen Geometrie liegt.

```csharp
Console.WriteLine(geometry3.Within(geometry1)); // True
```

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|-------|----------------|-----|
| **Unerwartetes `false` Ergebnis** | Punkt liegt in einem Loch (innerer Ring) des Polygons. | Stellen Sie sicher, dass Sie das richtige Polygon testen oder verwenden Sie `geometry1.ExteriorRing` für einfache Polygone ohne Löcher. |
| **NullReferenceException** | Geometrieobjekte wurden nicht initialisiert, bevor `SpatiallyContains` aufgerufen wurde. | Instanziieren Sie sowohl Polygon‑ als auch Point‑Objekte, bevor Sie räumliche Methoden aufrufen. |
| **Leistungsabfall bei großen Datensätzen** | Wiederholtes Erzeugen von Geometrieobjekten innerhalb von Schleifen. | Wiederverwenden von Geometrieinstanzen oder Stapelverarbeitung mit `GeometryCollection`. |

## Häufig gestellte Fragen

**Q: Ist Aspose.GIS mit .NET Core kompatibel?**  
A: Ja, Aspose.GIS unterstützt .NET Core vollständig und ermöglicht die Entwicklung plattformübergreifender geospatial‑Anwendungen.

**Q: Kann ich mit Aspose.GIS erweiterte geospatial‑Analysen durchführen?**  
A: Absolut. Die Bibliothek enthält räumliche Abfragen, Distanzberechnungen, Geometrie‑Transformationen und räumliche Indizierung.

**Q: Wie oft werden Updates für Aspose.GIS veröffentlicht?**  
A: Aspose.GIS erhält regelmäßige Updates – typischerweise alle 4‑6 Wochen – zur Leistungsverbesserung, zum Hinzufügen neuer Formate und zur Fehlerbehebung.

**Q: Gibt es ein Community‑Forum für Aspose.GIS‑Nutzer?**  
A: Ja, Sie können dem Aspose GIS Community‑Forum **[Aspose GIS community forum](https://forum.aspose.com/c/gis/33)** beitreten, um Fragen zu stellen und Erfahrungen zu teilen.

**Q: Kann ich Aspose.GIS vor dem Kauf testen?**  
A: Natürlich, Sie können Aspose.GIS erkunden, indem Sie die kostenlose Testversion von der **[Aspose releases page](https://releases.aspose.com/)** herunterladen.

**Q: Was passiert, wenn ich einen Punkt teste, der genau auf der Polygonkante liegt?**  
A: Aspose.GIS behandelt Punkte auf der Grenze als **inside** für die Methode `SpatiallyContains`. Verwenden Sie `Touches`, wenn Sie nur Kanten‑Erkennung benötigen.

## Fazit
In diesem Leitfaden haben wir eine praktische **check point inside polygon**‑Lösung mit Aspose.GIS für .NET demonstriert. Durch das Definieren Ihrer Geometrien und die Nutzung der Methode `SpatiallyContains` (oder `Within`) können Sie Einschluss‑Abfragen schnell beantworten – ein wesentlicher Bestandteil jedes **geospatial analysis .NET**‑Workflows. Experimentieren Sie gern mit größeren Datensätzen, verschiedenen Geometrietypen und kombinieren Sie diese Prüfungen mit anderen Aspose.GIS‑Funktionen wie Distanzberechnungen oder räumlicher Indizierung.

---

**Last Updated:** 2026-08-03  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Wie man Polygongeometrie mit Aspose.GIS für .NET erstellt](/gis/net/geometry-creation/create-polygon-geometry/)
- [Polygongeometrie in C# erstellen und Schnittprüfung mit Aspose.GIS für .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Wie man den Schwerpunkt einer Geometrie mit Aspose.GIS für .NET berechnet](/gis/net/geometry-analysis/get-geometry-centroid/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
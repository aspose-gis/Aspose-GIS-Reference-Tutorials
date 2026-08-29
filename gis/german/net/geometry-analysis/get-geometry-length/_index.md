---
date: 2026-08-13
description: Erfahren Sie, wie Sie Geometry Length in .NET mit Aspose.GIS für effizientes
  Spatial Data Handling berechnen. Enthält Beispiele für get line length C# und calculate
  line length C#.
keywords:
- calculate geometry length .net
- Aspose.GIS length calculation
- C# geometry length
lastmod: 2026-08-13
linktitle: Geometry Length abrufen
og_description: Berechnen Sie Geometry Length in .NET mit Aspose.GIS. Beispiele für
  get line length C# und polygon perimeter in einem prägnanten, leistungsstarken Leitfaden
  für .NET‑Entwickler.
og_image_alt: Developer guide showing how to calculate geometry length in .NET with
  Aspose.GIS
og_title: Geometry Length in .NET mit Aspose.GIS berechnen – Schnelle Spatial Measurements
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to calculate geometry length .NET using Aspose.GIS for efficient
    spatial data handling. Includes get line length C# and calculate line length C#
    examples.
  headline: How to Calculate Geometry Length .NET with Aspose.GIS
  type: TechArticle
- description: Learn how to calculate geometry length .NET using Aspose.GIS for efficient
    spatial data handling. Includes get line length C# and calculate line length C#
    examples.
  name: How to Calculate Geometry Length .NET with Aspose.GIS
  steps:
  - name: Create geometry objects
    text: To begin with, create the geometry objects representing the shapes for which
      you want to calculate the length. This can include lines, polygons, or any other
      geometrical shapes.
  - name: Calculate line length in C#
    text: Once you have created the line geometry, you can calculate its length using
      the `GetLength()` method. This demonstrates **calculate line length c#** in
      a single line of code.
  - name: Create polygon geometry
    text: Similarly, you can create polygon geometry objects using the `Polygon` and
      `LinearRing` classes.
  - name: Get length of a polygon
    text: For polygons, the `GetLength()` method returns the perimeter, which is effectively
      the **how to get length** of the shape.
  type: HowTo
- questions:
  - answer: Aspose.GIS for .NET is compatible with .NET Framework 4.6.1 or later versions,
      as well as .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with all .NET frameworks?
  - answer: Yes, you can avail of a free trial of Aspose.GIS for .NET from [here](https://releases.aspose.com/).
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: You can find support and assistance from the Aspose.GIS community forum
      [here](https://forum.aspose.com/c/gis/33).
    question: Where can I find support for Aspose.GIS for .NET?
  - answer: You can acquire a temporary license from [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Yes, Aspose.GIS for .NET provides various formatting options to customize
      the output format as per your requirements.
    question: Can I customize the output format for geometry length calculations?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geometry length
- Aspose.GIS
- C# GIS
- spatial calculations
- line length
title: Wie man Geometry Length in .NET mit Aspose.GIS berechnet
url: /de/net/geometry-analysis/get-geometry-length/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Geometrie‑Länge in .NET mit Aspose.GIS berechnet

## Einleitung
Wenn Sie nach einer klaren, praktischen Methode suchen, um **die Geometrie‑Länge in .NET zu berechnen**, sind Sie hier genau richtig. Aspose.GIS für .NET bietet Ihnen ein umfangreiches Set an GIS‑fokussierten APIs, die räumliche Berechnungen – wie das Messen von Linienlänge oder Polygonumfang – einfach und performant machen. In diesem Tutorial führen wir Sie durch den gesamten Prozess, vom Einrichten der Umgebung bis zum Schreiben des C#‑Codes, der genaue Längenwerte zurückgibt.

## Schnelle Antworten
- **Was gibt “GetLength()” zurück?** Für Linien gibt sie die Linienlänge zurück; für Polygone den Umfang.  
- **Welcher Namespace ist erforderlich?** `Aspose.Gis.Geometries`.  
- **Kann ich das mit .NET 6 verwenden?** Ja, Aspose.GIS unterstützt .NET 5, .NET 6 und später.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert für die Evaluierung; eine Lizenz ist für die Produktion erforderlich.  
- **Ist die Berechnung einheiten‑bewusst?** Die Länge wird in den Einheiten des Koordinatensystems zurückgegeben (z. B. Meter für projizierte CRS).  

## Was ist Geometrie‑Länge?
Geometry.GetLength() berechnet die gesamte lineare Distanz eines Geometrie‑Objekts basierend auf seinen Koordinatenwerten. Für ein LineString summiert es die Abstände zwischen aufeinanderfolgenden Scheitelpunkten und gibt die Linienlänge zurück. Wird es auf ein Polygon angewendet, addiert es die Längen aller Kanten und liefert damit effektiv den Umfang der Form.

## Warum Aspose.GIS für Längenberechnungen verwenden?
Aspose.GIS bietet eine vollständig verwaltete .NET‑Bibliothek, die räumliche Berechnungen ohne native Binärdateien durchführt, wodurch die Bereitstellung auf Windows, Linux und macOS einfach wird. Sie unterstützt über fünfzig Koordinatenreferenzsysteme und liefert hochpräzise Double‑Precision‑Ergebnisse selbst für mehrere hundert Kilometer lange LineStrings und integriert sich nahtlos in .NET 5/6/7‑Projekte, was konsistente Leistung und Genauigkeit gewährleistet.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

### 1. Aspose.GIS für .NET Bibliothek
Zunächst müssen Sie die Aspose.GIS für .NET Bibliothek in Ihrer Entwicklungsumgebung installiert haben. Falls Sie dies noch nicht getan haben, können Sie sie von der [Aspose.GIS für .NET Dokumentation](https://reference.aspose.com/gis/net/) Seite herunterladen.

### 2. .NET‑Entwicklungsumgebung
Stellen Sie sicher, dass Sie eine .NET‑Entwicklungsumgebung auf Ihrem Rechner eingerichtet haben. Dazu gehört, dass Visual Studio oder ein anderes kompatibles IDE installiert ist.

### 3. Grundlegendes Verständnis von C#
Ein grundlegendes Verständnis der Programmiersprache C# ist erforderlich, um diesem Tutorial folgen zu können.

## Namespaces importieren
Um die von Aspose.GIS für .NET bereitgestellten Funktionalitäten zu nutzen, müssen Sie die erforderlichen Namespaces in Ihr C#‑Projekt importieren.

### Importieren des Aspose.GIS Namespaces
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Wie man die Linienlänge in C# ermittelt
Ein `LineString` in Aspose.GIS stellt eine Reihe von zwei‑ oder mehr Punkten dar, die durch gerade Liniensegmente verbunden sind und lineare Merkmale wie Straßen, Flüsse oder Versorgungsleitungen innerhalb eines bestimmten Koordinatenreferenzsystems modellieren.  
Nachdem Sie den `LineString` mit den gewünschten Scheitelpunkten erstellt haben, liefert der Aufruf der Methode `GetLength()` die Gesamtdistanz in den Einheiten des CRS der Geometrie, sodass Sie schnell präzise Linienmessungen für Routing, distanzbasierte Analysen oder Berichtszwecke erhalten können, die bei Bedarf weiterverarbeitet oder gespeichert werden.

### Schritt 1: Geometrieobjekte erstellen
Beginnen Sie damit, die Geometrieobjekte zu erstellen, die die Formen repräsentieren, für die Sie die Länge berechnen möchten. Dies kann Linien, Polygone oder andere geometrische Formen umfassen.

```csharp
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(2, 2);
line.AddPoint(2, 0);
```

### Schritt 2: Linienlänge in C# berechnen
Nachdem Sie die Liniengeometrie erstellt haben, können Sie ihre Länge mit der Methode `GetLength()` berechnen. Dies demonstriert **Linienlänge in C# berechnen** in einer einzigen Codezeile.

```csharp
Console.WriteLine("{0:F}", line.GetLength()); // Output: 4.83
```

## Wie man die Polygonlänge in C# berechnet
Ein `Polygon` in Aspose.GIS besteht aus einem äußeren `LinearRing`, der seine Grenze definiert, und optionalen inneren Ringen für Löcher, die Flächenmerkmale wie Parzellen, Seen oder Verwaltungszonen innerhalb einer bestimmten räumlichen Referenz darstellen.  
Erstellen Sie den äußeren `LinearRing`, indem Sie die Eckpunkte des Polygons angeben, und instanziieren Sie anschließend ein `Polygon` mit diesem Ring; der Aufruf von `GetLength()` auf dem Polygon berechnet den gesamten Umfang, was für Aufgaben wie die Schätzung der Zaunlänge, Grenzberichte oder die Umrechnung von Umfangswerten in andere Einheiten nützlich ist.

### Schritt 3: Polygongeometrie erstellen
Analog können Sie Polygongeometrieobjekte mit den Klassen `Polygon` und `LinearRing` erstellen.

```csharp
var rectangle = new Polygon(new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(1, 0),
    new Point(0, 0),
}));
```

### Schritt 4: Länge eines Polygons ermitteln
Für Polygone gibt die Methode `GetLength()` den Umfang zurück, was im Wesentlichen **wie man die Länge erhält** der Form ist.

```csharp
Console.WriteLine("{0:F}", rectangle.GetLength()); // Output: 4.00
```

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Unerwartete Nulllänge** | Stellen Sie sicher, dass das Koordinatensystem der Geometrie mit den von Ihnen bereitgestellten Daten übereinstimmt; doppelte Punkte können Null‑Längen‑Segmente verursachen. |
| **Falsche Einheiten** | Denken Sie daran, dass `GetLength()` Werte in den CRS‑Einheiten zurückgibt. Konvertieren Sie bei Bedarf in Meter/Fuß. |
| **Leistung bei großen Datensätzen** | Wiederverwenden Sie Geometrieobjekte, wenn möglich, und vermeiden Sie das Erstellen von Tausenden temporärer Punkte in engen Schleifen. |

## Häufig gestellte Fragen

**F: Ist Aspose.GIS für .NET mit allen .NET‑Frameworks kompatibel?**  
A: Aspose.GIS für .NET ist kompatibel mit .NET Framework 4.6.1 oder neueren Versionen sowie mit .NET 5/6/7.

**F: Kann ich Aspose.GIS für .NET vor dem Kauf testen?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.GIS für .NET unter [hier](https://releases.aspose.com/) erhalten.

**F: Wo finde ich Support für Aspose.GIS für .NET?**  
A: Sie finden Unterstützung und Hilfe im Aspose.GIS Community‑Forum [hier](https://forum.aspose.com/c/gis/33).

**F: Wie kann ich eine temporäre Lizenz für Aspose.GIS für .NET erhalten?**  
A: Sie können eine temporäre Lizenz unter [hier](https://purchase.aspose.com/temporary-license/) erwerben.

**F: Kann ich das Ausgabeformat für Geometrie‑Längenberechnungen anpassen?**  
A: Ja, Aspose.GIS für .NET bietet verschiedene Formatierungsoptionen, um das Ausgabeformat nach Ihren Anforderungen anzupassen.

## Fazit
In diesem Tutorial haben wir **wie man die Geometrie‑Länge in .NET berechnet** für sowohl Linien- als auch Polygongeometrien mit Aspose.GIS für .NET behandelt. Durch das Befolgen der Schritt‑für‑Schritt‑Beispiele können Sie nun präzise räumliche Messungen in jede .NET‑Anwendung integrieren, sei es ein Desktop‑GIS‑Tool, ein Web‑Service oder eine Backend‑Datenverarbeitungspipeline.

---

**Zuletzt aktualisiert:** 2026-08-13  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [Erfahren Sie, wie Sie LineString-Geometrie mit Aspose.GIS für .NET erstellen](/gis/net/geometry-creation/create-linestring-geometry/)
- [Wie man Fläche mit Aspose.GIS für .NET berechnet](/gis/net/geometry-analysis/get-geometry-area/)
- [Wie man Punktgeometrie erstellt und den Geometrietyp mit Aspose.GIS für .NET ermittelt](/gis/net/geometry-analysis/get-geometry-type/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
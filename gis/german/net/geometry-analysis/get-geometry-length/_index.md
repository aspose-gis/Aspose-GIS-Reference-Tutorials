---
date: 2025-12-07
description: Erfahren Sie, wie Sie die Länge von Geometrien in .NET mit Aspose.GIS
  für eine effiziente Verarbeitung räumlicher Daten berechnen. Schritt‑für‑Schritt‑Anleitung
  mit Codebeispielen.
linktitle: Get Geometry Length
second_title: Aspose.GIS .NET API
title: Wie man die Länge einer Geometrie in .NET mit Aspose.GIS berechnet
url: /de/net/geometry-analysis/get-geometry-length/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Länge von Geometrien in .NET mit Aspose.GIS berechnet

## Einleitung
Wenn Sie nach einer klaren, praktischen Methode **wie man die Länge** von geometrischen Objekten in einer .NET‑Anwendung berechnet, sind Sie hier genau richtig. Aspose.GIS für .NET bietet Ihnen ein umfangreiches Set an GIS‑fokussierten APIs, die räumliche Berechnungen – wie das Messen von Linienlänge oder Polygon‑Umfang – einfach und performant machen. In diesem Tutorial führen wir Sie durch den gesamten Prozess, von der Einrichtung der Umgebung bis zum Schreiben des C#‑Codes, der genaue Längenwerte zurückgibt.

## Schnelle Antworten
- **Was gibt “GetLength()” zurück?** Für Linien gibt es die Linienlänge zurück; für Polygone den Umfang.  
- **Welcher Namespace wird benötigt?** `Aspose.Gis.Geometries`.  
- **Kann ich das mit .NET 6 verwenden?** Ja, Aspose.GIS unterstützt .NET 5, .NET 6 und neuere Versionen.  
- **Brauche ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion reicht für die Evaluierung; für die Produktion ist eine Lizenz erforderlich.  
- **Ist die Berechnung einheiten‑bewusst?** Die Länge wird in den Einheiten des Koordinatensystems zurückgegeben (z. B. Meter für ein projiziertes CRS).

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

### 1. Aspose.GIS für .NET Bibliothek
Zunächst müssen Sie die Aspose.GIS für .NET‑Bibliothek in Ihrer Entwicklungsumgebung installiert haben. Falls Sie das noch nicht getan haben, können Sie sie von der [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/) Seite herunterladen.

### 2. .NET Entwicklungsumgebung
Stellen Sie sicher, dass Sie eine .NET‑Entwicklungsumgebung auf Ihrem Rechner eingerichtet haben. Dazu gehört Visual Studio oder eine andere kompatible IDE.

### 3. Grundlegendes Verständnis von C#
Ein grundlegendes Verständnis der Programmiersprache C# ist erforderlich, um diesem Tutorial folgen zu können.

## Namespaces importieren
Um die von Aspose.GIS für .NET bereitgestellten Funktionalitäten zu nutzen, müssen Sie die erforderlichen Namespaces in Ihr C#‑Projekt importieren.

### Aspose.GIS Namespace importieren
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Was ist Geometrie‑Länge?
`Geometry.GetLength()` ist eine Methode, die die lineare Messung eines Geometrie‑Objekts zurückgibt. Für ein `LineString` liefert sie die gesamte Linienlänge, während sie für ein `Polygon` den Umfang (die Summe aller Kanten) zurückgibt. Diese Methode abstrahiert die zugrunde liegende Mathematik, sodass Sie sich auf die höhere GIS‑Logik konzentrieren können.

## Warum Aspose.GIS für Längenberechnungen verwenden?
- **Keine externen Abhängigkeiten** – reine .NET‑Bibliothek, keine nativen DLLs.  
- **Hohe Präzision** – verwendet double‑Precision‑Arithmetik für genaue Ergebnisse.  
- **Plattformübergreifend** – funktioniert unter Windows, Linux und macOS mit .NET Core/5/6+.  

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Geometrie‑Objekte erstellen
Erstellen Sie zunächst die Geometrie‑Objekte, die die Formen repräsentieren, für die Sie die Länge berechnen möchten. Dies kann Linien, Polygone oder andere geometrische Formen umfassen.

```csharp
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(2, 2);
line.AddPoint(2, 0);
```

### Schritt 2: Wie man die Linienlänge in C# berechnet
Nachdem Sie die Liniengeometrie erstellt haben, können Sie ihre Länge mit der `GetLength()`‑Methode berechnen. Dies demonstriert **calculate line length c#** in einer einzigen Code‑Zeile.

```csharp
Console.WriteLine("{0:F}", line.GetLength()); // Output: 4.83
```

### Schritt 3: Polygon‑Geometrie erstellen
Analog können Sie Polygon‑Geometrie‑Objekte mit den Klassen `Polygon` und `LinearRing` erzeugen.

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

### Schritt 4: Wie man die Länge eines Polygons erhält
Für Polygone gibt die `GetLength()`‑Methode den Umfang zurück, was im Wesentlichen **how to get length** der Form ist.

```csharp
Console.WriteLine("{0:F}", rectangle.GetLength()); // Output: 4.00
```

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Unerwartet null Länge** | Prüfen Sie, ob das Koordinatensystem der Geometrie mit den bereitgestellten Daten übereinstimmt; doppelte Punkte können Segmente mit Länge 0 erzeugen. |
| **Falsche Einheiten** | Denken Sie daran, dass `GetLength()` Werte in den CRS‑Einheiten zurückgibt. Konvertieren Sie bei Bedarf zu Metern/Fuß. |
| **Performance bei großen Datensätzen** | Wiederverwenden Sie Geometrie‑Objekte, wenn möglich, und vermeiden Sie das Erzeugen tausender temporärer Punkte in engen Schleifen. |

## Häufig gestellte Fragen

**F: Ist Aspose.GIS für .NET mit allen .NET‑Frameworks kompatibel?**  
A: Aspose.GIS für .NET ist kompatibel mit .NET Framework 4.6.1 oder neueren Versionen sowie .NET 5/6/7.

**F: Kann ich Aspose.GIS für .NET vor dem Kauf testen?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.GIS für .NET [hier](https://releases.aspose.com/) erhalten.

**F: Wo finde ich Support für Aspose.GIS für .NET?**  
A: Support und Hilfe erhalten Sie im Aspose.GIS Community‑Forum [hier](https://forum.aspose.com/c/gis/33).

**F: Wie kann ich eine temporäre Lizenz für Aspose.GIS für .NET erhalten?**  
A: Eine temporäre Lizenz können Sie [hier](https://purchase.aspose.com/temporary-license/) erwerben.

**F: Kann ich das Ausgabeformat für Längenberechnungen anpassen?**  
A: Ja, Aspose.GIS für .NET bietet verschiedene Formatierungsoptionen, um das Ausgabeformat nach Ihren Anforderungen zu gestalten.

## Fazit
In diesem Tutorial haben wir **wie man die Länge** sowohl von Linien‑ als auch von Polygon‑Geometrien mit Aspose.GIS für .NET berechnet. Durch die schritt‑für‑schritt‑Beispiele können Sie nun präzise räumliche Messungen in jede .NET‑Anwendung integrieren, sei es ein Desktop‑GIS‑Tool, ein Web‑Service oder eine Backend‑Datenverarbeitungspipeline.

---

**Zuletzt aktualisiert:** 2025-12-07  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-02-10
description: Erfahren Sie, wie Sie die Geometrie‑Länge in .NET mit Aspose.GIS für
  eine effiziente räumliche Datenverarbeitung berechnen. Enthält Beispiele zum Abrufen
  der Linienlänge in C# und zum Berechnen der Linienlänge in C#.
linktitle: Get Geometry Length
second_title: Aspose.GIS .NET API
title: Wie man die Länge einer Geometrie in .NET mit Aspose.GIS berechnet
url: /de/net/geometry-analysis/get-geometry-length/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Geometrie‑Länge in .NET mit Aspose.GIS berechnet

## Einführung
Wenn Sie nach einer klaren, praktischen Methode suchen, um **calculate geometry length .NET** zu berechnen, sind Sie hier genau richtig. Aspose.GIS für .NET bietet Ihnen ein umfangreiches Set an GIS‑fokussierten APIs, die räumliche Berechnungen – wie das Messen von Linienlänge oder Polygonumfang – einfach und performant machen. In diesem Tutorial führen wir Sie durch den gesamten Prozess, von der Einrichtung der Umgebung bis zum Schreiben des C#‑Codes, der genaue Längenwerte zurückgibt.

## Schnelle Antworten
- **What does “GetLength()” return?** Für Linien gibt sie die Linienlänge zurück; für Polygone den Umfang.  
- **Which namespace is required?** `Aspose.Gis.Geometries`.  
- **Can I use this with .NET 6?** Ja, Aspose.GIS unterstützt .NET 5, .NET 6 und neuere Versionen.  
- **Do I need a license for development?** Eine kostenlose Testversion reicht für die Evaluierung; für den Produktionseinsatz ist eine Lizenz erforderlich.  
- **Is the calculation unit‑aware?** Die Länge wird in den Einheiten des Koordinatensystems zurückgegeben (z. B. Meter für projizierte CRS).

## Was ist Geometry Length?
`Geometry.GetLength()` ist eine Methode, die die lineare Messung eines Geometrie‑Objekts zurückgibt. Für ein `LineString` liefert sie die Gesamtlänge der Linie, während sie für ein `Polygon` den Umfang (die Summe aller Kanten) zurückgibt. Diese Methode abstrahiert die zugrunde liegende Mathematik, sodass Sie sich auf die höhere GIS‑Logik konzentrieren können.

## Warum Aspose.GIS für Längenberechnungen verwenden?
- **No external dependencies** – reine .NET‑Bibliothek, keine nativen DLLs.  
- **High precision** – verwendet double‑Precision‑Arithmetik für genaue Ergebnisse.  
- **Cross‑platform** – funktioniert auf Windows, Linux und macOS mit .NET Core/5/6+.  

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

### 1. Aspose.GIS for .NET Library
Zunächst müssen Sie die Aspose.GIS for .NET‑Bibliothek in Ihrer Entwicklungsumgebung installiert haben. Falls Sie dies noch nicht getan haben, können Sie sie von der Seite [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/) herunterladen.

### 2. .NET Development Environment
Stellen Sie sicher, dass auf Ihrem Rechner eine .NET‑Entwicklungsumgebung eingerichtet ist. Dazu gehört Visual Studio oder ein anderes kompatibles IDE.

### 3. Basic Understanding of C#
Ein grundlegendes Verständnis der Programmiersprache C# ist erforderlich, um diesem Tutorial folgen zu können.

## Namespaces importieren
Um die von Aspose.GIS for .NET bereitgestellten Funktionalitäten zu nutzen, müssen Sie die erforderlichen Namespaces in Ihr C#‑Projekt importieren.

### Import Aspose.GIS Namespace
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Wie man Linienlänge in C# ermittelt
### Schritt 1: Geometry‑Objekte erstellen
Erstellen Sie zunächst die Geometrie‑Objekte, die die Formen repräsentieren, für die Sie die Länge berechnen möchten. Dies kann Linien, Polygone oder andere geometrische Formen umfassen.

```csharp
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(2, 2);
line.AddPoint(2, 0);
```

### Schritt 2: Linienlänge in C# berechnen
Nachdem Sie die Liniengeometrie erstellt haben, können Sie deren Länge mit der Methode `GetLength()` berechnen. Dies demonstriert **calculate line length c#** in einer einzigen Codezeile.

```csharp
Console.WriteLine("{0:F}", line.GetLength()); // Output: 4.83
```

## Wie man Linienlänge in C# für Polygone berechnet
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

### Schritt 4: Länge eines Polygons ermitteln
Für Polygone gibt die Methode `GetLength()` den Umfang zurück, was effektiv das **how to get length** der Form ist.

```csharp
Console.WriteLine("{0:F}", rectangle.GetLength()); // Output: 4.00
```

## Häufige Probleme und Lösungen
| Problem | Lösung |
|---------|--------|
| **Unexpected zero length** | Stellen Sie sicher, dass das Koordinatensystem der Geometrie mit den bereitgestellten Daten übereinstimmt; doppelte Punkte können Segmente mit Länge 0 erzeugen. |
| **Incorrect units** | Denken Sie daran, dass `GetLength()` Werte in den CRS‑Einheiten zurückgibt. Konvertieren Sie bei Bedarf in Meter/Fuß. |
| **Performance with large datasets** | Wiederverwenden Sie Geometrie‑Objekte, wenn möglich, und vermeiden Sie das Erzeugen von tausenden temporären Punkten in engen Schleifen. |

## Häufig gestellte Fragen

**Q: Ist Aspose.GIS for .NET mit allen .NET‑Frameworks kompatibel?**  
A: Aspose.GIS for .NET ist kompatibel mit .NET Framework 4.6.1 oder neueren Versionen sowie mit .NET 5/6/7.

**Q: Kann ich Aspose.GIS for .NET vor dem Kauf testen?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.GIS for .NET unter [here](https://releases.aspose.com/) erhalten.

**Q: Wo finde ich Support für Aspose.GIS for .NET?**  
A: Unterstützung und Hilfe erhalten Sie im Aspose.GIS Community‑Forum [here](https://forum.aspose.com/c/gis/33).

**Q: Wie kann ich eine temporäre Lizenz für Aspose.GIS for .NET erhalten?**  
A: Eine temporäre Lizenz können Sie unter [here](https://purchase.aspose.com/temporary-license/) erwerben.

**Q: Kann ich das Ausgabeformat für Geometrie‑Längenberechnungen anpassen?**  
A: Ja, Aspose.GIS for .NET bietet verschiedene Formatierungsoptionen, um das Ausgabeformat nach Ihren Anforderungen zu gestalten.

## Fazit
In diesem Tutorial haben wir **how to calculate geometry length .NET** für sowohl Linien‑ als auch Polygongeometrien mit Aspose.GIS for .NET behandelt. Durch die schritt‑für‑schritt Beispiele können Sie nun präzise räumliche Messungen in jede .NET‑Anwendung integrieren, sei es ein Desktop‑GIS‑Tool, ein Web‑Service oder eine Backend‑Datenverarbeitungspipeline.

---

**Zuletzt aktualisiert:** 2026-02-10  
**Getestet mit:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
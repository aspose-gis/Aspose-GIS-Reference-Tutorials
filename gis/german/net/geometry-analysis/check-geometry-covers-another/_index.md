---
date: 2026-08-03
description: Erfahren Sie, wie Sie mit Aspose.GIS für .NET einen Linestring in C#
  erstellen, Punkte zu einem Linestring hinzufügen und mithilfe der covers-Methode
  prüfen, ob ein Punkt auf einer Linie liegt.
keywords:
- create linestring c#
- point on line check
- add points to linestring
- use covers method
lastmod: 2026-08-03
linktitle: Linestring in C# erstellen – Prüfen, ob Geometrie eine andere abdeckt
og_description: Linestring in C# erstellen und Punkt‑auf‑Linie mit der Aspose.GIS
  covers-Methode verifizieren. Erfahren Sie präzise Geometrie‑Prüfungen für .NET‑Anwendungen.
  (150‑160 Zeichen)
og_image_alt: Developer guide showing linestring creation and covers check in C# with
  Aspose.GIS
og_title: Linestring in C# erstellen – Prüfen, ob Geometrie eine andere abdeckt (50‑60
  Zeichen)
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  headline: Create linestring c# – Check geometry covers another
  type: TechArticle
- description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  name: Create linestring c# – Check geometry covers another
  steps:
  - name: create a linestring object
    text: The `LineString` class represents a sequence of points connected by straight
      line segments in a two‑dimensional plane. Here, we instantiate a new `LineString`
      object, which represents a sequence of connected line segments in a two‑dimensional
      space.
  - name: add points to linestring
    text: '`AddPoint` appends a coordinate pair to the end of the `LineString` collection,
      preserving the order of insertion. We **add points to linestring** using the
      `AddPoint` method. In this example, we add two points: (0, 0) and (1, 1), forming
      a simple diagonal line segment.'
  - name: create a point object
    text: The `Point` class models a single location in a two‑dimensional coordinate
      system. Instantiate a `Point` object representing a single point in a two‑dimensional
      space. Here, we create a point at coordinates (0, 0).
  - name: perform a point on line check – does the line cover the point?
    text: '`Covers` determines whether the first geometry completely contains the
      second geometry, returning true only when every point of the second geometry
      lies inside the first. Use the `Covers` method to check if the line covers the
      point. In this case, it returns `True` because the point (0, 0) lies exac'
  - name: verify the reverse relationship – is the point covered by the line?
    text: '`CoveredBy` is the inverse of `Covers`; it returns true when the invoking
      geometry is entirely inside the target geometry. Similarly, use the `CoveredBy`
      method to check if the point is covered by the line. Since the point (0, 0)
      lies on the line, it also returns `True`.'
  type: HowTo
- questions:
  - answer: Yes, you can use Aspose.GIS for .NET in both commercial and non‑commercial
      projects after obtaining the appropriate license.
    question: Can I use Aspose.GIS for .NET in my commercial projects?
  - answer: Yes, Aspose.GIS for .NET is compatible with both .NET Framework and .NET
      Core environments.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Yes, Aspose.GIS for .NET supports a wide range of GIS formats including
      Shapefile, GeoJSON, KML, and more.
    question: Does Aspose.GIS for .NET support various GIS formats?
  - answer: Aspose.GIS for .NET is a proprietary library developed by Aspose, so external
      contributions are not accepted. However, you can provide feedback and suggestions
      to improve the library.
    question: Can I contribute to the development of Aspose.GIS for .NET?
  - answer: Updates for Aspose.GIS for .NET are released regularly to introduce new
      features, enhancements, and bug fixes. Check the [website](https://releases.aspose.com/gis/net/)
      for the latest releases.
    question: How often are updates released for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create linestring
- Aspose.GIS
- C# geometry analysis
title: Linestring in C# erstellen – Prüfen, ob Geometrie eine andere abdeckt
url: /de/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Geometrie prüfen, ob sie eine andere abdeckt

## Einleitung
In diesem Tutorial lernen Sie **wie man linestring c# erstellt** mit Aspose.GIS für .NET, Punkte zu einem linestring hinzuzufügen und eine zuverlässige **Punkt‑auf‑Linie‑Prüfung** mit den Methoden `Covers` und `CoveredBy` durchzuführen. Egal, ob Sie ein Mapping‑Tool bauen, räumliche Analysen durchführen oder einfach geometrische Beziehungen verifizieren müssen – das Beherrschen dieser Operationen verleiht Ihrer Anwendung die nötige Präzision.

## Schnelle Antworten
- **Was bedeutet „create linestring c#“?** Es bedeutet, ein `LineString` Geometrieobjekt zu instanziieren und es mit Koordinatenpunkten zu füllen.  
- **Welche Methode prüft, ob ein Punkt auf einer Linie liegt?** Verwenden Sie die `Covers`‑Methode auf dem `LineString` oder `CoveredBy` auf dem `Point`.  
- **Benötige ich eine Lizenz, um das Beispiel auszuführen?** Eine temporäre Lizenz reicht für die Evaluierung; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Kann das mit .NET Core verwendet werden?** Ja, Aspose.GIS unterstützt .NET Framework und .NET Core.  
- **Wie viele Punkte kann ich zu einem Linestring hinzufügen?** Es gibt keine feste Obergrenze; Sie können so viele Punkte hinzufügen, wie für Ihre räumliche Analyse nötig sind.

## Was ist create linestring c#?
`LineString` ist eine geometrische Form, die aus einer geordneten Liste von Punkten besteht, die durch gerade Liniensegmente verbunden sind. In C# erstellen Sie sie, indem Sie die `LineString`‑Klasse aus dem Namespace `Aspose.Gis.Geometries` instanziieren und dann **add points to linestring** mittels der `AddPoint`‑Methode hinzufügen. Dieses Objekt dient als Grundlage für jede lineare räumliche Analyse, wie Routenplanung oder Netzverfolgung.

## Warum Aspose.GIS für eine Punkt‑auf‑Linie‑Prüfung verwenden?
`Covers` ist eine räumliche Prädikat‑Methode, die **true** zurückgibt, wenn die erste Geometrie die zweite Geometrie vollständig enthält.  
Aspose.GIS bietet eine deterministische, hochpräzise Implementierung räumlicher Prädikate. Es unterstützt mehr als 50 Eingabe‑ und Ausgabe‑GIS‑Formate, kann mehrhundert‑Kilometer‑Liniennetze verarbeiten, ohne den gesamten Datensatz in den Speicher zu laden, und läuft auf .NET Framework, .NET Core und .NET 5/6+. Die Verwendung der `Covers`‑Methode stellt sicher, dass Rundungsfehler von Gleitkommazahlen berücksichtigt werden, und liefert zuverlässige Punkt‑auf‑Linie‑Ergebnisse selbst in anspruchsvollen Unternehmensszenarien.

## Voraussetzungen
Bevor Sie mit der Verwendung von Aspose.GIS für .NET beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen eingerichtet sind:

### 1. Visual Studio installieren
Stellen Sie sicher, dass Visual Studio auf Ihrem System installiert ist. Aspose.GIS für .NET lässt sich nahtlos in Visual Studio integrieren und bietet ein reibungsloses Entwicklungserlebnis.

### 2. Aspose.GIS für .NET erhalten
Laden Sie die Aspose.GIS für .NET‑Bibliothek von der [Website](https://releases.aspose.com/gis/net/) herunter. Sie können die Bibliothek entweder direkt herunterladen oder einen Paketmanager wie NuGet verwenden, um sie in Ihr Projekt zu installieren.

### 3. Vertrautheit mit dem .NET Framework
Grundlegende Kenntnisse des .NET‑Frameworks und der Programmiersprache C# sind erforderlich, um Aspose.GIS für .NET effektiv zu nutzen.

### 4. Zugriff auf Dokumentation und Support
Siehe die [Dokumentation](https://reference.aspose.com/gis/net/) für detaillierte Informationen zu den Aspose.GIS‑APIs und Funktionen. Falls Sie Probleme haben oder Fragen haben, nutzen Sie das [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) für Unterstützung.

### 5. Optional: temporäre Lizenz
Wenn Sie Aspose.GIS für .NET erkunden, können Sie eine temporäre Lizenz von der [temporären Lizenzseite](https://purchase.aspose.com/temporary-license/) erhalten, um die Funktionen der Bibliothek zu evaluieren.

## Namespaces importieren
Bevor Sie Aspose.GIS für .NET in Ihrem Projekt verwenden, müssen Sie die erforderlichen Namespaces importieren:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Jetzt zerlegen wir das bereitgestellte Beispiel in mehrere Schritte, um zu verstehen, wie man mit Aspose.GIS für .NET **prüft, ob eine Geometrie eine andere abdeckt**.

## Wie man linestring c# erstellt – Schritt‑für‑Schritt‑Anleitung
Laden Sie Ihr Projekt, importieren Sie die erforderlichen Namespaces und folgen Sie dann den fünf knappen Schritten unten. Mit nur wenigen Codezeilen erhalten Sie ein `LineString`‑Objekt, ein `Point`‑Objekt und zwei boolesche Prüfungen, die Ihnen sagen, ob die Linie den Punkt abdeckt und ob der Punkt von der Linie abgedeckt wird.

### Schritt 1: ein linestring‑Objekt erstellen
Die `LineString`‑Klasse repräsentiert eine Sequenz von Punkten, die durch gerade Liniensegmente in einer zweidimensionalen Ebene verbunden sind.  
```csharp
var line = new LineString();
```
Hier instanziieren wir ein neues `LineString`‑Objekt, das eine Sequenz verbundener Liniensegmente in einem zweidimensionalen Raum darstellt.

### Schritt 2: Punkte zum linestring hinzufügen
`AddPoint` fügt ein Koordinatenpaar am Ende der `LineString`‑Sammlung hinzu und bewahrt die Einfüge‑Reihenfolge.  
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
Wir **add points to linestring** mittels der `AddPoint`‑Methode. In diesem Beispiel fügen wir zwei Punkte hinzu: (0, 0) und (1, 1), wodurch ein einfaches diagonales Liniensegment entsteht.

### Schritt 3: ein point‑Objekt erstellen
Die `Point`‑Klasse modelliert einen einzelnen Ort in einem zweidimensionalen Koordinatensystem.  
```csharp
var point = new Point(0, 0);
```
Instanziieren Sie ein `Point`‑Objekt, das einen einzelnen Punkt in einem zweidimensionalen Raum darstellt. Hier erstellen wir einen Punkt bei den Koordinaten (0, 0).

### Schritt 4: Punkt‑auf‑Linie‑Prüfung durchführen – deckt die Linie den Punkt ab?
`Covers` bestimmt, ob die erste Geometrie die zweite Geometrie vollständig enthält, und gibt **true** nur zurück, wenn jeder Punkt der zweiten Geometrie innerhalb der ersten liegt.  
```csharp
Console.WriteLine(line.Covers(point));    // True
```
Verwenden Sie die `Covers`‑Methode, um zu prüfen, ob die Linie den Punkt abdeckt. In diesem Fall gibt sie `True` zurück, weil der Punkt (0, 0) exakt auf der Linie liegt.

### Schritt 5: die umgekehrte Beziehung prüfen – ist der Punkt von der Linie abgedeckt?
`CoveredBy` ist das Gegenstück zu `Covers`; es gibt **true** zurück, wenn die aufrufende Geometrie vollständig innerhalb der Zielgeometrie liegt.  
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
Verwenden Sie analog die `CoveredBy`‑Methode, um zu prüfen, ob der Punkt von der Linie abgedeckt wird. Da der Punkt (0, 0) auf der Linie liegt, gibt sie ebenfalls `True` zurück.

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|-------|----------------|-----|
| `line.Covers(point)` gibt `False` zurück, obwohl der Punkt auf der Linie zu liegen scheint | Die Punktkoordinaten stimmen aufgrund von Gleitkomma‑Präzision nicht exakt überein. | Verwenden Sie `Math.Round` für die Koordinaten oder führen Sie eine toleranzbasierte Prüfung mit `line.Distance(point) < epsilon` durch. |
| Fehlendes `using Aspose.Gis.Geometries;` | Namespace nicht importiert, was zu Kompilierungsfehlern führt. | Stellen Sie sicher, dass die Import‑Anweisung vorhanden ist (siehe Abschnitt **Namespaces importieren**). |
| Lizenz‑Ausnahme zur Laufzeit | Keine gültige Lizenz für die Produktion geladen. | Laden Sie eine temporäre oder Voll‑Lizenz mit `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Häufig gestellte Fragen

**Q: Kann ich Aspose.GIS für .NET in kommerziellen Projekten verwenden?**  
A: Ja, Sie können Aspose.GIS für .NET sowohl in kommerziellen als auch in nicht‑kommerziellen Projekten nach Erwerb der entsprechenden Lizenz verwenden.

**Q: Ist Aspose.GIS für .NET mit .NET Core kompatibel?**  
A: Ja, Aspose.GIS für .NET ist sowohl mit .NET Framework als auch mit .NET Core Umgebungen kompatibel.

**Q: Unterstützt Aspose.GIS für .NET verschiedene GIS‑Formate?**  
A: Ja, Aspose.GIS für .NET unterstützt eine Vielzahl von GIS‑Formaten, darunter Shapefile, GeoJSON, KML und weitere.

**Q: Kann ich zur Entwicklung von Aspose.GIS für .NET beitragen?**  
A: Aspose.GIS für .NET ist eine proprietäre Bibliothek von Aspose, daher werden externe Beiträge nicht akzeptiert. Sie können jedoch Feedback und Vorschläge zur Verbesserung der Bibliothek einreichen.

**Q: Wie häufig werden Updates für Aspose.GIS für .NET veröffentlicht?**  
A: Updates für Aspose.GIS für .NET werden regelmäßig veröffentlicht, um neue Funktionen, Verbesserungen und Fehlerbehebungen bereitzustellen. Besuchen Sie die [Website](https://releases.aspose.com/gis/net/) für die neuesten Versionen.

## Fazit
Durch die oben beschriebenen Schritte wissen Sie jetzt, wie man **create linestring c#** erstellt, **add points to linestring** hinzufügt und eine zuverlässige **point on line check** mithilfe der `Covers`‑ und `CoveredBy`‑Methoden durchführt. Diese Fähigkeit erweitert die räumlichen Analysefunktionen Ihrer Software und eröffnet den Zugang zu fortgeschritteneren GIS‑Operationen wie Routenvalidierung, Netzwerk‑Topologie‑Prüfungen und Nähe‑Abfragen.

---

**Zuletzt aktualisiert:** 2026-08-03  
**Getestet mit:** Aspose.GIS for .NET (latest release)  
**Autor:** Aspose

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Erfahren Sie, wie Sie LineString-Geometrie mit Aspose.GIS für .NET erstellen](/gis/net/geometry-creation/create-linestring-geometry/)
- [Wie man einen Punkt zu LineString hinzufügt und Geometrie in ein editierbares Format konvertiert mit Aspose.GIS](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [Punkt innerhalb Polygon c# – Geometrie enthält eine andere prüfen](/gis/net/geometry-analysis/check-geometry-contains-another/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
date: 2025-12-06
description: Erfahren Sie, wie Sie in C# mit Aspose.GIS für .NET ein LineString erstellen,
  Punkte zu einem LineString hinzufügen und prüfen, ob eine Geometrie eine andere
  überdeckt.
language: de
linktitle: Create LineString C# – Check Geometry Covers Another
second_title: Aspose.GIS .NET API
title: LineString in C# erstellen – Prüfen, ob Geometrie eine andere abdeckt
url: /net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Geometrie prüfen: Eine andere abdecken

## Einführung
Aspose.GIS für .NET ist eine leistungsstarke Bibliothek, die Entwicklern Werkzeuge zur effizienten Arbeit mit geografischen Daten in ihren .NET‑Anwendungen bereitstellt. Egal, ob Sie eine Kartenanwendung erstellen, räumliche Daten analysieren oder geografische Funktionen in Ihre Software integrieren – Aspose.GIS bietet ein umfassendes Set an Funktionalitäten, um Ihren Entwicklungsprozess zu vereinfachen. In diesem Tutorial lernen Sie **wie man ein LineString in C# erstellt**, Punkte zur Linie hinzufügt und eine **Punkt‑auf‑Linie‑Prüfung** mithilfe der Methoden `Covers` und `CoveredBy` durchführt.

## Schnelle Antworten
- **Was bedeutet „create LineString in C#“?** Es bedeutet, ein `LineString`‑Geometrieobjekt zu instanziieren und es mit Koordinatenpunkten zu füllen.  
- **Welche Methode prüft, ob ein Punkt auf einer Linie liegt?** Verwenden Sie die `Covers`‑Methode am `LineString` oder `CoveredBy` am `Point`.  
- **Benötige ich eine Lizenz, um das Beispiel auszuführen?** Eine temporäre Lizenz reicht für die Evaluierung; für den Produktionseinsatz ist eine Voll‑Lizenz erforderlich.  
- **Kann das mit .NET Core verwendet werden?** Ja, Aspose.GIS unterstützt .NET Framework und .NET Core.  
- **Wie viele Punkte kann ich zu einem LineString hinzufügen?** Es gibt keine feste Obergrenze; Sie können so viele Punkte hinzufügen, wie für Ihre räumliche Analyse nötig sind.

## Was ist **create LineString C#**?
Ein `LineString` ist eine geometrische Form, die aus einer geordneten Liste von Punkten besteht, die durch gerade Liniensegmente verbunden sind. In C# erstellen Sie ihn, indem Sie die `LineString`‑Klasse aus dem Namespace `Aspose.Gis.Geometries` instanziieren und anschließend **Punkte zum LineString `AddPoint`.

## Warum Aspose.GIS für eine Punkt‑auf‑Linie‑Prüfung verwenden?
- **Präzision** – Handhabt Gleitkomma‑Berechnungen und räumliche Prädikate exakt.  
- **Plattformübergreifend** – Funktioniert mit .NET Framework, .NET Core und .NET 5/6+.  
- **Umfangreiche API** – Bietet ein komplettes Set an räumlichen Beziehungs‑Methoden (`Covers`, `CoveredBy`, `Intersects` usw.).  

## Voraussetzungen
Bevor Sie mit Aspose.GIS für .NET beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

### 1. Visual Studio installieren
Stellen Sie sicher, dass Visual Studio auf Ihrem System installiert ist. Aspose.GIS für .NET lässt sich nahtlos in Visual Studio integrieren und bietet ein reibungsloses Entwicklungserlebnis.

### 2. Aspose.GIS für .NET beziehen
Laden Sie die Aspose.GIS für .NET‑Bibliothek von der [Website](https://releases.aspose.com/gis/net/) herunter. Sie können die Bibliothek direkt herunterladen oder einen Paket‑Manager wie NuGet verwenden, um sie in Ihr Projekt zu integrieren.

### 3. Vertrautheit mit dem .NET‑Framework
Grundlegende Kenntnisse des .NET‑Frameworks und der Programmiersprache C# sind erforderlich, um Aspose.GIS für .NET effektiv nutzen zu können.

### 4. Zugriff auf Dokumentation und Support
Lesen Sie die [Dokumentation](https://reference.aspose.com/gis/net/) für detaillierte Informationen zu den Aspose.GIS‑APIs und Funktionen. Bei Problemen oder Fragen nutzen Sie das [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) für Unterstützung.

### 5. Optional: Temporäre Lizenz
Wenn Sie Aspose.GIS für .NET erkunden, können Sie eine temporäre Lizenz von [hier](https://purchase.aspose.com/temporary-license/) erhalten, um die Bibliotheks‑Features zu evaluieren.

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

Nun zerlegen wir das bereitgestellte Beispiel in mehrere Schritte, um zu verstehen, **wie man prüft, ob eine Geometrie eine andere abdeckt** mithilfe von Aspose.GIS für .NET.

## Wie man **create LineString C#** – Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Ein LineString‑Objekt erstellen
```csharp
var line = new LineString();
```
Hier instanziieren wir ein neues `LineString`‑Objekt, das eine Sequenz verbundener Liniensegmente im zweidimensionalen Raum darstellt.

### Schritt 2: **Punkte zum LineString hinzufügen**
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
Wir **fügen dem LineString Punkte hinzu** mittels der Methode `AddPoint`. In diesem Beispiel fügen wir zwei Punkte hinzu: (0, 0) und (1, 1), wodurch ein einfacher diagonaler Linienabschnitt entsteht.

### Schritt 3: Ein Point‑Objekt erstellen
```csharp
var point = new Point(0, 0);
```
Instanziieren Sie ein `Point`‑Objekt, das einen einzelnen Punkt im zweidimensionalen Raum repräsentiert. Hier erstellen wir einen Punkt mit den Koordinaten (0, 0).

### Schritt 4: **Punkt‑auf‑Linie‑Prüfung** – Deckt die Linie den Punkt ab?
```csharp
Console.WriteLine(line.Covers(point));    // True
```
Verwenden Sie die Methode `Covers`, um zu prüfen, ob die Linie den Punkt abdeckt. In diesem Fall liefert sie `True`, weil der Punkt (0, 0) exakt auf der Linie liegt.

### Schritt 5: Umgekehrte Beziehung prüfen – Wird der Punkt von der Linie abgedeckt?
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
Analog dazu verwenden Sie die Methode `CoveredBy`, um zu prüfen, ob der Punkt von der Linie abgedeckt wird. Da der Punkt (0, 0) auf der Linie liegt, liefert auch diese Methode `True`.

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|-------|----------------|-----|
| `line.Covers(point)` gibt `False` zurück, obwohl der Punkt auf der Linie zu liegen scheint | Die Punktkoordinaten stimmen nicht exakt wegen Gleitkomma‑Präzision | Verwenden Sie `Math.Round` für die Koordinaten oder führen Sie eine Toleranz‑Prüfung mit `line.Distance(point) < epsilon` durch. |
| Fehlendes `using Aspose.Gis.Geometries;` | Namespace nicht importiert, was zu Kompilierfehlern führt | Stellen Sie sicher, dass die Import‑Anweisung vorhanden ist (siehe Abschnitt **Namespaces importieren**). |
| Lizenz‑Ausnahme zur Laufzeit | Keine gültige Lizenz für die Produktion geladen | Laden Sie eine temporäre oder vollständige Lizenz mit `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Häufig gestellte Fragen

**F: Kann ich Aspose.GIS für .NET in kommerziellen Projekten verwenden?**  
A: Ja, Sie können Aspose.GIS für .NET sowohl in kommerziellen als auch in nicht‑kommerziellen Projekten nach Erwerb der entsprechenden Lizenz nutzen.

**F: Ist Aspose.GIS für .NET mit .NET Core kompatibel?**  
A: Ja, Aspose.GIS für .NET ist sowohl mit dem .NET Framework als auch mit .NET Core kompatibel.

**F: Unterstützt Aspose.GIS für .NET verschiedene GIS‑Formate?**  
A: Ja, Aspose.GIS für .NET unterstützt eine breite Palette von GIS‑Formaten, darunter Shapefile, GeoJSON, KML und weitere.

**F: Kann ich zur Entwicklung von Aspose.GIS für .NET beitragen?**  
A: Aspose.GIS für .NET ist eine proprietäre Bibliothek von Aspose, externe Beiträge werden nicht angenommen. Sie können jedoch Feedback und Vorschläge einreichen, um die Bibliothek zu verbessern.

**F: Wie häufig werden Updates für Aspose.GIS für .NET veröffentlicht?**  
A: Updates für Aspose.GIS für .NET werden regelmäßig bereitgestellt, um neue Funktionen, Verbesserungen und Fehlerbehebungen zu integrieren. Aktuelle Versionen finden Sie auf der [Website](https://releases.aspose.com/gis/net/).

## Fazit
Zusammenfassend bietet Aspose.GIS für .NET leistungsstarke Werkzeuge zum Arbeiten mit geografischen Daten in .NET‑Anwendungen. Durch Befolgen der oben beschriebenen Schritte können Sie effizient **ein LineString in C# erstellen**, **Punkte zum LineString hinzufügen** und eine **Punkt‑auf‑Linie‑Prüfung** durchführen, um festzustellen, ob eine Geometrie eine andere abdeckt. Diese Fähigkeit erweitert die räumlichen Analysefunktionen Ihrer Software und eröffnet Möglichkeiten für weiterführende GIS‑Operationen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-06  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose
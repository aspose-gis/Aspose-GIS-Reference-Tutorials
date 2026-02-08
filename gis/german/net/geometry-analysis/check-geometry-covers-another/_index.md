---
date: 2026-02-08
description: Erfahren Sie, wie Sie in C# mit Aspose.GIS für .NET einen Linestring
  erstellen, Punkte zu einem Linestring hinzufügen und mithilfe der covers‑Methode
  prüfen, ob ein Punkt auf der Linie liegt.
linktitle: Create LineString C# – Check Geometry Covers Another
second_title: Aspose.GIS .NET API
title: LineString in C# erstellen – Prüfen, ob Geometrie eine andere abdeckt
url: /de/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Geometrie prüft, ob sie eine andere abdeckt

## Einleitung
In diesem Tutorial lernen Sie **wie man linestring c# erstellt** mit Aspose.GIS für .NET, Punkte zu einem Linestring hinzuzufügen und eine zuverlässige **Punkt-auf-Linie‑Prüfung** mit den Methoden `Covers` und `CoveredBy` durchzuführen. Egal, ob Sie ein Mapping‑Tool bauen, räumliche Analysen durchführen oder einfach geometrische Beziehungen verifizieren müssen – das Beherrschen dieser Operationen verleiht Ihrer Anwendung die nötige Präzision.

## Schnelle Antworten
- **Was bedeutet „create linestring c#“?** Es bedeutet, ein `LineString`‑Geometrieobjekt zu instanziieren und es mit Koordinatenpunkten zu füllen.  
- **Welche Methode prüft, ob ein Punkt auf einer Linie liegt?** Verwenden Sie die `Covers`‑Methode am `LineString` oder `CoveredBy` am `Point`.  
- **Benötige ich eine Lizenz, um das Beispiel auszuführen?** Eine temporäre Lizenz reicht für die Evaluierung; für den Produktionseinsatz ist eine Voll‑Lizenz erforderlich.  
- **Kann das mit .NET Core verwendet werden?** Ja, Aspose.GIS unterstützt .NET Framework und .NET Core.  
- **Wie viele Punkte kann ich zu einem Linestring hinzufügen?** Es gibt keine feste Obergrenze; Sie können so viele Punkte hinzufügen, wie Ihre räumliche Analyse erfordert.

## Was ist **create linestring c#**?
Ein `LineString` ist eine geometrische Form, die aus einer geordneten Liste von Punkten besteht, die durch gerade Liniensegmente verbunden sind. In C# erstellen Sie ihn, indem Sie die `LineString`‑Klasse aus dem Namespace `Aspose.Gis.Geometries` instanziieren und dann **Punkte zum Linestring hinzufügen** mittels der `AddPoint`‑Methode.

## Warum Aspose.GIS für einen Punkt‑auf‑Linie‑Test verwenden?
- **Precision** – Handhabt Gleitkomma‑Berechnungen und räumliche Prädikate exakt und liefert ein **precision point on line**‑Ergebnis.  
- **Cross‑platform** – Funktioniert mit .NET Framework, .NET Core und .NET 5/6+.  
- **Rich API** – Bietet eine komplette Suite von Methoden für räumliche Beziehungen (`Covers`, `CoveredBy`, `Intersects` usw.).

## Voraussetzungen
Bevor Sie mit Aspose.GIS für .NET beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

### 1. Visual Studio installieren
Stellen Sie sicher, dass Visual Studio auf Ihrem System installiert ist. Aspose.GIS für .NET integriert sich nahtlos in Visual Studio und bietet ein reibungsloses Entwicklungserlebnis.

### 2. Aspose.GIS für .NET erhalten
Laden Sie die Aspose.GIS für .NET‑Bibliothek von der [Website](https://releases.aspose.com/gis/net/) herunter. Sie können die Bibliothek direkt herunterladen oder einen Paket‑Manager wie NuGet verwenden, um sie in Ihr Projekt zu installieren.

### 3. Vertrautheit mit dem .NET Framework
Grundlegende Kenntnisse des .NET‑Frameworks und der Programmiersprache C# sind erforderlich, um Aspose.GIS für .NET effektiv zu nutzen.

### 4. Zugang zu Dokumentation und Support
Lesen Sie die [Documentation](https://reference.aspose.com/gis/net/) für detaillierte Informationen zu den Aspose.GIS‑APIs und Funktionen. Bei Problemen oder Fragen nutzen Sie das [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) für Unterstützung.

### 5. Optional: Temporäre Lizenz
Wenn Sie Aspose.GIS für .NET erkunden, können Sie eine temporäre Lizenz von [hier](https://purchase.aspose.com/temporary-license/) erhalten, um die Funktionen der Bibliothek zu evaluieren.

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

Nun zerlegen wir das bereitgestellte Beispiel in mehrere Schritte, um zu verstehen, wie man **prüft, ob eine Geometrie eine andere abdeckt** mit Aspose.GIS für .NET.

## Wie man linestring c# erstellt – Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Ein LineString-Objekt erstellen
```csharp
var line = new LineString();
```
Hier instanziieren wir ein neues `LineString`‑Objekt, das eine Sequenz verbundener Liniensegmente im zweidimensionalen Raum darstellt.

### Schritt 2: **Punkte zum LineString hinzufügen**
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
Wir **add points to linestring** mittels der `AddPoint`‑Methode. In diesem Beispiel fügen wir zwei Punkte hinzu: (0, 0) und (1, 1), wodurch ein einfacher diagonaler Linienabschnitt entsteht.

### Schritt 3: Ein Point-Objekt erstellen
```csharp
var point = new Point(0, 0);
```
Instanziieren Sie ein `Point`‑Objekt, das einen einzelnen Punkt im zweidimensionalen Raum repräsentiert. Hier erstellen wir einen Punkt bei den Koordinaten (0, 0).

### Schritt 4: Einen **Punkt-auf-Linie-Test** durchführen – Deckt die Linie den Punkt ab?
```csharp
Console.WriteLine(line.Covers(point));    // True
```
Verwenden Sie die `Covers`‑Methode, um zu prüfen, ob die Linie den Punkt abdeckt. In diesem Fall gibt sie `True` zurück, weil der Punkt (0, 0) exakt auf der Linie liegt.

### Schritt 5: Die umgekehrte Beziehung prüfen – Wird der Punkt von der Linie abgedeckt?
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
Analog dazu verwenden Sie die `CoveredBy`‑Methode, um zu prüfen, ob der Punkt von der Linie abgedeckt wird. Da der Punkt (0, 0) auf der Linie liegt, liefert sie ebenfalls `True`.

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|---------|-------------------|--------|
| `line.Covers(point)` gibt `False` zurück, obwohl der Punkt auf der Linie zu liegen scheint | Die Punktkoordinaten stimmen aufgrund von Gleitkomma‑Präzision nicht exakt überein. | Verwenden Sie `Math.Round` für die Koordinaten oder führen Sie eine Toleranz‑Prüfung mit `line.Distance(point) < epsilon` durch. |
| Fehlendes `using Aspose.Gis.Geometries;` | Namespace nicht importiert, führt zu Kompilierfehlern. | Stellen Sie sicher, dass die Import‑Anweisung vorhanden ist (siehe **Namespaces importieren**). |
| Lizenz‑Ausnahme zur Laufzeit | Keine gültige Lizenz für die Produktion geladen. | Laden Sie eine temporäre oder vollständige Lizenz mit `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Häufig gestellte Fragen

**Q: Kann ich Aspose.GIS für .NET in kommerziellen Projekten verwenden?**  
A: Ja, Sie können Aspose.GIS für .NET sowohl in kommerziellen als auch in nicht‑kommerziellen Projekten nutzen, nachdem Sie die passende Lizenz erworben haben.

**Q: Ist Aspose.GIS für .NET mit .NET Core kompatibel?**  
A: Ja, Aspose.GIS für .NET ist sowohl mit dem .NET Framework als auch mit .NET Core kompatibel.

**Q: Unterstützt Aspose.GIS für .NET verschiedene GIS‑Formate?**  
A: Ja, Aspose.GIS für .NET unterstützt eine breite Palette von GIS‑Formaten, darunter Shapefile, GeoJSON, KML und weitere.

**Q: Kann ich zur Entwicklung von Aspose.GIS für .NET beitragen?**  
A: Aspose.GIS für .NET ist eine proprietäre Bibliothek von Aspose, externe Beiträge werden nicht angenommen. Sie können jedoch Feedback und Vorschläge einreichen, um die Bibliothek zu verbessern.

**Q: Wie häufig werden Updates für Aspose.GIS für .NET veröffentlicht?**  
A: Updates für Aspose.GIS für .NET werden regelmäßig veröffentlicht, um neue Funktionen, Verbesserungen und Fehlerbehebungen bereitzustellen. Prüfen Sie die [Website](https://releases.aspose.com/gis/net/) für die neuesten Versionen.

## Fazit
Durch die oben beschriebenen Schritte wissen Sie nun, wie man **linestring c# erstellt**, **Punkte zum Linestring hinzufügt** und eine zuverlässige **Punkt‑auf‑Linie‑Prüfung** mit den Methoden `Covers` und `CoveredBy` durchführt. Diese Fähigkeit erweitert die räumlichen Analysefunktionen Ihrer Software und eröffnet den Zugang zu weiterführenden GIS‑Operationen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-02-08  
**Getestet mit:** Aspose.GIS for .NET (latest release)  
**Autor:** Aspose
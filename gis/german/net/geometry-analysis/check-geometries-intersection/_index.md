---
date: 2025-12-03
description: Erfahren Sie, wie Sie Polygongeometrien in C# erstellen und überlappende
  Polygone mit der Intersects‑Methode von Aspose.GIS für .NET erkennen.
linktitle: Create Polygon Geometry C#
second_title: Aspose.GIS .NET API
title: Polygon-Geometrie in C# erstellen und Schnitt mit Aspose.GIS für .NET prüfen
url: /de/net/geometry-analysis/check-geometries-intersection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Polygongeometrie in C erstellen und Schnittmenge mit Aspose.GIS für .NET prüfen

## Einleitung
Wenn Sie **Polygongeometrie in C# erstellen** und schnell bestimmen möchten, ob sich zwei Formen überschneiden, bietet Aspose.GIS für .NET eine saubere, leistungsstarke API. In diesem Leitfaden führen wir Sie durch den gesamten Prozess – von der Einrichtung der Bibliothek bis zur Verwendung der `Intersects`‑Methode, um **überlappende Polygone zu erkennen**. Am Ende können Sie Polygon‑Schnittmengenkontrollen in jede .NET‑Anwendung mit nur wenigen Codezeilen integrieren.

## Schnelle Antworten
- **Was macht die Intersects‑Methode?** Sie gibt `true` zurück, wenn zwei Geometrien irgendeinen gemeinsamen Bereich teilen.  
- **Welcher Namespace enthält Polygon‑Klassen?** `Aspose.Gis.Geometries`.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert zum Testen; für die Produktion ist eine kommerzielle Lizenz erforderlich.- **Kann ich das mit .NET Core / .NET 6+ verwenden?** Ja, Aspose.GIS unterstützt alle modernen .NET‑Runtimes.  
- **Wie lange dauert die Ausführung des Beispiels?** Weniger als eine Sekunde auf einer typischen Entwicklungsmaschine.

## Was bedeutet „Polygongeometrie in C# erstellen“?
Eine Polygongeometrie in C# zu erstellen bedeutet, die von Aspose.GIS bereitgestellte `Polygon`‑Klasse (oder andere Geometrie‑Typen) zu instanziieren und einen geschlossenen Ring aus `Point`‑Objekten zu übergeben, die die Eckpunkte der Form definieren. Sobald sie erstellt ist, kann die Geometrie an räumlichen Operationen wie Schnittmenge, Einschluss und Distanzberechnungen teilnehmen.

## Warum Aspose.GIS zur Erkennung überlappender Polygone verwenden?
- **Keine externen Abhängigkeiten** – reine .NET‑Bibliothek, keine nativen GIS‑Installationen.  
- **Umfangreiche räumliche Operationen** – `Intersects`, `Disjoint`, `Contains` usw., sofort einsatzbereit.  
- **Hohe Genauigkeit** – robuste Handhabung von Randfällen wie gemeinsamen Kanten oder Eckpunkten.  
- **Plattformübergreifend** – funktioniert unter Windows, Linux und macOS mit .NET Core/5/6.

## Voraussetzungen
1. **Aspose.GIS für .NET** installiert (siehe die Schritte unten).  
2. Eine .NET‑Entwicklungsumgebung (Visual Studio, VS Code oder Rider).  
3. .NET Framework 4.6+ oder .NET Core 3.1+.

### Installation von Aspose.GIS für .NET
1. Navigieren Sie zur Download‑Seite: Besuchen die [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/), um die neueste Version des Toolkits zu erhalten.  
2. Toolkit herunterladen: Wählen Sie die passende Version, die mit Ihrer Entwicklungsumgebung kompatibel ist, und laden Sie das Toolkit herunter.  
3. Toolkit installieren: Befolgen Sie die bereitgestellten Installationsanweisungen, um Aspose.GIS für .NET auf Ihrem Entwicklungsrechner zu installieren.

## Importieren von Namespaces
Um mit Aspose.GIS für .NET zu arbeiten, müssen Sie die erforderlichen Namespaces Ihr Projekt importieren.

1. Verweise hinzufügen: Fügen Sie in Ihrem Projekt Verweise auf die Aspose.GIS‑Assembly hinzu.  
2. Namespaces importieren: Importieren Sie die erforderlichen Namespaces in Ihrer Code‑Datei. Für das bereitgestellte Beispiel stellen Sie sicher, dass Sie die folgenden Namespaces importieren:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Wie erstelle ich Polygongeometrie in C# mit Aspose.GIS?
Jetzt, da die Umgebung bereit ist, erstellen wir zwei einfache Polygongeometrien, die wir später auf Überlappung testen werden.

### Schritt 1: Geometrien definieren
In diesem Schritt erstellen Sie Polygone, die zwei rechteckige Flächen darstellen. Die Eckpunkte werden im Uhrzeigersinn definiert, und der erste Punkt wird am Ende wiederholt, um den Ring zu schließen.

```csharp
var geometry1 = new Polygon(new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 3),
    new Point(3, 3),
    new Point(3, 0),
    new Point(0, 0),
}));
var geometry2 = new Polygon(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 4),
    new Point(4, 4),
    new Point(4, 1),
    new Point(1, 1),
}));
```

### Schritt 2: Intersects‑Methode verwenden, um überlappende Polygone zu erkennen
Nachdem die Geometrien definiert wurden, können wir nun die `Intersects`‑Methode aufrufen. Diese Methode **verwendet den Intersects‑Algorithmus**, um zu prüfen, ob irgendein Teil der beiden Polygone denselben Raum teilt.

```csharp
Console.WriteLine(geometry1.Intersects(geometry2)); // True
Console.WriteLine(geometry2.Intersects(geometry1)); // True
```

### Schritt 3: Auf disjunkte Geometrien prüfen (das Gegenteil von intersect)
Wenn Sie bestätigen müssen, dass sich zwei Formen **nicht** überlappen, liefert die `Disjoint`‑Methode das Gegenstück.

```csharp
// 'Disjoint' is opposite to 'Intersects'
Console.WriteLine(geometry1.Disjoint(geometry2)); // False
```

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|---------|-------------------|--------|
| **Gibt immer `false` zurück** | Die Polygone sind nicht geschlossen (erster Punkt ≠ letzter Punkt). | Stellen Sie sicher, dass der erste Punkt am Ende des Koordinatenarrays wiederholt wird. |
| **Unerwartetes `true` bei berührenden Kanten** | `Intersects` behandelt gemeinsame Kanten als Schnittmenge. | Verwenden Sie die `Touches`‑Methode, wenn Sie nur Kanten‑Erkennung benötigen. |
| **Leistungsverlust bei vielen Polygonen** | Jeder Aufruf prüft jedes Vertex‑Paar. | Stapelverarbeitung mit `GeometryCollection` oder räumlicher Indexierung (R‑Baum), falls unterstützt. |

## Häufig gestellte Fragen

**Q: Kann ich Aspose.GIS für .NET mit anderen .NET‑Frameworks verwenden?**  
A: Ja, AsposeIS für .NET ist mit verschiedenen .NET‑Frameworks kompatibel, einschließlich .NET Core und .NET Framework.

**Q: Gibt es eine kostenlose Testversion von Aspose.GIS für .NET?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.GIS für .NET [hier](https://releases.aspose.com/) erhalten.

**Q: Wo finde ich Support für Aspose.GIS für .NET?**  
A: Sie können Hilfe erhalten und sich mit der Community im [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) austauschen.

**Q: Kann ich eine temporäre Lizenz für Aspose.GIS für .NET erhalten?**  
A: Ja, Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erhalten.

**Q: Wo kann ich eine lizenzierte Version von Aspose.GIS für .NET erwerben?**  
A: Sie können eine lizenzierte Version von Aspose.GIS für .NET [hier](https://purchase.aspose.com/buy) erwerben.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2025-12-03  
**Getestet mit:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose
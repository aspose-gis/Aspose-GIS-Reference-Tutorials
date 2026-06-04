---
date: 2026-02-05
description: Erfahren Sie, wie Sie Geometrien in .NET mit Aspose.GIS vergleichen und
  die Gleichheit von Geometrien in Ihren Anwendungen prüfen.
linktitle: How to Compare Geometries for Equality
second_title: Aspose.GIS .NET API
title: Wie man Geometrien auf Gleichheit vergleicht mit Aspose.GIS für .NET
url: /de/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Geometrien auf Gleichheit vergleicht mit Aspose.GIS für .NET

## Einführung
In diesem Tutorial erfahren Sie **wie man Geometrien vergleicht** mit Aspose.GIS für .NET. Egal, ob Sie einen Mapping‑Dienst erstellen, räumliche Analysen durchführen oder einfach überprüfen müssen, ob zwei Formen denselben Ort darstellen, das Wissen, wie man Geometrien vergleicht, ist unerlässlich. Wir führen Sie durch ein vollständiges, End‑to‑End‑Beispiel, das zeigt, wie Sie Geometrien erstellen, ändern und die Gleichheit von Geometrien in nur wenigen Zeilen C#‑Code testen.

## Schnelle Antworten
- **Was bedeutet „Geometrien vergleichen“?** Es prüft, ob zwei geometrische Objekte denselben Raum einnehmen, unabhängig davon, wie sie konstruiert wurden.  
- **Welche Methode wird verwendet?** `SpatiallyEquals` aus der Aspose.GIS API.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert für Tests; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Unterstützte .NET‑Versionen?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Typische Implementierungszeit?** Etwa 5‑10 Minuten für eine grundlegende Gleichheitsprüfung.

## Was ist Geometrie‑Gleichheit?
Geometrie‑Gleichheit (oft räumliche Gleichheit genannt) bedeutet, dass zwei Geometrien exakt dieselbe Menge von Punkten auf der Erdoberfläche darstellen. Zwei Formen können unterschiedlich aufgebaut sein – ein MultiLineString gegenüber einem einzelnen LineString – aber dennoch räumlich gleich sein.

## Warum Aspose.GIS zum Vergleich von Geometrien verwenden?
Aspose.GIS bietet eine robuste, leistungsstarke Geometrie‑Engine, die:
- Ein breites Spektrum an Vektorformaten unterstützt (WKT, GeoJSON, Shapefile usw.).
- Präzisionsbewusste Vergleichsmethoden wie `SpatiallyEquals` bereitstellt.
- Offline arbeitet, ohne externe Dienste, und ist damit ideal für sichere oder isolierte Umgebungen.

### Warum das für Entwickler wichtig ist
Wenn Sie **wie man Geometrien vergleicht** in Batch‑Prozessen, Duplikaterkennungs‑Routinen oder Echtzeit‑Validierungen benötigen, entfernt eine zuverlässige Bibliothek das Rätselraten und garantiert konsistente Ergebnisse über verschiedene Datenquellen hinweg.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- **.NET Framework oder .NET Core installiert** – jede von Aspose.GIS unterstützte Version.
- **Aspose.GIS für .NET Bibliothek** – herunterladen von der [Aspose.GIS Download‑Seite](https://releases.aspose.com/gis/net/).
- **Eine Entwicklungs‑IDE** – Visual Studio, Rider oder VS Code mit C#‑Erweiterungen.

## Namespaces importieren
Fügen Sie in Ihrem .NET‑Projekt die erforderlichen `using`‑Anweisungen hinzu, damit der Compiler weiß, wo die GIS‑Klassen zu finden sind:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt 1: Geometrien definieren
Zuerst erstellen wir zwei Geometrien, die wir vergleichen werden. In diesem Beispiel ist `geometry1` ein `MultiLineString`, der aus zwei Liniensegmenten besteht, während `geometry2` ein einzelner `LineString` ist, der dieselben Start‑ und Endpunkte abdeckt.

```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```

## Schritt 2: Geometrien auf Gleichheit prüfen
Jetzt verwenden wir die Methode `SpatiallyEquals`, um zu sehen, ob die beiden Formen vom GIS‑Engine als gleich betrachtet werden.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

Die Konsole gibt `True` aus, weil beide Geometrien trotz unterschiedlicher Konstruktion dieselbe Linie von (0,0) bis (2,2) abdecken.

## Schritt 3: Eine Geometrie ändern
Um zu veranschaulichen, wie sich eine Änderung auf die Gleichheit auswirkt, fügen wir `geometry2` einen zusätzlichen Punkt hinzu.

```csharp
geometry2.AddPoint(3, 3);
```

## Schritt 4: Gleichheit nach Änderung erneut prüfen
Nach der Änderung sind die Geometrien nicht mehr identisch, sodass `SpatiallyEquals` `False` zurückgibt.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

Die Ausgabe `False` bestätigt, dass der zusätzliche Punkt die räumliche Gleichheit aufgehoben hat.

## Häufige Probleme & Tipps
- **Präzisionsprobleme** – Wenn Sie mit sehr hochpräzisen Koordinaten arbeiten, sollten Sie Rundungen in Betracht ziehen oder eine Toleranz‑Überladung von `SpatiallyEquals` verwenden.  
- **Unterschiedliche SRIDs** – Stellen Sie sicher, dass beide Geometrien denselben Spatial Reference System Identifier (SRID) teilen, bevor Sie vergleichen.  
- **Performance** – Für große Sammlungen können Batch‑Vergleiche mit LINQ den Aufwand reduzieren.

## Häufig gestellte Fragen
**F: Kann ich Aspose.GIS für .NET mit anderen .NET‑Frameworks verwenden?**  
A: Ja, Aspose.GIS funktioniert mit .NET Framework, .NET Core und .NET Standard‑Projekten.

**F: Gibt es eine kostenlose Testversion?**  
A: Auf jeden Fall. Laden Sie eine Testversion von der [Aspose.GIS Releases‑Seite](https://releases.aspose.com/) herunter.

**F: Wo finde ich die vollständige API‑Dokumentation?**  
A: Detaillierte Dokumentation finden Sie auf der [Aspose.GIS Dokumentations‑Seite](https://reference.aspose.com/gis/net/).

**F: Wie bekomme ich Hilfe, wenn ich auf ein Problem stoße?**  
A: Stellen Sie Ihre Frage im Aspose.GIS Community‑Forum [hier](https://forum.aspose.com/c/gis/33).

**F: Kann ich eine temporäre Lizenz für die Evaluierung erwerben?**  
A: Ja, temporäre Lizenzen sind auf der [Kauf‑Seite](https://purchase.aspose.com/temporary-license/) erhältlich.

## Fazit
Sie wissen jetzt **wie man Geometrien vergleicht** mit Aspose.GIS für .NET, von der Erstellung der Objekte über die Prüfung der räumlichen Gleichheit bis hin zur Handhabung von Änderungen. Diese Fähigkeit ist ein Baustein für weiterführende räumliche Analysen wie Topologie‑Validierung, Duplikaterkennung und geometriebasierte Filterung.

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.GIS for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
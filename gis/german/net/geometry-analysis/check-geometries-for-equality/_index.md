---
date: 2026-06-05
description: Erfahren Sie, wie Sie Geometries in .NET mit Aspose.GIS vergleichen,
  doppelte Geometries erkennen und die Gleichheit von Geometries in Ihren Anwendungen
  prüfen.
keywords:
- how to compare geometries
- detect duplicate geometries
- Aspose.GIS geometry equality
linktitle: Wie man Geometries auf Gleichheit vergleicht
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to compare geometries in .NET using Aspose.GIS, detect duplicate
    geometries, and check geometry equality in your applications.
  headline: How to Compare Geometries for Equality using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard
      projects.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. Download a trial from the [Aspose.GIS releases page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Detailed docs are on the [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).
    question: Where can I find the full API documentation?
  - answer: Post your question on the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How do I get help if I run into an issue?
  - answer: Yes, temporary licenses are available on the [purchase page](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Wie man Geometries auf Gleichheit vergleicht mit Aspose.GIS für .NET
url: /de/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Geometrien auf Gleichheit vergleicht mit Aspose.GIS für .NET

## Einführung
In diesem Tutorial lernen Sie **wie man Geometrien vergleicht** mit Aspose.GIS für .NET, eine Aufgabe, die wichtig ist, wenn Sie doppelte Geometrien erkennen, räumliche Daten validieren oder topologische Regeln durchsetzen müssen. Egal, ob Sie einen Mapping‑Service bauen, eine Stapel‑Räumlich‑Analyse durchführen oder einfach prüfen wollen, dass zwei Formen denselben Ort einnehmen, führt Sie dieser Leitfaden durch das Erstellen, Modifizieren und Testen von Geometrie‑Gleichheit mit sauberem, produktionsreifem C#‑Code.

## Schnelle Antworten
- **Was bedeutet „Geometrien vergleichen“?** Es prüft, ob zwei geometrische Objekte denselben Raum einnehmen, unabhängig davon, wie sie konstruiert wurden.  
- **Welche Methode wird verwendet?** `SpatiallyEquals` aus der Aspose.GIS‑API.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion reicht zum Testen; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Unterstützte .NET‑Versionen?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Typische Implementierungsdauer?** Etwa 5‑10 Minuten für eine grundlegende Gleichheitsprüfung.

## Was ist Geometrie‑Gleichheit?
Geometrie‑Gleichheit, auch räumliche Gleichheit genannt, bedeutet, dass zwei Geometrien exakt dieselbe Menge von Punkten auf der Erdoberfläche darstellen. Selbst wenn eine Geometrie als `MultiLineString` und die andere als einzelner `LineString` gebaut ist, werden sie als gleich angesehen, wenn jede Koordinate innerhalb der definierten Toleranz übereinstimmt. Diese Definition ermöglicht es Entwicklern, zuverlässig doppelte Geometrien über heterogene Datenquellen hinweg zu erkennen.

## Warum Aspose.GIS zum Vergleichen von Geometrien verwenden?
Aspose.GIS bietet eine hochleistungsfähige, offline Geometrie‑Engine, die den Bedarf an externen Diensten eliminiert. Es **unterstützt mehr als 30 Vektor‑ und Rasterformate** (inklusive WKT, GeoJSON, Shapefile, KML, GML) und kann Dateien mit **Hunderten von Tausenden von Scheitelpunkten** verarbeiten, während der Speicherverbrauch unter 50 MB bleibt. Die `SpatiallyEquals`‑Methode der Bibliothek ist präzisionsbewusst und liefert deterministische Ergebnisse selbst bei Gleitkomma‑Koordinaten.

### Warum das für Entwickler wichtig ist
Wenn Sie **doppelte Geometrien** in Batch‑Prozessen, Echtzeit‑Validierungspipelines oder GIS‑Datenmigrationen erkennen müssen, entfernt eine bewährte Bibliothek das Rätselraten und garantiert konsistente Ergebnisse über verschiedene Datenanbieter hinweg.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- **.NET Framework oder .NET Core installiert** – jede von Aspose.GIS unterstützte Version.  
- **Aspose.GIS für .NET Bibliothek** – herunterladen von der [Aspose.GIS download page](https://releases.aspose.com/gis/net/).  
- **Eine Entwicklungs‑IDE** – Visual Studio, Rider oder VS Code mit C#‑Erweiterungen.

## Namespaces importieren
Fügen Sie in Ihrem .NET‑Projekt die erforderlichen `using`‑Anweisungen hinzu, damit der Compiler die GIS‑Klassen findet:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt 1: Geometrien definieren
`MultiLineString` stellt eine Sammlung von Linienkomponenten dar, während `LineString` eine einzelne durchgehende Linie definiert. Beide Klassen erben vom Basistyp `Geometry`.

Zuerst erstellen wir zwei Geometrien, die wir vergleichen werden. In diesem Beispiel ist `geometry1` ein `MultiLineString`, das aus zwei Liniensegmenten besteht, während `geometry2` ein einzelner `LineString` ist, der dieselben Start‑ und Endpunkte abdeckt.

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

## Schritt 2: Geometrien auf Gleichheit prüfen
`SpatiallyEquals` bewertet, ob zwei Geometrien denselben Punktesatz belegen, optional mit einem Toleranzwert für Gleitkomma‑Ungenauigkeiten.

Jetzt verwenden wir die Methode `SpatiallyEquals`, um zu sehen, ob die beiden Formen vom GIS‑Engine als gleich angesehen werden.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

Die Konsole gibt `True` aus, weil trotz unterschiedlicher Konstruktion beide Geometrien dieselbe Linie von (0,0) bis (2,2) abdecken.

## Schritt 3: Eine Geometrie ändern
Um zu zeigen, wie sich eine Änderung auf die Gleichheit auswirkt, fügen wir `geometry2` einen zusätzlichen Punkt hinzu.

```csharp
geometry2.AddPoint(3, 3);
```

## Schritt 4: Gleichheit nach Änderung erneut prüfen
Nach der Modifikation sind die Geometrien nicht mehr identisch, sodass `SpatiallyEquals` `False` zurückgibt.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

Die Ausgabe `False` bestätigt, dass der zusätzliche Punkt die räumliche Gleichheit aufgehoben hat.

## Wie erkennt man doppelte Geometrien?
Laden Sie jede Geometrie, rufen Sie `SpatiallyEquals` mit einer geeigneten Toleranz auf und filtern Sie die Ergebnisse, die `True` zurückgeben. Dieses Muster skaliert gut mit LINQ und ermöglicht es Ihnen, doppelte Formen in großen Sammlungen mit nur wenigen Codezeilen zu identifizieren. Sie können es auch mit `GroupBy` kombinieren, um identische Geometrien zu aggregieren und Speicher­kosten zu reduzieren.

## Häufige Probleme & Tipps
- **Präzisionsprobleme** – Arbeiten Sie mit sehr hochpräzisen Koordinaten, sollten Sie runden oder die Toleranz‑Überladung von `SpatiallyEquals` verwenden.  
- **Unterschiedliche SRIDs** – Stellen Sie sicher, dass beide Geometrien dieselbe Spatial Reference System Identifier (SRID) besitzen, bevor Sie vergleichen.  
- **Leistung** – Für große Sammlungen können Batch‑Vergleiche mittels LINQ oder parallelen Schleifen den Aufwand erheblich reduzieren.

## Häufig gestellte Fragen
**Q: Kann ich Aspose.GIS für .NET mit anderen .NET‑Frameworks verwenden?**  
A: Ja, Aspose.GIS funktioniert mit .NET Framework, .NET Core und .NET Standard Projekten.

**Q: Ist eine kostenlose Testversion verfügbar?**  
A: Absolut. Laden Sie eine Testversion von der [Aspose.GIS releases page](https://releases.aspose.com/).

**Q: Wo finde ich die vollständige API‑Dokumentation?**  
A: Detaillierte Dokumentation finden Sie auf der [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).

**Q: Wie bekomme ich Hilfe, wenn ich auf ein Problem stoße?**  
A: Stellen Sie Ihre Frage im Aspose.GIS Community‑Forum [hier](https://forum.aspose.com/c/gis/33).

**Q: Kann ich eine temporäre Lizenz für die Evaluierung erwerben?**  
A: Ja, temporäre Lizenzen sind auf der [purchase page](https://purchase.aspose.com/temporary-license/) erhältlich.

## Fazit
Sie wissen jetzt **wie man Geometrien vergleicht** mit Aspose.GIS für .NET, vom Erstellen der Objekte über das Prüfen der räumlichen Gleichheit bis hin zum Umgang mit Modifikationen. Diese Fähigkeit ist ein Baustein für fortgeschrittene räumliche Analysen wie Topologie‑Validierung, Duplikaterkennung und geometrie‑basierte Filterung.

---

**Last Updated:** 2026-06-05  
**Tested With:** Aspose.GIS for .NET 24.11  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Polygongeometrie in C# erstellen und Schnittprüfung mit Aspose.GIS für .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Wie man räumliche Überlappungsanalyse von Geometrien mit Aspose.GIS für .NET durchführt](/gis/net/geometry-analysis/check-geometries-overlap/)
- [Netzwerk‑Routing‑Check: Berührende Geometrien mit Aspose.GIS](/gis/net/geometry-analysis/check-geometries-touching/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
date: 2026-04-03
description: Erfahren Sie, wie Sie mit Aspose.GIS für .NET einen Vektorlayer erstellen
  und die Präzision beim Lesen von Geometrien begrenzen. Schritt‑für‑Schritt‑Anleitung
  für eine optimale Verarbeitung von Geodaten.
keywords:
- create vector layer
- reduce shapefile size
- set precision model
linktitle: Präzision beim Lesen von Geometrien begrenzen
second_title: Aspose.GIS .NET API
title: Vektorlayer erstellen, Präzision begrenzen mit Aspose.GIS für .NET
url: /de/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen eines Vektor-Layers, Präzision begrenzen mit Aspose.GIS für .NET

## Einführung
Bei der Arbeit mit Geodaten müssen Sie häufig **create vector layer**-Objekte erstellen und entscheiden, wie viele Dezimalstellen bei den Koordinaten wirklich nötig sind. Das Begrenzen der Präzision beschleunigt nicht nur die Verarbeitung, sondern kann auch **reduce shapefile size** ermöglichen, wodurch Speicherung und Übertragung effizienter werden. In diesem Tutorial führen wir Sie durch das Erstellen eines Vektor-Layers, das Schreiben einer einfachen Punktgeometrie und das anschließende Auslesen mit sowohl exakten als auch gerundeten Präzisionsmodellen. Am Ende verstehen Sie, wie Sie **set precision model**-Optionen festlegen, die den Genauigkeitsanforderungen Ihrer Anwendung entsprechen.

## Schnelle Antworten
- **Was bedeutet „limit precision“?** Es rundet Koordinatenwerte auf eine definierte Anzahl von Dezimalstellen.  
- **Warum zuerst einen vector layer erstellen?** Ein vector layer ist der Container, der Geometrien wie Punkte, Linien und Polygone speichert.  
- **Welche Präzisionsmodelle stehen zur Verfügung?** `PrecisionModel.Exact` (keine Rundung) und `PrecisionModel.Rounding(n)` (Rundung auf *n* Dezimalstellen).  
- **Benötige ich eine Lizenz, um dies auszuprobieren?** Eine kostenlose Testversion ist auf der releases page verfügbar.  
- **Welche .NET-Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core und .NET 5/6+.

## Warum Präzision begrenzen und wie hilft das?
- **Leistungssteigerung** – Weniger Ziffern bedeuten weniger Daten zum Parsen und Serialisieren.  
- **Kleinere Dateien** – Das Runden von Koordinaten kann ein Shapefile merklich verkleinern, besonders bei großen Datensätzen.  
- **Ausreichende Genauigkeit** – Viele GIS-Analysen benötigen keine Unter‑Millimeter‑Präzision, sodass das Runden auf 2‑3 Dezimalstellen oft ausreicht.

## Voraussetzungen
Bevor wir diese Reise beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:
1. **Installation** – Die Aspose.GIS for .NET-Bibliothek sollte in Ihrer Entwicklungsumgebung installiert sein. Falls nicht, können Sie sie von der [releases page](https://releases.aspose.com/gis/net/) herunterladen.
2. **Vertrautheit mit .NET** – Grundkenntnisse in C# und dem .NET-Framework sind erforderlich, um die bereitgestellten Codebeispiele zu verstehen und umzusetzen.
3. **Entwicklungsumgebung** – Eine funktionierende .NET-Entwicklungsumgebung, wie Visual Studio, ist erforderlich.
4. **Dokumentenverzeichnis** – Richten Sie ein Verzeichnis ein, in dem Sie das während des Prozesses erzeugte Shapefile speichern und darauf zugreifen können.

## Namespaces importieren
Bevor wir beginnen, die Funktionalität zum Begrenzen der Präzision beim Lesen von Geometrien zu implementieren, stellen wir sicher, dass wir die erforderlichen Namespaces importieren:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Wie man einen Vector Layer erstellt
Der erste Schritt besteht darin, einen **create vector layer** zu erstellen, der unsere Geometrie hält. Dieser Layer wird als Shapefile gespeichert, sodass wir ihn später mit unterschiedlichen Präzisionseinstellungen wieder öffnen können.
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Präzisionsoptionen festlegen
Als Nächstes müssen wir Optionen für das Lesen von Geometrien definieren und das gewünschte Präzisionsmodell angeben. Wir können mit exakter Präzision beginnen:
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Geometrien mit exakter Präzision lesen
Jetzt öffnen wir den vector layer mit den angegebenen Optionen, um Geometrien mit exakter Präzision zu lesen:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Präzision kürzen
Wenn wir die Präzision auf eine bestimmte Anzahl von Dezimalstellen kürzen möchten, können wir das Präzisionsmodell entsprechend anpassen:
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Wie man das Präzisionsmodell für verschiedene Szenarien festlegt
Sie fragen sich vielleicht, wann `Exact` gegenüber `Rounding` zu verwenden ist. Hier sind zwei gängige Szenarien:

| Szenario | Empfohlenes Modell | Grund |
|----------|-------------------|--------|
| Hochpräzise wissenschaftliche Analyse | `PrecisionModel.Exact` | Kein Verlust von Koordinatendetails |
| Web‑Mapping‑Kacheln oder mobile Apps | `PrecisionModel.Rounding(2)` | Reduziert die Dateigröße und beschleunigt das Rendering |

Die Wahl des richtigen Modells ist Teil des **set precision model**‑Entscheidungsprozesses, der Genauigkeit gegen Leistung abwägt.

## Häufige Probleme und Lösungen
- **Unerwartete Koordinatenwerte** – Stellen Sie sicher, dass Sie `options.XYPrecisionModel` *vor* dem Öffnen des Layers setzen. Eine Änderung danach hat keine Wirkung.  
- **Datei nicht gefunden** – Überprüfen Sie, dass die Variable `path` auf ein gültiges Verzeichnis zeigt und dass das Shapefile im vorherigen Schritt erfolgreich erstellt wurde.  
- **Falscher Geometrietyp** – Das Beispiel verwendet einen `Point`. Für andere Geometrietypen (z. B. `LineString`) sollte das Casting dem tatsächlichen Typ entsprechen.  

## Tipps zur Reduzierung der Shapefile-Größe
- Verwenden Sie `PrecisionModel.Rounding` mit der kleinsten Anzahl von Dezimalstellen, die Ihre Genauigkeitsanforderungen noch erfüllt.  
- Entfernen Sie unnötige Attributfelder, bevor Sie den Layer schreiben.  
- Komprimieren Sie die resultierenden `.shp`, `.shx` und `.dbf`-Dateien mit gängigen ZIP-Tools, wenn Sie sie übertragen müssen.

## Fazit
Zusammenfassend ist das Verwalten der Präzision beim Lesen von Geometrien ein entscheidender Aspekt der Manipulation von Geodaten. Aspose.GIS für .NET bietet robuste Funktionen, um dies effizient zu erreichen. Durch die oben beschriebenen Schritte können Sie nahtlos **create vector layer**-Objekte, **set precision model** und sogar **reduce shapefile size** bei Bedarf reduzieren, wodurch eine optimale Datenverarbeitung in Ihren Anwendungen gewährleistet wird.

## FAQ
### Kann ich Aspose.GIS für .NET mit anderen .NET-Frameworks wie .NET Core oder .NET Standard verwenden?
Ja, Aspose.GIS für .NET ist mit verschiedenen .NET-Frameworks kompatibel, einschließlich .NET Core und .NET Standard.  
### Gibt es eine Testversion für Aspose.GIS für .NET?
Ja, Sie können eine kostenlose Testversion von der [releases page](https://releases.aspose.com/) erhalten.  
### Wo finde ich umfassende Dokumentation für Aspose.GIS für .NET?
Sie können die [documentation](https://reference.aspose.com/gis/net/) für detaillierte Informationen und Beispiele konsultieren.  
### Wie kann ich temporäre Lizenzen für Aspose.GIS für .NET erhalten?
Temporäre Lizenzen können von der [purchase page](https://purchase.aspose.com/temporary-license/) für Aspose.GIS erworben werden.  
### Wo kann ich Unterstützung oder Support für Aspose.GIS für .NET erhalten?
Sie können das Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) für Fragen, Diskussionen oder Support-Anfragen besuchen.

## Häufig gestellte Fragen
**Q: Hat das Begrenzen der Präzision Auswirkungen auf das originale Shapefile?**  
A: Nein. Die Präzision wird nur beim Lesen der Geometrie angewendet; die Quelldatei bleibt unverändert.  

**Q: Kann ich ein unterschiedliches Präzisionsmodell für X‑ und Y‑Koordinaten verwenden?**  
A: Aspose.GIS wendet derzeit dasselbe `XYPrecisionModel` auf beide Achsen an.  

**Q: Ist es möglich, eine benutzerdefinierte Rundungsfunktion festzulegen?**  
A: Die API unterstützt nur die integrierte Methode `PrecisionModel.Rounding(int)`. Für benutzerdefinierte Logik müssten Sie die Koordinaten nach dem Lesen nachbearbeiten.

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
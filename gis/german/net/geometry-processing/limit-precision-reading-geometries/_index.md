---
date: 2025-12-20
description: Erfahren Sie, wie Sie einen Vektorlayer erstellen und die Genauigkeit
  beim Lesen von Geometrien mit Aspose.GIS für .NET begrenzen. Schritt‑für‑Schritt‑Anleitung
  für die optimale Verarbeitung von Geodaten.
linktitle: Limit Precision Reading Geometries
second_title: Aspose.GIS .NET API
title: Vektorlayer erstellen, Präzision begrenzen mit Aspose.GIS für .NET
url: /de/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektorlayer erstellen, Präzision begrenzen mit Aspose.GIS für .NET

## Einleitung
Beim Arbeiten mit Geodaten müssen Sie häufig **Vektorlayer**‑Objekte erstellen und steuern, wie viele numerische Details beim Lesen erhalten bleiben. Aspose.GIS für .NET ermöglicht es, die Präzision einfach zu begrenzen, was die Leistung verbessern und den Speicherbedarf reduzieren kann, wenn ultra‑hohe Genauigkeit nicht erforderlich ist. In diesem Tutorial sehen Sie genau, wie Sie einen Vektorlayer erstellen, eine einfache Punktgeometrie schreiben und diese anschließend sowohl mit exakter als auch mit gekürzter Präzision wieder einlesen.

## Schnelle Antworten
- **Was bedeutet „Präzision begrenzen“?** Es rundet Koordinatenwerte auf eine definierte Anzahl von Dezimalstellen.  
- **Warum zuerst einen Vektorlayer erstellen?** Ein Vektorlayer ist der Container, der Geometrien wie Punkte, Linien und Polygone speichert.  
- **Welche Präzisionsmodelle stehen zur Verfügung?** `PrecisionModel.Exact` (kein Runden) und `PrecisionModel.Rounding(n)` (Runden auf *n* Dezimalstellen).  
- **Benötige ich eine Lizenz, um das auszuprobieren?** Eine kostenlose Testversion ist auf der Release‑Seite verfügbar.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core und .NET 5/6+.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:
1. **Installation** – Die Aspose.GIS für .NET‑Bibliothek sollte in Ihrer Entwicklungsumgebung installiert sein. Falls nicht, können Sie sie von der [Release‑Seite](https://releases.aspose.com/gis/net/) herunterladen.
2. **Vertrautheit mit .NET** – Grundkenntnisse in C# und dem .NET‑Framework sind nötig, um die bereitgestellten Code‑Beispiele zu verstehen und umzusetzen.
3. **Entwicklungsumgebung** – Eine funktionierende .NET‑Entwicklungsumgebung, z. B. Visual Studio, ist erforderlich.
4. **Dokumenten‑Verzeichnis** – Richten Sie ein Verzeichnis ein, in dem Sie die während des Prozesses erzeugte Shapefile speichern und darauf zugreifen können.

## Namespaces importieren
Bevor wir die Funktionalität zur Begrenzung der Präzision beim Lesen von Geometrien implementieren, stellen wir sicher, dass die notwendigen Namespaces importiert werden:
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

## So erstellen Sie einen Vektorlayer
Der erste Schritt besteht darin, einen **Vektorlayer** zu **erstellen**, der unsere Geometrie enthält. Dieser Layer wird als Shapefile gespeichert, sodass wir ihn später mit anderen Präzisionseinstellungen wieder öffnen können.
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
Als Nächstes definieren wir Optionen zum Lesen von Geometrien und geben das gewünschte Präzisionsmodell an. Wir können mit exakter Präzision beginnen:
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Geometrien mit exakter Präzision lesen
Jetzt öffnen wir den Vektorlayer mit den angegebenen Optionen, um Geometrien mit exakter Präzision zu lesen:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Präzision kürzen
Wenn wir die Präzision auf eine bestimmte Anzahl von Dezimalstellen kürzen möchten, passen wir das Präzisionsmodell entsprechend an:
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Häufige Probleme und Lösungen
- **Unerwartete Koordinatenwerte** – Stellen Sie sicher, dass Sie `options.XYPrecisionModel` *vor* dem Öffnen des Layers setzen. Eine Änderung danach hat keine Wirkung.
- **Datei nicht gefunden** – Prüfen Sie, ob die Variable `path` auf ein gültiges Verzeichnis zeigt und die Shapefile im vorherigen Schritt erfolgreich erstellt wurde.
- **Falscher Geometrietyp** – Das Beispiel verwendet einen `Point`. Für andere Geometrietypen (z. B. `LineString`) muss das Casting dem tatsächlichen Typ entsprechen.

## Fazit
Zusammenfassend ist das Management der Präzision beim Lesen von Geometrien ein entscheidender Aspekt der Geodaten‑Manipulation. Aspose.GIS für .NET bietet robuste Funktionen, um dies effizient zu erreichen. Durch Befolgen der in diesem Tutorial beschriebenen Schritte können Sie nahtlos **Vektorlayer**‑Objekte erstellen und die Präzision nach Ihren Anforderungen begrenzen, wodurch eine optimale Datenverarbeitung in Ihren Anwendungen gewährleistet wird.

## FAQ's
### Kann ich Aspose.GIS für .NET mit anderen .NET‑Frameworks wie .NET Core oder .NET Standard verwenden?
Ja, Aspose.GIS für .NET ist mit verschiedenen .NET‑Frameworks kompatibel, einschließlich .NET Core und .NET Standard.  
### Gibt es eine Testversion von Aspose.GIS für .NET?
Ja, Sie können eine kostenlose Testversion von der [Release‑Seite](https://releases.aspose.com/) erhalten.  
### Wo finde ich umfassende Dokumentation für Aspose.GIS für .NET?
Sie können die [Dokumentation](https://reference.aspose.com/gis/net/) für detaillierte Informationen und Beispiele einsehen.  
### Wie kann ich temporäre Lizenzen für Aspose.GIS für .NET erhalten?
Temporäre Lizenzen können Sie über die [Kauf‑Seite](https://purchase.aspose.com/temporary-license/) für Aspose.GIS erwerben.  
### Wo kann ich Unterstützung oder Support für Aspose.GIS für .NET erhalten?
Besuchen Sie das Aspose.GIS [Forum](https://forum.aspose.com/c/gis/33) für Fragen, Diskussionen oder Support‑Anfragen.

## Häufig gestellte Fragen
**F: Beeinflusst das Begrenzen der Präzision die ursprüngliche Shapefile?**  
A: Nein. Die Präzision wird nur beim Lesen der Geometrie angewendet; die Quelldatei bleibt unverändert.  

**F: Kann ich für X‑ und Y‑Koordinaten unterschiedliche Präzisionsmodelle verwenden?**  
A: Aspose.GIS wendet derzeit dasselbe `XYPrecisionModel` auf beide Achsen an.  

**F: Ist es möglich, eine benutzerdefinierte Rundungsfunktion festzulegen?**  
A: Die API unterstützt nur die eingebaute Methode `PrecisionModel.Rounding(int)`. Für benutzerdefinierte Logik müssten Sie die Koordinaten nach dem Lesen nachbearbeiten.

---

**Zuletzt aktualisiert:** 2025-12-20  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
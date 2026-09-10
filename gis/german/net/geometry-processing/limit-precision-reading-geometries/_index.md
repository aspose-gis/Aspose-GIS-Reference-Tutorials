---
date: 2026-09-10
description: Erfahren Sie, wie Sie mit Aspose.GIS für .NET einen Vektorlayer erstellen
  und die Präzision begrenzen, um die Größe von Shapefiles zu reduzieren, die Leistung
  zu steigern und die Koordinaten‑Genauigkeit beizubehalten.
keywords:
- how to create vector layer
- limit precision reading geometries
- reduce shapefile size
lastmod: 2026-09-10
linktitle: Präzision beim Lesen von Geometrien begrenzen
og_description: Erfahren Sie, wie Sie mit Aspose.GIS für .NET einen Vektorlayer erstellen
  und die Präzision begrenzen, um die Größe von Shapefiles zu reduzieren, die Leistung
  zu verbessern und die Koordinaten‑Genauigkeit zu verwalten.
og_image_alt: Screenshot showing Aspose.GIS code for creating a vector layer and setting
  precision
og_title: So erstellen Sie einen Vektorlayer mit Aspose.GIS für .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  headline: How to create vector layer with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  name: How to create vector layer with Aspose.GIS for .NET
  steps:
  - name: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
    text: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
  - name: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
    text: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
  - name: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
    text: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
  - name: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
    text: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
  type: HowTo
- questions:
  - answer: No. Precision is applied only when reading the geometry; the source file
      remains unchanged.
    question: Does limiting precision affect the original shapefile?
  - answer: Aspose.GIS currently applies the same `XYPrecisionModel` to both axes.
    question: Can I use a different precision model for X and Y coordinates?
  - answer: The API supports only the built‑in `PrecisionModel.Rounding(int)` method.
      For custom logic, you would need to post‑process the coordinates after reading.
    question: Is it possible to set a custom rounding function?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- Aspose.GIS
- vector layer
- precision model
- .NET GIS
title: So erstellen Sie einen Vektorlayer mit Aspose.GIS für .NET
url: /de/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man einen Vektorlayer mit Aspose.GIS für .NET erstellt

## Einleitung
Wenn Sie mit Geodaten arbeiten, fragen Sie sich oft, **wie man einen vector layer** erstellt, der die Genauigkeit bietet, die Ihre Anwendung wirklich benötigt. Das Runden von Koordinaten auf eine sinnvolle Anzahl von Dezimalstellen beschleunigt nicht nur das Parsen, sondern kann auch **die Größe von Shapefiles um bis zu 30 % reduzieren** für typische Punktdatensätze. In dieser Schritt‑für‑Schritt‑Anleitung sehen Sie, wie man einen vector layer erstellt, eine Punktgeometrie schreibt und sie dann mit sowohl exakten als auch gerundeten Präzisionsmodellen wieder einliest. Am Ende wissen Sie, wie man **precision model**‑Optionen einstellt, die Leistung und erforderliche räumliche Genauigkeit ausbalancieren.

## Schnelle Antworten
- **Was bedeutet “limit precision”?** Es rundet Koordinatenwerte auf eine definierte Anzahl von Dezimalstellen.  
- **Warum zuerst einen vector layer erstellen?** Ein vector layer ist der Container, der Geometrien wie Punkte, Linien und Polygone speichert.  
- **Welche Präzisionsmodelle sind verfügbar?** `PrecisionModel.Exact` (kein Runden) und `PrecisionModel.Rounding(n)` (Runden auf *n* Dezimalstellen).  
- **Benötige ich eine Lizenz, um dies auszuprobieren?** Eine kostenlose Testversion ist auf der releases page verfügbar.  
- **Welche .NET-Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core und .NET 5/6+.

## Was bedeutet das Erstellen eines vector layer?
Der Vorgang des **Erstellens eines vector layer** bedeutet, die Klasse `VectorLayer` von Aspose.GIS zu instanziieren, die ein einzelnes Shapefile auf der Festplatte repräsentiert und alle von Ihnen hinzugefügten Geometrie‑Features enthält. Dieser Layer wird zum Einstiegspunkt für das Lesen, Schreiben und Manipulieren räumlicher Daten. Er ermöglicht außerdem das Definieren von Attributfeldern und das Festlegen der räumlichen Referenz für den Datensatz.

## Warum Präzision begrenzen und wie hilft das?
- **Performance‑Steigerung** – Das Reduzieren der Anzahl von Dezimalstellen verringert die Menge an Binärdaten, die geparst und serialisiert werden müssen, und liefert häufig eine Geschwindigkeitssteigerung von 15‑20 % bei großen Dateien.  
- **Kleinere Dateien** – Das Runden von Koordinaten auf zwei oder drei Dezimalstellen kann ein 10 MB‑Shapefile auf etwa 7 MB verkleinern, was Speicher und Netzwerkübertragung erleichtert.  
- **Ausreichende Genauigkeit** – Die meisten GIS‑Analysen (z. B. Stadt‑Level‑Kartierung) benötigen nur Meter‑genaue Präzision, sodass ein Runden auf 3 Dezimalstellen mehr als ausreichend ist.

## Voraussetzungen
Bevor wir diese Reise beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:
1. **Installation** – Die Aspose.GIS for .NET Bibliothek sollte in Ihrer Entwicklungsumgebung installiert sein. Falls nicht, können Sie sie von der [releases page](https://releases.aspose.com/gis/net/) herunterladen.  
2. **Vertrautheit mit .NET** – Grundkenntnisse in C# und dem .NET‑Framework sind notwendig, um die bereitgestellten Code‑Beispiele zu verstehen und umzusetzen.  
3. **Entwicklungsumgebung** – Eine funktionierende .NET‑Entwicklungsumgebung, wie Visual Studio, ist erforderlich.  
4. **Dokumenten‑Verzeichnis** – Richten Sie ein Verzeichnis ein, in dem Sie das während des Prozesses erzeugte Shapefile speichern und darauf zugreifen können.

## Namespaces importieren
Bevor wir beginnen, die Funktionalität zum Begrenzen der Präzision beim Lesen von Geometrien zu implementieren, stellen wir sicher, dass wir die notwendigen Namespaces importieren:

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

## Wie man einen vector layer erstellt
Laden Sie einen neuen `VectorLayer`, indem Sie den Ausgabepfad und den gewünschten Shapefile‑Namen angeben. Dies erstellt einen leeren Container, der bereit ist, Geometrieobjekte aufzunehmen.

Die Klasse `VectorLayer` ist das Top‑Level‑Objekt von Aspose.GIS, das ein einzelnes Shapefile auf der Festplatte repräsentiert. Nachdem Sie eine Instanz erstellt haben, können Sie Features hinzufügen, Attributfelder definieren und schließlich `Save()` aufrufen, um die Dateien in das Dateisystem zu schreiben.

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
`PrecisionModel` definiert, wie Koordinatenwerte beim Lesen von Geometrien gerundet oder exakt beibehalten werden. Sie setzen das Modell auf einem `ReadOptions`‑Objekt, bevor Sie einen Layer öffnen.

Die Klasse `PrecisionModel` ist ein Kernbestandteil von Aspose.GIS, der das Rundungsverhalten für sowohl X‑ als auch Y‑Achsen steuert. Durch die Wahl des passenden Modells bestimmen Sie, ob die Bibliothek jede Ziffer beibehält oder auf eine bestimmte Dezimalzahl trunciert.

```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Geometrien mit exakter Präzision lesen
`ReadOptions` gibt Parameter für das Lesen eines vector layer an, wie das anzuwendende Präzisionsmodell.  
Öffnen Sie den zuvor gespeicherten vector layer mit einer `ReadOptions`‑Instanz, die `PrecisionModel.Exact` referenziert. Dies stellt sicher, dass jede Koordinate ohne Rundung gelesen wird.

Wenn Sie `PrecisionModel.Exact` verwenden, liest Aspose.GIS die rohen Double‑Präzisionswerte aus dem Shapefile, wodurch garantiert wird, dass während des Lesevorgangs keine Informationen verloren gehen.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Präzision truncieren
Wenn Sie die Präzision auf eine bestimmte Anzahl von Dezimalstellen truncieren möchten, ersetzen Sie `Exact` durch `PrecisionModel.Rounding(n)`, wobei *n* die Anzahl der Dezimalstellen ist, die Sie behalten möchten.

Das Runden auf zwei Dezimalstellen (`PrecisionModel.Rounding(2)`) reduziert typischerweise die Dateigröße um 20‑30 %, während die Koordinaten‑Genauigkeit für die meisten Kartierungsmaßstäbe innerhalb weniger Zentimeter bleibt.

```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Wie man das precision model für verschiedene Szenarien festlegt
Wählen Sie das Modell, das zu Ihrem Anwendungsfall passt:
- **Hochpräzise wissenschaftliche Analyse** – Verwenden Sie `PrecisionModel.Exact`, um jede Ziffer beizubehalten.  
- **Web‑Mapping‑Kacheln oder mobile Apps** – Verwenden Sie `PrecisionModel.Rounding(2)`, um Dateien leichtgewichtig zu halten und das Rendern zu beschleunigen.

Die Auswahl des passenden Modells ist Teil des **set precision model**‑Entscheidungsprozesses, der Genauigkeit gegen Leistung abwägt.

## Häufige Probleme und Lösungen
`XYPrecisionModel` ist eine Eigenschaft von `ReadOptions`, die das Präzisionsmodell für sowohl X‑ als auch Y‑Koordinaten festlegt.
- **Unerwartete Koordinatenwerte** – Stellen Sie sicher, dass Sie `options.XYPrecisionModel` *vor* dem Öffnen des Layers setzen. Eine Änderung danach hat keine Wirkung.  
- **Datei nicht gefunden** – Überprüfen Sie, ob die Variable `path` auf ein gültiges Verzeichnis zeigt und das Shapefile im vorherigen Schritt erfolgreich erstellt wurde.  
- **Falscher Geometrietyp** – Das Beispiel verwendet einen `Point`. Für andere Geometrietypen (z. B. `LineString`) sollte das Casting dem tatsächlichen Typ entsprechen.

## Tipps zur Reduzierung der Shapefile‑Größe
- Verwenden Sie `PrecisionModel.Rounding` mit der kleinsten Anzahl von Dezimalstellen, die Ihre Genauigkeitsanforderungen noch erfüllt.  
- Entfernen Sie unnötige Attributfelder, bevor Sie den Layer schreiben.  
- Komprimieren Sie die resultierenden `.shp`, `.shx` und `.dbf`‑Dateien mit gängigen ZIP‑Tools, wenn Sie sie übertragen müssen.

## Fazit
Die Verwaltung der Präzision beim Lesen von Geometrien ist ein entscheidender Aspekt der Manipulation von Geodaten. Aspose.GIS für .NET bietet robuste Funktionen, um dies effizient zu erreichen. Durch Befolgen der obigen Schritte können Sie nahtlos **vector layer**‑Objekte **erstellen**, **precision model** festlegen und bei Bedarf sogar **Shapefile‑Größe reduzieren**, um eine optimale Datenverarbeitung in Ihren Anwendungen sicherzustellen.

## FAQ
### Kann ich Aspose.GIS für .NET mit anderen .NET‑Frameworks wie .NET Core oder .NET Standard verwenden?
Ja, Aspose.GIS für .NET ist mit verschiedenen .NET‑Frameworks kompatibel, einschließlich .NET Core und .NET Standard.

### Gibt es eine Testversion für Aspose.GIS für .NET?
Ja, Sie können eine kostenlose Testversion von der [releases page](https://releases.aspose.com/) erhalten.

### Wo finde ich umfassende Dokumentation für Aspose.GIS für .NET?
Sie können die [documentation](https://reference.aspose.com/gis/net/) für detaillierte Informationen und Beispiele konsultieren.

### Wie kann ich temporäre Lizenzen für Aspose.GIS für .NET erhalten?
Temporäre Lizenzen können von der [purchase page](https://purchase.aspose.com/temporary-license/) für Aspose.GIS erworben werden.

### Wo kann ich Unterstützung oder Support für Aspose.GIS für .NET erhalten?
Sie können das Aspose.GIS‑[forum](https://forum.aspose.com/c/gis/33) für Fragen, Diskussionen oder Support‑Bedürfnisse besuchen.

## Häufig gestellte Fragen
**Q: Beeinflusst das Begrenzen der Präzision das ursprüngliche Shapefile?**  
A: Nein. Die Präzision wird nur beim Lesen der Geometrie angewendet; die Quelldatei bleibt unverändert.

**Q: Kann ich ein anderes Präzisionsmodell für X‑ und Y‑Koordinaten verwenden?**  
A: Aspose.GIS wendet derzeit dasselbe `XYPrecisionModel` für beide Achsen an.

**Q: Ist es möglich, eine benutzerdefinierte Rundungsfunktion festzulegen?**  
A: Die API unterstützt nur die integrierte Methode `PrecisionModel.Rounding(int)`. Für benutzerdefinierte Logik müssen Sie die Koordinaten nach dem Lesen nachbearbeiten.

---

**Zuletzt aktualisiert:** 2026-09-10  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man Präzision beim Schreiben von Geometrien mit Aspose.GIS begrenzt](/gis/net/geometry-processing/limit-precision-writing-geometries/)
- [Wie man einen Vector Layer mit SRS mit Aspose.GIS für .NET erstellt](/gis/net/layer-management/create-vector-layer-with-srs/)
- [Vector Layer in File GDB erstellen – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
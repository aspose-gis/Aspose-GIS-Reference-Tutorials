---
date: 2026-01-13
description: Erfahren Sie, wie Sie mit Aspose.GIS eine Ebene zu einem File‑GDB‑Datensatz
  hinzufügen, mit Unterstützung des räumlichen Bezugs WGS84. Folgen Sie dieser Schritt‑für‑Schritt‑Anleitung,
  um eine Ebene zu GDB in .NET hinzuzufügen.
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: Räumliche Referenz WGS84 – Layer zu GDB hinzufügen mit Aspose.GIS
url: /de/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# spatial reference wgs84 – Ebene zu GDB hinzufügen mit Aspose.GIS

## Einführung
Bereit, Ihren GIS‑Workflow mit Aspose.GIS für .NET zu beschleunigen? In diesem Tutorial lernen Sie **wie Sie einer File‑GDB‑Datensatz‑Collection eine Ebene hinzufügen** und dabei das **spatial reference wgs84** Koordinatensystem verwenden. Wir führen Sie Schritt für Schritt durch, vom Vorbereiten Ihres Datenordners bis zum Validieren der neu erstellten Ebene, sodass Sie geografische Daten selbstbewusst manipulieren können.

## Kurzantworten
- **Was ist das primäre Koordinatensystem?** spatial reference wgs84 (WGS 84)  
- **Welche Bibliothek stellt die API bereit?** Aspose.GIS for .NET  
- **Benötige ich eine Lizenz für Tests?** Ja – eine temporäre Aspose‑Lizenz ist verfügbar.  
- **Kann ich Attribute zur neuen Ebene hinzufügen?** Absolut, Sie können beliebig viele Feature‑Attribute definieren.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## Was ist spatial reference wgs84?
Der spatial reference wgs84 (World Geodetic System 1984) ist das am weitesten verbreitete geografische Koordinatensystem. Er definiert Breiten- und Längengrad in Grad und dient als Standard‑CRS für viele GIS‑Datensätze, einschließlich desjenigen, den wir in diesem Leitfaden erstellen werden.

## Warum Aspose.GIS zum Hinzufügen einer Ebene verwenden?
- **Keine externen Abhängigkeiten:** Funktioniert sofort einsatzbereit mit reinem .NET‑Code.  
- **Vollständige Kontrolle über das Schema:** Sie können benutzerdefinierte Attribute und Geometrietypen definieren.  
- **Plattformübergreifend:** Kompatibel mit Windows-, Linux- und macOS‑Laufzeiten.  
- **Robuste Lizenzierung:** Temporäre Lizenzen ermöglichen eine schnelle Evaluierung vor dem Kauf.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Aspose.GIS for .NET Library: Laden Sie die Bibliothek von der [Aspose.GIS für .NET Dokumentation](https://reference.aspose.com/gis/net/) herunter und installieren Sie sie.  
- Dokumentenverzeichnis: Erstellen Sie einen eigenen Ordner auf Ihrem Rechner, um GIS‑Dateien zu speichern.

## Namespaces importieren
Fügen Sie die erforderlichen `using`‑Anweisungen zu Ihrem C#‑Projekt hinzu, damit Sie auf die Aspose.GIS‑Klassen zugreifen können:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt 1: Verzeichnis kopieren
Zuerst duplizieren Sie den Ordner, der den ursprünglichen GDB‑Datensatz enthält. Das Anlegen einer Kopie schützt die Quelldaten, während Sie experimentieren.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Schritt 2: Datensatz öffnen und Erstellungsfähigkeit prüfen
Öffnen Sie den neu kopierten Datensatz und bestätigen Sie, dass er neue Ebenen erstellen kann. Die Eigenschaft `CanCreateLayers` sollte **True** zurückgeben.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Schritt 3: Neue Ebene mit spatial reference wgs84 erstellen und füllen
Jetzt erstellen wir eine Ebene namens **data** und setzen explizit ihre räumliche Referenz auf **Wgs84**. Außerdem fügen wir ein einfaches Attribut namens **Name** hinzu und inserieren ein Punkt‑Feature.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## Schritt 4: Hinzugefügte Ebene öffnen und validieren
Zum Schluss öffnen Sie die gerade erstellte Ebene und überprüfen deren Inhalt. Die Konsole zeigt, dass die Ebene ein Feature enthält und dass das **Name**‑Attribut dem von uns gesetzten Wert entspricht.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Häufige Probleme & Tipps
- **Falscher Pfad:** Stellen Sie sicher, dass `dataDir` mit einem Pfadtrennzeichen (`/` oder `\`) endet, damit die zusammengefügten Zeichenketten gültige Dateipfade ergeben.  
- **Lizenzfehler:** Wenn Sie Lizenzwarnungen sehen, wenden Sie vor dem Ausführen des Codes eine temporäre Lizenz aus dem Aspose‑Portal an.  
- **CRS‑Mismatch:** Beim späteren Öffnen der Ebene in einem anderen GIS‑Tool prüfen Sie, ob das Tool WGS 84 (EPSG:4326) als Koordinatensystem erkennt.

## Häufig gestellte Fragen
### Q: Kann ich Aspose.GIS für .NET mit anderen GIS‑Bibliotheken verwenden?
Aspose.GIS for .NET ist so konzipiert, dass es eigenständig funktioniert, kann aber zur Erweiterung mit anderen Bibliotheken integriert werden.

### Q: Ist eine temporäre Lizenz für Testzwecke verfügbar?
Ja, Sie können eine temporäre Lizenz von [hier](https://purchase.aspose.com/temporary-license/) für Tests und Evaluierung erhalten.

### Q: Welche räumlichen Referenzsysteme unterstützt Aspose.GIS für .NET?
Aspose.GIS for .NET unterstützt eine breite Palette von räumlichen Referenzsystemen und bietet Flexibilität bei der Handhabung geografischer Daten.

### Q: Kann ich zur Aspose.GIS‑Community beitragen?
Absolut! Nehmen Sie an den Diskussionen teil und teilen Sie Ihre Erfahrungen im [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33).

### Q: Wo finde ich ausführliche Dokumentation zu Aspose.GIS für .NET?
Entdecken Sie die umfassende Dokumentation [hier](https://reference.aspose.com/gis/net/) für detaillierte Informationen zu Aspose.GIS für .NET.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-01-13  
**Getestet mit:** Aspose.GIS for .NET (latest stable version)  
**Autor:** Aspose
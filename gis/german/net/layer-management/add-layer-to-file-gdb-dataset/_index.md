---
date: 2026-06-30
description: Erfahren Sie, wie Sie mit Aspose.GIS und dem räumlichen Bezug WGS84 eine
  Ebene zu einem File GDB Dataset hinzufügen. Folgen Sie dieser Schritt‑für‑Schritt‑Anleitung,
  um eine Ebene in .NET hinzuzufügen.
keywords:
- how to add layer
- spatial reference wgs84
- Aspose.GIS .NET
- File GDB dataset
linktitle: Ebene zu File GDB Dataset hinzufügen
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to add layer to a File GDB dataset using Aspose.GIS with
    spatial reference WGS84. Follow this step‑by‑step guide to add a layer in .NET.
  headline: How to Add Layer to File GDB Dataset with spatial reference WGS84 using
    Aspose.GIS
  type: TechArticle
- questions:
  - answer: spatial reference wgs84 (WGS 84)
    question: What is the primary coordinate system used?
  - answer: Aspose.GIS for .NET
    question: Which library provides the API?
  - answer: Yes – a temporary Aspose license is available.
    question: Do I need a license for testing?
  - answer: Absolutely, you can define any number of feature attributes.
    question: Can I add attributes to the new layer?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Wie man einer File GDB Dataset eine Ebene mit dem räumlichen Bezug WGS84 mithilfe
  von Aspose.GIS hinzufügt
url: /de/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man eine Ebene hinzufügt – räumliche Referenz WGS84 mit Aspose.GIS

## Einleitung
Bereit, Ihren GIS‑Workflow mit Aspose.GIS für .NET zu verbessern? In diesem Tutorial lernen Sie **wie man eine Ebene hinzufügt** zu einem File‑GDB‑Datensatz, während Sie mit dem **räumlichen Referenzsystem WGS84** arbeiten. Wir gehen jeden Schritt durch, von der Vorbereitung Ihres Datenordners bis zur Validierung der neu erstellten Ebene, damit Sie geografische Daten sicher und effizient manipulieren können.

## Schnelle Antworten
- **Was ist das primäre Koordinatensystem?** spatial reference wgs84 (WGS 84)  
- **Welche Bibliothek stellt die API bereit?** Aspose.GIS for .NET  
- **Benötige ich eine Lizenz für Tests?** Yes – a temporary Aspose license is available.  
- **Kann ich Attribute zur neuen Ebene hinzufügen?** Absolutely, you can define any number of feature attributes.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## Was ist die räumliche Referenz WGS84?
Die räumliche Referenz WGS84 (World Geodetic System 1984) ist das am weitesten verbreitete geografische Koordinatensystem. Sie definiert Breiten- und Längengrad in Grad und dient als Standard‑CRS für viele GIS‑Datensätze, einschließlich desjenigen, den wir in diesem Leitfaden erstellen werden.

## Warum Aspose.GIS zum Hinzufügen einer Ebene verwenden?
Laden Sie Ihre GIS‑Daten ohne Drittanbieter‑Binärdateien und behalten Sie die volle Kontrolle über die Schema‑Definition. Aspose.GIS unterstützt **40+ räumliche Referenzsysteme**, kann Dateien größer als **2 GB** verarbeiten, ohne den gesamten Datensatz in den Speicher zu laden, und läuft auf Windows, Linux und macOS. Das macht es zu einer zuverlässigen, plattformübergreifenden Lösung für GIS‑Automatisierung auf Unternehmensniveau.

## Voraussetzungen
- Aspose.GIS for .NET Bibliothek: Laden Sie die Bibliothek von der [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/) herunter und installieren Sie sie.  
- Dokumentenverzeichnis: Erstellen Sie einen eigenen Ordner auf Ihrem Rechner, um GIS‑Dateien zu speichern.  
- Eine temporäre Aspose‑Lizenz (optional für die Evaluierung) – siehe den FAQ unten für den Download‑Link.

## Namespaces importieren
Fügen Sie die erforderlichen `using`‑Anweisungen zu Ihrem C#‑Projekt hinzu, damit Sie auf Aspose.GIS‑Klassen zugreifen können:

*Kein Code‑Block ist hier erforderlich; fügen Sie einfach die folgenden Zeilen am Anfang Ihrer Datei ein:*

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
using Aspose.Gis.SpatialReference;
```

## Schritt 1: Verzeichnis kopieren
**Definition anchor:** Ein File‑GDB‑Datensatz ist eine ordnerbasierte ESRI‑Geodatenbank, die räumliche Daten in einer Menge von Dateien speichert.  
Zuerst duplizieren Sie den Ordner, der den ursprünglichen GDB‑Datensatz enthält. Das Behalten einer Kopie schützt die Quelldaten, während Sie experimentieren.

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

## Schritt 2: Datensatz öffnen und Erstellungsfähigkeit prüfen
`Dataset` repräsentiert eine Sammlung von GIS‑Ebenen, die in einem File‑GDB gespeichert sind. Öffnen Sie den neu kopierten Datensatz und bestätigen Sie, dass er neue Ebenen erstellen kann. Die Eigenschaft `CanCreateLayers` sollte **True** zurückgeben. **`CanCreateLayers` ist eine boolesche Eigenschaft, die angibt, ob der Datensatz das Erstellen neuer Ebenen unterstützt.**

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Schritt 3: Eine neue Ebene mit räumlicher Referenz WGS84 erstellen und füllen
Jetzt erstellen wir eine Ebene mit dem Namen **data** und setzen ihre räumliche Referenz explizit auf **Wgs84**. Wir fügen außerdem ein einfaches Attribut namens **Name** hinzu und fügen ein Punkt‑Feature ein. **`CreateLayer` erstellt eine neue Ebene im Datensatz mit dem angegebenen Namen und der räumlichen Referenz.** **`SpatialReference` stellt das Koordinatensystem dar, das von einer Ebene verwendet wird.** **`Feature` ist ein einzelnes geografisches Objekt (Punkt, Linie oder Polygon), das in einer Ebene gespeichert ist.**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Schritt 4: Ebene öffnen und validieren
Schließlich öffnen Sie die gerade erstellte Ebene und überprüfen ihren Inhalt. Die Konsole zeigt, dass die Ebene ein Feature enthält und dass das **Name**‑Attribut dem von uns gesetzten Wert entspricht. **`Layer.Open` öffnet eine vorhandene Ebene zum Lesen oder Bearbeiten.** Dies bestätigt, dass die Ebene korrekt hinzugefügt wurde und dass die räumliche Referenz WGS84 ist.

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

## Wie fügt man einer File GDB‑Datensatz eine Ebene hinzu?
Laden Sie den Datensatz, rufen Sie `CreateLayer` mit dem gewünschten Namen und der räumlichen Referenz auf, definieren Sie das Attribut‑Schema und fügen Sie dann Features ein. All dies kann mit wenigen Aspose.GIS‑Methodenaufrufen erledigt werden, und die API kümmert sich automatisch um Dateisperren und Schema‑Validierung. Der Vorgang stellt sicher, dass die neue Ebene der räumlichen Referenz des Datensatzes entspricht, dass Attributdefinitionen im Schema der Ebene gespeichert werden und dass die Daten von jeder GIS‑Software, die File‑GDB unterstützt, abgerufen werden können.

## Häufige Probleme & Tipps
- **Falscher Pfad:** Stellen Sie sicher, dass `dataDir` mit einem Pfadtrenner (`/` oder `\`) endet, damit die verketteten Zeichenfolgen gültige Dateipfade bilden.  
- **Lizenzfehler:** Wenn Sie Lizenzwarnungen sehen, wenden Sie vor dem Ausführen des Codes eine temporäre Lizenz aus dem Aspose‑Portal an.  
- **CRS‑Mismatch:** Beim späteren Öffnen der Ebene in einem anderen GIS‑Tool prüfen Sie, ob das Tool WGS 84 (EPSG:4326) als Koordinatensystem erkennt.  
- **Große Datensätze:** Für Datensätze, die 1 GB überschreiten, sollten Sie `Dataset.OpenReadOnly` verwenden, um den Speicherverbrauch zu reduzieren.

## Häufig gestellte Fragen
### Q: Kann ich Aspose.GIS für .NET mit anderen GIS‑Bibliotheken verwenden?
A: Ja, Aspose.GIS funktioniert eigenständig, kann aber mit Bibliotheken wie GDAL oder NetTopologySuite für fortgeschrittene Verarbeitung kombiniert werden.

### Q: Ist eine temporäre Lizenz für Testzwecke verfügbar?
A: Ja, Sie können eine temporäre Lizenz von [hier](https://purchase.aspose.com/temporary-license/) für Tests und Evaluierung erhalten.

### Q: Welche räumlichen Referenzsysteme unterstützt Aspose.GIS für .NET?
A: Aspose.GIS unterstützt über **40 EPSG‑Codes**, darunter gängige Systeme wie WGS84 (EPSG:4326), Web Mercator (EPSG:3857) und NAD83 (EPSG:4269). Erkunden Sie die umfassende Dokumentation [hier](https://reference.aspose.com/gis/net/).

### Q: Kann ich zur Aspose.GIS‑Community beitragen?
A: Absolut! Nehmen Sie an den Diskussionen teil und teilen Sie Ihre Erfahrungen im [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33).

### Q: Wo finde ich detaillierte Dokumentation für Aspose.GIS für .NET?
A: Erkunden Sie die umfassende Dokumentation [hier](https://reference.aspose.com/gis/net/) für detaillierte Informationen zu allen Klassen, Methoden und bewährten Verfahren.

---

**Zuletzt aktualisiert:** 2026-06-30  
**Getestet mit:** Aspose.GIS for .NET (latest stable version)  
**Autor:** Aspose

{{< blocks/products/products-backtop-button >}}

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Verwandte Tutorials

- [File‑Geodatenbank‑Datensatz .NET mit Aspose.GIS erstellen](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Vektor‑Ebene in File GDB erstellen – Aspose.GIS .NET‑Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [File GDB‑Datensatz erstellen und Toleranzen für eine Ebene festlegen](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
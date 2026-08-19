---
date: 2026-06-20
description: Erfahren Sie, wie Sie GeoJSON mit Aspose.GIS für .NET in GDB konvertieren.
  Diese Schritt‑für‑Schritt‑Anleitung behandelt das Einlesen von GeoJSON in C#, das
  Erstellen einer File Geodatabase und die Behandlung häufiger Probleme.
keywords:
- convert geojson to gdb
- how to convert geojson
- read geojson c#
- asp.net geojson conversion
linktitle: GeoJSON-Layer in GDB konvertieren
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to convert geojson to gdb with Aspose.GIS for .NET. This
    step‑by‑step guide covers reading GeoJSON in C#, creating a File Geodatabase,
    and handling common issues.
  headline: How to Convert GeoJSON to GDB Using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Converting a GeoJSON layer to a GDB with Aspose.GIS for .NET.
    question: What does this guide teach?
  - answer: '*convert geojson to gdb*.'
    question: Which primary keyword is targeted?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Supported .NET versions?
  - answer: Roughly 10‑15 minutes for a basic conversion.
    question: Implementation time?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Wie man GeoJSON mit Aspose.GIS für .NET in GDB konvertiert
url: /de/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man GeoJSON in GDB mit Aspose.GIS für .NET konvertiert

## Einführung
Wenn Sie **convert geojson to gdb** schnell und zuverlässig durchführen möchten, sind Sie hier genau richtig. Dieses Tutorial führt Sie durch jeden Schritt – vom Lesen einer GeoJSON‑Datei in C# bis zum Erstellen einer File Geodatabase (GDB) mit Aspose.GIS. Sie werden sehen, warum Aspose.GIS eine bevorzugte Bibliothek für die Konvertierung geospatieller Daten ist, wie Sie die Umgebung einrichten und die Konvertierung in nur wenigen Minuten ausführen können.

## Schnelle Antworten
- **Was lehrt dieser Leitfaden?** Konvertieren einer GeoJSON‑Ebene in ein GDB mit Aspose.GIS für .NET.  
- **Welches primäre Schlüsselwort wird angestrebt?** *convert geojson to gdb*.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert zum Testen; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Unterstützte .NET‑Versionen?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Implementierungszeit?** Ungefähr 10‑15 Minuten für eine einfache Konvertierung.

## Was ist GeoJSON und File GDB?
GeoJSON ist ein leichtgewichtiges, textbasiertes Format für geografische Features, während File GDB eine ordnerbasierte Hochleistungs‑ESRI‑Geodatenbank ist.  
GeoJSON speichert Punkte, Linien und Polygone als Klartext, was das Teilen und Bearbeiten erleichtert, während File GDB Daten in Binärdateien hält, die schnelle räumliche Abfragen und eine robuste Attributverarbeitung ermöglichen. Zusammen decken sie sowohl den web‑freundlichen Austausch als auch die Hochgeschwindigkeits‑Desktop‑GIS‑Verarbeitung ab.

## Warum Aspose.GIS für die Konvertierung geospatieller Daten verwenden?
Aspose.GIS bietet eine einheitliche, konsistente API, die format‑spezifische Eigenheiten verbirgt. Es unterstützt **30+ geospatiale Formate**, kann Dateien bis zu **2 GB** verarbeiten, ohne den gesamten Datensatz in den Speicher zu laden, und bewahrt automatisch Koordinatenreferenzsysteme. Das bedeutet, dass Sie weniger Zeit mit dem Schreiben von Parsern und mehr Zeit mit dem Aufbau Ihrer Anwendungslogik verbringen.

## Voraussetzungen
- Vertrautheit mit C# und der .NET‑Projektstruktur.  
- Aspose.GIS for .NET installiert. Wenn Sie es noch nicht installiert haben, laden Sie es von [hier](https://releases.aspose.com/gis/net/) herunter und folgen Sie der Installationsanleitung. Weitere Aspose‑Produkte können Sie unter [hier](https://releases.aspose.com/) erkunden.

## Namespaces importieren
Der erste Schritt besteht darin, die erforderlichen Namespaces in den Gültigkeitsbereich zu holen.

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

## Wie liest man GeoJSON in C#?
Laden Sie die GeoJSON‑Datei mit der Klasse `GeoJsonReader`, die das JSON parst und eine In‑Memory‑`FeatureCollection` erstellt. Der Reader erkennt automatisch das Koordinatenreferenzsystem, sodass Sie die CRS‑Analyse nicht manuell durchführen müssen. Er unterstützt außerdem das Streaming großer Dateien, bewahrt Attributtypen und kann bei Bedarf mit benutzerdefinierten Geometrie‑Transformationen kombiniert werden.

```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Add attributes
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    // Construct and add features
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```

## Schritt 1: GeoJSON‑Ebene einrichten
Erstellen Sie eine temporäre GeoJSON‑Datei, die die Attribute und Features enthält, die Sie konvertieren möchten. Dieses Beispiel fügt zwei einfache Punkt‑Features hinzu.

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## Schritt 2: Testdatensatz kopieren
Um die ursprünglichen Testdaten unverändert zu lassen, duplizieren Sie den bestehenden File‑GDB‑Datensatz. Das sorgt für eine saubere Umgebung für die Konvertierung.

```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copy attributes
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Add features
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```

## Schritt 3: GeoJSON in GDB konvertieren
`FileGdb` stellt einen File‑Geodatabase‑Container dar und bietet Methoden zur Verwaltung von Ebenen. Öffnen Sie die GeoJSON‑Ebene, erstellen Sie eine neue Ebene innerhalb des kopierten File‑GDB, kopieren Sie Attribute und übertragen Sie jedes Feature. Dies ist der Kern des **Aspose.GIS‑Konvertierungs**‑Prozesses.

CODE_BLOCK_PLACEHOLDER_4_END

## Wie konvertiert man GeoJSON in GDB?
Laden Sie das GeoJSON mit `GeoJsonReader`, instanziieren Sie ein `FileGdb`‑Objekt, das auf Ihren Zielordner zeigt, erstellen Sie eine neue Feature‑Ebene und iterieren Sie anschließend über jedes Feature, um es einzufügen. In der Praxis ist es ein dreistufiger Ablauf – lesen, erstellen, kopieren – der für typische Datensätze in weniger als einer Minute abgeschlossen ist.

## Häufige Probleme und Lösungen
- **Fehlende räumliche Referenz:** Stellen Sie sicher, dass das Quell‑GeoJSON eine CRS‑Definition enthält oder setzen Sie beim Erstellen der GDB‑Ebene explizit `SpatialReferenceSystem.Wgs84`.  
- **Attributtyp‑Fehlanpassung:** Die Attributdatentypen im GeoJSON müssen dem Zielschema entsprechen; andernfalls wirft Aspose.GIS eine Ausnahme.  
- **Dateizugriffsfehler:** Vergewissern Sie sich, dass der Zielordner Schreibrechte hat und kein anderer Prozess die GDB‑Dateien sperrt.

## Häufig gestellte Fragen
### Ist Aspose.GIS mit dem neuesten .NET‑Framework kompatibel?
Ja, Aspose.GIS funktioniert mit .NET Framework 4.5+, .NET Core 3.1+, .NET 5 und .NET 6+.

### Kann ich andere geospatiale Formate mit Aspose.GIS konvertieren?
Absolut! Aspose.GIS unterstützt mehr als 30 Eingabe‑ und Ausgabeformate, einschließlich Shapefile, KML, GML und SQLite.

### Gibt es eine Testversion von Aspose.GIS?
Ja, Sie können die Funktionen von Aspose.GIS testen, indem Sie die Testversion [hier](https://releases.aspose.com/) herunterladen.

### Wie kann ich Unterstützung für Aspose.GIS‑bezogene Anfragen erhalten?
Besuchen Sie das Aspose.GIS‑[Forum](https://forum.aspose.com/c/gis/33) für dedizierte Unterstützung durch die Community und das Produktteam.

### Kann ich eine temporäre Lizenz für Aspose.GIS erhalten?
Ja, Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erhalten.

---

**Zuletzt aktualisiert:** 2026-06-20  
**Getestet mit:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [File‑Geodatabase‑Dataset für .NET mit Aspose.GIS erstellen](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Features aus File‑Geodatabase in Aspose.GIS lesen](/gis/net/layer-data-operations/read-features-from-file-geodatabase/)
- [Vektor‑Ebene in File‑GDB erstellen – Aspose.GIS .NET‑Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
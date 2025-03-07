---
title: GIS-Beherrschung – Hinzufügen von Ebenen zu GDB mit Aspose.GIS für .NET
linktitle: Fügen Sie dem Datei-GDB-Datensatz eine Ebene hinzu
second_title: Aspose.GIS .NET-API
description: Nutzen Sie die Leistungsfähigkeit von GIS mit Aspose.GIS für .NET! Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie Layer zu File-GDB-Datensätzen hinzufügen. #geografische Daten #Aspose #GIS
weight: 16
url: /de/net/layer-management/add-layer-to-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GIS-Beherrschung – Hinzufügen von Ebenen zu GDB mit Aspose.GIS für .NET

## Einführung
Sind Sie bereit, Ihre GIS-Funktionen mit Aspose.GIS für .NET zu erweitern? In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess des Hinzufügens eines Layers zu einem File Geodatabase (GDB)-Datensatz. Aspose.GIS für .NET bietet leistungsstarke Funktionen zum Bearbeiten geografischer Informationen. Mit diesem Tutorial können Sie zusätzliche Ebenen nahtlos in Ihre Datensätze integrieren.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
-  Aspose.GIS für .NET-Bibliothek: Laden Sie die Bibliothek von herunter und installieren Sie sie[Aspose.GIS für .NET-Dokumentation](https://reference.aspose.com/gis/net/).
- Dokumentenverzeichnis: Erstellen Sie auf Ihrem Computer ein spezielles Dokumentenverzeichnis zum Speichern und Verwalten von GIS-bezogenen Dateien.
## Namespaces importieren
Stellen Sie in Ihrem .NET-Projekt sicher, dass Sie die erforderlichen Namespaces importieren, um auf die Aspose.GIS-Funktionen zuzugreifen. Verwenden Sie den folgenden Codeausschnitt:
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
## Schritt 1: Verzeichnis kopieren
Bevor Sie fortfahren, duplizieren Sie das Verzeichnis, das Ihren GDB-Datensatz enthält. Dieser Schritt stellt sicher, dass der ursprüngliche Datensatz intakt bleibt. Verwenden Sie das bereitgestellte Code-Snippet:
```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```
## Schritt 2: Öffnen Sie den Datensatz und prüfen Sie die Erstellungsfähigkeit
 Öffnen Sie den duplizierten Datensatz und prüfen Sie, ob er Ebenen erstellen kann. Dies wird durch die Anwesenheit von bestätigt`True` in der Konsolenausgabe.
```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // WAHR
```
## Schritt 3: Erstellen und füllen Sie eine neue Ebene
Erstellen Sie einen neuen Layer innerhalb des Datensatzes und definieren Sie dessen räumliches Bezugssystem, Attribute und ein Beispielmerkmal. Dieses Code-Snippet demonstriert den Prozess:
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
## Schritt 4: Öffnen und validieren Sie die hinzugefügte Ebene
Öffnen Sie die Ebene, die Sie gerade erstellt haben, und validieren Sie ihren Inhalt. Überprüfen Sie die Anzahl und rufen Sie die Attributwerte mit dem folgenden Code ab:
```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // „Name_1“
}
```
## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.GIS für .NET einen Layer zu einem File-GDB-Dataset hinzufügen. Mit diesen neu erworbenen Fähigkeiten können Sie geografische Daten in Ihren GIS-Projekten effizient bearbeiten.
## Häufig gestellte Fragen
### F: Kann ich Aspose.GIS für .NET mit anderen GIS-Bibliotheken verwenden?
Aspose.GIS für .NET ist für den unabhängigen Betrieb konzipiert, kann jedoch zur Erweiterung der Funktionalität in andere Bibliotheken integriert werden.
### F: Ist zu Testzwecken eine temporäre Lizenz verfügbar?
 Ja, Sie können eine temporäre Lizenz erhalten von[Hier](https://purchase.aspose.com/temporary-license/) zum Testen und Bewerten.
### F: Welche räumlichen Bezugssysteme unterstützt Aspose.GIS für .NET?
Aspose.GIS für .NET unterstützt eine Vielzahl räumlicher Bezugssysteme und bietet so Flexibilität bei der Verarbeitung geografischer Daten.
### F: Kann ich zur Aspose.GIS-Community beitragen?
 Absolut! Beteiligen Sie sich an den Diskussionen und teilen Sie Ihre Erfahrungen auf der[Aspose.GIS-Forum](https://forum.aspose.com/c/gis/33).
### F: Wo finde ich eine ausführliche Dokumentation zu Aspose.GIS für .NET?
 Entdecken Sie die umfassende Dokumentation[Hier](https://reference.aspose.com/gis/net/) Ausführliche Informationen zu Aspose.GIS für .NET finden Sie hier.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

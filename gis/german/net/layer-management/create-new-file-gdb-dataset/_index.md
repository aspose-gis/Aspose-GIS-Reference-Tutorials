---
title: Erstellen Sie einen neuen Datei-GDB-Datensatz
linktitle: Erstellen Sie einen neuen Datei-GDB-Datensatz
second_title: Aspose.GIS .NET-API
description: Entdecken Sie Aspose.GIS für .NET, um mühelos GIS-Datensätze zu erstellen und zu verwalten. Laden Sie es jetzt herunter und profitieren Sie von einer nahtlosen Geodatenentwicklung. #Aspose #GIS
weight: 10
url: /de/net/layer-management/create-new-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen Sie einen neuen Datei-GDB-Datensatz

## Einführung
Im Bereich der Geodatenentwicklung zeichnet sich Aspose.GIS für .NET als leistungsstarkes Toolkit zur Verwaltung und Bearbeitung von GIS-Daten (Geographic Information System) aus. Unabhängig davon, ob Sie ein erfahrener Entwickler sind oder gerade erst Ihre Reise in den GIS-Bereich beginnen, führt Sie dieses Tutorial durch den Prozess der Erstellung eines neuen File Geodatabase (GDB)-Datensatzes mit Aspose.GIS für .NET.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
-  Aspose.GIS für .NET: Stellen Sie sicher, dass die Aspose.GIS für .NET-Bibliothek installiert ist. Sie können es hier herunterladen[Aspose.GIS für .NET-Downloadseite](https://releases.aspose.com/gis/net/).
- Entwicklungsumgebung: Richten Sie Ihre Entwicklungsumgebung mit einer kompatiblen IDE wie Visual Studio ein und verfügen Sie über grundlegende Kenntnisse der .NET-Programmierung.
- Dokumentverzeichnis: Ersetzen Sie „Ihr Dokumentverzeichnis“ im Code-Snippet durch den entsprechenden Pfad, in dem Sie Ihren GDB-Datensatz speichern möchten.
- Vertrautheit mit C#: In diesem Tutorial wird davon ausgegangen, dass Sie mit der Programmiersprache C# vertraut sind.
## Namespaces importieren
Importieren Sie in den ersten Schritten die erforderlichen Namespaces, um die Aspose.GIS-Funktionalität in Ihrer .NET-Anwendung zu nutzen:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Schritt 1: Erstellen Sie einen neuen Datei-GDB-Datensatz
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Ausgabe: 0
    // Fahren Sie mit den folgenden Schritten fort...
}
```
 Erläuterung: In diesem Schritt erstellen wir einen neuen GDB-Datensatz mit`Dataset.Create` Methode. Wir geben den Pfad und den Treiber (FileGdb) an, um eine File-Geodatabase zu erstellen. Die Konsolenausgabe zeigt die anfängliche Ebenenanzahl an, die zu diesem Zeitpunkt Null ist.
## Schritt 2: Layer_1 erstellen und füllen
```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```
Erläuterung: Dieser Schritt umfasst das Erstellen eines Layers mit dem Namen „layer_1“ innerhalb des Datensatzes. Es definiert ein Attribut mit dem Namen „Wert“ vom Typ „Ganzzahl“ und füllt den Layer mit zehn Features, von denen jedes eine Punktgeometrie aufweist.
## Schritt 3: Layer_2 erstellen und füllen
```csharp
using (var layer = dataset.CreateLayer("layer_2"))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Erläuterung: Hier erstellen wir einen zweiten Layer mit dem Namen „layer_2“ und fügen ein einzelnes Feature mit einer Linienzuggeometrie hinzu.
## Schritt 4: Überprüfen Sie die Anzahl der aktualisierten Ebenen
```csharp
Console.WriteLine(dataset.LayersCount); // Ausgabe: 2
```
Erläuterung: Abschließend überprüfen wir die aktualisierte Ebenenanzahl, nachdem wir die beiden Ebenen hinzugefügt haben. In diesem Fall sollte die Ausgabe 2 sein.
## Abschluss
Glückwunsch! Sie haben erfolgreich ein neues File-GDB-Dataset erstellt und es mithilfe von Aspose.GIS für .NET mit Layern gefüllt. Dieses Tutorial vermittelt ein grundlegendes Verständnis für die Arbeit mit Geodaten in einer .NET-Umgebung.
## Häufig gestellte Fragen
### F: Kann ich Aspose.GIS für .NET mit anderen GIS-Bibliotheken verwenden?
Aspose.GIS für .NET ist ein eigenständiges Toolkit; Sie können es jedoch in andere .NET-Bibliotheken integrieren, um die Funktionalität zu erweitern.
### F: Gibt es ein Community-Forum für die Aspose.GIS-Unterstützung?
 Ja, Sie können Unterstützung und Diskussionen auf der finden[Aspose.GIS-Forum](https://forum.aspose.com/c/gis/33).
### F: Wie kann ich eine temporäre Lizenz für Aspose.GIS erhalten?
 Besuche den[Temporäre Lizenz](https://purchase.aspose.com/temporary-license/) Informationen zum Erhalt einer temporären Lizenz finden Sie auf dieser Seite.
### F: Sind zusätzliche Beispiele und Dokumentation verfügbar?
 Entdecke die[Aspose.GIS-Dokumentation](https://reference.aspose.com/gis/net/) Weitere Beispiele und detaillierte Informationen finden Sie hier.
### F: Wo kann ich Aspose.GIS für .NET kaufen?
 Sie können Aspose.GIS für .NET auf der Website erwerben[Kaufseite](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

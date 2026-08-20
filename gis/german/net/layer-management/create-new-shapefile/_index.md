---
date: 2026-06-30
description: Erfahren Sie, wie Sie mit Aspose.GIS für .NET eine Shapefile erstellen.
  Diese Schritt‑für‑Schritt‑Anleitung zeigt Ihnen, wie Sie einen vector layer definieren,
  ein date attribute hinzufügen und spatial data effizient verwalten.
keywords:
- how to create shapefile
- temporal gis shapefile
- Aspose.GIS vector layer
- GIS data automation
linktitle: Neue Shapefile erstellen
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create shapefile using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to define a vector layer, add a date attribute, and manage
    spatial data efficiently.
  headline: How to Create Shapefile with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS primarily supports .NET, but there are versions available for
      Java as well.
    question: Can I use Aspose.GIS with other programming languages?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I find support for Aspose.GIS?
  - answer: Get your temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license?
  - answer: You can buy the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Wie man eine Shapefile mit Aspose.GIS für .NET erstellt
url: /de/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Neues Shapefile erstellen

## Einführung
Wenn Sie sich mit der Entwicklung von geografischen Informationssystemen (GIS) in .NET beschäftigen, ist Aspose.GIS Ihre Lösung, um **wie man ein Shapefile erstellt** programmgesteuert zu realisieren. Diese Bibliothek gibt Ihnen die volle Kontrolle über Vektorlayer, Attributschemata und die Einhaltung von Dateiformaten, sodass Sie Datenpipelines automatisieren oder Testdatensätze in wenigen Minuten erzeugen können.

## Schnelle Antworten
- **Was lehrt dieses Tutorial?** Wie man ein neues Shapefile erstellt, einen Vektorlayer definiert und Attribute hinzufügt (einschließlich eines Datumsfeldes).  
- **Welche Bibliothek wird benötigt?** Aspose.GIS für .NET.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht zum Lernen; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Welche IDE sollte ich verwenden?** Visual Studio (jede aktuelle Version).  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für das Basisbeispiel.

## Wie erstelle ich ein Shapefile mit Aspose.GIS für .NET?
Laden Sie die Aspose.GIS-Bibliothek, legen Sie den Ausgabepfad fest, erstellen Sie ein `VectorLayer`, definieren Sie Attribute und fügen Sie Features hinzu – dieser gesamte Workflow lässt sich in weniger als 30 Zeilen C# schreiben. Die Bibliothek übernimmt die Erstellung von Geometrien, die Typisierung von Attributen und das Schreiben der Datei automatisch, sodass Sie sich nicht um die Low‑Level‑Spezifikationen von Shapefiles kümmern müssen.

## Voraussetzungen
Bevor wir mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundlegendes Verständnis der Programmiersprache C#.  
- Visual Studio auf Ihrem Rechner installiert.  
- Aspose.GIS für .NET Bibliothek. Sie können sie [hier](https://releases.aspose.com/gis/net/) herunterladen.

## Namespaces importieren
Start by importing the necessary namespaces to leverage the functionality of Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt 1: Projekt einrichten
Beginnen Sie damit, ein neues C#‑Projekt in Visual Studio zu erstellen und die Aspose.GIS‑Bibliothek einzubinden.

## Schritt 2: Dokumentverzeichnis festlegen
```csharp
string dataDir = "Your Document Directory";
```
Ersetzen Sie *Your Document Directory* durch den tatsächlichen Pfad, an dem Sie Ihr neues Shapefile speichern möchten.

## Schritt 3: VectorLayer erstellen
Die Klasse `VectorLayer` repräsentiert einen einzelnen Shapefile‑Layer, der Geometrie‑ und Attributdaten speichert.  
In diesem Schritt definieren wir einen Vektorlayer und deklarieren drei Attribute: ein Textfeld (`name`), ein Ganzzahlfeld (`age`) und ein Datums‑Zeit‑Feld (`dob`). Das Hinzufügen des Datumsattributs ist entscheidend für **temporale GIS‑Shapefile**‑Analysen.

```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```

## Schritt 4: Features hinzufügen
### Fall 1: Werte einzeln setzen
Die Methode `SetValues` weist einem Feature Attributwerte in der Reihenfolge zu, in der sie definiert wurden.  
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
Hier erstellen wir zwei Punkte, setzen jedes Attribut separat und fügen die Features dem Layer hinzu.

### Fall 2: Neue Werte für alle Attribute setzen
Alternativ können Sie alle Attributwerte auf einmal mit `SetValues` und einem Objekt‑Array übergeben.  
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
In diesem Ansatz füllen wir alle Attributwerte in einem Aufruf mithilfe eines Objekt‑Arrays – praktisch, wenn Sie viele Attribute haben.

## Warum ist das wichtig?
Ein Shapefile programmgesteuert zu erstellen ermöglicht es Ihnen, Datenpipelines zu automatisieren, Testdatensätze zu erzeugen oder GIS‑Ausgaben direkt in Web‑Services einzubetten. Aspose.GIS unterstützt **30+ Vektor‑ und Rasterformate** und kann mehrseitige Shapefiles schreiben, ohne die gesamte Datei in den Speicher zu laden, was sowohl Geschwindigkeit als auch Skalierbarkeit liefert.

## Häufige Fallstricke & Tipps
- **Pfadtrennzeichen:** Verwenden Sie `Path.Combine` für plattformübergreifende Kompatibilität anstelle von String‑Verkettung.  
- **Attributreihenfolge:** Die Reihenfolge der Werte in `SetValues` muss der Reihenfolge entsprechen, in der Sie die Attribute hinzugefügt haben.  
- **Datumsbehandlung:** Verwenden Sie stets `DateTimeKind.Utc`, wenn Ihre GIS‑Daten über Zeitzonen hinweg geteilt werden.

## Fazit
Herzlichen Glückwunsch! Sie haben erfolgreich ein neues Shapefile mit Aspose.GIS für .NET erstellt. Dieses Tutorial behandelte die Grundlagen zum Einrichten Ihres Projekts, zum Definieren eines Vektorlayers und zum Hinzufügen von Features – einschließlich eines Datumsattributs. Wenn Sie weiterforschen, konsultieren Sie die [Dokumentation](https://reference.aspose.com/gis/net/) für erweiterte Funktionen und Möglichkeiten.

## Häufig gestellte Fragen
**F: Kann ich Aspose.GIS mit anderen Programmiersprachen verwenden?**  
A: Aspose.GIS unterstützt hauptsächlich .NET, es gibt jedoch auch Versionen für Java.

**F: Gibt es eine kostenlose Testversion?**  
A: Ja, Sie können die kostenlose Testversion [hier](https://releases.aspose.com/) nutzen.

**F: Wo finde ich Support für Aspose.GIS?**  
A: Besuchen Sie das [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) für Community‑Support und Diskussionen.

**F: Wie kann ich eine temporäre Lizenz erhalten?**  
A: Holen Sie Ihre temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/).

**F: Wo kann ich Aspose.GIS für .NET kaufen?**  
A: Sie können die Bibliothek [hier](https://purchase.aspose.com/buy) erwerben.

---

**Zuletzt aktualisiert:** 2026-06-30  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [Layer-Attribute abrufen – Layer-Attributinformationen mit Aspose.GIS für .NET erhalten](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Vektorlayer erstellen und räumliches Referenzsystem des Layers festlegen](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Vektorlayer in File GDB erstellen – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
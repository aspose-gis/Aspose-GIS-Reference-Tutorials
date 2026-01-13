---
date: 2026-01-13
description: Erfahren Sie, wie Sie mit Aspose.GIS für .NET ein neues Shapefile erstellen.
  Diese Schritt‑für‑Schritt‑Anleitung zeigt Ihnen, wie Sie einen Vektorlayer definieren,
  ein Datumsattribut hinzufügen und räumliche Daten verwalten.
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
title: Neue Shapefile erstellen
url: /de/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Neues Shapefile erstellen

## Einleitung
Wenn Sie sich mit der Entwicklung von Geographic Information Systems (GIS) in .NET beschäftigen, ist Aspose.GIS Ihre Lösung. Diese leistungsstarke Bibliothek ermöglicht Entwicklern die nahtlose Arbeit mit räumlichen Daten, und in diesem Tutorial führen wir Sie Schritt für Schritt, wie Sie mit Aspose.GIS für .NET **ein neues Shapefile erstellen**. Sie werden sehen, warum das Definieren einer Vektorebene und das Hinzufügen eines Datumsattributs wesentliche Schritte für robuste GIS‑Projekte sind.

## Schnelle Antworten
- **Was lehrt dieses Tutorial?** Wie man ein neues Shapefile erstellt, eine Vektorebene definiert und Attribute hinzufügt (einschließlich eines Datumsfeldes).  
- **Welche Bibliothek wird benötigt?** Aspose.GIS für .NET.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht zum Lernen; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche IDE sollte ich verwenden?** Visual Studio (jede aktuelle Version).  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für das Grundbeispiel.

## Voraussetzungen
Bevor wir mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:
- Grundlegendes Verständnis der Programmiersprache C#.
- Visual Studio auf Ihrem Rechner installiert.
- Aspose.GIS für .NET Bibliothek. Sie können sie [hier](https://releases.aspose.com/gis/net/) herunterladen.

## Namespaces importieren
Beginnen Sie damit, die erforderlichen Namespaces zu importieren, um die Funktionalität von Aspose.GIS zu nutzen:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt 1: Projekt einrichten
Beginnen Sie damit, ein neues C#‑Projekt in Visual Studio zu erstellen und die Aspose.GIS‑Bibliothek einzubinden.

## Schritt 2: Dokumentverzeichnis festlegen
```csharp
string dataDir = "Your Document Directory";
```
Ersetzen Sie *Your Document Directory* durch den tatsächlichen Pfad, in dem Sie Ihr neues Shapefile speichern möchten.

## Schritt 3: VectorLayer erstellen
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Dieses Code‑Segment **definiert eine Vektorebene** und deklariert drei Attribute: ein Textfeld (`name`), ein Ganzzahlfeld (`age`) und ein Datum‑Uhrzeit‑Feld (`dob`). Das Hinzufügen des Datumsattributs ist für zeitliche GIS‑Analysen entscheidend.

## Schritt 4: Features hinzufügen
### Fall 1: Werte einzeln setzen
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
Hier erstellen wir zwei Punkte, setzen jedes Attribut separat und fügen die Features zur Ebene hinzu.

### Fall 2: Neue Werte für alle Attribute setzen
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
Bei diesem Ansatz füllen wir alle Attributwerte in einem Aufruf mithilfe eines Objekt‑Arrays – praktisch, wenn Sie viele Attribute haben.

## Warum das wichtig ist
Das programmatische Erstellen eines Shapefiles ermöglicht es Ihnen, Datenpipelines zu automatisieren, Testdatensätze zu erzeugen oder GIS‑Ausgaben direkt in Web‑Services zu integrieren. Wenn Sie **wie man ein Shapefile erstellt** mit Aspose.GIS beherrschen, erhalten Sie die volle Kontrolle über Feature‑Geometrie, Attribut‑Schema und die Einhaltung des Dateiformats.

## Häufige Fallstricke & Tipps
- **Pfadtrennzeichen:** Verwenden Sie `Path.Combine` für plattformübergreifende Kompatibilität anstelle von String‑Verkettung.  
- **Attributreihenfolge:** Die Reihenfolge der Werte in `SetValues` muss der Reihenfolge entsprechen, in der Sie die Attribute hinzugefügt haben.  
- **Datumsbehandlung:** Verwenden Sie stets `DateTimeKind.Utc`, wenn Ihre GIS‑Daten über Zeitzonen hinweg geteilt werden.

## Fazit
Herzlichen Glückwunsch! Sie haben erfolgreich ein neues Shapefile mit Aspose.GIS für .NET erstellt. Dieses Tutorial behandelte die Grundlagen zum Einrichten Ihres Projekts, zum Definieren einer Vektorebene und zum Hinzufügen von Features – einschließlich eines Datumsattributs. Wenn Sie weiterforschen, konsultieren Sie die [Dokumentation](https://reference.aspose.com/gis/net/) für erweiterte Funktionen und Möglichkeiten.

## Häufig gestellte Fragen
### Q: Kann ich Aspose.GIS mit anderen Programmiersprachen verwenden?
Aspose.GIS unterstützt hauptsächlich .NET, es gibt jedoch auch Versionen für Java.

### Q: Gibt es eine kostenlose Testversion?
Ja, Sie können die kostenlose Testversion [hier](https://releases.aspose.com/) nutzen.

### Q: Wo finde ich Support für Aspose.GIS?
Besuchen Sie das [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) für Community‑Support und Diskussionen.

### Q: Wie kann ich eine temporäre Lizenz erhalten?
Holen Sie Ihre temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/).

### Q: Wo kann ich Aspose.GIS für .NET erwerben?
Sie können die Bibliothek [hier](https://purchase.aspose.com/buy) kaufen.

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}